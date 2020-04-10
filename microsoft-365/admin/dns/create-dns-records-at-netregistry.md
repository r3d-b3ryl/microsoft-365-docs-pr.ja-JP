---
title: Office 365 の Netregistry で DNS レコードを作成する
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: ドメインを確認し、電子メール、Skype for Business Online、および Netregistry for Office 365 の他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: e1f2414817357b8435bc002860a35c6e76d4314e
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211136"
---
# <a name="create-dns-records-at-netregistry-for-office-365"></a><span data-ttu-id="fc9e7-103">Office 365 の Netregistry で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="fc9e7-103">Create DNS records at Netregistry for Office 365</span></span>

<span data-ttu-id="fc9e7-104">探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)してください。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="fc9e7-105">使用している DNS ホスティング プロバイダーが Netregistry の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-105">If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="fc9e7-106">追加する主なレコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-106">These are the main records to add.</span></span>
  
- [<span data-ttu-id="fc9e7-107">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="fc9e7-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="fc9e7-108">MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする</span><span class="sxs-lookup"><span data-stu-id="fc9e7-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)

- [<span data-ttu-id="fc9e7-109">Office 365 に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="fc9e7-109">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="fc9e7-110">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="fc9e7-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="fc9e7-111">Office 365 に必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="fc9e7-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="fc9e7-112">これらのレコードを Netregistry で追加すると、使用しているドメインが、Office 365 サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-112">After you add these records at Netregistry, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="fc9e7-113">Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="fc9e7-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="fc9e7-117">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="fc9e7-117">Add a TXT record for verification</span></span>
<span data-ttu-id="fc9e7-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="fc9e7-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="fc9e7-p102">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fc9e7-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="fc9e7-p104">まず、[こちらのリンク](https://theconsole.netregistry.com.au/)を使って、Netregistry のドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-p104">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. <span data-ttu-id="fc9e7-126">管理するドメインの横にある、[ **Manage** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-126">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. <span data-ttu-id="fc9e7-128">[ **Zone Manager** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-128">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. <span data-ttu-id="fc9e7-130">[ **Add a zone record**] の一覧から [ **TXT record** ] を選択し、[**新しいレコードの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-130">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > <span data-ttu-id="fc9e7-132">TXT ボックスでは、エントリの前後に引用符を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-132">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    <span data-ttu-id="fc9e7-133">[ **New TXT Record** ] フォームに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-133">In the **New TXT Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="fc9e7-134">**名前**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-134">**Name**</span></span>|<span data-ttu-id="fc9e7-135">**TTL (秒)**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-135">**TTL (SEC)**</span></span>|<span data-ttu-id="fc9e7-136">**TXT (ポイント先のアドレスまたは値)**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-136">**TXT (Points to address or value)**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="fc9e7-137">(空白のまま)</span><span class="sxs-lookup"><span data-stu-id="fc9e7-137">(leave blank)</span></span>  <br/> |<span data-ttu-id="fc9e7-138">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="fc9e7-138">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="fc9e7-139">"MS = msXXXXXXXX"</span><span class="sxs-lookup"><span data-stu-id="fc9e7-139">"MS=msXXXXXXXX"</span></span>  <br/> <span data-ttu-id="fc9e7-140">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-140">**Note:** This is an example.</span></span> <span data-ttu-id="fc9e7-141">Office 365 の表から [**宛先またはポイント先のアドレス**] の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-141">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="fc9e7-142">確認する方法</span><span class="sxs-lookup"><span data-stu-id="fc9e7-142">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. <span data-ttu-id="fc9e7-144">[ **Add record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-144">Select **Add record**.</span></span>
    
<span data-ttu-id="fc9e7-145">これで、ドメイン レジストラーのサイトでレコードが追加されました。Office 365 に戻り、Office 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-145">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="fc9e7-146">Office 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-146">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="fc9e7-147">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-147">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="fc9e7-148">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="fc9e7-149">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="fc9e7-150">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="fc9e7-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="fc9e7-154">MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする</span><span class="sxs-lookup"><span data-stu-id="fc9e7-154">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="fc9e7-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="fc9e7-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="fc9e7-p107">まず、[こちらのリンク](https://theconsole.netregistry.com.au/)を使って、Netregistry のドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-p107">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. <span data-ttu-id="fc9e7-159">管理するドメインの横にある、[ **Manage** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-159">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. <span data-ttu-id="fc9e7-161">[ **Zone Manager** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-161">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. <span data-ttu-id="fc9e7-163">[**現在のゾーンレコード**] で、リスト内の各 mx レコードの横にある [**削除**] を選択して、既定の mx レコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-163">Under **Current zone records**, remove the default MX records by selecting **Remove** next to each MX record in the list.</span></span> 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. <span data-ttu-id="fc9e7-165">[ **Add a zone record**] の一覧から [ **MX record** ] を選択し、[**新しいレコードの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-165">Under **Add a zone record**, choose **MX Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. <span data-ttu-id="fc9e7-167">[**新しい MX レコード**] フォームで、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-167">In the **New MX Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="fc9e7-168">**名前**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-168">**Name**</span></span>|<span data-ttu-id="fc9e7-169">**TTL (秒)**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-169">**TTL (SEC)**</span></span>|<span data-ttu-id="fc9e7-170">**Exchange (ポイント先アドレスまたは値)**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-170">**Exchange (Points to address or value)**</span></span>|<span data-ttu-id="fc9e7-171">**ホストは完全に修飾されていますか?**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-171">**Is host fully qualified?**</span></span>|<span data-ttu-id="fc9e7-172">**優先順位 (優先度)**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-172">**Preference (Priority)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="fc9e7-173">(空白のまま)</span><span class="sxs-lookup"><span data-stu-id="fc9e7-173">(leave blank)</span></span>  <br/> |<span data-ttu-id="fc9e7-174">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="fc9e7-174">3600 (seconds)</span></span>  <br/> | <span data-ttu-id="fc9e7-175">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="fc9e7-175">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="fc9e7-176">**注:** Office 365 アカウントから\* \<ドメイン\>キー\*を取得します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-176">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="fc9e7-177">確認する方法</span><span class="sxs-lookup"><span data-stu-id="fc9e7-177">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      |<span data-ttu-id="fc9e7-178">(チェックボックスをオンにします)</span><span class="sxs-lookup"><span data-stu-id="fc9e7-178">(select the checkbox)</span></span>  <br/> |<span data-ttu-id="fc9e7-179">10 </span><span class="sxs-lookup"><span data-stu-id="fc9e7-179">10</span></span>  <br/> <span data-ttu-id="fc9e7-180">For more information about priority, see What is MX priority?</span><span class="sxs-lookup"><span data-stu-id="fc9e7-180">For more information about priority, see What is MX priority?</span></span>  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. <span data-ttu-id="fc9e7-182">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-182">Select **Add Record**.</span></span>
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="fc9e7-184">Office 365 に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="fc9e7-184">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="fc9e7-185"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="fc9e7-185"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="fc9e7-p109">まず、[こちらのリンク](https://theconsole.netregistry.com.au/)を使って、Netregistry のドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-p109">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. <span data-ttu-id="fc9e7-189">管理するドメインの横にある、[ **Manage** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-189">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. <span data-ttu-id="fc9e7-191">[ **Zone Manager** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-191">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. <span data-ttu-id="fc9e7-193">[ **Add a zone record**] の一覧から [ **CNAME record** ] を選択し、[**新しいレコードの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-193">Under  **Add a zone record**, choose **CNAME Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. <span data-ttu-id="fc9e7-195">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-195">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="fc9e7-196">**名前**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-196">**Name**</span></span>|<span data-ttu-id="fc9e7-197">**Type**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-197">**Type**</span></span>|<span data-ttu-id="fc9e7-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-198">**TTL**</span></span>|<span data-ttu-id="fc9e7-199">**ホスト (ポイントまたはアドレスの値)**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-199">**HOST (Points to or address value)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="fc9e7-200">autodiscover</span><span class="sxs-lookup"><span data-stu-id="fc9e7-200">autodiscover</span></span>  <br/> |<span data-ttu-id="fc9e7-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="fc9e7-201">CNAME</span></span>  <br/> |<span data-ttu-id="fc9e7-202">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="fc9e7-202">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="fc9e7-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="fc9e7-203">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="fc9e7-204">sip</span><span class="sxs-lookup"><span data-stu-id="fc9e7-204">sip</span></span>  <br/> |<span data-ttu-id="fc9e7-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="fc9e7-205">CNAME</span></span>  <br/> |<span data-ttu-id="fc9e7-206">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="fc9e7-206">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="fc9e7-207">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fc9e7-207">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="fc9e7-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="fc9e7-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="fc9e7-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="fc9e7-209">CNAME</span></span>  <br/> |<span data-ttu-id="fc9e7-210">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="fc9e7-210">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="fc9e7-211">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fc9e7-211">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="fc9e7-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="fc9e7-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="fc9e7-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="fc9e7-213">CNAME</span></span>  <br/> |<span data-ttu-id="fc9e7-214">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="fc9e7-214">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="fc9e7-215">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="fc9e7-215">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="fc9e7-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="fc9e7-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="fc9e7-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="fc9e7-217">CNAME</span></span>  <br/> |<span data-ttu-id="fc9e7-218">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="fc9e7-218">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="fc9e7-219">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fc9e7-219">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. <span data-ttu-id="fc9e7-221">[ **Add record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-221">Select **Add record**.</span></span>
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. <span data-ttu-id="fc9e7-223">前の手順を繰り返し、他の 5 つの CNAME レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-223">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="fc9e7-224">レコードごとに、上のテーブルの次の行の値をそのレコードのボックスに入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-224">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="fc9e7-225">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="fc9e7-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="fc9e7-226"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="fc9e7-226"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc9e7-227">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="fc9e7-228">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="fc9e7-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="fc9e7-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="fc9e7-230">代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-230">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="fc9e7-p111">まず、[こちらのリンク](https://theconsole.netregistry.com.au/)を使って、Netregistry のドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-p111">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. <span data-ttu-id="fc9e7-234">管理するドメインの横にある、[ **Manage** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-234">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. <span data-ttu-id="fc9e7-236">[ **Zone Manager** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-236">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. <span data-ttu-id="fc9e7-238">[ **Add a zone record**] の一覧から [ **TXT record** ] を選択し、[**新しいレコードの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-238">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. <span data-ttu-id="fc9e7-240">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-240">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="fc9e7-241">TXT ボックスでは、エントリの前後に引用符を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-241">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    |<span data-ttu-id="fc9e7-242">**名前**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-242">**Name**</span></span>|<span data-ttu-id="fc9e7-243">**Type**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-243">**Type**</span></span>|<span data-ttu-id="fc9e7-244">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-244">**TTL**</span></span>|<span data-ttu-id="fc9e7-245">**TXT データ (ターゲット)**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-245">**TXT Data (Target)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="fc9e7-246">(空白のまま)</span><span class="sxs-lookup"><span data-stu-id="fc9e7-246">(leave blank)</span></span>  <br/> |<span data-ttu-id="fc9e7-247">TXT</span><span class="sxs-lookup"><span data-stu-id="fc9e7-247">TXT</span></span>  <br/> |<span data-ttu-id="fc9e7-248">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="fc9e7-248">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="fc9e7-249">"v = spf1 には、以下のようにします。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-249">"v=spf1 include:spf.protection.outlook.com -all"</span></span>  <br/> <span data-ttu-id="fc9e7-250">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-250">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Netregistry_SPF-TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. <span data-ttu-id="fc9e7-252">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-252">Select **Add Record**.</span></span>
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="fc9e7-254">Office 365 に必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="fc9e7-254">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="fc9e7-255"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="fc9e7-255"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="fc9e7-p112">まず、[こちらのリンク](https://theconsole.netregistry.com.au/)を使って、Netregistry のドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-p112">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. <span data-ttu-id="fc9e7-259">管理するドメインの横にある [ **manage**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-259">Next to the domain you want to manage, select  **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. <span data-ttu-id="fc9e7-261">[ **Zone Manager** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-261">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. <span data-ttu-id="fc9e7-263">[ **Add a zone record**] の一覧から [ **SRV record** ] を選択し、[**新しいレコードの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-263">Under  **Add a zone record**, choose **SRV Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. <span data-ttu-id="fc9e7-265">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-265">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fc9e7-266">[名前] フィールドは、サービス (たとえば、_sip) とプロトコル (たとえば、_tls) の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-266">The Name field is a combination of the service (for example, _sip) and protocol (for example, _tls).</span></span> 
  
    |<span data-ttu-id="fc9e7-267">**Type**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-267">**Type**</span></span>|<span data-ttu-id="fc9e7-268">**名前**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-268">**Name**</span></span>|<span data-ttu-id="fc9e7-269">**TTL (秒)**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-269">**TTL (SEC)**</span></span>|<span data-ttu-id="fc9e7-270">**Priority**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-270">**Priority**</span></span>|<span data-ttu-id="fc9e7-271">**Weight**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-271">**Weight**</span></span>|<span data-ttu-id="fc9e7-272">**Port**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-272">**Port**</span></span>|<span data-ttu-id="fc9e7-273">**対象**</span><span class="sxs-lookup"><span data-stu-id="fc9e7-273">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="fc9e7-274">SRV (サービス)</span><span class="sxs-lookup"><span data-stu-id="fc9e7-274">SRV (service)</span></span>  <br/> |<span data-ttu-id="fc9e7-275">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="fc9e7-275">_sip._tls</span></span>  <br/> |<span data-ttu-id="fc9e7-276">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="fc9e7-276">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="fc9e7-277">100</span><span class="sxs-lookup"><span data-stu-id="fc9e7-277">100</span></span>  <br/> |<span data-ttu-id="fc9e7-278">1-d</span><span class="sxs-lookup"><span data-stu-id="fc9e7-278">1</span></span>  <br/> |<span data-ttu-id="fc9e7-279">443</span><span class="sxs-lookup"><span data-stu-id="fc9e7-279">443</span></span>  <br/> |<span data-ttu-id="fc9e7-280">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fc9e7-280">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="fc9e7-281">SRV (サービス)</span><span class="sxs-lookup"><span data-stu-id="fc9e7-281">SRV (service)</span></span>  <br/> |<span data-ttu-id="fc9e7-282">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="fc9e7-282">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="fc9e7-283">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="fc9e7-283">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="fc9e7-284">100</span><span class="sxs-lookup"><span data-stu-id="fc9e7-284">100</span></span>  <br/> |<span data-ttu-id="fc9e7-285">1-d</span><span class="sxs-lookup"><span data-stu-id="fc9e7-285">1</span></span>  <br/> |<span data-ttu-id="fc9e7-286">5061</span><span class="sxs-lookup"><span data-stu-id="fc9e7-286">5061</span></span>  <br/> |<span data-ttu-id="fc9e7-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fc9e7-287">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. <span data-ttu-id="fc9e7-289">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-289">Select **Add Record**.</span></span>
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. <span data-ttu-id="fc9e7-291">上記の手順を繰り返し、他の SRV レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-291">Repeat the previous steps to create the other SRV record.</span></span>
    
    <span data-ttu-id="fc9e7-292">2 番目のレコードのボックスに、上の表の 2 行目の値を入力するかコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-292">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fc9e7-p113">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc9e7-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

