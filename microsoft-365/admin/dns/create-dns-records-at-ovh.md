---
title: Microsoft 用の「Excel で DNS レコードを作成する」
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: ドメインを確認し、電子メール、Skype for Business Online、およびその他の Microsoft 用のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 01c455f54a7ee2efc6114dba1c01170b97ea5f71
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629289"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a><span data-ttu-id="6cb5d-103">Microsoft 用の「Excel で DNS レコードを作成する」</span><span class="sxs-lookup"><span data-stu-id="6cb5d-103">Create DNS records at OVH for Microsoft</span></span>

<span data-ttu-id="6cb5d-104">探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)してください。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6cb5d-105">使用している DNS ホスティング プロバイダーが OVH の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="6cb5d-106">追加する主なレコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="6cb5d-107">Microsoft 用の「Excel で DNS レコードを作成する」</span><span class="sxs-lookup"><span data-stu-id="6cb5d-107">Create DNS records at OVH for Microsoft</span></span>](#create-dns-records-at-ovh-for-microsoft)
    
- [<span data-ttu-id="6cb5d-108">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="6cb5d-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="6cb5d-109">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="6cb5d-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="6cb5d-110">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="6cb5d-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="6cb5d-111">Microsoft に必要な2つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="6cb5d-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="6cb5d-112">これらのレコードを "準備中" で追加すると、使用しているドメインが Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-112">After you add these records at OVH, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="6cb5d-113">Microsoft を使用した web サイトのホストと DNS の詳細については、「 [microsoft とのパブリック web サイトの使用](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-113">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="6cb5d-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6cb5d-117">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="6cb5d-117">Add a TXT record for verification</span></span>
<span data-ttu-id="6cb5d-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="6cb5d-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="6cb5d-119">ドメインを Microsoft で使用する前に、必ずそのドメインを所有していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-119">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="6cb5d-120">ドメインレジストラーで自分のアカウントにログインし、DNS レコードを作成することにより、そのドメインを所有していることが Microsoft に証明されます。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-120">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6cb5d-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="6cb5d-p104">まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-p104">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="6cb5d-126">[ **Domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-126">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="6cb5d-128">[ **DNS zone**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-128">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="6cb5d-130">[**エントリを追加する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-130">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="6cb5d-132">**TXT**の選択</span><span class="sxs-lookup"><span data-stu-id="6cb5d-132">Select **TXT**</span></span>
    
    ![[すべて選択] TXT エントリ](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="6cb5d-134">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-134">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="6cb5d-135">TTL 値を割り当てるには、ドロップダウンリストから [**個人用**] を選択し、テキストボックスに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-135">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="6cb5d-136">**Record type**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-136">**Record type**</span></span>|<span data-ttu-id="6cb5d-137">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-137">**Sub-domain**</span></span>|<span data-ttu-id="6cb5d-138">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-138">**TTL**</span></span>|<span data-ttu-id="6cb5d-139">**値**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-139">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6cb5d-140">TXT</span><span class="sxs-lookup"><span data-stu-id="6cb5d-140">TXT</span></span>  <br/> |<span data-ttu-id="6cb5d-141">(空白のまま)</span><span class="sxs-lookup"><span data-stu-id="6cb5d-141">(leave blank)</span></span>  <br/> |<span data-ttu-id="6cb5d-142">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="6cb5d-142">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="6cb5d-143">MS=msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="6cb5d-143">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="6cb5d-144">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-144">**Note:** This is an example.</span></span> <span data-ttu-id="6cb5d-145">この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="6cb5d-146">確認する方法</span><span class="sxs-lookup"><span data-stu-id="6cb5d-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="6cb5d-147">[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-147">Select **Confirm**.</span></span> 
    
    ![OVH confirm TXT for verification](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="6cb5d-149">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-149">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6cb5d-150">これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft に戻ってレコードを要求します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-150">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="6cb5d-151">Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-151">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6cb5d-152">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-152">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="6cb5d-153">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-153">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="6cb5d-154">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-154">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="6cb5d-155">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-155">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="6cb5d-p107">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="6cb5d-159">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="6cb5d-159">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="6cb5d-160"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="6cb5d-160"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="6cb5d-p108">まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-p108">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="6cb5d-164">[ **Domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-164">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="6cb5d-166">[ **DNS zone**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-166">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="6cb5d-168">[**エントリを追加する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-168">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="6cb5d-170">[ **MX**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-170">Select **MX**.</span></span>
    
    ![OVH MX record type](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="6cb5d-172">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-172">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="6cb5d-173">TTL 値を割り当てるには、ドロップダウンリストから [**個人用**] を選択し、テキストボックスに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-173">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="6cb5d-174">既定では、移動先の相対表記を使用します。これにより、ターゲットレコードの末尾にドメイン名が追加されます。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-174">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="6cb5d-175">絶対表記を代わりに使用するには、次の表に示すように、ターゲット レコードにドットを追加します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-175">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="6cb5d-176">**Record type**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-176">**Record type**</span></span>|<span data-ttu-id="6cb5d-177">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-177">**Sub-domain**</span></span>|<span data-ttu-id="6cb5d-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-178">**TTL**</span></span>|<span data-ttu-id="6cb5d-179">**優先度**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-179">**Priority**</span></span>|<span data-ttu-id="6cb5d-180">**Target**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-180">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6cb5d-181">MX</span><span class="sxs-lookup"><span data-stu-id="6cb5d-181">MX</span></span>  <br/> |<span data-ttu-id="6cb5d-182">(空白のまま)</span><span class="sxs-lookup"><span data-stu-id="6cb5d-182">(leave blank)</span></span>  <br/> |<span data-ttu-id="6cb5d-183">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="6cb5d-183">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="6cb5d-184">10 </span><span class="sxs-lookup"><span data-stu-id="6cb5d-184">10</span></span>  <br/> <span data-ttu-id="6cb5d-185">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="6cb5d-186">\<domain-key\>.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="6cb5d-186">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="6cb5d-187">**注:** Microsoft アカウントから\* \<ドメインキー\> \*を取得します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-187">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="6cb5d-188">確認する方法</span><span class="sxs-lookup"><span data-stu-id="6cb5d-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![メールの "差し込み" MX レコード](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="6cb5d-190">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-190">Select **Next**.</span></span>
    
    ![OVH MX record select Next](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="6cb5d-192">[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-192">Select **Confirm**.</span></span>
    
    ![OVH MX record select Confirm](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="6cb5d-194">MX レコードが他にもある場合は、[ **DNS zone** ] ページですべて削除します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-194">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="6cb5d-195">各レコードを選択し、[**アクション**] 列で [ごみ箱-**削除**可能] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-195">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH delete MX record](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="6cb5d-197">[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-197">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="6cb5d-198">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="6cb5d-198">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="6cb5d-199"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="6cb5d-199"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="6cb5d-p113">まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-p113">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="6cb5d-203">[ **Domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-203">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="6cb5d-205">[ **DNS zone**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-205">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="6cb5d-207">[**エントリを追加する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-207">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="6cb5d-209">[ **CNAME**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-209">Select **CNAME**.</span></span>
    
    ![OVH add CNAME record type](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="6cb5d-211">1 番目の CNAME レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-211">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="6cb5d-212">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-212">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="6cb5d-213">TTL 値を割り当てるには、ドロップダウンリストから [**個人用**] を選択し、テキストボックスに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-213">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="6cb5d-214">**Record type**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-214">**Record type**</span></span>|<span data-ttu-id="6cb5d-215">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-215">**Sub-domain**</span></span>|<span data-ttu-id="6cb5d-216">**ターゲット**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-216">**Target**</span></span>|<span data-ttu-id="6cb5d-217">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-217">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6cb5d-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="6cb5d-218">CNAME</span></span>  <br/> |<span data-ttu-id="6cb5d-219">autodiscover</span><span class="sxs-lookup"><span data-stu-id="6cb5d-219">autodiscover</span></span>  <br/> |<span data-ttu-id="6cb5d-220">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-220">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="6cb5d-221">3,600 秒</span><span class="sxs-lookup"><span data-stu-id="6cb5d-221">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="6cb5d-222">CNAME</span><span class="sxs-lookup"><span data-stu-id="6cb5d-222">CNAME</span></span>  <br/> |<span data-ttu-id="6cb5d-223">sip</span><span class="sxs-lookup"><span data-stu-id="6cb5d-223">sip</span></span>  <br/> |<span data-ttu-id="6cb5d-224">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-224">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="6cb5d-225">3,600 秒</span><span class="sxs-lookup"><span data-stu-id="6cb5d-225">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="6cb5d-226">CNAME</span><span class="sxs-lookup"><span data-stu-id="6cb5d-226">CNAME</span></span>  <br/> |<span data-ttu-id="6cb5d-227">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6cb5d-227">lyncdiscover</span></span>  <br/> |<span data-ttu-id="6cb5d-228">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-228">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="6cb5d-229">3,600 秒</span><span class="sxs-lookup"><span data-stu-id="6cb5d-229">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="6cb5d-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="6cb5d-230">CNAME</span></span>  <br/> |<span data-ttu-id="6cb5d-231">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="6cb5d-231">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="6cb5d-232">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-232">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="6cb5d-233">3,600 秒</span><span class="sxs-lookup"><span data-stu-id="6cb5d-233">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="6cb5d-234">CNAME</span><span class="sxs-lookup"><span data-stu-id="6cb5d-234">CNAME</span></span>  <br/> |<span data-ttu-id="6cb5d-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="6cb5d-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="6cb5d-236">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-236">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="6cb5d-237">3,600 秒</span><span class="sxs-lookup"><span data-stu-id="6cb5d-237">3600 seconds</span></span>  <br/> |
   
    !["はい" CNAME レコード](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="6cb5d-239">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-239">Select **Next**.</span></span>
    
    ![OVH Add CNAME values and select Next](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="6cb5d-241">[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-241">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="6cb5d-242">前の手順を繰り返し、他の 5 つの CNAME レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-242">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="6cb5d-243">レコードごとに、上のテーブルの次の行の値をそのレコードのボックスに入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-243">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="6cb5d-244">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="6cb5d-244">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="6cb5d-245"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="6cb5d-245"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="6cb5d-246">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-246">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="6cb5d-247">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="6cb5d-248">ドメインに対して既に SPF レコードがある場合は、Microsoft 用に新しいを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-248">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="6cb5d-249">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-249">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="6cb5d-p116">まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-p116">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="6cb5d-253">[ **Domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-253">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="6cb5d-255">[ **DNS zone**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-255">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="6cb5d-257">[**エントリを追加する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-257">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="6cb5d-259">[ **TXT**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-259">Select **TXT**.</span></span>
    
6. <span data-ttu-id="6cb5d-260">新規レコードのボックスに次の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-260">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="6cb5d-261">**レコードの種類**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-261">**Record type**</span></span>|<span data-ttu-id="6cb5d-262">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-262">**Sub-domain**</span></span>|<span data-ttu-id="6cb5d-263">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-263">**TTL**</span></span>|<span data-ttu-id="6cb5d-264">**TXT 値**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-264">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6cb5d-265">TXT</span><span class="sxs-lookup"><span data-stu-id="6cb5d-265">TXT</span></span>  <br/> |<span data-ttu-id="6cb5d-266">(空白のまま)</span><span class="sxs-lookup"><span data-stu-id="6cb5d-266">(leave blank)</span></span>  <br/> |<span data-ttu-id="6cb5d-267">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="6cb5d-267">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="6cb5d-268">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="6cb5d-268">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="6cb5d-269">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![[詳細] SPF の TXT レコードを追加する](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="6cb5d-271">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-271">Select **Next**.</span></span>
    
    ![[追加] SPF の TXT レコードを追加し、[次へ] を選択します。](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="6cb5d-273">[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-273">Select **Confirm**.</span></span>
    
    ![OVH Add TXT record for SPF and Confirm](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="6cb5d-275">Microsoft に必要な2つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="6cb5d-275">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="6cb5d-276"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="6cb5d-276"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="6cb5d-p117">まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-p117">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="6cb5d-280">[ **Domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-280">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="6cb5d-282">[ **DNS zone**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-282">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="6cb5d-284">[**エントリを追加する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-284">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="6cb5d-286">[ **SRV**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-286">Select **SRV**.</span></span>
    
    ![OVH select SRV record type](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="6cb5d-288">1 番目の SRV レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-288">Create the first SRV record.</span></span>
    
    <span data-ttu-id="6cb5d-289">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-289">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="6cb5d-290">TTL 値を割り当てるには、ドロップダウンリストから [**個人用**] を選択し、テキストボックスに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-290">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="6cb5d-291">**Record type**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-291">**Record type**</span></span>|<span data-ttu-id="6cb5d-292">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-292">**Sub-domain**</span></span>|<span data-ttu-id="6cb5d-293">**Priority**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-293">**Priority**</span></span>|<span data-ttu-id="6cb5d-294">**Weight**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-294">**Weight**</span></span>|<span data-ttu-id="6cb5d-295">**Port**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-295">**Port**</span></span>|<span data-ttu-id="6cb5d-296">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-296">**TTL**</span></span>|<span data-ttu-id="6cb5d-297">**ターゲット**</span><span class="sxs-lookup"><span data-stu-id="6cb5d-297">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6cb5d-298">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="6cb5d-298">SRV (Service)</span></span>  <br/> |<span data-ttu-id="6cb5d-299">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="6cb5d-299">_sip._tls</span></span>  <br/> |<span data-ttu-id="6cb5d-300">100</span><span class="sxs-lookup"><span data-stu-id="6cb5d-300">100</span></span>  <br/> |<span data-ttu-id="6cb5d-301">1-d</span><span class="sxs-lookup"><span data-stu-id="6cb5d-301">1</span></span>  <br/> |<span data-ttu-id="6cb5d-302">443</span><span class="sxs-lookup"><span data-stu-id="6cb5d-302">443</span></span>  <br/> |<span data-ttu-id="6cb5d-303">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="6cb5d-303">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="6cb5d-304">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-304">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="6cb5d-305">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="6cb5d-305">SRV (Service)</span></span>  <br/> |<span data-ttu-id="6cb5d-306">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="6cb5d-306">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="6cb5d-307">100</span><span class="sxs-lookup"><span data-stu-id="6cb5d-307">100</span></span>  <br/> |<span data-ttu-id="6cb5d-308">1-d</span><span class="sxs-lookup"><span data-stu-id="6cb5d-308">1</span></span>  <br/> |<span data-ttu-id="6cb5d-309">5061</span><span class="sxs-lookup"><span data-stu-id="6cb5d-309">5061</span></span>  <br/> |<span data-ttu-id="6cb5d-310">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="6cb5d-310">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="6cb5d-311">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-311">sipfed.online.lync.com.</span></span>  <br/> |
       
    !["はい" SRV レコード](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="6cb5d-313">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-313">Select **Next**.</span></span>
    
    ![OVH SRV record select Next](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="6cb5d-315">[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-315">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="6cb5d-p119">上記の手順を繰り返し、他の SRV レコードを作成します。2 番目のレコードのボックスに、上の表の 2 行目の値を入力するかコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-p119">Repeat the previous steps to create the other SRV record. Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="6cb5d-p120">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cb5d-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
