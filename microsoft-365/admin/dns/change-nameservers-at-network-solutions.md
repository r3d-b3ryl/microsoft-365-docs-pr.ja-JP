---
title: Network Solutions で Office 365 をセットアップするためにネームサーバーを変更する
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
ms.assetid: d4ba60f3-4e1c-4180-99bd-250b8955be2a
description: 'Office 365 で DNS レコードを管理する場合は、ネットワークソリューションを使用して Office 365 カスタムドメインをセットアップする方法について説明します。 '
ms.openlocfilehash: c9465da507e6b4dea35f9ead50b5bc7c14a1b38f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42242610"
---
# <a name="change-nameservers-to-set-up-office-365-with-network-solutions"></a><span data-ttu-id="64296-103">Network Solutions で Office 365 をセットアップするためにネームサーバーを変更する</span><span class="sxs-lookup"><span data-stu-id="64296-103">Change nameservers to set up Office 365 with Network Solutions</span></span>

 <span data-ttu-id="64296-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="64296-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="64296-p101">Office 365 に Office 365 DNS レコードを管理させる場合は、次の手順に従います ([Network Solutions で Office 365 のすべての DNS レコードを管理することもできます](create-dns-records-at-network-solutions.md))。</span><span class="sxs-lookup"><span data-stu-id="64296-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Network Solutions](create-dns-records-at-network-solutions.md).)</span></span>
  
    
## <a name="add-a-txt-record-at-network-solutions-to-verify-that-you-own-the-domain"></a><span data-ttu-id="64296-107">Network Solutions で TXT レコードを追加して、ドメインを所有していることを確認する</span><span class="sxs-lookup"><span data-stu-id="64296-107">Add a TXT record at Network Solutions to verify that you own the domain</span></span>

<span data-ttu-id="64296-p102">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="64296-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="64296-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="64296-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="64296-112">次の手順を実行するか、[ビデオ (47 秒から開始) を参照](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="64296-112">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="64296-p104">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="64296-p104">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="64296-115">[**ログイン**] ボタンを選択する前に、[ **Log in to** ] ドロップダウンリストで [ **Manage My Domain Names** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="64296-115">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span>
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="64296-117">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="64296-117">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="64296-119">[ **EDIT DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="64296-119">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="64296-121">[ **Manage ADVANCED DNS Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="64296-121">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="64296-122">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="64296-122">(You may have to scroll down.)</span></span>
    
    ![[Manage Advanced DNS Records] を選択します。](../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="64296-124">[**テキスト (Txt レコード)** ] セクションまでスクロールしてから、[ **Txt レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="64296-124">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![[TXT レコードの編集] を選択する](../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="64296-126">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="64296-126">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
|<span data-ttu-id="64296-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="64296-127">**Host**</span></span>|<span data-ttu-id="64296-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="64296-128">**TTL**</span></span>|<span data-ttu-id="64296-129">**Text**</span><span class="sxs-lookup"><span data-stu-id="64296-129">**Text**</span></span>|
|:-----|:-----|:-----|
|@  <br/> <span data-ttu-id="64296-130">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="64296-130">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="64296-131">3600</span><span class="sxs-lookup"><span data-stu-id="64296-131">3600</span></span>  <br/> |<span data-ttu-id="64296-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="64296-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="64296-133">**注**: これは例です。</span><span class="sxs-lookup"><span data-stu-id="64296-133">**Note**: This is an example.</span></span> <span data-ttu-id="64296-134">Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="64296-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="64296-135">確認する方法</span><span class="sxs-lookup"><span data-stu-id="64296-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
   
    
   ![新しいレコードのボックスに値を入力するか貼り付けます。](../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="64296-137">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="64296-137">Select **Continue**.</span></span>
    
    ![[続行] を選択する](../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="64296-139">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="64296-139">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択する](../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="64296-141">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="64296-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="64296-142">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="64296-142">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="64296-143">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="64296-143">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="64296-144">管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="64296-144">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="64296-145">[**ドメイン**] ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="64296-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="64296-146">[**セットアップ**] ページで、[**セットアップの開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="64296-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="64296-147">[**ドメインの確認**] ページで、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="64296-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="64296-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64296-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="64296-151">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="64296-151">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="64296-p107">Office 365 でドメインをセットアップするには、Office 365 のプライマリ ネーム サーバーとセカンダリ ネーム サーバーを参照するように、ドメインの NS レコードをドメイン レジストラーで変更します。これで、ドメインの DNS レコードを更新するように Office 365 で設定されます。メール、Skype for Business Online、一般向け Web サイトをドメインで利用できるようにすべてのレコードを追加し、すべての設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="64296-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="64296-p108">ドメインの NS レコードを Office 365 のネーム サーバーをポイントするように変更すると、現在ドメインに関連付けられているすべてのサービスが影響を受けます。たとえば、この変更後、ドメイン (rob@ *your_domain*  .com など) に送信されるすべてのメールは、Office 365 に送信されるようになります。</span><span class="sxs-lookup"><span data-stu-id="64296-p108">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span>
  
<span data-ttu-id="64296-p109">Office 365 でドメインをセットアップできるように、NS レコードを変更する準備ができましたか? 次の手順を実行するか、[ビデオ (2 分 23 秒から開始) を参照](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="64296-p109">Ready to change your NS records so Office 365 can set up your domain? Follow the steps below or [watch the video (start at 2:23)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="64296-159">このセクションの手順を完了すると、次の4つのネームサーバー*のみ*が一覧表示されます。 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**、および**ns4.bdm.microsoftonline.com**。</span><span class="sxs-lookup"><span data-stu-id="64296-159">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span> <span data-ttu-id="64296-160">次の手順では、他の不要なネームサーバーを一覧から削除する方法、および上記のネームサーバーが一覧に表示されていない場合に、 *正しい*  ネームサーバーを追加する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="64296-160">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="64296-161">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="64296-161">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="64296-162">ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="64296-162">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="64296-163">[**ログイン**] ボタンを選択する前に、[ **Log in to** ] ドロップダウンリストで [ **Manage My Domain Names** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="64296-163">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="64296-165">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="64296-165">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="64296-167">[ **EDIT DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="64296-167">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="64296-169">[ **MOVE DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="64296-169">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-1-1](../media/e57a30f3-63d5-4bcb-84c6-c8be21c261a2.png)
  
5. <span data-ttu-id="64296-171">現在表示されているページに既に一覧表示されているネームサーバーがあるかどうかに応じて、以下の 2 つの手順のいずれかに進みます。</span><span class="sxs-lookup"><span data-stu-id="64296-171">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="64296-172">既に一覧表示されているネーム サーバーが **ない** 場合は、 [既に一覧表示されているネームサーバーがない場合](#if-there-are-no-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="64296-172">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="64296-173">既に一覧表示されているネーム サーバーが **ある** 場合は、 [既に一覧表示されているネームサーバーがある場合](#if-there-are-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="64296-173">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="64296-174">既に一覧表示されているネームサーバーがない場合</span><span class="sxs-lookup"><span data-stu-id="64296-174">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="64296-175">[**ドメイン**] ページの [ **Domain Name servers の指定**] セクションで、[さらに**ネームサーバーを追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="64296-175">On the **Domains** page, in the **Specify Domain Name Servers** section, select **Add More Name Servers**.</span></span>
    
    ![NetworkSolutionsBP-1-2-1](../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
2. <span data-ttu-id="64296-177">[ **Domain Names**] ページに、次の表のネームサーバーの値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="64296-177">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="64296-178">**Name Server 1**</span><span class="sxs-lookup"><span data-stu-id="64296-178">**Name Server 1**</span></span> <br/> |<span data-ttu-id="64296-179">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="64296-179">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="64296-180">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="64296-180">**Name Server 2**</span></span> <br/> |<span data-ttu-id="64296-181">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="64296-181">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="64296-182">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="64296-182">**Name Server 2**</span></span> <br/> |<span data-ttu-id="64296-183">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="64296-183">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="64296-184">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="64296-184">**Name Server 2**</span></span> <br/> |<span data-ttu-id="64296-185">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="64296-185">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NetworkSolutionsBP-1-2-2](../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
3. <span data-ttu-id="64296-187">[ **MOVE DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="64296-187">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-1-2-3](../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
4. <span data-ttu-id="64296-189">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="64296-189">Select **Save Changes**.</span></span>
    
    ![NetworkSolutionsBP-1-2-4](../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="64296-p112">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。Office 365 のメールと他のサービスの準備が完了し、ドメインで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="64296-p112">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="64296-193">既に一覧表示されているネームサーバーがある場合</span><span class="sxs-lookup"><span data-stu-id="64296-193">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="64296-p113">これらの手順は、前途した 4 件の *正しい*  ネームサーバー以外にも既存のネームサーバーがある場合に  *のみ*  行ってください (つまり、現在のネームサーバーのうち *ns1.bdm.microsoftonline.com* 、 *ns2.bdm.microsoftonline.com* 、 **ns3.bdm.microsoftonline.com** 、 **ns4.bdm.microsoftonline.com** のいずれでも  **ない**  もの  **だけ**  を削除します)。</span><span class="sxs-lookup"><span data-stu-id="64296-p113">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
1. <span data-ttu-id="64296-196">他のネームサーバーが表示されている場合は、各ネームサーバーを選び、キーボードの **Delete** キーを押して、ネームサーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="64296-196">If there are any other nameservers listed, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span>
    
    ![NetworkSolutions-BP-Redelegate-1-5](../media/eeb8ad22-bf4a-43a8-b97a-f09c3654d89b.png)
  
2. <span data-ttu-id="64296-198">[**その他のネームサーバーを追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="64296-198">Select **Add More Name Servers**.</span></span>
    
    ![NetworkSolutionsBP-1-2-1](../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
3. <span data-ttu-id="64296-200">[ **Domain Names**] ページに、次の表のネームサーバーの値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="64296-200">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span>
 
    
|||
|:-----|:-----|
|<span data-ttu-id="64296-201">**Name Server 1**</span><span class="sxs-lookup"><span data-stu-id="64296-201">**Name Server 1**</span></span> <br/> |<span data-ttu-id="64296-202">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="64296-202">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="64296-203">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="64296-203">**Name Server 2**</span></span> <br/> |<span data-ttu-id="64296-204">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="64296-204">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="64296-205">**Name Server 3**</span><span class="sxs-lookup"><span data-stu-id="64296-205">**Name Server 3**</span></span> <br/> |<span data-ttu-id="64296-206">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="64296-206">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="64296-207">**Name Server 4**</span><span class="sxs-lookup"><span data-stu-id="64296-207">**Name Server 4**</span></span> <br/> |<span data-ttu-id="64296-208">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="64296-208">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NetworkSolutionsBP-1-2-2](../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
4. <span data-ttu-id="64296-210">[ **MOVE DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="64296-210">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-1-2-3](../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
5. <span data-ttu-id="64296-212">[ **Save Changes** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="64296-212">Select **Save Changes.**</span></span>
    
    ![NetworkSolutionsBP-1-2-4](../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="64296-p114">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。Office 365 のメールと他のサービスの準備が完了し、ドメインで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="64296-p114">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span>