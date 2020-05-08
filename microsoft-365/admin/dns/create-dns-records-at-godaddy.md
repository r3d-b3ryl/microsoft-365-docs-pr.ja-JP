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
ms.openlocfilehash: b1c5539af6683bbf8f94fd15880fb870caf31342
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049025"
---
# <a name="create-dns-records-at-godaddy-for-microsoft"></a><span data-ttu-id="4b1e3-103">Microsoft の GoDaddy で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="4b1e3-103">Create DNS records at GoDaddy for Microsoft</span></span>

 <span data-ttu-id="4b1e3-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="4b1e3-105">使用している DNS ホスティング プロバイダーが GoDaddy の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="4b1e3-106">これらのレコードを GoDaddy で追加すると、使用しているドメインが、Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-106">After you add these records at GoDaddy, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="4b1e3-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4b1e3-110">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="4b1e3-110">Add a TXT record for verification</span></span>
<span data-ttu-id="4b1e3-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="4b1e3-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="4b1e3-p102">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="4b1e3-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="4b1e3-116">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-116">Follow the steps below.</span></span>

1. <span data-ttu-id="4b1e3-p104">まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="4b1e3-120">[ **Domains**] の下で、編集するドメインの下の [DNS] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-120">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="4b1e3-122">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-122">Select **Add**.</span></span>

    ![GoDaddy-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="4b1e3-124">ドロップダウン リストから [ **TXT (Text)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-124">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="4b1e3-125">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="4b1e3-126">**Record type**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-126">**Record type**</span></span> |<span data-ttu-id="4b1e3-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-127">**Host**</span></span>|<span data-ttu-id="4b1e3-128">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-128">**TXT Value**</span></span>|<span data-ttu-id="4b1e3-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-129">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4b1e3-130">TXT (テキスト)</span><span class="sxs-lookup"><span data-stu-id="4b1e3-130">TXT (Text)</span></span>|@|<span data-ttu-id="4b1e3-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="4b1e3-131">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="4b1e3-132">**注**: これは例です。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-132">**Note**: This is an example.</span></span> <span data-ttu-id="4b1e3-133">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="4b1e3-134">確認する方法</span><span class="sxs-lookup"><span data-stu-id="4b1e3-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="4b1e3-135">1 時間</span><span class="sxs-lookup"><span data-stu-id="4b1e3-135">1 hour</span></span>  <br><span data-ttu-id="4b1e3-136">(ドロップダウンリストから値を選択します。)</span><span class="sxs-lookup"><span data-stu-id="4b1e3-136">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-検証-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="4b1e3-138">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-138">Select **Save**.</span></span>

6. <span data-ttu-id="4b1e3-139">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="4b1e3-140">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>

<span data-ttu-id="4b1e3-141">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4b1e3-142">Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="4b1e3-143">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="4b1e3-144">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-144">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="4b1e3-145">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-145">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="4b1e3-p107">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="4b1e3-149">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="4b1e3-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="4b1e3-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="4b1e3-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="4b1e3-151">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-151">Follow the steps below.</span></span>

1. <span data-ttu-id="4b1e3-p108">まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="4b1e3-155">[ **Domains**] の下で、編集するドメインの下の [DNS] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-155">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="4b1e3-157">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-157">Select **Add**.</span></span>

    ![GoDaddy-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="4b1e3-159">ドロップダウン リストから [ **MX (Mail Exchanger)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-159">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="4b1e3-161">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-161">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="4b1e3-162">(ドロップダウンリストから [ **TTL** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="4b1e3-162">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="4b1e3-163">**Record type**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-163">**Record type**</span></span>|<span data-ttu-id="4b1e3-164">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-164">**Host**</span></span>|<span data-ttu-id="4b1e3-165">**Points to**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-165">**Points to**</span></span>|<span data-ttu-id="4b1e3-166">**Priority**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-166">**Priority**</span></span>|<span data-ttu-id="4b1e3-167">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-167">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4b1e3-168">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="4b1e3-168">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="4b1e3-169">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4b1e3-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="4b1e3-170">**注:** Microsoft アカウントから\* \<ドメインキー\> \*を取得します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-170">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="4b1e3-171">確認する方法</span><span class="sxs-lookup"><span data-stu-id="4b1e3-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="4b1e3-172">10  </span><span class="sxs-lookup"><span data-stu-id="4b1e3-172">10</span></span>  <br/> <span data-ttu-id="4b1e3-173">優先度の詳細については、「[MX 優先度とは何か](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-173">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="4b1e3-174">1 hour</span><span class="sxs-lookup"><span data-stu-id="4b1e3-174">1 hour</span></span>  <br/> |

6. <span data-ttu-id="4b1e3-175">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-175">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="4b1e3-176">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="4b1e3-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="4b1e3-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="4b1e3-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="4b1e3-178">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-178">Follow the steps below.</span></span>

1. <span data-ttu-id="4b1e3-p110">まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="4b1e3-182">[ **Domains**] の下で、編集するドメインの下の [DNS] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-182">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="4b1e3-184">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-184">Select **Add**.</span></span>

    ![GoDaddy-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="4b1e3-186">ドロップダウン リストから [ **CNAME (Alias)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-186">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="4b1e3-188">1 番目の CNAME レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-188">Create the first CNAME record.</span></span>

    <span data-ttu-id="4b1e3-189">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="4b1e3-190">(ドロップダウンリストから [ **TTL** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="4b1e3-190">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="4b1e3-191">**Record type**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-191">**Record type**</span></span>|<span data-ttu-id="4b1e3-192">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-192">**Host**</span></span>|<span data-ttu-id="4b1e3-193">**Points to**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-193">**Points to**</span></span>|<span data-ttu-id="4b1e3-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4b1e3-195">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="4b1e3-195">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="4b1e3-196">autodiscover</span><span class="sxs-lookup"><span data-stu-id="4b1e3-196">autodiscover</span></span>  <br/> |<span data-ttu-id="4b1e3-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4b1e3-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="4b1e3-198">1 時間</span><span class="sxs-lookup"><span data-stu-id="4b1e3-198">1 hour</span></span>  <br/> |
    |<span data-ttu-id="4b1e3-199">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="4b1e3-199">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="4b1e3-200">sip</span><span class="sxs-lookup"><span data-stu-id="4b1e3-200">sip</span></span>  <br/> |<span data-ttu-id="4b1e3-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4b1e3-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="4b1e3-202">1 時間</span><span class="sxs-lookup"><span data-stu-id="4b1e3-202">1 hour</span></span>  <br/> |
    |<span data-ttu-id="4b1e3-203">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="4b1e3-203">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="4b1e3-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4b1e3-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="4b1e3-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4b1e3-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="4b1e3-206">1 時間</span><span class="sxs-lookup"><span data-stu-id="4b1e3-206">1 hour</span></span>  <br/> |
    |<span data-ttu-id="4b1e3-207">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="4b1e3-207">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="4b1e3-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="4b1e3-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="4b1e3-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="4b1e3-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="4b1e3-210">1 時間</span><span class="sxs-lookup"><span data-stu-id="4b1e3-210">1 hour</span></span>  <br/> |
    |<span data-ttu-id="4b1e3-211">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="4b1e3-211">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="4b1e3-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="4b1e3-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="4b1e3-213">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4b1e3-213">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="4b1e3-214">1 時間</span><span class="sxs-lookup"><span data-stu-id="4b1e3-214">1 hour</span></span>  <br/> |



6. <span data-ttu-id="4b1e3-215">これらの手順を繰り返して、すべての CNAME レコードを作成するまで、次の CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-215">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="4b1e3-216">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="4b1e3-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="4b1e3-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="4b1e3-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="4b1e3-218">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="4b1e3-219">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="4b1e3-220">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="4b1e3-221">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="4b1e3-222">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-222">Follow the steps below.</span></span>

1. <span data-ttu-id="4b1e3-p112">まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="4b1e3-226">[ **Domains**] の下で、編集するドメインの下の [DNS] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-226">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="4b1e3-228">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-228">Select **Add**.</span></span>

    ![GoDaddy-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="4b1e3-230">ドロップダウン リストから [ **TXT (Text)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-230">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="4b1e3-232">新規レコードのボックスに次の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-232">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="4b1e3-233">(ドロップダウンリストから [ **TTL** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="4b1e3-233">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="4b1e3-234">**Record type**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-234">**Record type**</span></span>|<span data-ttu-id="4b1e3-235">**Host**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-235">**Host**</span></span>|<span data-ttu-id="4b1e3-236">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-236">**TXT Value**</span></span>|<span data-ttu-id="4b1e3-237">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-237">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4b1e3-238">TXT (テキスト)</span><span class="sxs-lookup"><span data-stu-id="4b1e3-238">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="4b1e3-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="4b1e3-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="4b1e3-240">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="4b1e3-241">1 時間</span><span class="sxs-lookup"><span data-stu-id="4b1e3-241">1 hour</span></span>  <br/> |

    ![GoDaddy-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="4b1e3-243">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-243">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="4b1e3-244">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="4b1e3-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="4b1e3-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="4b1e3-245"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="4b1e3-246">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-246">Follow the steps below.</span></span>

1. <span data-ttu-id="4b1e3-p113">まず、[このリンク](https://account.godaddy.com/products/?go_redirect=disabled)を使って GoDaddy でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="4b1e3-250">[ **Domains**] の下で、編集するドメインの下の [DNS] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-250">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="4b1e3-252">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-252">Select **Add**.</span></span>

    ![GoDaddy-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="4b1e3-254">ドロップダウン リストから [ **SRV (Service)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-254">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="4b1e3-256">1 番目の SRV レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-256">Create the first SRV record.</span></span>

    <span data-ttu-id="4b1e3-257">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-257">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="4b1e3-258">(ドロップダウンリストから [ **Record type** ] と [ **TTL** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="4b1e3-258">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="4b1e3-259">**Record type**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-259">**Record type**</span></span>|<span data-ttu-id="4b1e3-260">**Name**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-260">**Name**</span></span>|<span data-ttu-id="4b1e3-261">**Target**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-261">**Target**</span></span>|<span data-ttu-id="4b1e3-262">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-262">**Protocol**</span></span>|<span data-ttu-id="4b1e3-263">**Service**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-263">**Service**</span></span>|<span data-ttu-id="4b1e3-264">**Priority**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-264">**Priority**</span></span>|<span data-ttu-id="4b1e3-265">**Weight**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-265">**Weight**</span></span>|<span data-ttu-id="4b1e3-266">**Port**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-266">**Port**</span></span>|<span data-ttu-id="4b1e3-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4b1e3-267">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4b1e3-268">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="4b1e3-268">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="4b1e3-269">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4b1e3-269">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="4b1e3-270">_tls</span><span class="sxs-lookup"><span data-stu-id="4b1e3-270">_tls</span></span>  <br/> |<span data-ttu-id="4b1e3-271">_sip</span><span class="sxs-lookup"><span data-stu-id="4b1e3-271">_sip</span></span>  <br/> |<span data-ttu-id="4b1e3-272">100</span><span class="sxs-lookup"><span data-stu-id="4b1e3-272">100</span></span>  <br/> |<span data-ttu-id="4b1e3-273">1-d</span><span class="sxs-lookup"><span data-stu-id="4b1e3-273">1</span></span>  <br/> |<span data-ttu-id="4b1e3-274">443</span><span class="sxs-lookup"><span data-stu-id="4b1e3-274">443</span></span>  <br/> |<span data-ttu-id="4b1e3-275">1 hour</span><span class="sxs-lookup"><span data-stu-id="4b1e3-275">1 hour</span></span>  <br/> |
    |<span data-ttu-id="4b1e3-276">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="4b1e3-276">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="4b1e3-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4b1e3-277">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="4b1e3-278">_tcp</span><span class="sxs-lookup"><span data-stu-id="4b1e3-278">_tcp</span></span>  <br/> |<span data-ttu-id="4b1e3-279">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="4b1e3-279">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="4b1e3-280">100</span><span class="sxs-lookup"><span data-stu-id="4b1e3-280">100</span></span>  <br/> |<span data-ttu-id="4b1e3-281">1-d</span><span class="sxs-lookup"><span data-stu-id="4b1e3-281">1</span></span>  <br/> |<span data-ttu-id="4b1e3-282">5061</span><span class="sxs-lookup"><span data-stu-id="4b1e3-282">5061</span></span>  <br/> |<span data-ttu-id="4b1e3-283">1 時間</span><span class="sxs-lookup"><span data-stu-id="4b1e3-283">1 hour</span></span>  <br/> |

    ![GoDaddy-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="4b1e3-285">**手順 5**を繰り返して、他の SRV レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-285">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="4b1e3-286">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-286">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="4b1e3-p114">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b1e3-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
