---
title: Amazon Web サービスを使用して Microsoft をセットアップするためにネームサーバーを変更する (AWS)
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Amazon Web サービス (AWS) で DNS レコードを管理するように Microsoft をセットアップする方法について説明します。 '
ms.openlocfilehash: 6efe06400652783ffbc6732b5c6327067c5c484c
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400679"
---
# <a name="change-nameservers-to-set-up-microsoft-with-amazon-web-services-aws"></a><span data-ttu-id="4ffc7-103">Amazon Web サービスを使用して Microsoft をセットアップするためにネームサーバーを変更する (AWS)</span><span class="sxs-lookup"><span data-stu-id="4ffc7-103">Change nameservers to set up Microsoft with Amazon Web Services (AWS)</span></span>

 <span data-ttu-id="4ffc7-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="4ffc7-105">Microsoft が DNS レコードを管理する場合は、次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="4ffc7-106">(必要に応じ[て、すべての MICROSOFT DNS レコードを AWS で管理](create-dns-records-at-aws.md)できます。)</span><span class="sxs-lookup"><span data-stu-id="4ffc7-106">(If you prefer, you can [manage all your Microsoft DNS records at AWS](create-dns-records-at-aws.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4ffc7-107">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="4ffc7-107">Add a TXT record for verification</span></span>

<span data-ttu-id="4ffc7-p102">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4ffc7-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="4ffc7-p104">まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="4ffc7-114">[**リソース**] ページで、[ **Hosted Zones**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-114">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="4ffc7-115">[ **Hosted Zones** ] ページの [ **domain Name** ] 列で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-115">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="4ffc7-116">[ **Create Record Set**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-116">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="4ffc7-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="4ffc7-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4ffc7-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="4ffc7-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="4ffc7-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="4ffc7-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4ffc7-121">**名前**</span><span class="sxs-lookup"><span data-stu-id="4ffc7-121">**Name**</span></span> <br/> |<span data-ttu-id="4ffc7-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="4ffc7-122">**Type**</span></span> <br/> |<span data-ttu-id="4ffc7-123">**Alias**</span><span class="sxs-lookup"><span data-stu-id="4ffc7-123">**Alias**</span></span> <br/> |<span data-ttu-id="4ffc7-124">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="4ffc7-124">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="4ffc7-125">**Value**</span><span class="sxs-lookup"><span data-stu-id="4ffc7-125">**Value**</span></span> <br/> |<span data-ttu-id="4ffc7-126">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="4ffc7-126">**Routing Policy**</span></span> <br/> |
|<span data-ttu-id="4ffc7-127">(このフィールドは空のままにします)</span><span class="sxs-lookup"><span data-stu-id="4ffc7-127">(Leave this field empty)</span></span>  <br/> |<span data-ttu-id="4ffc7-128">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="4ffc7-128">TXT - Text</span></span>  <br/> |<span data-ttu-id="4ffc7-129">No</span><span class="sxs-lookup"><span data-stu-id="4ffc7-129">No</span></span>  <br/> |<span data-ttu-id="4ffc7-130">300</span><span class="sxs-lookup"><span data-stu-id="4ffc7-130">300</span></span>  <br/> |<span data-ttu-id="4ffc7-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="4ffc7-131">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="4ffc7-132">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-132">**Note:** This is an example.</span></span> <span data-ttu-id="4ffc7-133">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="4ffc7-134">確認する方法</span><span class="sxs-lookup"><span data-stu-id="4ffc7-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  <br/>  |<span data-ttu-id="4ffc7-135">Simple</span><span class="sxs-lookup"><span data-stu-id="4ffc7-135">Simple</span></span> <br/> |
   
6. <span data-ttu-id="4ffc7-136">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-136">Select **Create**.</span></span>
    
7. <span data-ttu-id="4ffc7-137">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="4ffc7-138">これで、ドメインレジストラーのサイトでレコードが追加されました。 Microsoft に戻って、レコードの検索を要求します。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="4ffc7-139">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4ffc7-140">Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="4ffc7-141">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="4ffc7-142">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="4ffc7-143">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4ffc7-p107">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="4ffc7-147">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="4ffc7-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="4ffc7-148">Microsoft によるドメインの設定を完了するには、ドメインレジストラーでドメインの NS レコードを変更して、Microsoft プライマリネームサーバーとセカンダリネームサーバーをポイントするようにします。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-148">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="4ffc7-149">これにより、ドメインの DNS レコードが更新されるように Microsoft が設定されます。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-149">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="4ffc7-150">メール、Skype for Business Online、一般向け Web サイトをドメインで利用できるようにすべてのレコードを追加し、すべての設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-150">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="4ffc7-151">ドメインの NS レコードを変更して Microsoft ネームサーバーをポイントすると、現在ドメインに関連付けられているすべてのサービスが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-151">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="4ffc7-152">たとえば、ドメインに送信されるすべての電子メール (rob@ *your_domain*など) は、この変更を行った後に Microsoft に送られ始めます。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-152">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="4ffc7-153">次の手順では、リストからその他の不要なネームサーバーを削除する方法と、正しいネームサーバーが表示されていない場合には追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-153">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="4ffc7-154">> このセクションの手順を完了すると、次の4つのネームサーバーのみが表示されます。 > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4ffc7-154">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="4ffc7-155">まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-155">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="4ffc7-156">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-156">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="4ffc7-157">[**リソース**] ページで、[ **Hosted Zones**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-157">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="4ffc7-158">[ **Hosted Zones** ] ページの [ **domain Name** ] 列で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-158">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="4ffc7-159">[ **Nameserver**] レコード セットを選びます。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-159">Select the **Nameserver** record set.</span></span> 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. <span data-ttu-id="4ffc7-161">[ **Value**] ボックスの [ **NS - Name server**] レコード セットで、すべてのネームサーバーを選んでキーボードの **Delete** キーを押して削除します。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-161">In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="4ffc7-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="4ffc7-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="4ffc7-163">(つまり、 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**、または**ns4.bdm.microsoftonline.com**という名前が付いて*いない*現在のネームサーバーのみを削除します)。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-163">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. <span data-ttu-id="4ffc7-165">[ **TTL (秒):** ] 領域で、[ **1H** (1 時間)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-165">In the **TTL (Seconds):** area, select **1h** (1 Hour).</span></span> 
    
    ![1時間の場合は [1H] を選択します。](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. <span data-ttu-id="4ffc7-167">[ **Value**] ボックスの [ **NS - Name server**] レコード セットで、次の表の **第 1 行**の値を入力するかコピーして貼り付けてからキーボードの **Enter** キーを押し、次の **行**の値を入力するかコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-167">Still in the **NS - Name server** record set, in the **Value** box, type or copy and paste the **First line** value from the following table, then press the **Enter** key on your keyboard and type or copy and paste the next **line** value.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="4ffc7-168">Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration.</span><span class="sxs-lookup"><span data-stu-id="4ffc7-168">Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4ffc7-169">**第 1 行**</span><span class="sxs-lookup"><span data-stu-id="4ffc7-169">**First line**</span></span> <br/> |<span data-ttu-id="4ffc7-170">ns1.bdm.microsoftonline.com。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-170">ns1.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="4ffc7-171">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="4ffc7-171">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="4ffc7-172">**第 2 行**</span><span class="sxs-lookup"><span data-stu-id="4ffc7-172">**Second line**</span></span> <br/> |<span data-ttu-id="4ffc7-173">ns2.bdm.microsoftonline.com。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-173">ns2.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="4ffc7-174">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="4ffc7-174">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="4ffc7-175">**第 3 行**</span><span class="sxs-lookup"><span data-stu-id="4ffc7-175">**Third line**</span></span> <br/> |<span data-ttu-id="4ffc7-176">ns3.bdm.microsoftonline.com。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-176">ns3.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="4ffc7-177">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="4ffc7-177">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="4ffc7-178">**第 4 行**</span><span class="sxs-lookup"><span data-stu-id="4ffc7-178">**Fourth line**</span></span> <br/> |<span data-ttu-id="4ffc7-179">ns4.bdm.microsoftonline.com。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-179">ns4.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="4ffc7-180">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="4ffc7-180">**This value MUST end with a period (.)**</span></span> <br/> |
   
   ![[値] ボックスに最初の行の値を入力するか貼り付けます。](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. <span data-ttu-id="4ffc7-182">[ **Save Record Set**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-182">Select **Save Record Set**.</span></span>
    
    ![レコードセットの保存の選択](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> <span data-ttu-id="4ffc7-184">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="4ffc7-184">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="4ffc7-185">その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。</span><span class="sxs-lookup"><span data-stu-id="4ffc7-185">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
