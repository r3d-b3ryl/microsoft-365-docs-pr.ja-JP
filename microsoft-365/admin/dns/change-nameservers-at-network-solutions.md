---
title: ネットワークソリューションを使用して Microsoft をセットアップするためにネームサーバーを変更する
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
ms.assetid: d4ba60f3-4e1c-4180-99bd-250b8955be2a
description: 'DNS レコードを管理する場合は、microsoft カスタムドメインとネットワークソリューションをセットアップする方法について説明します。 '
ms.openlocfilehash: 69e63a6e5dac6e75e66cb816538d356fdd922581
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780387"
---
# <a name="change-nameservers-to-set-up-microsoft-with-network-solutions"></a><span data-ttu-id="bb9ec-103">ネットワークソリューションを使用して Microsoft をセットアップするためにネームサーバーを変更する</span><span class="sxs-lookup"><span data-stu-id="bb9ec-103">Change nameservers to set up Microsoft with Network Solutions</span></span>

 <span data-ttu-id="bb9ec-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="bb9ec-105">Microsoft が DNS レコードを管理する場合は、次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="bb9ec-106">(必要に応じ[て、すべての MICROSOFT DNS レコードをネットワークソリューションで管理](create-dns-records-at-network-solutions.md)できます。)</span><span class="sxs-lookup"><span data-stu-id="bb9ec-106">(If you prefer, you can [manage all your Microsoft DNS records at Network Solutions](create-dns-records-at-network-solutions.md).)</span></span>
  
    
## <a name="add-a-txt-record-at-network-solutions-to-verify-that-you-own-the-domain"></a><span data-ttu-id="bb9ec-107">Network Solutions で TXT レコードを追加して、ドメインを所有していることを確認する</span><span class="sxs-lookup"><span data-stu-id="bb9ec-107">Add a TXT record at Network Solutions to verify that you own the domain</span></span>

<span data-ttu-id="bb9ec-108">Before you use your domain with Microsoft, we have to make sure that you own it.</span><span class="sxs-lookup"><span data-stu-id="bb9ec-108">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="bb9ec-109">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span><span class="sxs-lookup"><span data-stu-id="bb9ec-109">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bb9ec-110">This record is used only to verify that you own your domain; it doesn't affect anything else.</span><span class="sxs-lookup"><span data-stu-id="bb9ec-110">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> <span data-ttu-id="bb9ec-111">You can delete it later, if you like.</span><span class="sxs-lookup"><span data-stu-id="bb9ec-111">You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="bb9ec-112">次の手順を実行するか、[ビデオ (47 秒から開始) を参照](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261)してください。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-112">Follow the steps below or [watch the video (start at 0:47)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).</span></span>
  
1. <span data-ttu-id="bb9ec-113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="bb9ec-113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="bb9ec-114">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="bb9ec-114">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bb9ec-115">[**ログイン**] ボタンを選択する前に、[ **Log in to** ] ドロップダウンリストで [ **Manage My Domain Names** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-115">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span>
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="bb9ec-117">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-117">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="bb9ec-119">[ **EDIT DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-119">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="bb9ec-121">[ **Manage ADVANCED DNS Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-121">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="bb9ec-122">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="bb9ec-122">(You may have to scroll down.)</span></span>
    
    ![[Manage Advanced DNS Records] を選択します。](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="bb9ec-124">[**テキスト (Txt レコード)** ] セクションまでスクロールしてから、[ **Txt レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-124">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![[TXT レコードの編集] を選択する](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="bb9ec-126">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-126">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
|<span data-ttu-id="bb9ec-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="bb9ec-127">**Host**</span></span>|<span data-ttu-id="bb9ec-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bb9ec-128">**TTL**</span></span>|<span data-ttu-id="bb9ec-129">**Text**</span><span class="sxs-lookup"><span data-stu-id="bb9ec-129">**Text**</span></span>|
|:-----|:-----|:-----|
|@  <br/> <span data-ttu-id="bb9ec-130">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="bb9ec-130">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="bb9ec-131">3600</span><span class="sxs-lookup"><span data-stu-id="bb9ec-131">3600</span></span>  <br/> |<span data-ttu-id="bb9ec-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="bb9ec-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="bb9ec-133">**注**: これは例です。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-133">**Note**: This is an example.</span></span> <span data-ttu-id="bb9ec-134">Microsoft 365 の表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-134">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="bb9ec-135">確認する方法</span><span class="sxs-lookup"><span data-stu-id="bb9ec-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
   
    
   ![新しいレコードのボックスに値を入力するか貼り付けます。](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="bb9ec-137">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-137">Select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="bb9ec-139">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-139">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択する](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="bb9ec-141">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="bb9ec-142">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft 365 に戻り、Microsoft 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="bb9ec-143">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="bb9ec-144">Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="bb9ec-145">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="bb9ec-146">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="bb9ec-147">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="bb9ec-148">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="bb9ec-148">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="bb9ec-149">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="bb9ec-149">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="bb9ec-150">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="bb9ec-150">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="bb9ec-151">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="bb9ec-151">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="bb9ec-152">Microsoft によるドメインの設定を完了するには、ドメインレジストラーでドメインの NS レコードを変更して、Microsoft プライマリネームサーバーとセカンダリネームサーバーをポイントするようにします。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-152">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="bb9ec-153">これにより、ドメインの DNS レコードが更新されるように Microsoft が設定されます。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-153">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="bb9ec-154">メール、Skype for Business Online、一般向け Web サイトをドメインで利用できるようにすべてのレコードを追加し、すべての設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-154">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="bb9ec-155">ドメインの NS レコードを変更して Microsoft ネームサーバーをポイントすると、現在ドメインに関連付けられているすべてのサービスが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-155">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="bb9ec-156">たとえば、ドメインに送信されるすべての電子メール (rob@ *your_domain*など) は、この変更を行った後に Microsoft に送られ始めます。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-156">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span>
  
<span data-ttu-id="bb9ec-157">Microsoft がドメインをセットアップできるように、NS レコードを変更する準備はできましたか?</span><span class="sxs-lookup"><span data-stu-id="bb9ec-157">Ready to change your NS records so Microsoft can set up your domain?</span></span> <span data-ttu-id="bb9ec-158">次の手順を実行するか、[ビデオ (2 分 23 秒から開始) を参照](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261)してください。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-158">Follow the steps below or [watch the video (start at 2:23)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="bb9ec-159">このセクションの手順を完了すると、次の4つのネームサーバー*のみ*が一覧表示されます。 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**、および**ns4.bdm.microsoftonline.com**。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-159">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span> <span data-ttu-id="bb9ec-160">次の手順では、他の不要なネームサーバーを一覧から削除する方法、および上記のネームサーバーが一覧に表示されていない場合に、 *正しい*  ネームサーバーを追加する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-160">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="bb9ec-161">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-161">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="bb9ec-162">ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-162">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bb9ec-163">[**ログイン**] ボタンを選択する前に、[ **Log in to** ] ドロップダウンリストで [ **Manage My Domain Names** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-163">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="bb9ec-165">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-165">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="bb9ec-167">[ **EDIT DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-167">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="bb9ec-169">[ **MOVE DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-169">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-1-1](../../media/e57a30f3-63d5-4bcb-84c6-c8be21c261a2.png)
  
5. <span data-ttu-id="bb9ec-171">現在表示されているページに既に一覧表示されているネームサーバーがあるかどうかに応じて、以下の 2 つの手順のいずれかに進みます。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-171">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="bb9ec-172">既に一覧表示されているネーム サーバーが **ない** 場合は、 [既に一覧表示されているネームサーバーがない場合](#if-there-are-no-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-172">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="bb9ec-173">既に一覧表示されているネーム サーバーが **ある** 場合は、 [既に一覧表示されているネームサーバーがある場合](#if-there-are-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-173">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="bb9ec-174">既に一覧表示されているネームサーバーがない場合</span><span class="sxs-lookup"><span data-stu-id="bb9ec-174">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="bb9ec-175">[**ドメイン**] ページの [ **Domain Name servers の指定**] セクションで、[さらに**ネームサーバーを追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-175">On the **Domains** page, in the **Specify Domain Name Servers** section, select **Add More Name Servers**.</span></span>
    
    ![NetworkSolutionsBP-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
2. <span data-ttu-id="bb9ec-177">[ **Domain Names**] ページに、次の表のネームサーバーの値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-177">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="bb9ec-178">**Name Server 1**</span><span class="sxs-lookup"><span data-stu-id="bb9ec-178">**Name Server 1**</span></span> <br/> |<span data-ttu-id="bb9ec-179">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="bb9ec-179">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="bb9ec-180">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="bb9ec-180">**Name Server 2**</span></span> <br/> |<span data-ttu-id="bb9ec-181">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="bb9ec-181">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="bb9ec-182">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="bb9ec-182">**Name Server 2**</span></span> <br/> |<span data-ttu-id="bb9ec-183">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="bb9ec-183">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="bb9ec-184">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="bb9ec-184">**Name Server 2**</span></span> <br/> |<span data-ttu-id="bb9ec-185">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="bb9ec-185">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NetworkSolutionsBP-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
3. <span data-ttu-id="bb9ec-187">[ **MOVE DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-187">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
4. <span data-ttu-id="bb9ec-189">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-189">Select **Save Changes**.</span></span>
    
    ![NetworkSolutionsBP-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="bb9ec-191">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-191">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="bb9ec-192">その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-192">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="bb9ec-193">既に一覧表示されているネームサーバーがある場合</span><span class="sxs-lookup"><span data-stu-id="bb9ec-193">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="bb9ec-194">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers.</span><span class="sxs-lookup"><span data-stu-id="bb9ec-194">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers.</span></span> <span data-ttu-id="bb9ec-195">(That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="bb9ec-195">(That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
1. <span data-ttu-id="bb9ec-196">他のネームサーバーが表示されている場合は、各ネームサーバーを選び、キーボードの **Delete** キーを押して、ネームサーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-196">If there are any other nameservers listed, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span>
    
    ![NetworkSolutions-BP-Redelegate-1-5](../../media/eeb8ad22-bf4a-43a8-b97a-f09c3654d89b.png)
  
2. <span data-ttu-id="bb9ec-198">[**その他のネームサーバーを追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-198">Select **Add More Name Servers**.</span></span>
    
    ![NetworkSolutionsBP-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
3. <span data-ttu-id="bb9ec-200">[ **Domain Names**] ページに、次の表のネームサーバーの値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-200">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span>
 
    
|||
|:-----|:-----|
|<span data-ttu-id="bb9ec-201">**Name Server 1**</span><span class="sxs-lookup"><span data-stu-id="bb9ec-201">**Name Server 1**</span></span> <br/> |<span data-ttu-id="bb9ec-202">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="bb9ec-202">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="bb9ec-203">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="bb9ec-203">**Name Server 2**</span></span> <br/> |<span data-ttu-id="bb9ec-204">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="bb9ec-204">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="bb9ec-205">**Name Server 3**</span><span class="sxs-lookup"><span data-stu-id="bb9ec-205">**Name Server 3**</span></span> <br/> |<span data-ttu-id="bb9ec-206">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="bb9ec-206">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="bb9ec-207">**Name Server 4**</span><span class="sxs-lookup"><span data-stu-id="bb9ec-207">**Name Server 4**</span></span> <br/> |<span data-ttu-id="bb9ec-208">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="bb9ec-208">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NetworkSolutionsBP-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
4. <span data-ttu-id="bb9ec-210">[ **MOVE DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-210">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
5. <span data-ttu-id="bb9ec-212">[ **Save Changes** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-212">Select **Save Changes.**</span></span>
    
    ![NetworkSolutionsBP-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="bb9ec-214">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-214">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="bb9ec-215">その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。</span><span class="sxs-lookup"><span data-stu-id="bb9ec-215">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
