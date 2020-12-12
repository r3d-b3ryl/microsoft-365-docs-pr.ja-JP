---
title: 1&1 の間で MICROSOFT をセットアップするためにネームサーバーを変更する
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: 1&1 インターネットが DNS ホスティング プロバイダーである場合に、21Vianet が運用している Office 365 をセットアップして DNS レコードを管理する方法について説明します。
ms.openlocfilehash: b363718c7d1d1845117f44317ae9e6b24e9a2e28
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658034"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-11-ionos"></a><span data-ttu-id="a5c3a-103">1 対 1 の間で MICROSOFT 365 をセットアップするためにネーム&変更する</span><span class="sxs-lookup"><span data-stu-id="a5c3a-103">Change nameservers to set up Microsoft 365 with 1&1 IONOS</span></span>

 <span data-ttu-id="a5c3a-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a5c3a-105">Microsoft 365 で Microsoft 365 DNS レコードを管理する場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-105">Follow these instructions if you want Microsoft 365 to manage your Microsoft 365 DNS records for you.</span></span> <span data-ttu-id="a5c3a-106">(必要に応じて [、MICROSOFT 365 のすべての DNS レコードを 1&1 の間で管理できます](create-dns-records-at-1-1-internet.md)。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-106">(If you prefer, you can [manage all your Microsoft 365 DNS records at 1&1 IONOS](create-dns-records-at-1-1-internet.md).)</span></span> 
  

    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a5c3a-107">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="a5c3a-107">Add a TXT record for verification</span></span>


<span data-ttu-id="a5c3a-p102">Microsoft 365 のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-p102">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a5c3a-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="a5c3a-112">次の手順を実行するか、[ビデオ (0 分 42 秒から開始) をご覧ください](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3)。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-112">Follow the steps below or [watch the video (start at 0:42)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span></span>
  
1. <span data-ttu-id="a5c3a-113">To get started, go to your domains page at 1&1 IONOS via [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span><span class="sxs-lookup"><span data-stu-id="a5c3a-113">To get started, go to your domains page at 1&1 IONOS via [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="a5c3a-114">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="a5c3a-114">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="a5c3a-115">[MY **DOMAINS] で、[Manage domains]** **(ドメインの管理) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-115">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="a5c3a-116">[ **ドメイン センター] ページ** で、更新するドメインを探します。次に、その **ドメインの Panel** **(v)** コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-116">On the **Domain Center** page, find the domain that you want to update; then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="a5c3a-117">[ドメイン設定 **] 領域で** 、[DNS 設定の編集 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-117">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="a5c3a-118">[TXT レコード **と SRV レコード] セクションで** 、[Add Record ] (レコードの追加) **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-118">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
    <span data-ttu-id="a5c3a-119">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="a5c3a-119">(You may have to scroll down.)</span></span> 
    
6. <span data-ttu-id="a5c3a-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="a5c3a-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="a5c3a-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="a5c3a-121">**Type**</span></span> <br/> |<span data-ttu-id="a5c3a-122">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="a5c3a-122">**Prefix**</span></span> <br/> |<span data-ttu-id="a5c3a-123">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="a5c3a-123">**Name Value**</span></span> <br/> |
|<span data-ttu-id="a5c3a-124">TXT</span><span class="sxs-lookup"><span data-stu-id="a5c3a-124">TXT</span></span>  <br/> |<span data-ttu-id="a5c3a-125">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="a5c3a-125">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="a5c3a-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a5c3a-126">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="a5c3a-127">**注**: これは例です。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-127">**Note**: This is an example.</span></span> <span data-ttu-id="a5c3a-128">Microsoft 365 の表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-128">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="a5c3a-129">確認する方法</span><span class="sxs-lookup"><span data-stu-id="a5c3a-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. <span data-ttu-id="a5c3a-130">[保存 **] を** 選択し、[保存] **を再び** 選択します。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-130">Select **Save**, and then **Save** again.</span></span> 
    
8. <span data-ttu-id="a5c3a-131">[DNS 設定 **の編集] ダイアログ** ボックスで、[はい] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-131">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
9. <span data-ttu-id="a5c3a-132">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a5c3a-133">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft 365 に戻り、Microsoft 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="a5c3a-134">Microsoft 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-134">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a5c3a-135">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a5c3a-136">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="a5c3a-137">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="a5c3a-138">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a5c3a-139">通常は DNS の変更が反映されるまで約 15 分かかります。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a5c3a-140">ただし、インターネットの DNS システム全体を更新するための変更を行った場合、それ以上の時間がかかる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a5c3a-141">IF you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a5c3a-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="a5c3a-142">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="a5c3a-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="a5c3a-143">Microsoft 365 でドメインのセットアップを完了するには、ドメイン レジストラーでドメインの NS レコードを変更して、Microsoft 365 プライマリ ネーム サーバーとセカンダリ ネーム サーバーをポイントします。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-143">To complete setting up your domain with Microsoft 365, you change your domain's NS records at your domain registrar to point to the Microsoft 365 primary and secondary name servers.</span></span> <span data-ttu-id="a5c3a-144">これにより、ドメインの DNS レコードを更新する Microsoft 365 がセットアップされます。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-144">This sets up Microsoft 365 to update the domain's DNS records for you.</span></span> <span data-ttu-id="a5c3a-145">メール、Skype for Business Online、一般向け Web サイトをドメインで利用できるようにすべてのレコードを追加し、すべての設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-145">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="a5c3a-146">Microsoft 365 ネーム サーバーを指すドメインの NS レコードを変更すると、現在ドメインに関連付けられているすべてのサービスが影響を受ける。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-146">When you change your domain's NS records to point to the Microsoft 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="a5c3a-147">たとえば、ドメインに送信されたメール (rob@ *your_domain*  .com など) は、この変更を行った後に Microsoft 365 に届きます。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-147">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft 365 after you make this change.</span></span> 
  
<span data-ttu-id="a5c3a-148">Microsoft 365 でドメインをセットアップできるよう、NS レコードを変更する準備はできましたか?</span><span class="sxs-lookup"><span data-stu-id="a5c3a-148">Ready to change your NS records so Microsoft 365 can set up your domain?</span></span> <span data-ttu-id="a5c3a-149">次の手順を実行するか、[ビデオ (2 分 47 秒から開始) をご覧ください](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3)。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-149">Follow the steps below or [watch the video (start at 2:47)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="a5c3a-150">次の手順では、他の不要なネームサーバーを一覧から削除する方法と、正しいネームサーバーが一覧に表示されていない場合に追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-150">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="a5c3a-151">>このセクションの手順を完了すると、次の 4 つのネームサーバーだけが表示されます。> ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a5c3a-151">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="a5c3a-152">To get started, go to your domains page at 1&1 BY USING [THIS LINK](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span><span class="sxs-lookup"><span data-stu-id="a5c3a-152">To get started, go to your domains page at 1&1 IONOS by using [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="a5c3a-153">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="a5c3a-153">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="a5c3a-154">[MY **DOMAINS] で、[Manage domains]** **(ドメインの管理) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-154">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="a5c3a-155">[ **ドメイン センター] ページ** で、更新するドメインを見つけ、そのドメインの **Panel** ( **v**) コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-155">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="a5c3a-156">[ドメイン設定 **] 領域で** 、[DNS 設定の編集 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-156">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="a5c3a-157">[ **Name Server Settings**] セクションで、[ **Other name servers**] を選びます</span><span class="sxs-lookup"><span data-stu-id="a5c3a-157">In the **Name Server Settings** section, select **Other name servers**.</span></span>
    
    <span data-ttu-id="a5c3a-158">(下へスクロールしなければならないことがあります)。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-158">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="a5c3a-159">現在表示されているページに既に一覧表示されているネームサーバーがあるかどうかに応じて、以下の 2 つの手順のいずれかに進みます。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="a5c3a-160">既に一覧表示されているネーム サーバーが **ない** 場合は、 [既に一覧表示されているネームサーバーがない場合](#if-there-are-no-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="a5c3a-161">既に一覧表示されているネーム サーバーが **ある** 場合は、 [既に一覧表示されているネームサーバーがある場合](#if-there-are-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="a5c3a-162">既に一覧表示されているネームサーバーがない場合</span><span class="sxs-lookup"><span data-stu-id="a5c3a-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="a5c3a-163">[ **Name server 1**] ボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-163">In the **Name server 1** box, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="a5c3a-164">**Name server 1**</span><span class="sxs-lookup"><span data-stu-id="a5c3a-164">**Name server 1**</span></span> <br/> |<span data-ttu-id="a5c3a-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a5c3a-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![[ネーム サーバー 1] ボックスに値を入力する](../../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. <span data-ttu-id="a5c3a-167">[ **Additional name servers**] ドロップダウン リストで、[ **My secondary name servers**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-167">In the **Additional name servers** drop-down list, choose **My secondary name servers**.</span></span>
    
    ![Choosing My secondary name servers in the list](../../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. <span data-ttu-id="a5c3a-169">**[Name server 2]、[Name server 3]、[Name server 4]** ボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-169">In the **Name server 2, 3, and 4** boxes, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="a5c3a-170">**Name server 2**</span><span class="sxs-lookup"><span data-stu-id="a5c3a-170">**Name server 2**</span></span> <br/> |<span data-ttu-id="a5c3a-171">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a5c3a-171">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a5c3a-172">**ネーム サーバー 3**</span><span class="sxs-lookup"><span data-stu-id="a5c3a-172">**Name server 3**</span></span> <br/> |<span data-ttu-id="a5c3a-173">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a5c3a-173">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a5c3a-174">**ネーム サーバー 4**</span><span class="sxs-lookup"><span data-stu-id="a5c3a-174">**Name server 4**</span></span> <br/> |<span data-ttu-id="a5c3a-175">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a5c3a-175">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
![ネーム サーバーの値を入力する](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. <span data-ttu-id="a5c3a-177">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-177">Select **Save**.</span></span>
    
    ![[ネーム サーバー設定] ページで [保存] を選択する](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. <span data-ttu-id="a5c3a-179">[DNS 設定 **の編集] ダイアログ** ボックスで、[はい] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-179">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![[DNS 設定の編集] ダイアログ ボックスで [保存] を選択する](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="a5c3a-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="a5c3a-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="a5c3a-182">その後、Microsoft のメールと他のサービスはすべて、ドメインで動作する設定に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-182">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="a5c3a-183">既に一覧表示されているネームサーバーがある場合</span><span class="sxs-lookup"><span data-stu-id="a5c3a-183">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="a5c3a-p113">これらの手順は、前途した 4 件の *正しい*  ネームサーバー以外にも既存のネームサーバーがある場合に  *のみ*  行ってください (つまり、現在のネームサーバーのうち *ns1.bdm.microsoftonline.com* 、 *ns2.bdm.microsoftonline.com* 、 **ns3.bdm.microsoftonline.com** 、 **ns4.bdm.microsoftonline.com** のいずれでも  **ない**  もの  **だけ**  を削除します)。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-p113">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="a5c3a-186">[ **Name server**] にネームサーバーが既に表示されている場合は、各ネームサーバーを選び、キーボードの **Delete** キーを押して、ネームサーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-186">If there are already nameservers listed in the **Name server** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting name servers](../../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. <span data-ttu-id="a5c3a-188">**[Name server 1]、[Name server 2]、[Name server 3]、[Name server 4]** ボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-188">In the **Name server 1, 2, 3, and 4** boxes, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="a5c3a-189">**Name server 1**</span><span class="sxs-lookup"><span data-stu-id="a5c3a-189">**Name server 1**</span></span> <br/> |<span data-ttu-id="a5c3a-190">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a5c3a-190">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a5c3a-191">**Name server 2**</span><span class="sxs-lookup"><span data-stu-id="a5c3a-191">**Name server 2**</span></span> <br/> |<span data-ttu-id="a5c3a-192">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a5c3a-192">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a5c3a-193">**ネーム サーバー 3**</span><span class="sxs-lookup"><span data-stu-id="a5c3a-193">**Name server 3**</span></span> <br/> |<span data-ttu-id="a5c3a-194">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a5c3a-194">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a5c3a-195">**ネーム サーバー 4**</span><span class="sxs-lookup"><span data-stu-id="a5c3a-195">**Name server 4**</span></span> <br/> |<span data-ttu-id="a5c3a-196">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a5c3a-196">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![ネーム サーバーの値を入力する](../../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. <span data-ttu-id="a5c3a-198">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-198">Select **Save**.</span></span>
    
    ![[ネーム サーバー設定] ページで [保存] を選択する](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. <span data-ttu-id="a5c3a-200">[DNS 設定 **の編集] ダイアログ** ボックスで、[はい] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-200">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![[DNS 設定の編集] ダイアログ ボックスで [保存] を選択する](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="a5c3a-202">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="a5c3a-202">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="a5c3a-203">その後、Microsoft のメールと他のサービスはすべて、ドメインで動作する設定に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a5c3a-203">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  


