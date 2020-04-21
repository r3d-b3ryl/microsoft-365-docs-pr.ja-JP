---
title: Microsoft の GoDaddy で DNS レコードを作成する
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
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: ドメインを確認し、電子メール、Skype for Business Online、および GoDaddy のその他のサービスの DNS レコードを Microsoft 用にセットアップする方法について説明します。
ms.custom: okr_smb
ms.openlocfilehash: 0e9b75bcd4aa93270efd9b2d94fa2ceeb6e55f75
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629553"
---
# <a name="create-dns-records-at-godaddy-for-microsoft"></a><span data-ttu-id="5313c-103">Microsoft の GoDaddy で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="5313c-103">Create DNS records at GoDaddy for Microsoft</span></span>

 <span data-ttu-id="5313c-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="5313c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="5313c-105">使用している DNS ホスティング プロバイダーが GoDaddy の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="5313c-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="5313c-106">これらのレコードを GoDaddy で追加すると、使用しているドメインが、Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="5313c-106">After you add these records at GoDaddy, your domain will be set up to work with Microsoft services.</span></span>

<span data-ttu-id="5313c-107">Microsoft を使用した web サイトのホストと DNS の詳細については、「 [microsoft とのパブリック web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5313c-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>

> [!NOTE]
> <span data-ttu-id="5313c-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5313c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5313c-111">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="5313c-111">Add a TXT record for verification</span></span>
<span data-ttu-id="5313c-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="5313c-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="5313c-113">ドメインを Microsoft で使用する前に、必ずそのドメインを所有していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5313c-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="5313c-114">ドメインレジストラーで自分のアカウントにログインし、DNS レコードを作成することにより、そのドメインを所有していることが Microsoft に証明されます。</span><span class="sxs-lookup"><span data-stu-id="5313c-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="5313c-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="5313c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="5313c-117">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5313c-117">Follow the steps below.</span></span>

1. <span data-ttu-id="5313c-p104">まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="5313c-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="5313c-121">[ **Domains**] の下で、編集するドメインの下の [DNS] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5313c-121">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="5313c-123">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5313c-123">Select **Add**.</span></span>

    ![GoDaddy-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="5313c-125">ドロップダウン リストから [ **TXT (Text)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5313c-125">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="5313c-126">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5313c-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="5313c-127">**Record type**</span><span class="sxs-lookup"><span data-stu-id="5313c-127">**Record type**</span></span> |<span data-ttu-id="5313c-128">**Host**</span><span class="sxs-lookup"><span data-stu-id="5313c-128">**Host**</span></span>|<span data-ttu-id="5313c-129">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="5313c-129">**TXT Value**</span></span>|<span data-ttu-id="5313c-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5313c-130">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5313c-131">TXT (テキスト)</span><span class="sxs-lookup"><span data-stu-id="5313c-131">TXT (Text)</span></span>|@|<span data-ttu-id="5313c-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5313c-132">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="5313c-133">**注**: これは例です。</span><span class="sxs-lookup"><span data-stu-id="5313c-133">**Note**: This is an example.</span></span> <span data-ttu-id="5313c-134">この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="5313c-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="5313c-135">確認する方法</span><span class="sxs-lookup"><span data-stu-id="5313c-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="5313c-136">1 時間</span><span class="sxs-lookup"><span data-stu-id="5313c-136">1 hour</span></span>  <br><span data-ttu-id="5313c-137">(ドロップダウンリストから値を選択します。)</span><span class="sxs-lookup"><span data-stu-id="5313c-137">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-検証-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="5313c-139">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5313c-139">Select **Save**.</span></span>

6. <span data-ttu-id="5313c-140">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="5313c-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="5313c-141">これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft に戻ってレコードを要求します。</span><span class="sxs-lookup"><span data-stu-id="5313c-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>

<span data-ttu-id="5313c-142">Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。</span><span class="sxs-lookup"><span data-stu-id="5313c-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5313c-143">Microsoft 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>の**設定** \> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="5313c-143">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="5313c-144">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="5313c-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="5313c-145">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5313c-145">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="5313c-146">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5313c-146">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="5313c-p107">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5313c-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="5313c-150">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="5313c-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="5313c-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5313c-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="5313c-152">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5313c-152">Follow the steps below.</span></span>

1. <span data-ttu-id="5313c-p108">まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="5313c-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="5313c-156">[ **Domains**] の下で、編集するドメインの下の [DNS] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5313c-156">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="5313c-158">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5313c-158">Select **Add**.</span></span>

    ![GoDaddy-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="5313c-160">ドロップダウン リストから [ **MX (Mail Exchanger)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5313c-160">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="5313c-162">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5313c-162">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="5313c-163">(ドロップダウンリストから [ **TTL** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="5313c-163">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="5313c-164">**Record type**</span><span class="sxs-lookup"><span data-stu-id="5313c-164">**Record type**</span></span>|<span data-ttu-id="5313c-165">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="5313c-165">**Host**</span></span>|<span data-ttu-id="5313c-166">**Points to**</span><span class="sxs-lookup"><span data-stu-id="5313c-166">**Points to**</span></span>|<span data-ttu-id="5313c-167">**Priority**</span><span class="sxs-lookup"><span data-stu-id="5313c-167">**Priority**</span></span>|<span data-ttu-id="5313c-168">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5313c-168">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5313c-169">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="5313c-169">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="5313c-170">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5313c-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="5313c-171">**注:** Microsoft アカウントから\* \<ドメインキー\> \*を取得します。</span><span class="sxs-lookup"><span data-stu-id="5313c-171">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="5313c-172">確認する方法</span><span class="sxs-lookup"><span data-stu-id="5313c-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="5313c-173">10 </span><span class="sxs-lookup"><span data-stu-id="5313c-173">10</span></span>  <br/> <span data-ttu-id="5313c-174">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5313c-174">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="5313c-175">1 hour</span><span class="sxs-lookup"><span data-stu-id="5313c-175">1 hour</span></span>  <br/> |

6. <span data-ttu-id="5313c-176">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5313c-176">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="5313c-177">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="5313c-177">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="5313c-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5313c-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="5313c-179">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5313c-179">Follow the steps below.</span></span>

1. <span data-ttu-id="5313c-p110">まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="5313c-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="5313c-183">[ **Domains**] の下で、編集するドメインの下の [DNS] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5313c-183">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="5313c-185">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5313c-185">Select **Add**.</span></span>

    ![GoDaddy-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="5313c-187">ドロップダウン リストから [ **CNAME (Alias)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5313c-187">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="5313c-189">1 番目の CNAME レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="5313c-189">Create the first CNAME record.</span></span>

    <span data-ttu-id="5313c-190">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5313c-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="5313c-191">(ドロップダウンリストから [ **TTL** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="5313c-191">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="5313c-192">**Record type**</span><span class="sxs-lookup"><span data-stu-id="5313c-192">**Record type**</span></span>|<span data-ttu-id="5313c-193">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="5313c-193">**Host**</span></span>|<span data-ttu-id="5313c-194">**Points to**</span><span class="sxs-lookup"><span data-stu-id="5313c-194">**Points to**</span></span>|<span data-ttu-id="5313c-195">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5313c-195">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5313c-196">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="5313c-196">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="5313c-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="5313c-197">autodiscover</span></span>  <br/> |<span data-ttu-id="5313c-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5313c-198">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="5313c-199">1 時間</span><span class="sxs-lookup"><span data-stu-id="5313c-199">1 hour</span></span>  <br/> |
    |<span data-ttu-id="5313c-200">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="5313c-200">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="5313c-201">sip</span><span class="sxs-lookup"><span data-stu-id="5313c-201">sip</span></span>  <br/> |<span data-ttu-id="5313c-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5313c-202">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="5313c-203">1 時間</span><span class="sxs-lookup"><span data-stu-id="5313c-203">1 hour</span></span>  <br/> |
    |<span data-ttu-id="5313c-204">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="5313c-204">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="5313c-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5313c-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5313c-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5313c-206">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="5313c-207">1 時間</span><span class="sxs-lookup"><span data-stu-id="5313c-207">1 hour</span></span>  <br/> |
    |<span data-ttu-id="5313c-208">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="5313c-208">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="5313c-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5313c-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5313c-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="5313c-210">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="5313c-211">1 hour</span><span class="sxs-lookup"><span data-stu-id="5313c-211">1 hour</span></span>  <br/> |
    |<span data-ttu-id="5313c-212">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="5313c-212">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="5313c-213">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5313c-213">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5313c-214">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5313c-214">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="5313c-215">1 時間</span><span class="sxs-lookup"><span data-stu-id="5313c-215">1 hour</span></span>  <br/> |



6. <span data-ttu-id="5313c-216">これらの手順を繰り返して、すべての CNAME レコードを作成するまで、次の CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5313c-216">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5313c-217">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="5313c-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5313c-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="5313c-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5313c-219">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="5313c-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5313c-220">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="5313c-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5313c-221">ドメインに対して既に SPF レコードがある場合は、Microsoft 用に新しいを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="5313c-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="5313c-222">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="5313c-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="5313c-223">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5313c-223">Follow the steps below.</span></span>

1. <span data-ttu-id="5313c-p112">まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="5313c-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="5313c-227">[ **Domains**] の下で、編集するドメインの下の [DNS] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5313c-227">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="5313c-229">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5313c-229">Select **Add**.</span></span>

    ![GoDaddy-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="5313c-231">ドロップダウン リストから [ **TXT (Text)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5313c-231">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="5313c-233">新規レコードのボックスに次の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5313c-233">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="5313c-234">(ドロップダウンリストから [ **TTL** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="5313c-234">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="5313c-235">**Record type**</span><span class="sxs-lookup"><span data-stu-id="5313c-235">**Record type**</span></span>|<span data-ttu-id="5313c-236">**Host**</span><span class="sxs-lookup"><span data-stu-id="5313c-236">**Host**</span></span>|<span data-ttu-id="5313c-237">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="5313c-237">**TXT Value**</span></span>|<span data-ttu-id="5313c-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5313c-238">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5313c-239">TXT (テキスト)</span><span class="sxs-lookup"><span data-stu-id="5313c-239">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="5313c-240">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5313c-240">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="5313c-241">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5313c-241">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="5313c-242">1 時間</span><span class="sxs-lookup"><span data-stu-id="5313c-242">1 hour</span></span>  <br/> |

    ![GoDaddy-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="5313c-244">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5313c-244">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="5313c-245">Microsoft に必要な2つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="5313c-245">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="5313c-246"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="5313c-246"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="5313c-247">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5313c-247">Follow the steps below.</span></span>

1. <span data-ttu-id="5313c-p113">まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="5313c-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="5313c-251">[ **Domains**] の下で、編集するドメインの下の [DNS] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5313c-251">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="5313c-253">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5313c-253">Select **Add**.</span></span>

    ![GoDaddy-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="5313c-255">ドロップダウン リストから [ **SRV (Service)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5313c-255">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="5313c-257">1 番目の SRV レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="5313c-257">Create the first SRV record.</span></span>

    <span data-ttu-id="5313c-258">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5313c-258">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="5313c-259">(ドロップダウンリストから [ **Record type** ] と [ **TTL** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="5313c-259">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="5313c-260">**Record type**</span><span class="sxs-lookup"><span data-stu-id="5313c-260">**Record type**</span></span>|<span data-ttu-id="5313c-261">**Name**</span><span class="sxs-lookup"><span data-stu-id="5313c-261">**Name**</span></span>|<span data-ttu-id="5313c-262">**Target**</span><span class="sxs-lookup"><span data-stu-id="5313c-262">**Target**</span></span>|<span data-ttu-id="5313c-263">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="5313c-263">**Protocol**</span></span>|<span data-ttu-id="5313c-264">**Service**</span><span class="sxs-lookup"><span data-stu-id="5313c-264">**Service**</span></span>|<span data-ttu-id="5313c-265">**Priority**</span><span class="sxs-lookup"><span data-stu-id="5313c-265">**Priority**</span></span>|<span data-ttu-id="5313c-266">**Weight**</span><span class="sxs-lookup"><span data-stu-id="5313c-266">**Weight**</span></span>|<span data-ttu-id="5313c-267">**Port**</span><span class="sxs-lookup"><span data-stu-id="5313c-267">**Port**</span></span>|<span data-ttu-id="5313c-268">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5313c-268">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5313c-269">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="5313c-269">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="5313c-270">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5313c-270">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="5313c-271">_tls</span><span class="sxs-lookup"><span data-stu-id="5313c-271">_tls</span></span>  <br/> |<span data-ttu-id="5313c-272">_sip</span><span class="sxs-lookup"><span data-stu-id="5313c-272">_sip</span></span>  <br/> |<span data-ttu-id="5313c-273">100</span><span class="sxs-lookup"><span data-stu-id="5313c-273">100</span></span>  <br/> |<span data-ttu-id="5313c-274">1-d</span><span class="sxs-lookup"><span data-stu-id="5313c-274">1</span></span>  <br/> |<span data-ttu-id="5313c-275">443</span><span class="sxs-lookup"><span data-stu-id="5313c-275">443</span></span>  <br/> |<span data-ttu-id="5313c-276">1 hour</span><span class="sxs-lookup"><span data-stu-id="5313c-276">1 hour</span></span>  <br/> |
    |<span data-ttu-id="5313c-277">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="5313c-277">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="5313c-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5313c-278">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="5313c-279">_tcp</span><span class="sxs-lookup"><span data-stu-id="5313c-279">_tcp</span></span>  <br/> |<span data-ttu-id="5313c-280">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="5313c-280">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="5313c-281">100</span><span class="sxs-lookup"><span data-stu-id="5313c-281">100</span></span>  <br/> |<span data-ttu-id="5313c-282">1-d</span><span class="sxs-lookup"><span data-stu-id="5313c-282">1</span></span>  <br/> |<span data-ttu-id="5313c-283">5061</span><span class="sxs-lookup"><span data-stu-id="5313c-283">5061</span></span>  <br/> |<span data-ttu-id="5313c-284">1 時間</span><span class="sxs-lookup"><span data-stu-id="5313c-284">1 hour</span></span>  <br/> |

    ![GoDaddy-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="5313c-286">**手順 5**を繰り返して、他の SRV レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="5313c-286">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="5313c-287">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5313c-287">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="5313c-p114">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5313c-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
