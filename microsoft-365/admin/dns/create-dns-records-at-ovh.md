---
title: OVH for Microsoft で DNS レコードを作成する
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: OVH for Microsoft でドメインを確認し、メール、Skype for Business Online、その他のサービスの DNS レコードをセットアップする方法について説明します。
ms.openlocfilehash: 14c3796ff6686ae0d98ec32ec6ddf6afc004a3c3
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657781"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a><span data-ttu-id="bdc4c-103">OVH for Microsoft で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="bdc4c-103">Create DNS records at OVH for Microsoft</span></span>

<span data-ttu-id="bdc4c-104">探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.yml)してください。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-104">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="bdc4c-105">使用している DNS ホスティング プロバイダーが OVH の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="bdc4c-106">追加する主なレコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="bdc4c-107">OVH for Microsoft で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="bdc4c-107">Create DNS records at OVH for Microsoft</span></span>](#create-dns-records-at-ovh-for-microsoft)
    
- [<span data-ttu-id="bdc4c-108">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="bdc4c-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="bdc4c-109">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="bdc4c-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="bdc4c-110">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="bdc4c-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="bdc4c-111">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="bdc4c-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="bdc4c-112">OVH でこれらのレコードを追加すると、ドメインは Microsoft サービスで動作する設定に設定されます。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-112">After you add these records at OVH, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="bdc4c-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="bdc4c-116">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="bdc4c-116">Add a TXT record for verification</span></span>
<span data-ttu-id="bdc4c-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="bdc4c-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="bdc4c-p102">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bdc4c-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="bdc4c-p104">まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-p104">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="bdc4c-125">**[Domains]** で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-125">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="bdc4c-127">**DNS ゾーンを選択します**。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-127">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="bdc4c-129">[エントリ **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-129">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="bdc4c-131">SELECT **TXT**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-131">Select **TXT**</span></span>
    
    ![OVH select TXT entry](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="bdc4c-133">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-133">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="bdc4c-134">TTL 値を割り当てるには、ドロップダウン リストから **[カスタマイズ** ] を選択し、テキスト ボックスに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-134">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="bdc4c-135">**Record type**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-135">**Record type**</span></span>|<span data-ttu-id="bdc4c-136">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-136">**Sub-domain**</span></span>|<span data-ttu-id="bdc4c-137">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-137">**TTL**</span></span>|<span data-ttu-id="bdc4c-138">**値**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-138">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="bdc4c-139">TXT</span><span class="sxs-lookup"><span data-stu-id="bdc4c-139">TXT</span></span>  <br/> |<span data-ttu-id="bdc4c-140">(空白のまま)</span><span class="sxs-lookup"><span data-stu-id="bdc4c-140">(leave blank)</span></span>  <br/> |<span data-ttu-id="bdc4c-141">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="bdc4c-141">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="bdc4c-142">MS=msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="bdc4c-142">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="bdc4c-143">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-143">**Note:** This is an example.</span></span> <span data-ttu-id="bdc4c-144">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="bdc4c-145">確認する方法</span><span class="sxs-lookup"><span data-stu-id="bdc4c-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="bdc4c-146">**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-146">Select **Confirm**.</span></span> 
    
    ![OVH confirm TXT for verification](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="bdc4c-148">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-148">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="bdc4c-149">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-149">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="bdc4c-150">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-150">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="bdc4c-151">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="bdc4c-152">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="bdc4c-153">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="bdc4c-154">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="bdc4c-p107">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="bdc4c-158">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="bdc4c-158">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="bdc4c-159"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="bdc4c-159"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="bdc4c-p108">まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-p108">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="bdc4c-163">**[Domains]** で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-163">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="bdc4c-165">**DNS ゾーンを選択します**。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-165">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="bdc4c-167">[エントリ **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-167">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="bdc4c-169">**[MX] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-169">Select **MX**.</span></span>
    
    ![OVH MX record type](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="bdc4c-171">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-171">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="bdc4c-172">TTL 値を割り当てるには、ドロップダウン リストから **[カスタマイズ** ] を選択し、テキスト ボックスに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-172">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="bdc4c-173">既定では、OVH はターゲットに相対表記を使用し、ターゲット レコードの末尾にドメイン名を追加します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-173">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="bdc4c-174">絶対表記を代わりに使用するには、次の表に示すように、ターゲット レコードにドットを追加します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-174">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="bdc4c-175">**Record type**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-175">**Record type**</span></span>|<span data-ttu-id="bdc4c-176">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-176">**Sub-domain**</span></span>|<span data-ttu-id="bdc4c-177">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-177">**TTL**</span></span>|<span data-ttu-id="bdc4c-178">**優先度**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-178">**Priority**</span></span>|<span data-ttu-id="bdc4c-179">**ターゲット**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-179">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="bdc4c-180">MX</span><span class="sxs-lookup"><span data-stu-id="bdc4c-180">MX</span></span>  <br/> |<span data-ttu-id="bdc4c-181">(空白のまま)</span><span class="sxs-lookup"><span data-stu-id="bdc4c-181">(leave blank)</span></span>  <br/> |<span data-ttu-id="bdc4c-182">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="bdc4c-182">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="bdc4c-183">10 </span><span class="sxs-lookup"><span data-stu-id="bdc4c-183">10</span></span>  <br/> <span data-ttu-id="bdc4c-184">優先度の詳細については、「[MX 優先度とは何か](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-184">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="bdc4c-185">\<domain-key\>.mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-185">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="bdc4c-186">**注:** Microsoft アカウント  *\<domain-key\>*  からユーザーを取得します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-186">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="bdc4c-187">確認する方法</span><span class="sxs-lookup"><span data-stu-id="bdc4c-187">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![OVH MX record for mail](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="bdc4c-189">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-189">Select **Next**.</span></span>
    
    ![OVH MX record select Next](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="bdc4c-191">**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-191">Select **Confirm**.</span></span>
    
    ![OVH MX record select Confirm](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="bdc4c-193">MX レコードが他にもある場合は、[ **DNS zone** ] ページですべて削除します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-193">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="bdc4c-194">各レコードを選択し、[Actions]列でごみ箱の [削除] アイコンを **選択** します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-194">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH delete MX record](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="bdc4c-196">**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-196">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="bdc4c-197">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="bdc4c-197">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="bdc4c-198"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="bdc4c-198"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="bdc4c-p113">まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-p113">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="bdc4c-202">**[Domains]** で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-202">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="bdc4c-204">**DNS ゾーンを選択します**。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-204">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="bdc4c-206">[エントリ **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-206">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="bdc4c-208">CNAME **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-208">Select **CNAME**.</span></span>
    
    ![OVH add CNAME record type](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="bdc4c-210">1 番目の CNAME レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-210">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="bdc4c-211">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-211">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="bdc4c-212">TTL 値を割り当てるには、ドロップダウン リストから **[カスタマイズ** ] を選択し、テキスト ボックスに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-212">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="bdc4c-213">**Record type**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-213">**Record type**</span></span>|<span data-ttu-id="bdc4c-214">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-214">**Sub-domain**</span></span>|<span data-ttu-id="bdc4c-215">**ターゲット**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-215">**Target**</span></span>|<span data-ttu-id="bdc4c-216">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-216">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="bdc4c-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="bdc4c-217">CNAME</span></span>  <br/> |<span data-ttu-id="bdc4c-218">autodiscover</span><span class="sxs-lookup"><span data-stu-id="bdc4c-218">autodiscover</span></span>  <br/> |<span data-ttu-id="bdc4c-219">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="bdc4c-219">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="bdc4c-220">3,600 秒</span><span class="sxs-lookup"><span data-stu-id="bdc4c-220">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="bdc4c-221">CNAME</span><span class="sxs-lookup"><span data-stu-id="bdc4c-221">CNAME</span></span>  <br/> |<span data-ttu-id="bdc4c-222">sip</span><span class="sxs-lookup"><span data-stu-id="bdc4c-222">sip</span></span>  <br/> |<span data-ttu-id="bdc4c-223">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="bdc4c-223">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="bdc4c-224">3,600 秒</span><span class="sxs-lookup"><span data-stu-id="bdc4c-224">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="bdc4c-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="bdc4c-225">CNAME</span></span>  <br/> |<span data-ttu-id="bdc4c-226">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="bdc4c-226">lyncdiscover</span></span>  <br/> |<span data-ttu-id="bdc4c-227">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="bdc4c-227">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="bdc4c-228">3,600 秒</span><span class="sxs-lookup"><span data-stu-id="bdc4c-228">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="bdc4c-229">CNAME</span><span class="sxs-lookup"><span data-stu-id="bdc4c-229">CNAME</span></span>  <br/> |<span data-ttu-id="bdc4c-230">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="bdc4c-230">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="bdc4c-231">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="bdc4c-231">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="bdc4c-232">3,600 秒</span><span class="sxs-lookup"><span data-stu-id="bdc4c-232">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="bdc4c-233">CNAME</span><span class="sxs-lookup"><span data-stu-id="bdc4c-233">CNAME</span></span>  <br/> |<span data-ttu-id="bdc4c-234">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="bdc4c-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="bdc4c-235">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="bdc4c-235">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="bdc4c-236">3,600 秒</span><span class="sxs-lookup"><span data-stu-id="bdc4c-236">3600 seconds</span></span>  <br/> |
   
    ![OVH CNAME record](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="bdc4c-238">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-238">Select **Next**.</span></span>
    
    ![OVH Add CNAME values and select Next](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="bdc4c-240">**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-240">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="bdc4c-241">前の手順を繰り返し、他の 5 つの CNAME レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-241">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="bdc4c-242">レコードごとに、上のテーブルの次の行の値をそのレコードのボックスに入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-242">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="bdc4c-243">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="bdc4c-243">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="bdc4c-244"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="bdc4c-244"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="bdc4c-245">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-245">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="bdc4c-246">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-246">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="bdc4c-247">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-247">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="bdc4c-248">代わりに、必要な Microsoft の値を現在のレコードに追加して、両方の値のセットを含む  *1*  つの SPF レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-248">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="bdc4c-p116">まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-p116">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="bdc4c-252">**[Domains]** で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-252">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="bdc4c-254">**DNS ゾーンを選択します**。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-254">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="bdc4c-256">[エントリ **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-256">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="bdc4c-258">SELECT **TXT**.</span><span class="sxs-lookup"><span data-stu-id="bdc4c-258">Select **TXT**.</span></span>
    
6. <span data-ttu-id="bdc4c-259">新規レコードのボックスに次の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-259">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="bdc4c-260">**レコードの種類**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-260">**Record type**</span></span>|<span data-ttu-id="bdc4c-261">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-261">**Sub-domain**</span></span>|<span data-ttu-id="bdc4c-262">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-262">**TTL**</span></span>|<span data-ttu-id="bdc4c-263">**TXT 値**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-263">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="bdc4c-264">TXT</span><span class="sxs-lookup"><span data-stu-id="bdc4c-264">TXT</span></span>  <br/> |<span data-ttu-id="bdc4c-265">(空白のまま)</span><span class="sxs-lookup"><span data-stu-id="bdc4c-265">(leave blank)</span></span>  <br/> |<span data-ttu-id="bdc4c-266">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="bdc4c-266">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="bdc4c-267">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="bdc4c-267">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="bdc4c-268">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH Add TXT record for SPF](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="bdc4c-270">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-270">Select **Next**.</span></span>
    
    ![OVH Add TXT record for SPF and select Next](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="bdc4c-272">**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-272">Select **Confirm**.</span></span>
    
    ![OVH Add TXT record for SPF and Confirm](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="bdc4c-274">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="bdc4c-274">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="bdc4c-275"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="bdc4c-275"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="bdc4c-p117">まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-p117">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="bdc4c-279">**[Domains]** で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-279">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="bdc4c-281">**DNS ゾーンを選択します**。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-281">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="bdc4c-283">[エントリ **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-283">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="bdc4c-285">**[SRV] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-285">Select **SRV**.</span></span>
    
    ![OVH select SRV record type](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="bdc4c-287">1 番目の SRV レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-287">Create the first SRV record.</span></span>
    
    <span data-ttu-id="bdc4c-288">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-288">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="bdc4c-289">TTL 値を割り当てるには、ドロップダウン リストから **[カスタマイズ** ] を選択し、テキスト ボックスに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-289">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="bdc4c-290">**Record type**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-290">**Record type**</span></span>|<span data-ttu-id="bdc4c-291">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-291">**Sub-domain**</span></span>|<span data-ttu-id="bdc4c-292">**Priority**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-292">**Priority**</span></span>|<span data-ttu-id="bdc4c-293">**Weight**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-293">**Weight**</span></span>|<span data-ttu-id="bdc4c-294">**Port**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-294">**Port**</span></span>|<span data-ttu-id="bdc4c-295">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-295">**TTL**</span></span>|<span data-ttu-id="bdc4c-296">**ターゲット**</span><span class="sxs-lookup"><span data-stu-id="bdc4c-296">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="bdc4c-297">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="bdc4c-297">SRV (Service)</span></span>  <br/> |<span data-ttu-id="bdc4c-298">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="bdc4c-298">_sip._tls</span></span>  <br/> |<span data-ttu-id="bdc4c-299">100</span><span class="sxs-lookup"><span data-stu-id="bdc4c-299">100</span></span>  <br/> |<span data-ttu-id="bdc4c-300">1 </span><span class="sxs-lookup"><span data-stu-id="bdc4c-300">1</span></span>  <br/> |<span data-ttu-id="bdc4c-301">443</span><span class="sxs-lookup"><span data-stu-id="bdc4c-301">443</span></span>  <br/> |<span data-ttu-id="bdc4c-302">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="bdc4c-302">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="bdc4c-303">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="bdc4c-303">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="bdc4c-304">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="bdc4c-304">SRV (Service)</span></span>  <br/> |<span data-ttu-id="bdc4c-305">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="bdc4c-305">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="bdc4c-306">100</span><span class="sxs-lookup"><span data-stu-id="bdc4c-306">100</span></span>  <br/> |<span data-ttu-id="bdc4c-307">1 </span><span class="sxs-lookup"><span data-stu-id="bdc4c-307">1</span></span>  <br/> |<span data-ttu-id="bdc4c-308">5061</span><span class="sxs-lookup"><span data-stu-id="bdc4c-308">5061</span></span>  <br/> |<span data-ttu-id="bdc4c-309">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="bdc4c-309">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="bdc4c-310">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-310">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![OVH SRV レコード](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="bdc4c-312">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-312">Select **Next**.</span></span>
    
    ![OVH SRV record select Next](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="bdc4c-314">**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-314">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="bdc4c-p119">上記の手順を繰り返し、他の SRV レコードを作成します。2 番目のレコードのボックスに、上の表の 2 行目の値を入力するかコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-p119">Repeat the previous steps to create the other SRV record. Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="bdc4c-p120">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdc4c-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
