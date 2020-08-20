---
title: Microsoft 365 にドメインを追加する
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
description: Microsoft 365 管理センターで Microsoft 365 にドメインを追加するには、DNS ホストで DNS レコードを追加します。 これらの手順を案内するウィザードがあります。
ms.openlocfilehash: 0adf8b4dcd5d7bd31038b74a574f449f32bfb037
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814434"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="fcd4e-104">Microsoft 365 にドメインを追加する</span><span class="sxs-lookup"><span data-stu-id="fcd4e-104">Add a domain to Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="fcd4e-105">管理センターは変更されました。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-105">The admin center is changing.</span></span> <span data-ttu-id="fcd4e-106">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="fcd4e-107">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-107">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="fcd4e-108">*追加、変更またはドメインを削除するには、[ビジネスまたはエンタープライズ プラン](https://products.office.com/business/office)の**グローバル管理者**である**必要**があります。これらの変更は、テナント全体、*カスタマイズ管理者*または*正規ユーザー*に影響を与え、変更を加えることはできません。*</span><span class="sxs-lookup"><span data-stu-id="fcd4e-108">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="fcd4e-109">以下の手順に従って、ドメインの追加、セットアップ、またはセットアップの続行を行います。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-109">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="fcd4e-110"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> の管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="fcd4e-111"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> から管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="fcd4e-112"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> から管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="fcd4e-113">[**設定**]  >  [**ドメイン**] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-113">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="fcd4e-114">[**ドメインの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-114">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="fcd4e-115">追加するドメインの名前を入力し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-115">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="fcd4e-116">ドメインの所有を確認する方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-116">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="fcd4e-117">ドメインが GoDaddy または 1 &amp; 1 に登録されている場合は、[**次へ Sign in**  >  **Next]** を選び、Microsoft[がレコードを自動的に設定します](../get-help-with-domains/domain-connect.md)。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-117">If your domain is registered at GoDaddy or 1&amp;1, select **Sign in** > **Next** and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="fcd4e-118">ドメインに登録している連絡先に、検証コードを含むメールを送信できます。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-118">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="fcd4e-119">レコードのメールに見覚えがない、またはメールにアクセスできない場合、3 番目のオプションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-119">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="fcd4e-120">TXT レコードを使用し、ドメインを検証できます。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-120">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="fcd4e-121">これを選択し、**[次へ]** を選択すると、この DNS レコードをレジストラーの Web サイトに追加する方法が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-121">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="fcd4e-122">レコードを追加すると、検証に最大 30 分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-122">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    
6. <span data-ttu-id="fcd4e-123">Office でドメインを使用するために必要な DNS 変更の方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-123">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="fcd4e-124">DNS を Office に自動構成させる場合、**[DNS レコードを追加してもらう]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-124">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="fcd4e-125">自分 **で DNS レコードを自分で追加します。** その場合、特定の Microsoft 365 サービスのみをドメインに接続する場合、またはここではスキップして後で行います。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-125">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="fcd4e-126">**次のように、操作内容を正確に把握している場合に、このオプションを選択します。**</span><span class="sxs-lookup"><span data-stu-id="fcd4e-126">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="fcd4e-127">*DNS レコードを自分で追加する*を選択した場合、**[次へ]** を選択します。そして、ドメインを設定するために、レジストラー Web サイトに追加する必要があるすべてのレコードが含まれるページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-127">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="fcd4e-128">ポータルでレジストラーが認識されない場合、[一般的な方法に従うことができます](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-128">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="fcd4e-129">[ホスト固有の命令](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)の一覧からお使いのホストを見つけ、手順に従って必要なすべてのレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-129">Check our list of [host-specific instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="fcd4e-130">ドメインの DNS ホスティング プロバイダーまたはドメイン レジストラーがわからない場合は、「[ドメイン レジストラーまたは DNS ホスティング プロバイダーを探す](../get-help-with-domains/find-your-domain-registrar.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-130">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="fcd4e-131">後で行う場合、下にスクロールして **[この手順をスキップ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-131">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="fcd4e-132">**[完了]** を選択します。これで完了です!</span><span class="sxs-lookup"><span data-stu-id="fcd4e-132">Select **Finish** - you're done!</span></span> 

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="fcd4e-133">カスタムの DNS レコードを追加または編集する</span><span class="sxs-lookup"><span data-stu-id="fcd4e-133">Add or edit custom DNS records</span></span>

<span data-ttu-id="fcd4e-134">Web サイトまたはサード パーティのサービスのカスタム レコードを追加するには、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-134">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="fcd4e-135">Microsoft 管理センターにサインインします <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-135">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="fcd4e-136">[**設定**]   >  [**ドメイン**] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-136">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="fcd4e-137">[ **ドメイン**] ページで、ドメインを選びます。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-137">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="fcd4e-138">[DNS **設定] で**、[カスタム レコード **] を選択します**。次に新しい **カスタム レコードを選択します**。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-138">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="fcd4e-139">追加する DNS レコードの種類を選択し、新しいレコードの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-139">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="fcd4e-140">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-140">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="fcd4e-141">Domain Connect を使用したレジストラー</span><span class="sxs-lookup"><span data-stu-id="fcd4e-141">Registrars with Domain Connect</span></span>

<span data-ttu-id="fcd4e-142">[ドメイン接続](https://www.domainconnect.org/) が有効になっているレジストラーでは、3 段階のプロセスで Microsoft 365 にドメインを追加できますが、少し時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-142">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="fcd4e-143">ウィザードでは、ドメインを所有していることを確認したうし、ドメインのレコードが自動的にセットアップされるので、Microsoft 365 や Teams などの他の Microsoft 365 サービスが自分のドメインで機能するようにメールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-143">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fcd4e-144">セットアップ ウィザードを開始する前に、ブラウザーのポップアップ ブロック機能が無効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-144">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="fcd4e-145">Microsoft 365 との統合ドメイン接続レジストラー</span><span class="sxs-lookup"><span data-stu-id="fcd4e-145">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="fcd4e-146">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="fcd4e-146">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="fcd4e-147">123Reg</span><span class="sxs-lookup"><span data-stu-id="fcd4e-147">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="fcd4e-148">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="fcd4e-148">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="fcd4e-149">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="fcd4e-149">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="fcd4e-150">WordPress</span><span class="sxs-lookup"><span data-stu-id="fcd4e-150">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="fcd4e-151">Plesk</span><span class="sxs-lookup"><span data-stu-id="fcd4e-151">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="fcd4e-152">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="fcd4e-152">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="fcd4e-153">SecureServer または WildWestDomains (SecureServer DNS ホスティングを使用する GoDaddy リセラー)</span><span class="sxs-lookup"><span data-stu-id="fcd4e-153">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="fcd4e-154">MadDog Domains</span><span class="sxs-lookup"><span data-stu-id="fcd4e-154">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="fcd4e-155">CheapNames</span><span class="sxs-lookup"><span data-stu-id="fcd4e-155">CheapNames</span></span>](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="fcd4e-156">電子メールと Web サイトはどうなりうですか?</span><span class="sxs-lookup"><span data-stu-id="fcd4e-156">What happens to my email and website?</span></span>

<span data-ttu-id="fcd4e-157">セットアップを終了すると、ユーザーのドメインの MX レコードが Microsoft 365 を指定するように更新され、そのドメインのすべてのメールが Microsoft 365 に送信されるされるになります。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-157">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="fcd4e-158">ユーザーのドメインにメールを持つすべてのユーザーが Microsoft 365 に追加され、メールボックスが設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-158">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="fcd4e-159">ビジネスで使用している Web サイトがある場合は、そのままの場所で稼働し続けます。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-159">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="fcd4e-160">ドメイン接続のセットアップ手順は、Web サイトには影響を与えない。</span><span class="sxs-lookup"><span data-stu-id="fcd4e-160">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="fcd4e-161">関連記事</span><span class="sxs-lookup"><span data-stu-id="fcd4e-161">Related articles</span></span>

[<span data-ttu-id="fcd4e-162">ドメイン FAQ</span><span class="sxs-lookup"><span data-stu-id="fcd4e-162">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="fcd4e-163">ドメインとは</span><span class="sxs-lookup"><span data-stu-id="fcd4e-163">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="fcd4e-164">Microsoft 365 でドメイン名を購入する</span><span class="sxs-lookup"><span data-stu-id="fcd4e-164">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="fcd4e-165">ドメインを設定する (ホストに固有の手順)</span><span class="sxs-lookup"><span data-stu-id="fcd4e-165">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
