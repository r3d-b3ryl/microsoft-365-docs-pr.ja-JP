---
title: Microsoft の Amazon Web Services (AWS) で DNS レコードを作成する
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: ドメインを確認し、Microsoft の Amazon Web Services (AWS) で電子メール、Skype for Business Online、その他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 12f9341ab381324266cf2da1ca6b5423df9973dd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910416"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a><span data-ttu-id="e847a-103">Microsoft の Amazon Web Services (AWS) で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="e847a-103">Create DNS records at Amazon Web Services (AWS) for Microsoft</span></span>

 <span data-ttu-id="e847a-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e847a-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e847a-105">AWS が DNS ホスティング プロバイダーの場合は、この記事の手順に従ってドメインを確認し、メール、Skype Online for Business などのための DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="e847a-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="e847a-106">これらのレコードを AWS で追加すると、ドメインは Microsoft サービスで動作するために設定されます。</span><span class="sxs-lookup"><span data-stu-id="e847a-106">After you add these records at AWS, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="e847a-p101">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e847a-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e847a-110">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="e847a-110">Add a TXT record for verification</span></span>
<span data-ttu-id="e847a-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="e847a-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="e847a-p102">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="e847a-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e847a-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="e847a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e847a-p104">まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="e847a-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e847a-118">[リソース] **ページで** 、[ホストゾーン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e847a-118">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="e847a-119">[ホスト **ゾーン] ページ** の [ **ドメイン** 名] 列で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="e847a-119">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="e847a-120">[レコード **セットの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e847a-120">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="e847a-121">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="e847a-121">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e847a-122">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="e847a-122">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="e847a-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="e847a-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e847a-125">**名前**</span><span class="sxs-lookup"><span data-stu-id="e847a-125">**Name**</span></span> <br/> |<span data-ttu-id="e847a-126">**型**</span><span class="sxs-lookup"><span data-stu-id="e847a-126">**Type**</span></span> <br/> |<span data-ttu-id="e847a-127">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e847a-127">**Alias**</span></span> <br/> |<span data-ttu-id="e847a-128">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="e847a-128">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="e847a-129">**Value**</span><span class="sxs-lookup"><span data-stu-id="e847a-129">**Value**</span></span> <br/> |<span data-ttu-id="e847a-130">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="e847a-130">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="e847a-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="e847a-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="e847a-132">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="e847a-132">TXT - Text</span></span>  <br/> |<span data-ttu-id="e847a-133">No</span><span class="sxs-lookup"><span data-stu-id="e847a-133">No</span></span>  <br/> |<span data-ttu-id="e847a-134">300</span><span class="sxs-lookup"><span data-stu-id="e847a-134">300</span></span>  <br/> |<span data-ttu-id="e847a-135">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e847a-135">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="e847a-136">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="e847a-136">**Note:** This is an example.</span></span> <span data-ttu-id="e847a-137">Microsoft 365 の表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="e847a-137">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="e847a-138">確認する方法</span><span class="sxs-lookup"><span data-stu-id="e847a-138">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="e847a-139">Simple</span><span class="sxs-lookup"><span data-stu-id="e847a-139">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="e847a-140">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e847a-140">Select **Create**.</span></span>
    
7. <span data-ttu-id="e847a-141">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="e847a-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e847a-142">ドメイン レジストラーのサイトにレコードを追加したので、Microsoft に戻り、レコードの検索を要求します。</span><span class="sxs-lookup"><span data-stu-id="e847a-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="e847a-143">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="e847a-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e847a-144">Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e847a-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="e847a-145">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e847a-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="e847a-146">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e847a-146">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="e847a-147">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e847a-147">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e847a-p107">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e847a-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a><span data-ttu-id="e847a-151">ドメインのメールが Microsoft 365 に届く MX レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="e847a-151">Add an MX record so email for your domain will come to Microsoft 365</span></span>
<span data-ttu-id="e847a-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e847a-152"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="e847a-p108">まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="e847a-p108">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e847a-155">[リソース] **ページで** 、[ホストゾーン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e847a-155">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="e847a-156">[ホスト **ゾーン] ページ** の [ **ドメイン** 名] 列で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="e847a-156">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="e847a-157">[レコード **セットの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e847a-157">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="e847a-158">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="e847a-158">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e847a-159">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="e847a-159">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="e847a-160">**名前**</span><span class="sxs-lookup"><span data-stu-id="e847a-160">**Name**</span></span>|<span data-ttu-id="e847a-161">**型**</span><span class="sxs-lookup"><span data-stu-id="e847a-161">**Type**</span></span>|<span data-ttu-id="e847a-162">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e847a-162">**Alias**</span></span>|<span data-ttu-id="e847a-163">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="e847a-163">**TTL (Seconds)**</span></span>|<span data-ttu-id="e847a-164">**Value**</span><span class="sxs-lookup"><span data-stu-id="e847a-164">**Value**</span></span>|<span data-ttu-id="e847a-165">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="e847a-165">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e847a-166">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="e847a-166">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="e847a-167">MX - Mail Exchange</span><span class="sxs-lookup"><span data-stu-id="e847a-167">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="e847a-168">No</span><span class="sxs-lookup"><span data-stu-id="e847a-168">No</span></span>  <br/> |<span data-ttu-id="e847a-169">300</span><span class="sxs-lookup"><span data-stu-id="e847a-169">300</span></span>  <br/> |<span data-ttu-id="e847a-170">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e847a-170">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="e847a-p109">0 は、MX 優先度の値です。 この値を MX 値の先頭に追加して、スペースで他の値から分離します。  </span><span class="sxs-lookup"><span data-stu-id="e847a-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="e847a-173">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="e847a-173">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="e847a-174">**注:** Microsoft \<*domain-key*\> 365 アカウントから取得します。</span><span class="sxs-lookup"><span data-stu-id="e847a-174">**Note:** Get your \<*domain-key*\> from your Microsoft 365 account.</span></span> [<span data-ttu-id="e847a-175">確認する方法</span><span class="sxs-lookup"><span data-stu-id="e847a-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="e847a-176">Simple</span><span class="sxs-lookup"><span data-stu-id="e847a-176">Simple</span></span>  <br/> |
       
    ![AWS-BP-Configure-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="e847a-178">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e847a-178">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="e847a-180">他の MX レコードがある場合は削除します。</span><span class="sxs-lookup"><span data-stu-id="e847a-180">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e847a-181">AWS は、複数のレコードを含む可能性があるセットとして MX レコードを格納します。</span><span class="sxs-lookup"><span data-stu-id="e847a-181">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="e847a-182">**[レコード** セット **の削除]** を選択しない場合は、追加した MX レコードを含むすべての MX レコードが削除されます。</span><span class="sxs-lookup"><span data-stu-id="e847a-182">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="e847a-183">代わりに、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="e847a-183">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="e847a-184">最初に、MX レコード セットを選択します。</span><span class="sxs-lookup"><span data-stu-id="e847a-184">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="e847a-186">次に、[ **Edit Record Set**] 領域で、[ **Value**] ボックスのエントリを選んで、キーボードの **Delete** キーを押し、使われなくなった MX レコードをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="e847a-186">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="e847a-188">[レコード **セットの保存] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e847a-188">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="e847a-190">Microsoft 365 に必要な 5 つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="e847a-190">Add the five CNAME records that are required for Microsoft 365</span></span>
<span data-ttu-id="e847a-191"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e847a-191"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="e847a-p112">まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="e847a-p112">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e847a-194">[リソース] **ページで** 、[ホストゾーン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e847a-194">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="e847a-195">[ホスト **ゾーン] ページ** の [ **ドメイン** 名] 列で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="e847a-195">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="e847a-196">[レコード **セットの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e847a-196">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="e847a-197">1 番目の CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e847a-197">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="e847a-198">[ **Create Record Set**] 領域にある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="e847a-198">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="e847a-199">[ **Type**] と [ **Routing Policy**] の値をドロップダウン リストから選びます。</span><span class="sxs-lookup"><span data-stu-id="e847a-199">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="e847a-200">**名前**</span><span class="sxs-lookup"><span data-stu-id="e847a-200">**Name**</span></span>|<span data-ttu-id="e847a-201">**型**</span><span class="sxs-lookup"><span data-stu-id="e847a-201">**Type**</span></span>|<span data-ttu-id="e847a-202">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e847a-202">**Alias**</span></span>|<span data-ttu-id="e847a-203">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="e847a-203">**TTL (Seconds)**</span></span>|<span data-ttu-id="e847a-204">**Value**</span><span class="sxs-lookup"><span data-stu-id="e847a-204">**Value**</span></span>|<span data-ttu-id="e847a-205">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="e847a-205">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e847a-206">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e847a-206">autodiscover</span></span>  <br/> |<span data-ttu-id="e847a-207">CNAME - 正規名</span><span class="sxs-lookup"><span data-stu-id="e847a-207">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="e847a-208">No</span><span class="sxs-lookup"><span data-stu-id="e847a-208">No</span></span>  <br/> |<span data-ttu-id="e847a-209">300</span><span class="sxs-lookup"><span data-stu-id="e847a-209">300</span></span>  <br/> |<span data-ttu-id="e847a-210">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e847a-210">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="e847a-211">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="e847a-211">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e847a-212">Simple</span><span class="sxs-lookup"><span data-stu-id="e847a-212">Simple</span></span>  <br/> |
    |<span data-ttu-id="e847a-213">sip</span><span class="sxs-lookup"><span data-stu-id="e847a-213">sip</span></span>  <br/> |<span data-ttu-id="e847a-214">CNAME - 正規名</span><span class="sxs-lookup"><span data-stu-id="e847a-214">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="e847a-215">No</span><span class="sxs-lookup"><span data-stu-id="e847a-215">No</span></span>  <br/> |<span data-ttu-id="e847a-216">300</span><span class="sxs-lookup"><span data-stu-id="e847a-216">300</span></span>  <br/> |<span data-ttu-id="e847a-217">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e847a-217">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="e847a-218">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="e847a-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e847a-219">Simple</span><span class="sxs-lookup"><span data-stu-id="e847a-219">Simple</span></span>  <br/> |
    |<span data-ttu-id="e847a-220">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e847a-220">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e847a-221">CNAME - 正規名</span><span class="sxs-lookup"><span data-stu-id="e847a-221">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="e847a-222">No</span><span class="sxs-lookup"><span data-stu-id="e847a-222">No</span></span>  <br/> |<span data-ttu-id="e847a-223">300</span><span class="sxs-lookup"><span data-stu-id="e847a-223">300</span></span>  <br/> |<span data-ttu-id="e847a-224">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e847a-224">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="e847a-225">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="e847a-225">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e847a-226">Simple</span><span class="sxs-lookup"><span data-stu-id="e847a-226">Simple</span></span>  <br/> |
    |<span data-ttu-id="e847a-227">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e847a-227">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e847a-228">CNAME - 正規名</span><span class="sxs-lookup"><span data-stu-id="e847a-228">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="e847a-229">No</span><span class="sxs-lookup"><span data-stu-id="e847a-229">No</span></span>  <br/> |<span data-ttu-id="e847a-230">300</span><span class="sxs-lookup"><span data-stu-id="e847a-230">300</span></span>  <br/> |<span data-ttu-id="e847a-231">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="e847a-231">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="e847a-232">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="e847a-232">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e847a-233">Simple</span><span class="sxs-lookup"><span data-stu-id="e847a-233">Simple</span></span>  <br/> |
    |<span data-ttu-id="e847a-234">EnterpriseEnrollment</span><span class="sxs-lookup"><span data-stu-id="e847a-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e847a-235">CNAME - 正規名</span><span class="sxs-lookup"><span data-stu-id="e847a-235">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="e847a-236">No</span><span class="sxs-lookup"><span data-stu-id="e847a-236">No</span></span>  <br/> |<span data-ttu-id="e847a-237">300</span><span class="sxs-lookup"><span data-stu-id="e847a-237">300</span></span>  <br/> |<span data-ttu-id="e847a-238">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e847a-238">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="e847a-239">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="e847a-239">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e847a-240">Simple</span><span class="sxs-lookup"><span data-stu-id="e847a-240">Simple</span></span>  <br/> |
   
    ![AWS-BP-Configure-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="e847a-242">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e847a-242">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="e847a-244">残りの 4 つの CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e847a-244">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="e847a-245">[ホスト **ゾーン] ページ** で、[レコード セットの作成] を選択し、テーブルの次の行の値を使用してレコードを作成し、もう一度 [**作成**] を選択してそのレコードを完了します。</span><span class="sxs-lookup"><span data-stu-id="e847a-245">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="e847a-246">5 つの CNAME レコードすべてが作成されるまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e847a-246">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e847a-247">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="e847a-247">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e847a-248"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="e847a-248"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e847a-249">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e847a-249">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e847a-250">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="e847a-250">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e847a-251">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="e847a-251">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="e847a-252">代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む  *1*  つの SPF レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="e847a-252">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="e847a-253">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e847a-253">Need examples?</span></span> <span data-ttu-id="e847a-254">こちらの[Microsoft の外部ドメイン ネーム システムのレコード](../../enterprise/external-domain-name-system-records.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e847a-254">Check out these [External Domain Name System records for Microsoft](../../enterprise/external-domain-name-system-records.md).</span></span> <span data-ttu-id="e847a-255">SPF レコードを検証するには、次のいずれかの[SPF 検証ツールを使用できます](../setup/domains-faq.yml)。</span><span class="sxs-lookup"><span data-stu-id="e847a-255">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="e847a-256">まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e847a-256">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="e847a-257">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="e847a-257">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e847a-258">[リソース] **ページで** 、[ホストゾーン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e847a-258">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="e847a-259">[ホスト **ゾーン] ページ** の [ **ドメイン** 名] 列で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="e847a-259">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="e847a-260">TXT レコード **セットを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="e847a-260">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="e847a-p115">[ **レコード セットの編集**] 領域で、既存のレコード用の [ **Value:**] ボックス内にある現在のエントリの最後で、キーボードの Enter キーを押して新規の行を作成します。次に、その行 (既存の値の下) に、次のテーブルの値を入力、またはコピーして貼り付けます (表の下のイラストに例があります)。</span><span class="sxs-lookup"><span data-stu-id="e847a-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="e847a-264">**Value:**</span><span class="sxs-lookup"><span data-stu-id="e847a-264">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="e847a-265">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e847a-265">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e847a-p116">(画面の手順で必要になる引用符は自動的に補完されます。手動で入力する必要はありません。)  </span><span class="sxs-lookup"><span data-stu-id="e847a-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="e847a-268">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e847a-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS-BP-Configure-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="e847a-270">[レコード **セットの保存] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e847a-270">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="e847a-272">Microsoft 365 に必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="e847a-272">Add the two SRV records that are required for Microsoft 365</span></span>
<span data-ttu-id="e847a-273"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="e847a-273"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="e847a-p117">まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="e847a-p117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e847a-276">[リソース] **ページで** 、[ホストゾーン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e847a-276">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="e847a-277">[ホスト **ゾーン] ページ** の [ **ドメイン** 名] 列で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="e847a-277">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="e847a-278">[レコード **セットの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e847a-278">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="e847a-279">1 番目の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e847a-279">Add the first SRV record:</span></span>
    
    <span data-ttu-id="e847a-280">[ **Create Record Set**] 領域にある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="e847a-280">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="e847a-281">[ **Type**] と [ **Routing Policy**] の値をドロップダウン リストから選びます。</span><span class="sxs-lookup"><span data-stu-id="e847a-281">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="e847a-282">**名前**</span><span class="sxs-lookup"><span data-stu-id="e847a-282">**Name**</span></span>|<span data-ttu-id="e847a-283">**型**</span><span class="sxs-lookup"><span data-stu-id="e847a-283">**Type**</span></span>|<span data-ttu-id="e847a-284">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e847a-284">**Alias**</span></span>|<span data-ttu-id="e847a-285">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="e847a-285">**TTL (Seconds)**</span></span>|<span data-ttu-id="e847a-286">**Value**</span><span class="sxs-lookup"><span data-stu-id="e847a-286">**Value**</span></span>|<span data-ttu-id="e847a-287">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="e847a-287">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e847a-288">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="e847a-288">_sip._tls</span></span>|<span data-ttu-id="e847a-289">SRV - サービス ロケータ</span><span class="sxs-lookup"><span data-stu-id="e847a-289">SRV - Service locator</span></span>|<span data-ttu-id="e847a-290">No</span><span class="sxs-lookup"><span data-stu-id="e847a-290">No</span></span>|<span data-ttu-id="e847a-291">300</span><span class="sxs-lookup"><span data-stu-id="e847a-291">300</span></span>|<span data-ttu-id="e847a-292">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e847a-292">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="e847a-293">**この値は、ピリオド (.) で終了する必要があります。**></span><span class="sxs-lookup"><span data-stu-id="e847a-293">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="e847a-294">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e847a-294">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="e847a-295">Simple</span><span class="sxs-lookup"><span data-stu-id="e847a-295">Simple</span></span>|
    |<span data-ttu-id="e847a-296">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="e847a-296">_sipfederationtls._tcp</span></span>|<span data-ttu-id="e847a-297">SRV - サービス ロケータ</span><span class="sxs-lookup"><span data-stu-id="e847a-297">SRV - Service locator</span></span>|<span data-ttu-id="e847a-298">No</span><span class="sxs-lookup"><span data-stu-id="e847a-298">No</span></span>|<span data-ttu-id="e847a-299">300</span><span class="sxs-lookup"><span data-stu-id="e847a-299">300</span></span>|<span data-ttu-id="e847a-300">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e847a-300">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="e847a-301">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="e847a-301">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="e847a-302">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e847a-302">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="e847a-303">シンプル</span><span class="sxs-lookup"><span data-stu-id="e847a-303">Simple</span></span>|
   
    ![AWS-BP-Configure-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="e847a-305">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e847a-305">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="e847a-307">他の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e847a-307">To add the other SRV record:</span></span>
    
    <span data-ttu-id="e847a-308">[ホスト **ゾーン] ページ** で、[レコード セットの作成] を選択し、テーブルの次の行の値を使用してレコードを作成し、もう一度 [**作成**] を選択してそのレコードを完了します。</span><span class="sxs-lookup"><span data-stu-id="e847a-308">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="e847a-p120">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e847a-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
