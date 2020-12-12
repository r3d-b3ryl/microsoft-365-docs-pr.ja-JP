---
title: Microsoft 365 にドメインを追加する
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
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: DNS ホストで DNS レコードを追加して、Microsoft 365 管理センターの Microsoft 365 にドメインを追加します。 これらの手順を案内するウィザードがあります。
ms.openlocfilehash: 3e7463bd4cf6b7836a9770421e0b8ce597524a67
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658053"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="c8071-104">Microsoft 365 にドメインを追加する</span><span class="sxs-lookup"><span data-stu-id="c8071-104">Add a domain to Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c8071-105">管理センターは変更されました。</span><span class="sxs-lookup"><span data-stu-id="c8071-105">The admin center is changing.</span></span> <span data-ttu-id="c8071-106">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8071-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="c8071-107">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](domains-faq.yml)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8071-107">**[Check the Domains FAQ](domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="c8071-108">*追加、変更またはドメインを削除するには、[ビジネスまたはエンタープライズ プラン](https://products.office.com/business/office)の **グローバル管理者** である **必要** があります。これらの変更は、テナント全体、*カスタマイズ管理者\* または *正規ユーザー* に影響を与え、変更を加えることはできません。\*</span><span class="sxs-lookup"><span data-stu-id="c8071-108">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="c8071-109">以下の手順に従って、ドメインの追加、セットアップ、またはセットアップの続行を行います。</span><span class="sxs-lookup"><span data-stu-id="c8071-109">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c8071-110"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> の管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c8071-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="c8071-111"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> から管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c8071-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c8071-112"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> から管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c8071-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="c8071-113">[**設定**]  >  [**ドメイン**] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c8071-113">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="c8071-114">[**ドメインの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8071-114">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="c8071-115">追加するドメインの名前を入力し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8071-115">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="c8071-116">ドメインの所有を確認する方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8071-116">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="c8071-117">ドメイン レジストラーが [ドメイン](#domain-connect-registrars-integrating-with-microsoft-365)接続を使用している場合 [、Microsoft](../get-help-with-domains/domain-connect.md) は、レジストラーにサインインして Microsoft 365 への接続を確認することで、レコードを自動的に設定します。</span><span class="sxs-lookup"><span data-stu-id="c8071-117">If your domain registrar uses [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span> <span data-ttu-id="c8071-118">You'll be returned to the admin center and Microsoft will then automatically verify your domain.</span><span class="sxs-lookup"><span data-stu-id="c8071-118">You'll be returned to the admin center and Microsoft will then automatically verify your domain.</span></span>
    2. <span data-ttu-id="c8071-119">TXT レコードを使用し、ドメインを検証できます。</span><span class="sxs-lookup"><span data-stu-id="c8071-119">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="c8071-120">これを選択し、**[次へ]** を選択すると、この DNS レコードをレジストラーの Web サイトに追加する方法が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8071-120">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="c8071-121">レコードを追加すると、検証に最大 30 分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="c8071-121">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    3. <span data-ttu-id="c8071-122">ドメインの Web サイトにテキスト ファイルを追加できます。</span><span class="sxs-lookup"><span data-stu-id="c8071-122">You can add a text file to your domain's website.</span></span> <span data-ttu-id="c8071-123">セットアップ ウィザードから .txt ファイルを選択してダウンロードし、Web サイトのトップ レベル フォルダーにファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="c8071-123">Select and download the .txt file from the setup wizard, then upload the file to your website's top level folder.</span></span> <span data-ttu-id="c8071-124">ファイルへのパスは次のように表示されます `http://mydomain.com/ms39978200.txt` 。</span><span class="sxs-lookup"><span data-stu-id="c8071-124">The path to the file should look similar to: `http://mydomain.com/ms39978200.txt`.</span></span> <span data-ttu-id="c8071-125">Web サイトでファイルを見つけることで、ドメインを所有している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8071-125">We'll confirm you own the domain by finding the file on your website.</span></span>
    
6. <span data-ttu-id="c8071-126">Microsoft がドメインを使用するために必要な DNS 変更を行う方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8071-126">Choose how you want to make the DNS changes required for Microsoft to use your domain.</span></span>
    
    1. <span data-ttu-id="c8071-127">レジスト **ラーが** Domain [Connect](#domain-connect-registrars-integrating-with-microsoft-365)をサポートし [、Microsoft](../get-help-with-domains/domain-connect.md) がレジストラーにサインインして Microsoft 365 への接続を確認してレコードを自動的にセットアップする場合は、[DNS レコードの追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8071-127">Choose **Add the DNS records for me** if your registrar supports [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span>
    2. <span data-ttu-id="c8071-128">特定 **の** Microsoft 365 サービスのみをドメインに接続する場合、または今のところこれをスキップして後で行う場合は、[自分で DNS レコードを追加する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8071-128">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="c8071-129">**次のように、操作内容を正確に把握している場合に、このオプションを選択します。**</span><span class="sxs-lookup"><span data-stu-id="c8071-129">**Choose this option if you know exactly what you're doing.**</span></span>

7. <span data-ttu-id="c8071-130">DNS レコードを自分で追加することを選択した場合は、[次へ] を選択すると、ドメインをセットアップするためにレジストラー Web サイトに追加する必要があるすべてのレコードを含むページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8071-130">If you chose to *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 

    <span data-ttu-id="c8071-131">ポータルでレジストラーが認識されない場合、[一般的な方法に従うことができます](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="c8071-131">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="c8071-132">[ホスト固有の命令](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)の一覧からお使いのホストを見つけ、手順に従って必要なすべてのレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c8071-132">Check our list of [host-specific instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="c8071-133">ドメインの DNS ホスティング プロバイダーまたはドメイン レジストラーがわからない場合は、「[ドメイン レジストラーまたは DNS ホスティング プロバイダーを探す](../get-help-with-domains/find-your-domain-registrar.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8071-133">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="c8071-134">後で待つ場合は、すべてのサービスの選択を解除して [続行] をクリックするか、前のドメイン接続手順で [その他のオプション] を選択し、[今はスキップする] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="c8071-134">If you want to wait for later, either unselect all the services and click **Continue**, or in the previous domain connection step choose **More Options** and select **Skip this for now**.</span></span>
    
8. <span data-ttu-id="c8071-135">**[完了]** を選択します。これで完了です!</span><span class="sxs-lookup"><span data-stu-id="c8071-135">Select **Finish** - you're done!</span></span>

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="c8071-136">カスタムの DNS レコードを追加または編集する</span><span class="sxs-lookup"><span data-stu-id="c8071-136">Add or edit custom DNS records</span></span>

<span data-ttu-id="c8071-137">以下の手順に従って、Web サイトまたはサードパーティ サービスのカスタム レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c8071-137">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="c8071-138">で Microsoft 管理センターにサインインします <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="c8071-138">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="c8071-139">[**設定**]   >  [**ドメイン**] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c8071-139">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="c8071-140">[ **ドメイン**] ページで、ドメインを選びます。</span><span class="sxs-lookup"><span data-stu-id="c8071-140">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="c8071-141">[DNS **設定] で、[** カスタム レコード **] を選択します**。次に、[ **新しいカスタム レコード] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8071-141">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="c8071-142">追加する DNS レコードの種類を選択し、新しいレコードの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="c8071-142">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="c8071-143">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8071-143">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="c8071-144">ドメイン接続を使用するレジストラー</span><span class="sxs-lookup"><span data-stu-id="c8071-144">Registrars with Domain Connect</span></span>

<span data-ttu-id="c8071-145">[ドメイン接続](https://www.domainconnect.org/) が有効なレジストラーを使用すると、数分かかる 3 段階のプロセスでドメインを Microsoft 365 に追加できます。</span><span class="sxs-lookup"><span data-stu-id="c8071-145">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="c8071-146">ウィザードでは、ドメインを所有し、ドメインのレコードを自動的にセットアップするだけなので、メールが Microsoft 365 や Teams などの他の Microsoft 365 サービスに届きます。</span><span class="sxs-lookup"><span data-stu-id="c8071-146">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c8071-147">セットアップ ウィザードを開始する前に、ブラウザーのポップアップ ブロック機能が無効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c8071-147">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="c8071-148">Microsoft 365 と統合されたドメイン接続レジストラー</span><span class="sxs-lookup"><span data-stu-id="c8071-148">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="c8071-149">1 &amp; 1</span><span class="sxs-lookup"><span data-stu-id="c8071-149">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="c8071-150">EuroDNS</span><span class="sxs-lookup"><span data-stu-id="c8071-150">EuroDNS</span></span>](https://www.eurodns.com/)
- [<span data-ttu-id="c8071-151">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="c8071-151">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="c8071-152">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="c8071-152">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="c8071-153">WordPress.com</span><span class="sxs-lookup"><span data-stu-id="c8071-153">WordPress.com</span></span>](https://wordpress.com/)
- [<span data-ttu-id="c8071-154">クシュク</span><span class="sxs-lookup"><span data-stu-id="c8071-154">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="c8071-155">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="c8071-155">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="c8071-156">SecureServer または WildWestDomains (SecureServer DNS ホスティングを使用する GoDaddy リセラー)</span><span class="sxs-lookup"><span data-stu-id="c8071-156">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - <span data-ttu-id="c8071-157">例:</span><span class="sxs-lookup"><span data-stu-id="c8071-157">Examples:</span></span>
        - [<span data-ttu-id="c8071-158">DomainsPricedRight</span><span class="sxs-lookup"><span data-stu-id="c8071-158">DomainsPricedRight</span></span>](https://www.domainspricedright.com/products/domain-registration)
        - [<span data-ttu-id="c8071-159">DomainRightNow</span><span class="sxs-lookup"><span data-stu-id="c8071-159">DomainRightNow</span></span>](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="c8071-160">メールと Web サイトは何が起こりますか?</span><span class="sxs-lookup"><span data-stu-id="c8071-160">What happens to my email and website?</span></span>

<span data-ttu-id="c8071-161">セットアップが完了すると、ドメインの MX レコードが Microsoft 365 を指すまで更新され、ドメインのすべてのメールが Microsoft 365 に届きます。</span><span class="sxs-lookup"><span data-stu-id="c8071-161">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="c8071-162">ドメインでメールを受け取るすべてのユーザーに対して、ユーザーを追加し、Microsoft 365 でメールボックスを設定してください。</span><span class="sxs-lookup"><span data-stu-id="c8071-162">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="c8071-163">ビジネスで使用している Web サイトがある場合は、そのままの場所で稼働し続けます。</span><span class="sxs-lookup"><span data-stu-id="c8071-163">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="c8071-164">ドメイン接続のセットアップ手順は、Web サイトには影響を与えいません。</span><span class="sxs-lookup"><span data-stu-id="c8071-164">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="c8071-165">関連記事</span><span class="sxs-lookup"><span data-stu-id="c8071-165">Related articles</span></span>

[<span data-ttu-id="c8071-166">ドメイン FAQ</span><span class="sxs-lookup"><span data-stu-id="c8071-166">Domains FAQ</span></span>](domains-faq.yml)

[<span data-ttu-id="c8071-167">ドメインとは</span><span class="sxs-lookup"><span data-stu-id="c8071-167">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="c8071-168">Microsoft 365 でドメイン名を購入する</span><span class="sxs-lookup"><span data-stu-id="c8071-168">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="c8071-169">ドメインを設定する (ホストに固有の手順)</span><span class="sxs-lookup"><span data-stu-id="c8071-169">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
