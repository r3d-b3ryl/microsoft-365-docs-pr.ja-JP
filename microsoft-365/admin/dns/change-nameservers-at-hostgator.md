---
title: Hostgator を使用して Microsoft をセットアップするためにネームサーバーを変更する
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
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: Hostgator でカスタムドメインの DNS レコードを管理するように Microsoft をセットアップする方法について説明します。
ms.openlocfilehash: 787fe5f5e768d9d93cfca9d1644037142822216e
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400643"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-hostgator"></a><span data-ttu-id="9e35d-103">Hostgator で Microsoft 365 をセットアップするためにネームサーバーを変更する</span><span class="sxs-lookup"><span data-stu-id="9e35d-103">Change nameservers to set up Microsoft 365 with Hostgator</span></span>

 <span data-ttu-id="9e35d-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e35d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="9e35d-105">Microsoft が DNS レコードを管理する場合は、次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="9e35d-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="9e35d-106">(必要に応じ[て、すべての MICROSOFT DNS レコードを Hostgator で管理](create-dns-records-at-hostgator.md)できます。)</span><span class="sxs-lookup"><span data-stu-id="9e35d-106">(If you prefer, you can [manage all your Microsoft DNS records at Hostgator](create-dns-records-at-hostgator.md).)</span></span>
  
    
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="9e35d-107">ドメインがホスティング アカウントを指すようにします。</span><span class="sxs-lookup"><span data-stu-id="9e35d-107">Point your domain to your hosting account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e35d-108">次のセクション「 **確認のための TXT レコードを追加する** 」の手順の前に、この操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e35d-108">You must perform this procedure before you perform the procedure in the following section, **Add a TXT record for verification**.</span></span>
  
<span data-ttu-id="9e35d-109">次の手順に従って、ドメインとホスティング アカウントの関連付けを行ってください。</span><span class="sxs-lookup"><span data-stu-id="9e35d-109">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="9e35d-p102">まず、[このリンク](https://portal.hostgator.com/domain/manage)を使って Hostgator でカスタマー ポータル ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9e35d-p102">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Hostgator-BP-Redelegate-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="9e35d-113">[**ドメイン**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e35d-113">Select the **Domains** tab.</span></span>
    
    ![Hostgator-BP-Redelegate-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="9e35d-115">[**ドメインの管理**] ページの **[マイドメイン**] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e35d-115">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span>
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="9e35d-117">[**ドメインの概要**] ページの [**名前サーバー** ] 領域で、[**変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e35d-117">On the **Domains Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="9e35d-119">ドメインの [**ネームサーバー** ] ページの [**ホスティングアカウントの選択**] ドロップダウンリストで、ドメインに関連付けられている**ホスティングアカウント**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e35d-119">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span>
    
    ![Hostgator-BP-Redelegate-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="9e35d-121">[ **Save Name Servers**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9e35d-121">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-9](../../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9e35d-123">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9e35d-123">Add a TXT record for verification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e35d-124">この手順を実行する前に、この記事の最初のセクションの手順を実行してから、[ドメインがホスティングアカウントを指すよう](#point-your-domain-to-your-hosting-account)にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e35d-124">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account.](#point-your-domain-to-your-hosting-account).</span></span>
  
<span data-ttu-id="9e35d-p103">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="9e35d-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9e35d-p104">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="9e35d-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>
  
1. <span data-ttu-id="9e35d-p105">開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9e35d-p105">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="9e35d-p106">(Hostgator でホストされる各アカウントに一意の cPanel アドレスが割り当てられます。 cPanel アドレスは、以下のような形式になります。https://YourSiteAddress:secure-port-number。 Hostgator から届くサインアップ メールで、そのアドレスが指定されます。)</span><span class="sxs-lookup"><span data-stu-id="9e35d-p106">(Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. The sign-up email you received from Hostgator will specify that address.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9e35d-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="9e35d-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="9e35d-135">開始するには、Hostgator からホスティングアカウントを購入するか、Microsoft をポイントするように[ドメインのネームサーバー (NS) レコードを変更](#change-your-domains-nameserver-ns-records)することができます。</span><span class="sxs-lookup"><span data-stu-id="9e35d-135">To get started, you can either purchase a hosting account from Hostgator or [change your domain's nameserver (NS) records](#change-your-domains-nameserver-ns-records) to point to Microsoft.</span></span> 
  
2. <span data-ttu-id="9e35d-136">[**コントロールパネル**] ページの [**ドメイン**] 領域で、[ **Advanced DNS Zone Editor**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e35d-136">On the **Control Panel** page, in the **Domains** area, select **Advanced DNS Zone Editor**.</span></span>
    
    <span data-ttu-id="9e35d-137">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="9e35d-137">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="9e35d-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9e35d-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9e35d-139">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="9e35d-139">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9e35d-140">**Name**</span><span class="sxs-lookup"><span data-stu-id="9e35d-140">**Name**</span></span> <br/> |<span data-ttu-id="9e35d-141">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9e35d-141">**TTL**</span></span> <br/> |<span data-ttu-id="9e35d-142">**Type**</span><span class="sxs-lookup"><span data-stu-id="9e35d-142">**Type**</span></span> <br/> |<span data-ttu-id="9e35d-143">**TXT Data**</span><span class="sxs-lookup"><span data-stu-id="9e35d-143">**TXT Data**</span></span> <br/> |
|<span data-ttu-id="9e35d-p108">Use your  *domain_name*  . (for example, fourthcoffee.com.)  </span><span class="sxs-lookup"><span data-stu-id="9e35d-p108">Use your  *domain_name*  . (for example, fourthcoffee.com.)  </span></span><br/> <span data-ttu-id="9e35d-146">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="9e35d-146">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="9e35d-147">1 </span><span class="sxs-lookup"><span data-stu-id="9e35d-147">1</span></span>  <br/> |<span data-ttu-id="9e35d-148">TXT</span><span class="sxs-lookup"><span data-stu-id="9e35d-148">TXT</span></span>  <br/> |<span data-ttu-id="9e35d-149">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9e35d-149">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9e35d-150">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="9e35d-150">**Note:** This is an example.</span></span> <span data-ttu-id="9e35d-151">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="9e35d-151">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="9e35d-152">確認する方法</span><span class="sxs-lookup"><span data-stu-id="9e35d-152">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. <span data-ttu-id="9e35d-153">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e35d-153">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="9e35d-154">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="9e35d-154">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9e35d-155">これで、ドメインレジストラーのサイトでレコードが追加されました。 Microsoft に戻って、レコードの検索を要求します。</span><span class="sxs-lookup"><span data-stu-id="9e35d-155">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="9e35d-156">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="9e35d-156">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9e35d-157">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="9e35d-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="9e35d-158">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e35d-158">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="9e35d-159">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e35d-159">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="9e35d-160">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e35d-160">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9e35d-p110">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e35d-p110">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="9e35d-164">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="9e35d-164">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="9e35d-165">Microsoft によるドメインの設定を完了するには、ドメインレジストラーでドメインの NS レコードを変更して、Microsoft プライマリネームサーバーとセカンダリネームサーバーをポイントするようにします。</span><span class="sxs-lookup"><span data-stu-id="9e35d-165">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="9e35d-166">これにより、ドメインの DNS レコードが更新されるように Microsoft が設定されます。</span><span class="sxs-lookup"><span data-stu-id="9e35d-166">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="9e35d-167">メール、Skype for Business Online、一般向け Web サイトをドメインで利用できるようにすべてのレコードを追加し、すべての設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="9e35d-167">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="9e35d-168">ドメインの NS レコードを変更して Microsoft ネームサーバーをポイントすると、現在ドメインに関連付けられているすべてのサービスが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="9e35d-168">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="9e35d-169">たとえば、ドメインに送信されるすべての電子メール (rob@ *your_domain*など) は、この変更を行った後に Microsoft に送られ始めます。</span><span class="sxs-lookup"><span data-stu-id="9e35d-169">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9e35d-170">次の手順では、リストからその他の不要なネームサーバーを削除する方法と、正しいネームサーバーが表示されていない場合には追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e35d-170">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="9e35d-171">このセクションの手順を完了すると、次の4つのネームサーバーのみが一覧表示されます。 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**、および**ns4.bdm.microsoftonline.com**。</span><span class="sxs-lookup"><span data-stu-id="9e35d-171">When you have completed the steps in this section, the only nameservers that should be listed are these four:  **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span>
  
1. <span data-ttu-id="9e35d-p114">まず、[このリンク](https://portal.hostgator.com/domain/manage)を使って Hostgator でカスタマー ポータル ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9e35d-p114">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Hostgator-BP-Redelegate-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="9e35d-175">[**ドメイン**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e35d-175">Select the **Domains** tab.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="9e35d-177">[**ドメインの管理**] ページの **[マイドメイン**] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e35d-177">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="9e35d-179">[**ドメインの概要**] ページの [**名前サーバー** ] 領域で、[**変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e35d-179">On the **Domain Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="9e35d-181">ドメインの [**ネームサーバー** ] ページの [**ホスティングアカウントの選択**] ドロップダウンリストで、ドメインに関連付けられている**ホスティングアカウント**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e35d-181">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="9e35d-183">[**自分のネームサーバーを手動で設定**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e35d-183">Select **Manually set my name servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-5](../../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   <span data-ttu-id="9e35d-185">**注意**: これらの手順は、4つの正しいネームサーバー以外の既存のネームサーバーがある場合にのみ実行してください。</span><span class="sxs-lookup"><span data-stu-id="9e35d-185">**CAUTION**: Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="9e35d-186">(つまり、 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**、または**ns4.bdm.microsoftonline.com**という名前が付いて*いない*現在のネームサーバーのみを削除します)。</span><span class="sxs-lookup"><span data-stu-id="9e35d-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
        <span data-ttu-id="9e35d-187">ドメインの [ **Name Servers**] ページにあるネームサーバーのリストで、各ネームサーバーを削除します。リストから選択してキーボードの **Delete** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9e35d-187">Still on the **Name Servers** page for your domain, in the list of nameservers, delete each nameserver in the list by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
   ![Hostgator-BP-Redelegate-1-6](../../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. <span data-ttu-id="9e35d-189">ネームサーバーのリストに、次の表の最初の 2 つの値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9e35d-189">Still in the list of nameservers, type or copy and paste the first two values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="9e35d-190">**Name Server 1:**</span><span class="sxs-lookup"><span data-stu-id="9e35d-190">**Name Server 1:**</span></span> <br/> |<span data-ttu-id="9e35d-191">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9e35d-191">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="9e35d-192">**Name Server 2:**</span><span class="sxs-lookup"><span data-stu-id="9e35d-192">**Name Server 2:**</span></span> <br/> |<span data-ttu-id="9e35d-193">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9e35d-193">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="9e35d-194">**Name Server 3:**</span><span class="sxs-lookup"><span data-stu-id="9e35d-194">**Name Server 3:**</span></span> <br/> |<span data-ttu-id="9e35d-195">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9e35d-195">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="9e35d-196">**Name Server 4:**</span><span class="sxs-lookup"><span data-stu-id="9e35d-196">**Name Server 4:**</span></span> <br/> |<span data-ttu-id="9e35d-197">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9e35d-197">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Hostgator-BP-Redelegate-1-7-1](../../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. <span data-ttu-id="9e35d-199">他のネームサーバー値を追加します。</span><span class="sxs-lookup"><span data-stu-id="9e35d-199">Add the other nameserver values.</span></span>
    
    <span data-ttu-id="9e35d-200">[追加] **(+)** を選択し、テーブルの次の行の値をレコードのボックスに入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9e35d-200">Select **(+)** add, and then type or copy and paste the value from the next row of the table into the box for the record.</span></span> 
    
    <span data-ttu-id="9e35d-201">4 つの nameserver レコードの作成がすべて完了するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9e35d-201">Repeat this process until you have created all four nameserver records.</span></span>
    
    ![Hostgator-BP-Redelegate-1-7-2](../../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. <span data-ttu-id="9e35d-203">[ **Save Name Servers**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9e35d-203">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-8](../../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> <span data-ttu-id="9e35d-205">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9e35d-205">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="9e35d-206">その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。</span><span class="sxs-lookup"><span data-stu-id="9e35d-206">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
