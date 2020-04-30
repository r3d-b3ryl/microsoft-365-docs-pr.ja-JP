---
title: 1&1 の IONOS を設定するためにネームサーバーを変更する
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: Dns レコードを管理するために21Vianet が運用している Office 365 をセットアップする方法について説明します。 1&1 インターネットが DNS ホスティングプロバイダーである場合です。
ms.openlocfilehash: 99ac40472d0afa0cb734b0e86a0f10d7904133e1
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939420"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-11-ionos"></a><span data-ttu-id="9ce29-103">IONOS 1 を&使用するように Microsoft 365 をセットアップするためにネームサーバーを変更</span><span class="sxs-lookup"><span data-stu-id="9ce29-103">Change nameservers to set up Microsoft 365 with 1&1 IONOS</span></span>

 <span data-ttu-id="9ce29-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ce29-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9ce29-105">Microsoft 365 で Microsoft 365 の DNS レコードを管理するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="9ce29-105">Follow these instructions if you want Microsoft 365 to manage your Microsoft 365 DNS records for you.</span></span> <span data-ttu-id="9ce29-106">(必要に応じ[て、すべての Microsoft 365 DNS レコードを 1&1 IONOS に管理](create-dns-records-at-1-1-internet.md)することができます。)</span><span class="sxs-lookup"><span data-stu-id="9ce29-106">(If you prefer, you can [manage all your Microsoft 365 DNS records at 1&1 IONOS](create-dns-records-at-1-1-internet.md).)</span></span> 
  

    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9ce29-107">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9ce29-107">Add a TXT record for verification</span></span>


<span data-ttu-id="9ce29-p102">Microsoft 365 のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="9ce29-p102">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9ce29-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="9ce29-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="9ce29-112">次の手順を実行するか、[ビデオ (0 分 42 秒から開始) をご覧ください](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="9ce29-112">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="9ce29-113">まず、[このリンク](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F)を使用して 1&1 IONOS でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9ce29-113">To get started, go to your domains page at 1&1 IONOS via [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="9ce29-114">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="9ce29-114">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="9ce29-115">[**マイドメイン**] で、[**ドメインの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ce29-115">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="9ce29-116">[**ドメインセンター** ] ページで、更新するドメインを見つけます。そのドメインの [Panel ( **v**) **]** コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ce29-116">On the **Domain Center** page, find the domain that you want to update; then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="9ce29-117">[**ドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ce29-117">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="9ce29-118">[ **TXT および SRV Records** ] セクションで、[ **Add Record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ce29-118">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
    <span data-ttu-id="9ce29-119">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="9ce29-119">(You may have to scroll down.)</span></span> 
    
6. <span data-ttu-id="9ce29-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9ce29-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="9ce29-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="9ce29-121">**Type**</span></span> <br/> |<span data-ttu-id="9ce29-122">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="9ce29-122">**Prefix**</span></span> <br/> |<span data-ttu-id="9ce29-123">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="9ce29-123">**Name Value**</span></span> <br/> |
|<span data-ttu-id="9ce29-124">TXT</span><span class="sxs-lookup"><span data-stu-id="9ce29-124">TXT</span></span>  <br/> |<span data-ttu-id="9ce29-125">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="9ce29-125">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="9ce29-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9ce29-126">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="9ce29-127">**注**: これは例です。</span><span class="sxs-lookup"><span data-stu-id="9ce29-127">**Note**: This is an example.</span></span> <span data-ttu-id="9ce29-128">Microsoft 365 の表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="9ce29-128">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="9ce29-129">確認する方法</span><span class="sxs-lookup"><span data-stu-id="9ce29-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. <span data-ttu-id="9ce29-130">[**保存**] を選択し、もう一度**保存**します。</span><span class="sxs-lookup"><span data-stu-id="9ce29-130">Select **Save**, and then **Save** again.</span></span> 
    
8. <span data-ttu-id="9ce29-131">[ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ce29-131">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
9. <span data-ttu-id="9ce29-132">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="9ce29-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9ce29-133">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft 365 に戻り、Microsoft 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="9ce29-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="9ce29-134">Microsoft 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="9ce29-134">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9ce29-135">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="9ce29-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="9ce29-136">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ce29-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="9ce29-137">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ce29-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="9ce29-138">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ce29-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9ce29-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="9ce29-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="9ce29-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="9ce29-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="9ce29-141">DNS レコードの追加後にメールフローなどに問題が発生した場合は、「 [Microsoft 365 でドメインまたは DNS レコードを追加した後に問題を見つけて修正](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ce29-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="9ce29-142">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="9ce29-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="9ce29-143">Microsoft 365 でのドメインの設定を完了するには、ドメインレジストラーでドメインの NS レコードを変更して、Microsoft 365 プライマリおよびセカンダリネームサーバーをポイントするようにします。</span><span class="sxs-lookup"><span data-stu-id="9ce29-143">To complete setting up your domain with Microsoft 365, you change your domain's NS records at your domain registrar to point to the Microsoft 365 primary and secondary name servers.</span></span> <span data-ttu-id="9ce29-144">これにより、Microsoft 365 がドメインの DNS レコードを更新するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="9ce29-144">This sets up Microsoft 365 to update the domain's DNS records for you.</span></span> <span data-ttu-id="9ce29-145">メール、Skype for Business Online、一般向け Web サイトをドメインで利用できるようにすべてのレコードを追加し、すべての設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="9ce29-145">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="9ce29-146">ドメインの NS レコードを変更して、Microsoft 365 のネームサーバーを参照すると、現在ドメインに関連付けられているすべてのサービスが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="9ce29-146">When you change your domain's NS records to point to the Microsoft 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="9ce29-147">たとえば、この変更を行った後、ドメインに送信されるすべての電子メール (rob@ *your_domain*など) は、Microsoft 365 に送られ始めます。</span><span class="sxs-lookup"><span data-stu-id="9ce29-147">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft 365 after you make this change.</span></span> 
  
<span data-ttu-id="9ce29-148">Microsoft 365 がドメインをセットアップできるように、NS レコードを変更する準備ができましたか?</span><span class="sxs-lookup"><span data-stu-id="9ce29-148">Ready to change your NS records so Microsoft 365 can set up your domain?</span></span> <span data-ttu-id="9ce29-149">次の手順を実行するか、[ビデオ (2 分 47 秒から開始) をご覧ください](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="9ce29-149">Follow the steps below or [watch the video (start at 2:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="9ce29-150">次の手順では、リストからその他の不要なネームサーバーを削除する方法と、正しいネームサーバーが表示されていない場合には追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ce29-150">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="9ce29-151">> このセクションの手順を完了すると、次の4つのネームサーバーのみが表示されます。 > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9ce29-151">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="9ce29-152">まず、[このリンク](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F)を使用して 1&1 IONOS でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9ce29-152">To get started, go to your domains page at 1&1 IONOS by using [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="9ce29-153">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="9ce29-153">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="9ce29-154">[**マイドメイン**] で、[**ドメインの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ce29-154">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="9ce29-155">[**ドメインセンター** ] ページで、更新するドメインを見つけて、そのドメインの [ **Panel** ( **v**)] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ce29-155">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="9ce29-156">[**ドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ce29-156">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="9ce29-157">[ **Name Server Settings**] セクションで、[ **Other name servers**] を選びます</span><span class="sxs-lookup"><span data-stu-id="9ce29-157">In the **Name Server Settings** section, select **Other name servers**.</span></span>
    
    <span data-ttu-id="9ce29-158">(下へスクロールしなければならないことがあります)。</span><span class="sxs-lookup"><span data-stu-id="9ce29-158">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="9ce29-159">現在表示されているページに既に一覧表示されているネームサーバーがあるかどうかに応じて、以下の 2 つの手順のいずれかに進みます。</span><span class="sxs-lookup"><span data-stu-id="9ce29-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="9ce29-160">既に一覧表示されているネーム サーバーが **ない** 場合は、 [既に一覧表示されているネームサーバーがない場合](#if-there-are-no-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="9ce29-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="9ce29-161">既に一覧表示されているネーム サーバーが **ある** 場合は、 [既に一覧表示されているネームサーバーがある場合](#if-there-are-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="9ce29-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="9ce29-162">既に一覧表示されているネームサーバーがない場合</span><span class="sxs-lookup"><span data-stu-id="9ce29-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="9ce29-163">[ **Name server 1**] ボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9ce29-163">In the **Name server 1** box, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="9ce29-164">**Name server 1**</span><span class="sxs-lookup"><span data-stu-id="9ce29-164">**Name server 1**</span></span> <br/> |<span data-ttu-id="9ce29-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9ce29-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![[Name server 1] ボックスに値を入力する](../../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. <span data-ttu-id="9ce29-167">[ **Additional name servers**] ドロップダウン リストで、[ **My secondary name servers**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9ce29-167">In the **Additional name servers** drop-down list, choose **My secondary name servers**.</span></span>
    
    ![Choosing My secondary name servers in the list](../../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. <span data-ttu-id="9ce29-169">**[Name server 2]、[Name server 3]、[Name server 4]** ボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9ce29-169">In the **Name server 2, 3, and 4** boxes, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="9ce29-170">**Name server 2**</span><span class="sxs-lookup"><span data-stu-id="9ce29-170">**Name server 2**</span></span> <br/> |<span data-ttu-id="9ce29-171">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9ce29-171">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="9ce29-172">**ネーム サーバー 3**</span><span class="sxs-lookup"><span data-stu-id="9ce29-172">**Name server 3**</span></span> <br/> |<span data-ttu-id="9ce29-173">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9ce29-173">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="9ce29-174">**ネーム サーバー 4**</span><span class="sxs-lookup"><span data-stu-id="9ce29-174">**Name server 4**</span></span> <br/> |<span data-ttu-id="9ce29-175">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9ce29-175">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
![名前サーバーの値を入力する](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. <span data-ttu-id="9ce29-177">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ce29-177">Select **Save**.</span></span>
    
    ![[名前サーバーの設定] ページの [保存] を選択する](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. <span data-ttu-id="9ce29-179">[ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ce29-179">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![[DNS 設定の編集] ダイアログボックスの [保存] を選択する](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="9ce29-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="9ce29-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="9ce29-182">その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。</span><span class="sxs-lookup"><span data-stu-id="9ce29-182">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="9ce29-183">既に一覧表示されているネームサーバーがある場合</span><span class="sxs-lookup"><span data-stu-id="9ce29-183">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="9ce29-p113">これらの手順は、前途した 4 件の *正しい*  ネームサーバー以外にも既存のネームサーバーがある場合に  *のみ*  行ってください (つまり、現在のネームサーバーのうち *ns1.bdm.microsoftonline.com* 、 *ns2.bdm.microsoftonline.com* 、 **ns3.bdm.microsoftonline.com** 、 **ns4.bdm.microsoftonline.com** のいずれでも  **ない**  もの  **だけ**  を削除します)。</span><span class="sxs-lookup"><span data-stu-id="9ce29-p113">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="9ce29-186">[ **Name server**] にネームサーバーが既に表示されている場合は、各ネームサーバーを選び、キーボードの **Delete** キーを押して、ネームサーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="9ce29-186">If there are already nameservers listed in the **Name server** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting name servers](../../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. <span data-ttu-id="9ce29-188">**[Name server 1]、[Name server 2]、[Name server 3]、[Name server 4]** ボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9ce29-188">In the **Name server 1, 2, 3, and 4** boxes, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="9ce29-189">**Name server 1**</span><span class="sxs-lookup"><span data-stu-id="9ce29-189">**Name server 1**</span></span> <br/> |<span data-ttu-id="9ce29-190">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9ce29-190">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="9ce29-191">**Name server 2**</span><span class="sxs-lookup"><span data-stu-id="9ce29-191">**Name server 2**</span></span> <br/> |<span data-ttu-id="9ce29-192">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9ce29-192">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="9ce29-193">**ネーム サーバー 3**</span><span class="sxs-lookup"><span data-stu-id="9ce29-193">**Name server 3**</span></span> <br/> |<span data-ttu-id="9ce29-194">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9ce29-194">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="9ce29-195">**ネーム サーバー 4**</span><span class="sxs-lookup"><span data-stu-id="9ce29-195">**Name server 4**</span></span> <br/> |<span data-ttu-id="9ce29-196">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9ce29-196">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![名前サーバーの値を入力する](../../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. <span data-ttu-id="9ce29-198">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ce29-198">Select **Save**.</span></span>
    
    ![[名前サーバーの設定] ページの [保存] を選択する](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. <span data-ttu-id="9ce29-200">[ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ce29-200">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![[DNS 設定の編集] ダイアログボックスの [保存] を選択する](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="9ce29-202">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="9ce29-202">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="9ce29-203">その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。</span><span class="sxs-lookup"><span data-stu-id="9ce29-203">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  


