---
title: MyDomain を使用して Microsoft をセットアップするためにネームサーバーを変更する
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
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: ユーザーが自分のカスタムドメインの DNS レコードを管理するように Microsoft を設定する方法については、MyDomain を参照してください。
ms.openlocfilehash: 44d36f872ddbeeba1948ee8a7a4db029895fcb8c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646417"
---
# <a name="change-nameservers-to-set-up-microsoft-with-mydomain"></a><span data-ttu-id="6661a-103">MyDomain を使用して Microsoft をセットアップするためにネームサーバーを変更する</span><span class="sxs-lookup"><span data-stu-id="6661a-103">Change nameservers to set up Microsoft with MyDomain</span></span>

 <span data-ttu-id="6661a-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6661a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="6661a-105">Microsoft が DNS レコードを管理する場合は、次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="6661a-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="6661a-106">(必要に応じ [て、MyDomain にあるすべての MICROSOFT DNS レコードを管理](create-dns-records-at-mydomain.md)することができます)。</span><span class="sxs-lookup"><span data-stu-id="6661a-106">(If you prefer, you can [manage all your Microsoft DNS records at MyDomain](create-dns-records-at-mydomain.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6661a-107">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="6661a-107">Add a TXT record for verification</span></span>

<span data-ttu-id="6661a-p102">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="6661a-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6661a-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="6661a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="6661a-p104">まず、[このリンク](https://www.mydomain.com/controlpanel)を使って MyDomain でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="6661a-p104">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6661a-114">[**お気に入り**] セクションで、[**Domain Central**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6661a-114">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="6661a-115">[**ドメイン**] で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="6661a-115">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="6661a-116">[**概要**] 行で、[**DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6661a-116">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="6661a-117">[**変更**] ドロップダウン リストから、[**TXT/SPF レコード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6661a-117">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="6661a-118">[**Content**] の新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="6661a-118">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
||
|:-----|
|<span data-ttu-id="6661a-119">**Content**</span><span class="sxs-lookup"><span data-stu-id="6661a-119">**Content**</span></span> <br/> |
|<span data-ttu-id="6661a-120">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6661a-120">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="6661a-121">**注**: これは例です。</span><span class="sxs-lookup"><span data-stu-id="6661a-121">**Note**: This is an example.</span></span> <span data-ttu-id="6661a-122">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="6661a-122">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="6661a-123">確認する方法</span><span class="sxs-lookup"><span data-stu-id="6661a-123">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="6661a-124">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6661a-124">Select **Add**.</span></span>
    
8. <span data-ttu-id="6661a-125">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="6661a-125">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6661a-126">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft 365 に戻り、Microsoft 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="6661a-126">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="6661a-127">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="6661a-127">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6661a-128">Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="6661a-128">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="6661a-129">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="6661a-129">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="6661a-130">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6661a-130">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="6661a-131">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6661a-131">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6661a-p106">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6661a-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="6661a-135">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="6661a-135">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="6661a-136">Microsoft によるドメインの設定を完了するには、ドメインレジストラーでドメインの NS レコードを変更して、Microsoft プライマリネームサーバーとセカンダリネームサーバーをポイントするようにします。</span><span class="sxs-lookup"><span data-stu-id="6661a-136">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="6661a-137">これにより、ドメインの DNS レコードが更新されるように Microsoft が設定されます。</span><span class="sxs-lookup"><span data-stu-id="6661a-137">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="6661a-138">メール、Skype for Business Online、一般向け Web サイトをドメインで利用できるようにすべてのレコードを追加し、すべての設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="6661a-138">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="6661a-139">ドメインの NS レコードを変更して Microsoft ネームサーバーをポイントすると、現在ドメインに関連付けられているすべてのサービスが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="6661a-139">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="6661a-140">たとえば、ドメインに送信されるすべての電子メール (rob@ など *your_domain。*</span><span class="sxs-lookup"><span data-stu-id="6661a-140">For example, all email sent to your domain (like rob@ *your_domain.*</span></span> <span data-ttu-id="6661a-141">この変更を行った後、com) は Microsoft に送られ始めます。</span><span class="sxs-lookup"><span data-stu-id="6661a-141">com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6661a-p109">次の手順では、他の不要なネームサーバーを一覧から削除する方法、および上記のネームサーバーが一覧に表示されていない場合に、正しいネームサーバーを追加する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="6661a-p109">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. </span></span><br/> <span data-ttu-id="6661a-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span><span class="sxs-lookup"><span data-stu-id="6661a-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span>
  
1. <span data-ttu-id="6661a-p110">まず、[このリンク](https://www.mydomain.com/controlpanel)を使って MyDomain でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="6661a-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6661a-146">[**お気に入り**] セクションで、[**Domain Central**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6661a-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="6661a-147">[**ドメイン**] で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="6661a-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="6661a-148">**概要**行で、[**ネーム**サーバー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6661a-148">In the **Overview** row, select **Nameservers**.</span></span>
    
    ![MyDomain-BP-1-1](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. <span data-ttu-id="6661a-150">[ **Update Name Servers**] セクションで [ **Use different name servers**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6661a-150">In the **Update Name Servers** section, select **Use different name servers**.</span></span>
    
    ![MyDomain-BP-1-2-1](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. <span data-ttu-id="6661a-152">現在表示されているページに既にネームサーバーが表示されているかどうかに応じて、次の2つの手順のいずれかに進みます。</span><span class="sxs-lookup"><span data-stu-id="6661a-152">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-the-correct-nameservers-are-already-listed"></a><span data-ttu-id="6661a-153">正しいネームサーバーが表示されている場合</span><span class="sxs-lookup"><span data-stu-id="6661a-153">If the correct nameservers ARE already listed</span></span>

- <span data-ttu-id="6661a-154">正しいネームサーバーが表示されている場合は、この手順をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="6661a-154">If the correct nameservers are already listed, you can skip this step.</span></span>
    
    ![MyDomain-BP-1-2-2](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a><span data-ttu-id="6661a-156">正しいネームサーバーが表示されていない場合</span><span class="sxs-lookup"><span data-stu-id="6661a-156">If the correct nameservers are NOT already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="6661a-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="6661a-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="6661a-158">(つまり、 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**、または**ns4.bdm.microsoftonline.com**という名前が付いて*いない*現在のネームサーバーのみを削除します)。</span><span class="sxs-lookup"><span data-stu-id="6661a-158">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="6661a-159">[ **Nameserver**] フィールドの各エントリを選び、キーボードの **Delete** キーを押して既存のネームサーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="6661a-159">Delete the existing nameservers by selecting each entry in the **Nameserver:** field, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![MyDomain-BP-1-3-1](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. <span data-ttu-id="6661a-161">[ **追加** ] を2回選択して、2つの新しいネームサーバー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="6661a-161">Select **Add More** twice to add two new Nameserver rows.</span></span> 
    
    ![MyDomain-BP-1-3-2](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. <span data-ttu-id="6661a-163">レコードのボックスに、次の表の nameserver の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="6661a-163">In the boxes for the records, type or copy and paste the nameserver values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="6661a-164">**Nameserver 1**</span><span class="sxs-lookup"><span data-stu-id="6661a-164">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="6661a-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6661a-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6661a-166">**Nameserver 2**</span><span class="sxs-lookup"><span data-stu-id="6661a-166">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="6661a-167">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6661a-167">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6661a-168">**Nameserver 3**</span><span class="sxs-lookup"><span data-stu-id="6661a-168">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="6661a-169">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6661a-169">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6661a-170">**Nameserver 4**</span><span class="sxs-lookup"><span data-stu-id="6661a-170">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="6661a-171">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6661a-171">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![MyDomain-BP-1-4](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. <span data-ttu-id="6661a-173">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6661a-173">Select **Save**.</span></span>
    
    ![MyDomain-BP-1-5](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> <span data-ttu-id="6661a-175">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6661a-175">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="6661a-176">その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。</span><span class="sxs-lookup"><span data-stu-id="6661a-176">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
