---
title: GoDaddy で Office 365 用の DNS レコードを作成する
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
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: ドメインを確認し、電子メール、Skype for Business Online、および GoDaddy for Office 365 のその他のサービスの DNS レコードを設定する方法について説明します。
ms.custom: okr_smb
ms.openlocfilehash: e037e989a51a95b16077d1edfcdff4b341ee3b80
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349238"
---
# <a name="create-dns-records-at-godaddy-for-office-365"></a><span data-ttu-id="485cb-103">GoDaddy で Office 365 用の DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="485cb-103">Create DNS records at GoDaddy for Office 365</span></span>

 <span data-ttu-id="485cb-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="485cb-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="485cb-105">使用している DNS ホスティング プロバイダーが GoDaddy の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="485cb-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="485cb-106">これらのレコードを GoDaddy で追加すると、使用しているドメインが、Office 365 のサービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="485cb-106">After you add these records at GoDaddy, your domain will be set up to work with Office 365 services.</span></span>

<span data-ttu-id="485cb-107">Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="485cb-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>

> [!NOTE]
> <span data-ttu-id="485cb-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="485cb-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="485cb-111">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="485cb-111">Add a TXT record for verification</span></span>
<span data-ttu-id="485cb-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="485cb-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="485cb-p102">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="485cb-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="485cb-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="485cb-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="485cb-117">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="485cb-117">Follow the steps below.</span></span>

1. <span data-ttu-id="485cb-p104">まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="485cb-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="485cb-121">[ **Domains**] の下で、編集するドメインの下の [DNS] を選択します。</span><span class="sxs-lookup"><span data-stu-id="485cb-121">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="485cb-123">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="485cb-123">Select **Add**.</span></span>

    ![GoDaddy-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="485cb-125">ドロップダウン リストから [ **TXT (Text)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="485cb-125">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="485cb-126">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="485cb-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="485cb-127">**Record type**</span><span class="sxs-lookup"><span data-stu-id="485cb-127">**Record type**</span></span> |<span data-ttu-id="485cb-128">**Host**</span><span class="sxs-lookup"><span data-stu-id="485cb-128">**Host**</span></span>|<span data-ttu-id="485cb-129">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="485cb-129">**TXT Value**</span></span>|<span data-ttu-id="485cb-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="485cb-130">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="485cb-131">TXT (テキスト)</span><span class="sxs-lookup"><span data-stu-id="485cb-131">TXT (Text)</span></span>|@|<span data-ttu-id="485cb-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="485cb-132">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="485cb-133">**注**: これは例です。</span><span class="sxs-lookup"><span data-stu-id="485cb-133">**Note**: This is an example.</span></span> <span data-ttu-id="485cb-134">Office 365 の表から [**宛先またはポイント先のアドレス**] の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="485cb-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="485cb-135">確認する方法</span><span class="sxs-lookup"><span data-stu-id="485cb-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="485cb-136">1 時間</span><span class="sxs-lookup"><span data-stu-id="485cb-136">1 hour</span></span>  <br><span data-ttu-id="485cb-137">(ドロップダウンリストから値を選択します。)</span><span class="sxs-lookup"><span data-stu-id="485cb-137">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-検証-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="485cb-139">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="485cb-139">Select **Save**.</span></span>

6. <span data-ttu-id="485cb-140">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="485cb-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="485cb-141">これで、ドメイン レジストラーのサイトでレコードが追加されました。Office 365 に戻り、Office 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="485cb-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>

<span data-ttu-id="485cb-142">Office 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="485cb-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="485cb-143">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="485cb-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="485cb-144">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="485cb-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="485cb-145">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="485cb-145">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="485cb-146">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="485cb-146">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="485cb-p107">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="485cb-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="485cb-150">MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする</span><span class="sxs-lookup"><span data-stu-id="485cb-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="485cb-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="485cb-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="485cb-152">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="485cb-152">Follow the steps below.</span></span>

1. <span data-ttu-id="485cb-p108">まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="485cb-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="485cb-156">[ **Domains**] の下で、編集するドメインの下の [DNS] を選択します。</span><span class="sxs-lookup"><span data-stu-id="485cb-156">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="485cb-158">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="485cb-158">Select **Add**.</span></span>

    ![GoDaddy-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="485cb-160">ドロップダウン リストから [ **MX (Mail Exchanger)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="485cb-160">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="485cb-162">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="485cb-162">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="485cb-163">(ドロップダウンリストから [ **TTL** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="485cb-163">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="485cb-164">**Record type**</span><span class="sxs-lookup"><span data-stu-id="485cb-164">**Record type**</span></span>|<span data-ttu-id="485cb-165">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="485cb-165">**Host**</span></span>|<span data-ttu-id="485cb-166">**Points to**</span><span class="sxs-lookup"><span data-stu-id="485cb-166">**Points to**</span></span>|<span data-ttu-id="485cb-167">**Priority**</span><span class="sxs-lookup"><span data-stu-id="485cb-167">**Priority**</span></span>|<span data-ttu-id="485cb-168">**TTL**</span><span class="sxs-lookup"><span data-stu-id="485cb-168">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="485cb-169">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="485cb-169">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="485cb-170">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="485cb-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="485cb-171">**注:** Office 365 アカウントから\* \<ドメイン\>キー\*を取得します。</span><span class="sxs-lookup"><span data-stu-id="485cb-171">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="485cb-172">確認する方法</span><span class="sxs-lookup"><span data-stu-id="485cb-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="485cb-173">10 </span><span class="sxs-lookup"><span data-stu-id="485cb-173">10</span></span>  <br/> <span data-ttu-id="485cb-174">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="485cb-174">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="485cb-175">1 hour</span><span class="sxs-lookup"><span data-stu-id="485cb-175">1 hour</span></span>  <br/> |

6. <span data-ttu-id="485cb-176">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="485cb-176">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="485cb-177">Office 365 に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="485cb-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="485cb-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="485cb-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="485cb-179">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="485cb-179">Follow the steps below.</span></span>

1. <span data-ttu-id="485cb-p110">まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="485cb-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="485cb-183">[ **Domains**] の下で、編集するドメインの下の [DNS] を選択します。</span><span class="sxs-lookup"><span data-stu-id="485cb-183">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="485cb-185">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="485cb-185">Select **Add**.</span></span>

    ![GoDaddy-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="485cb-187">ドロップダウン リストから [ **CNAME (Alias)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="485cb-187">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="485cb-189">1 番目の CNAME レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="485cb-189">Create the first CNAME record.</span></span>

    <span data-ttu-id="485cb-190">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="485cb-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="485cb-191">(ドロップダウンリストから [ **TTL** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="485cb-191">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="485cb-192">**Record type**</span><span class="sxs-lookup"><span data-stu-id="485cb-192">**Record type**</span></span>|<span data-ttu-id="485cb-193">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="485cb-193">**Host**</span></span>|<span data-ttu-id="485cb-194">**Points to**</span><span class="sxs-lookup"><span data-stu-id="485cb-194">**Points to**</span></span>|<span data-ttu-id="485cb-195">**TTL**</span><span class="sxs-lookup"><span data-stu-id="485cb-195">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="485cb-196">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="485cb-196">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="485cb-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="485cb-197">autodiscover</span></span>  <br/> |<span data-ttu-id="485cb-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="485cb-198">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="485cb-199">1 時間</span><span class="sxs-lookup"><span data-stu-id="485cb-199">1 hour</span></span>  <br/> |
    |<span data-ttu-id="485cb-200">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="485cb-200">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="485cb-201">sip</span><span class="sxs-lookup"><span data-stu-id="485cb-201">sip</span></span>  <br/> |<span data-ttu-id="485cb-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="485cb-202">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="485cb-203">1 時間</span><span class="sxs-lookup"><span data-stu-id="485cb-203">1 hour</span></span>  <br/> |
    |<span data-ttu-id="485cb-204">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="485cb-204">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="485cb-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="485cb-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="485cb-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="485cb-206">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="485cb-207">1 時間</span><span class="sxs-lookup"><span data-stu-id="485cb-207">1 hour</span></span>  <br/> |
    |<span data-ttu-id="485cb-208">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="485cb-208">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="485cb-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="485cb-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="485cb-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="485cb-210">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="485cb-211">1 hour</span><span class="sxs-lookup"><span data-stu-id="485cb-211">1 hour</span></span>  <br/> |
    |<span data-ttu-id="485cb-212">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="485cb-212">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="485cb-213">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="485cb-213">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="485cb-214">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="485cb-214">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="485cb-215">1 時間</span><span class="sxs-lookup"><span data-stu-id="485cb-215">1 hour</span></span>  <br/> |



6. <span data-ttu-id="485cb-216">これらの手順を繰り返して、すべての CNAME レコードを作成するまで、次の CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="485cb-216">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="485cb-217">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="485cb-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="485cb-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="485cb-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="485cb-219">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="485cb-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="485cb-220">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="485cb-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="485cb-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="485cb-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="485cb-222">代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。</span><span class="sxs-lookup"><span data-stu-id="485cb-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="485cb-223">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="485cb-223">Follow the steps below.</span></span>

1. <span data-ttu-id="485cb-p112">まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="485cb-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="485cb-227">[ **Domains**] の下で、編集するドメインの下の [DNS] を選択します。</span><span class="sxs-lookup"><span data-stu-id="485cb-227">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="485cb-229">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="485cb-229">Select **Add**.</span></span>

    ![GoDaddy-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="485cb-231">ドロップダウン リストから [ **TXT (Text)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="485cb-231">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="485cb-233">新規レコードのボックスに次の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="485cb-233">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="485cb-234">(ドロップダウンリストから [ **TTL** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="485cb-234">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="485cb-235">**Record type**</span><span class="sxs-lookup"><span data-stu-id="485cb-235">**Record type**</span></span>|<span data-ttu-id="485cb-236">**Host**</span><span class="sxs-lookup"><span data-stu-id="485cb-236">**Host**</span></span>|<span data-ttu-id="485cb-237">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="485cb-237">**TXT Value**</span></span>|<span data-ttu-id="485cb-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="485cb-238">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="485cb-239">TXT (テキスト)</span><span class="sxs-lookup"><span data-stu-id="485cb-239">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="485cb-240">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="485cb-240">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="485cb-241">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="485cb-241">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="485cb-242">1 時間</span><span class="sxs-lookup"><span data-stu-id="485cb-242">1 hour</span></span>  <br/> |

    ![GoDaddy-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="485cb-244">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="485cb-244">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="485cb-245">Office 365 に必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="485cb-245">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="485cb-246"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="485cb-246"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="485cb-247">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="485cb-247">Follow the steps below.</span></span>

1. <span data-ttu-id="485cb-p113">まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="485cb-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="485cb-251">[ **Domains**] の下で、編集するドメインの下の [DNS] を選択します。</span><span class="sxs-lookup"><span data-stu-id="485cb-251">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="485cb-253">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="485cb-253">Select **Add**.</span></span>

    ![GoDaddy-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="485cb-255">ドロップダウン リストから [ **SRV (Service)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="485cb-255">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="485cb-257">1 番目の SRV レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="485cb-257">Create the first SRV record.</span></span>

    <span data-ttu-id="485cb-258">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="485cb-258">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="485cb-259">(ドロップダウンリストから [ **Record type** ] と [ **TTL** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="485cb-259">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="485cb-260">**Record type**</span><span class="sxs-lookup"><span data-stu-id="485cb-260">**Record type**</span></span>|<span data-ttu-id="485cb-261">**Name**</span><span class="sxs-lookup"><span data-stu-id="485cb-261">**Name**</span></span>|<span data-ttu-id="485cb-262">**Target**</span><span class="sxs-lookup"><span data-stu-id="485cb-262">**Target**</span></span>|<span data-ttu-id="485cb-263">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="485cb-263">**Protocol**</span></span>|<span data-ttu-id="485cb-264">**Service**</span><span class="sxs-lookup"><span data-stu-id="485cb-264">**Service**</span></span>|<span data-ttu-id="485cb-265">**Priority**</span><span class="sxs-lookup"><span data-stu-id="485cb-265">**Priority**</span></span>|<span data-ttu-id="485cb-266">**Weight**</span><span class="sxs-lookup"><span data-stu-id="485cb-266">**Weight**</span></span>|<span data-ttu-id="485cb-267">**Port**</span><span class="sxs-lookup"><span data-stu-id="485cb-267">**Port**</span></span>|<span data-ttu-id="485cb-268">**TTL**</span><span class="sxs-lookup"><span data-stu-id="485cb-268">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="485cb-269">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="485cb-269">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="485cb-270">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="485cb-270">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="485cb-271">_tls</span><span class="sxs-lookup"><span data-stu-id="485cb-271">_tls</span></span>  <br/> |<span data-ttu-id="485cb-272">_sip</span><span class="sxs-lookup"><span data-stu-id="485cb-272">_sip</span></span>  <br/> |<span data-ttu-id="485cb-273">100</span><span class="sxs-lookup"><span data-stu-id="485cb-273">100</span></span>  <br/> |<span data-ttu-id="485cb-274">1-d</span><span class="sxs-lookup"><span data-stu-id="485cb-274">1</span></span>  <br/> |<span data-ttu-id="485cb-275">443</span><span class="sxs-lookup"><span data-stu-id="485cb-275">443</span></span>  <br/> |<span data-ttu-id="485cb-276">1 hour</span><span class="sxs-lookup"><span data-stu-id="485cb-276">1 hour</span></span>  <br/> |
    |<span data-ttu-id="485cb-277">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="485cb-277">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="485cb-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="485cb-278">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="485cb-279">_tcp</span><span class="sxs-lookup"><span data-stu-id="485cb-279">_tcp</span></span>  <br/> |<span data-ttu-id="485cb-280">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="485cb-280">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="485cb-281">100</span><span class="sxs-lookup"><span data-stu-id="485cb-281">100</span></span>  <br/> |<span data-ttu-id="485cb-282">1-d</span><span class="sxs-lookup"><span data-stu-id="485cb-282">1</span></span>  <br/> |<span data-ttu-id="485cb-283">5061</span><span class="sxs-lookup"><span data-stu-id="485cb-283">5061</span></span>  <br/> |<span data-ttu-id="485cb-284">1 時間</span><span class="sxs-lookup"><span data-stu-id="485cb-284">1 hour</span></span>  <br/> |

    ![GoDaddy-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="485cb-286">**手順 5**を繰り返して、他の SRV レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="485cb-286">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="485cb-287">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="485cb-287">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="485cb-p114">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="485cb-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
