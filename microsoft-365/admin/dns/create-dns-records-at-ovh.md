---
title: OVH for Office 365 で DNS レコードを作成する
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: ドメインを確認し、電子メール、Skype for Business Online、および Office 365 用のその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 4857addd7dfd096c1ddd6e59f1f17ace76b75a9e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42354348"
---
# <a name="create-dns-records-at-ovh-for-office-365"></a><span data-ttu-id="c4bdd-103">OVH for Office 365 で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="c4bdd-103">Create DNS records at OVH for Office 365</span></span>

<span data-ttu-id="c4bdd-104">探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)してください。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c4bdd-105">使用している DNS ホスティング プロバイダーが OVH の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="c4bdd-106">追加する主なレコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="c4bdd-107">Office 365 用の「Office の DNS レコードを作成する」</span><span class="sxs-lookup"><span data-stu-id="c4bdd-107">Create DNS records at OVH for Office 365</span></span>](#create-dns-records-at-ovh-for-office-365)
    
- [<span data-ttu-id="c4bdd-108">MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする</span><span class="sxs-lookup"><span data-stu-id="c4bdd-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="c4bdd-109">Office 365 に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c4bdd-109">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="c4bdd-110">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c4bdd-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="c4bdd-111">Office 365 に必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c4bdd-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="c4bdd-112">OVH でこれらのレコードを追加すると、ドメインは Office 365 サービスと連携するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-112">After you add these records at OVH, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="c4bdd-113">Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="c4bdd-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c4bdd-117">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c4bdd-117">Add a TXT record for verification</span></span>
<span data-ttu-id="c4bdd-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="c4bdd-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="c4bdd-p102">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c4bdd-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="c4bdd-p104">まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-p104">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="c4bdd-126">[ **Domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-126">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="c4bdd-128">[ **DNS zone**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-128">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="c4bdd-130">[**エントリを追加する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-130">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="c4bdd-132">**TXT**の選択</span><span class="sxs-lookup"><span data-stu-id="c4bdd-132">Select **TXT**</span></span>
    
    ![[すべて選択] TXT エントリ](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="c4bdd-134">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-134">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="c4bdd-135">TTL 値を割り当てるには、ドロップダウンリストから [**個人用**] を選択し、テキストボックスに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-135">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="c4bdd-136">**Record type**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-136">**Record type**</span></span>|<span data-ttu-id="c4bdd-137">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-137">**Sub-domain**</span></span>|<span data-ttu-id="c4bdd-138">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-138">**TTL**</span></span>|<span data-ttu-id="c4bdd-139">**値**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-139">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c4bdd-140">TXT</span><span class="sxs-lookup"><span data-stu-id="c4bdd-140">TXT</span></span>  <br/> |<span data-ttu-id="c4bdd-141">(空白のまま)</span><span class="sxs-lookup"><span data-stu-id="c4bdd-141">(leave blank)</span></span>  <br/> |<span data-ttu-id="c4bdd-142">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="c4bdd-142">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="c4bdd-143">MS=msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="c4bdd-143">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="c4bdd-p106">**注:** これは例です。Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。           [情報の取得方法](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="c4bdd-p106">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
7. <span data-ttu-id="c4bdd-147">[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-147">Select **Confirm**.</span></span> 
    
    ![OVH confirm TXT for verification](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="c4bdd-149">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-149">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c4bdd-150">これで、ドメイン レジストラーのサイトでレコードが追加されました。Office 365 に戻り、Office 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-150">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="c4bdd-151">Office 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-151">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c4bdd-152">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-152">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="c4bdd-153">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-153">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="c4bdd-154">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-154">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="c4bdd-155">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-155">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="c4bdd-p107">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="c4bdd-159">MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする</span><span class="sxs-lookup"><span data-stu-id="c4bdd-159">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="c4bdd-160"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="c4bdd-160"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="c4bdd-p108">まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-p108">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="c4bdd-164">[ **Domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-164">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="c4bdd-166">[ **DNS zone**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-166">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="c4bdd-168">[**エントリを追加する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-168">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="c4bdd-170">[ **MX**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-170">Select **MX**.</span></span>
    
    ![OVH MX record type](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="c4bdd-172">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-172">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="c4bdd-173">TTL 値を割り当てるには、ドロップダウンリストから [**個人用**] を選択し、テキストボックスに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-173">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c4bdd-174">既定では、移動先の相対表記を使用します。これにより、ターゲットレコードの末尾にドメイン名が追加されます。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-174">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="c4bdd-175">絶対表記を代わりに使用するには、次の表に示すように、ターゲット レコードにドットを追加します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-175">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="c4bdd-176">**Record type**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-176">**Record type**</span></span>|<span data-ttu-id="c4bdd-177">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-177">**Sub-domain**</span></span>|<span data-ttu-id="c4bdd-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-178">**TTL**</span></span>|<span data-ttu-id="c4bdd-179">**優先度**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-179">**Priority**</span></span>|<span data-ttu-id="c4bdd-180">**Target**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-180">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c4bdd-181">MX</span><span class="sxs-lookup"><span data-stu-id="c4bdd-181">MX</span></span>  <br/> |<span data-ttu-id="c4bdd-182">(空白のまま)</span><span class="sxs-lookup"><span data-stu-id="c4bdd-182">(leave blank)</span></span>  <br/> |<span data-ttu-id="c4bdd-183">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="c4bdd-183">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="c4bdd-184">10 </span><span class="sxs-lookup"><span data-stu-id="c4bdd-184">10</span></span>  <br/> <span data-ttu-id="c4bdd-185">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="c4bdd-186">\<domain-key\>.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="c4bdd-186">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="c4bdd-187">**注:** Office 365 アカウントから\* \<ドメイン\>キー\*を取得します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-187">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="c4bdd-188">確認する方法</span><span class="sxs-lookup"><span data-stu-id="c4bdd-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![メールの "差し込み" MX レコード](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="c4bdd-190">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-190">Select **Next**.</span></span>
    
    ![OVH MX record select Next](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="c4bdd-192">[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-192">Select **Confirm**.</span></span>
    
    ![OVH MX record select Confirm](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="c4bdd-194">MX レコードが他にもある場合は、[ **DNS zone** ] ページですべて削除します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-194">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="c4bdd-195">各レコードを選択し、[**アクション**] 列で [ごみ箱-**削除**可能] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-195">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH delete MX record](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="c4bdd-197">[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-197">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="c4bdd-198">Office 365 に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c4bdd-198">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="c4bdd-199"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="c4bdd-199"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="c4bdd-p113">まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-p113">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="c4bdd-203">[ **Domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-203">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="c4bdd-205">[ **DNS zone**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-205">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="c4bdd-207">[**エントリを追加する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-207">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="c4bdd-209">[ **CNAME**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-209">Select **CNAME**.</span></span>
    
    ![OVH add CNAME record type](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="c4bdd-211">1 番目の CNAME レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-211">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="c4bdd-212">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-212">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="c4bdd-213">TTL 値を割り当てるには、ドロップダウンリストから [**個人用**] を選択し、テキストボックスに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-213">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="c4bdd-214">**Record type**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-214">**Record type**</span></span>|<span data-ttu-id="c4bdd-215">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-215">**Sub-domain**</span></span>|<span data-ttu-id="c4bdd-216">**ターゲット**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-216">**Target**</span></span>|<span data-ttu-id="c4bdd-217">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-217">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c4bdd-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="c4bdd-218">CNAME</span></span>  <br/> |<span data-ttu-id="c4bdd-219">autodiscover</span><span class="sxs-lookup"><span data-stu-id="c4bdd-219">autodiscover</span></span>  <br/> |<span data-ttu-id="c4bdd-220">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-220">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="c4bdd-221">3,600 秒</span><span class="sxs-lookup"><span data-stu-id="c4bdd-221">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="c4bdd-222">CNAME</span><span class="sxs-lookup"><span data-stu-id="c4bdd-222">CNAME</span></span>  <br/> |<span data-ttu-id="c4bdd-223">sip</span><span class="sxs-lookup"><span data-stu-id="c4bdd-223">sip</span></span>  <br/> |<span data-ttu-id="c4bdd-224">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-224">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="c4bdd-225">3,600 秒</span><span class="sxs-lookup"><span data-stu-id="c4bdd-225">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="c4bdd-226">CNAME</span><span class="sxs-lookup"><span data-stu-id="c4bdd-226">CNAME</span></span>  <br/> |<span data-ttu-id="c4bdd-227">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c4bdd-227">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c4bdd-228">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-228">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="c4bdd-229">3,600 秒</span><span class="sxs-lookup"><span data-stu-id="c4bdd-229">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="c4bdd-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="c4bdd-230">CNAME</span></span>  <br/> |<span data-ttu-id="c4bdd-231">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c4bdd-231">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c4bdd-232">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-232">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="c4bdd-233">3,600 秒</span><span class="sxs-lookup"><span data-stu-id="c4bdd-233">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="c4bdd-234">CNAME</span><span class="sxs-lookup"><span data-stu-id="c4bdd-234">CNAME</span></span>  <br/> |<span data-ttu-id="c4bdd-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c4bdd-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c4bdd-236">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-236">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="c4bdd-237">3,600 秒</span><span class="sxs-lookup"><span data-stu-id="c4bdd-237">3600 seconds</span></span>  <br/> |
   
    !["はい" CNAME レコード](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="c4bdd-239">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-239">Select **Next**.</span></span>
    
    ![OVH Add CNAME values and select Next](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="c4bdd-241">[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-241">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="c4bdd-242">前の手順を繰り返し、他の 5 つの CNAME レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-242">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="c4bdd-243">レコードごとに、上のテーブルの次の行の値をそのレコードのボックスに入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-243">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c4bdd-244">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c4bdd-244">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="c4bdd-245"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="c4bdd-245"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4bdd-246">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-246">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="c4bdd-247">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="c4bdd-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="c4bdd-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="c4bdd-249">代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-249">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="c4bdd-p116">まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-p116">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="c4bdd-253">[ **Domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-253">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="c4bdd-255">[ **DNS zone**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-255">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="c4bdd-257">[**エントリを追加する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-257">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="c4bdd-259">[ **TXT**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-259">Select **TXT**.</span></span>
    
6. <span data-ttu-id="c4bdd-260">新規レコードのボックスに次の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-260">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="c4bdd-261">**レコードの種類**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-261">**Record type**</span></span>|<span data-ttu-id="c4bdd-262">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-262">**Sub-domain**</span></span>|<span data-ttu-id="c4bdd-263">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-263">**TTL**</span></span>|<span data-ttu-id="c4bdd-264">**TXT 値**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-264">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c4bdd-265">TXT</span><span class="sxs-lookup"><span data-stu-id="c4bdd-265">TXT</span></span>  <br/> |<span data-ttu-id="c4bdd-266">(空白のまま)</span><span class="sxs-lookup"><span data-stu-id="c4bdd-266">(leave blank)</span></span>  <br/> |<span data-ttu-id="c4bdd-267">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="c4bdd-267">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="c4bdd-268">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c4bdd-268">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="c4bdd-269">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![[詳細] SPF の TXT レコードを追加する](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="c4bdd-271">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-271">Select **Next**.</span></span>
    
    ![[追加] SPF の TXT レコードを追加し、[次へ] を選択します。](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="c4bdd-273">[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-273">Select **Confirm**.</span></span>
    
    ![OVH Add TXT record for SPF and Confirm](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="c4bdd-275">Office 365 に必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c4bdd-275">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="c4bdd-276"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="c4bdd-276"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="c4bdd-p117">まず、[このリンク](https://www.ovh.com/manager/)を使って OVH でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-p117">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="c4bdd-280">[ **Domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-280">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="c4bdd-282">[ **DNS zone**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-282">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="c4bdd-284">[**エントリを追加する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-284">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="c4bdd-286">[ **SRV**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-286">Select **SRV**.</span></span>
    
    ![OVH select SRV record type](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="c4bdd-288">1 番目の SRV レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-288">Create the first SRV record.</span></span>
    
    <span data-ttu-id="c4bdd-289">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-289">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="c4bdd-290">TTL 値を割り当てるには、ドロップダウンリストから [**個人用**] を選択し、テキストボックスに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-290">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="c4bdd-291">**Record type**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-291">**Record type**</span></span>|<span data-ttu-id="c4bdd-292">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-292">**Sub-domain**</span></span>|<span data-ttu-id="c4bdd-293">**Priority**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-293">**Priority**</span></span>|<span data-ttu-id="c4bdd-294">**Weight**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-294">**Weight**</span></span>|<span data-ttu-id="c4bdd-295">**Port**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-295">**Port**</span></span>|<span data-ttu-id="c4bdd-296">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-296">**TTL**</span></span>|<span data-ttu-id="c4bdd-297">**ターゲット**</span><span class="sxs-lookup"><span data-stu-id="c4bdd-297">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c4bdd-298">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="c4bdd-298">SRV (Service)</span></span>  <br/> |<span data-ttu-id="c4bdd-299">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="c4bdd-299">_sip._tls</span></span>  <br/> |<span data-ttu-id="c4bdd-300">100</span><span class="sxs-lookup"><span data-stu-id="c4bdd-300">100</span></span>  <br/> |<span data-ttu-id="c4bdd-301">1-d</span><span class="sxs-lookup"><span data-stu-id="c4bdd-301">1</span></span>  <br/> |<span data-ttu-id="c4bdd-302">443</span><span class="sxs-lookup"><span data-stu-id="c4bdd-302">443</span></span>  <br/> |<span data-ttu-id="c4bdd-303">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="c4bdd-303">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="c4bdd-304">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-304">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="c4bdd-305">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="c4bdd-305">SRV (Service)</span></span>  <br/> |<span data-ttu-id="c4bdd-306">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="c4bdd-306">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="c4bdd-307">100</span><span class="sxs-lookup"><span data-stu-id="c4bdd-307">100</span></span>  <br/> |<span data-ttu-id="c4bdd-308">1-d</span><span class="sxs-lookup"><span data-stu-id="c4bdd-308">1</span></span>  <br/> |<span data-ttu-id="c4bdd-309">5061</span><span class="sxs-lookup"><span data-stu-id="c4bdd-309">5061</span></span>  <br/> |<span data-ttu-id="c4bdd-310">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="c4bdd-310">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="c4bdd-311">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-311">sipfed.online.lync.com.</span></span>  <br/> |
       
    !["はい" SRV レコード](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="c4bdd-313">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-313">Select **Next**.</span></span>
    
    ![OVH SRV record select Next](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="c4bdd-315">[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-315">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="c4bdd-p119">上記の手順を繰り返し、他の SRV レコードを作成します。2 番目のレコードのボックスに、上の表の 2 行目の値を入力するかコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-p119">Repeat the previous steps to create the other SRV record. Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="c4bdd-p120">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4bdd-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
