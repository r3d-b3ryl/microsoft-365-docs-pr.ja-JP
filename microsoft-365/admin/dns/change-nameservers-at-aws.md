---
title: ネームサーバーを変更して Amazon Web Services (AWS) で Office 365 をセットアップする
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Amazon Web サービス (AWS) で DNS レコードを管理するように Office 365 をセットアップする方法について説明します。 '
ms.openlocfilehash: a7125cf0add8200fe152c426f47e7f27a8f6226c
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212355"
---
# <a name="change-nameservers-to-set-up-office-365-with-amazon-web-services-aws"></a><span data-ttu-id="f51e1-103">ネームサーバーを変更して Amazon Web Services (AWS) で Office 365 をセットアップする</span><span class="sxs-lookup"><span data-stu-id="f51e1-103">Change nameservers to set up Office 365 with Amazon Web Services (AWS)</span></span>

 <span data-ttu-id="f51e1-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="f51e1-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f51e1-p101">Office 365 に Office 365 DNS レコードを管理させる場合は、次の手順に従ってください ([AWS で Office 365 のすべての DNS レコードを管理することもできます](create-dns-records-at-aws.md))。</span><span class="sxs-lookup"><span data-stu-id="f51e1-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at AWS](create-dns-records-at-aws.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f51e1-107">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="f51e1-107">Add a TXT record for verification</span></span>

<span data-ttu-id="f51e1-p102">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="f51e1-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f51e1-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="f51e1-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="f51e1-p104">まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="f51e1-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f51e1-114">[**リソース**] ページで、[ **Hosted Zones**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f51e1-114">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="f51e1-115">[ **Hosted Zones** ] ページの [ **domain Name** ] 列で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="f51e1-115">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="f51e1-116">[ **Create Record Set**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f51e1-116">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="f51e1-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="f51e1-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f51e1-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="f51e1-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="f51e1-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="f51e1-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f51e1-121">**名前**</span><span class="sxs-lookup"><span data-stu-id="f51e1-121">**Name**</span></span> <br/> |<span data-ttu-id="f51e1-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="f51e1-122">**Type**</span></span> <br/> |<span data-ttu-id="f51e1-123">**Alias**</span><span class="sxs-lookup"><span data-stu-id="f51e1-123">**Alias**</span></span> <br/> |<span data-ttu-id="f51e1-124">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="f51e1-124">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="f51e1-125">**Value**</span><span class="sxs-lookup"><span data-stu-id="f51e1-125">**Value**</span></span> <br/> |<span data-ttu-id="f51e1-126">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="f51e1-126">**Routing Policy**</span></span> <br/> |
|<span data-ttu-id="f51e1-127">(このフィールドは空のままにします)</span><span class="sxs-lookup"><span data-stu-id="f51e1-127">(Leave this field empty)</span></span>  <br/> |<span data-ttu-id="f51e1-128">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="f51e1-128">TXT - Text</span></span>  <br/> |<span data-ttu-id="f51e1-129">No</span><span class="sxs-lookup"><span data-stu-id="f51e1-129">No</span></span>  <br/> |<span data-ttu-id="f51e1-130">300</span><span class="sxs-lookup"><span data-stu-id="f51e1-130">300</span></span>  <br/> |<span data-ttu-id="f51e1-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f51e1-131">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="f51e1-132">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="f51e1-132">**Note:** This is an example.</span></span> <span data-ttu-id="f51e1-133">Office 365 の表から [**宛先またはポイント先のアドレス**] の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="f51e1-133">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="f51e1-134">確認する方法</span><span class="sxs-lookup"><span data-stu-id="f51e1-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  <br/>  |<span data-ttu-id="f51e1-135">Simple</span><span class="sxs-lookup"><span data-stu-id="f51e1-135">Simple</span></span> <br/> |
   
6. <span data-ttu-id="f51e1-136">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f51e1-136">Select **Create**.</span></span>
    
7. <span data-ttu-id="f51e1-137">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="f51e1-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f51e1-138">これで、ドメイン レジストラーのサイトでレコードが追加されました。Office 365 に戻り、Office 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="f51e1-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="f51e1-139">Office 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="f51e1-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f51e1-140">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f51e1-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="f51e1-141">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="f51e1-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="f51e1-142">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f51e1-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="f51e1-143">[**ドメインの確認**] ページで、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f51e1-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f51e1-p107">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f51e1-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="f51e1-147">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="f51e1-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="f51e1-p108">Office 365 でドメインをセットアップするには、Office 365 のプライマリ ネーム サーバーとセカンダリ ネーム サーバーを参照するように、ドメインの NS レコードをドメイン レジストラーで変更します。これで、ドメインの DNS レコードを更新するように Office 365 で設定されます。メール、Skype for Business Online、一般向け Web サイトをドメインで利用できるようにすべてのレコードを追加し、すべての設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="f51e1-p108">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="f51e1-p109">ドメインの NS レコードを Office 365 のネーム サーバーをポイントするように変更すると、現在ドメインに関連付けられているすべてのサービスが影響を受けます。たとえば、この変更後、ドメイン (rob@ *your_domain*  .com など) に送信されるすべてのメールは、Office 365 に送信されるようになります。</span><span class="sxs-lookup"><span data-stu-id="f51e1-p109">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="f51e1-153">次の手順では、リストからその他の不要なネームサーバーを削除する方法と、正しいネームサーバーが表示されていない場合には追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f51e1-153">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="f51e1-154">> このセクションの手順を完了すると、次の4つのネームサーバーのみが表示されます。 > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f51e1-154">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="f51e1-155">まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f51e1-155">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="f51e1-156">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="f51e1-156">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f51e1-157">[**リソース**] ページで、[ **Hosted Zones**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f51e1-157">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="f51e1-158">[ **Hosted Zones** ] ページの [ **domain Name** ] 列で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="f51e1-158">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="f51e1-159">[ **Nameserver**] レコード セットを選びます。</span><span class="sxs-lookup"><span data-stu-id="f51e1-159">Select the **Nameserver** record set.</span></span> 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. <span data-ttu-id="f51e1-161">[ **Value**] ボックスの [ **NS - Name server**] レコード セットで、すべてのネームサーバーを選んでキーボードの **Delete** キーを押して削除します。</span><span class="sxs-lookup"><span data-stu-id="f51e1-161">In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="f51e1-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="f51e1-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="f51e1-163">(つまり、 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**、または**ns4.bdm.microsoftonline.com**という名前が付いて*いない*現在のネームサーバーのみを削除します)。</span><span class="sxs-lookup"><span data-stu-id="f51e1-163">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. <span data-ttu-id="f51e1-165">[ **TTL (秒):** ] 領域で、[ **1H** (1 時間)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f51e1-165">In the **TTL (Seconds):** area, select **1h** (1 Hour).</span></span> 
    
    ![1時間の場合は [1H] を選択します。](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. <span data-ttu-id="f51e1-167">[ **Value**] ボックスの [ **NS - Name server**] レコード セットで、次の表の **第 1 行**の値を入力するかコピーして貼り付けてからキーボードの **Enter** キーを押し、次の **行**の値を入力するかコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f51e1-167">Still in the **NS - Name server** record set, in the **Value** box, type or copy and paste the **First line** value from the following table, then press the **Enter** key on your keyboard and type or copy and paste the next **line** value.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="f51e1-168">Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration.</span><span class="sxs-lookup"><span data-stu-id="f51e1-168">Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f51e1-169">**第 1 行**</span><span class="sxs-lookup"><span data-stu-id="f51e1-169">**First line**</span></span> <br/> |<span data-ttu-id="f51e1-170">ns1.bdm.microsoftonline.com。</span><span class="sxs-lookup"><span data-stu-id="f51e1-170">ns1.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="f51e1-171">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="f51e1-171">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="f51e1-172">**第 2 行**</span><span class="sxs-lookup"><span data-stu-id="f51e1-172">**Second line**</span></span> <br/> |<span data-ttu-id="f51e1-173">ns2.bdm.microsoftonline.com。</span><span class="sxs-lookup"><span data-stu-id="f51e1-173">ns2.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="f51e1-174">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="f51e1-174">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="f51e1-175">**第 3 行**</span><span class="sxs-lookup"><span data-stu-id="f51e1-175">**Third line**</span></span> <br/> |<span data-ttu-id="f51e1-176">ns3.bdm.microsoftonline.com。</span><span class="sxs-lookup"><span data-stu-id="f51e1-176">ns3.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="f51e1-177">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="f51e1-177">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="f51e1-178">**第 4 行**</span><span class="sxs-lookup"><span data-stu-id="f51e1-178">**Fourth line**</span></span> <br/> |<span data-ttu-id="f51e1-179">ns4.bdm.microsoftonline.com。</span><span class="sxs-lookup"><span data-stu-id="f51e1-179">ns4.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="f51e1-180">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="f51e1-180">**This value MUST end with a period (.)**</span></span> <br/> |
   
   ![[値] ボックスに最初の行の値を入力するか貼り付けます。](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. <span data-ttu-id="f51e1-182">[ **Save Record Set**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f51e1-182">Select **Save Record Set**.</span></span>
    
    ![レコードセットの保存の選択](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> <span data-ttu-id="f51e1-p113">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。Office 365 のメールと他のサービスの準備が完了し、ドメインで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f51e1-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
