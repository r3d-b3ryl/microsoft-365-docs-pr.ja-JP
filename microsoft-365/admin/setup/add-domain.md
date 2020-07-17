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
description: Dns レコードを DNS ホストに追加して、365 Microsoft 365 の microsoft にドメインを追加します。 これらの手順を案内するウィザードがあります。
ms.openlocfilehash: ccebd7dd5e78663b7fd1d5318b17dfbc09bd8fb0
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079727"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="52991-104">Microsoft 365 にドメインを追加する</span><span class="sxs-lookup"><span data-stu-id="52991-104">Add a domain to Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="52991-105">管理センターは変更されました。</span><span class="sxs-lookup"><span data-stu-id="52991-105">The admin center is changing.</span></span> <span data-ttu-id="52991-106">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52991-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="52991-107">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52991-107">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="52991-108">*追加、変更またはドメインを削除するには、[ビジネスまたはエンタープライズ プラン](https://products.office.com/business/office)の**グローバル管理者**である**必要**があります。これらの変更は、テナント全体、*カスタマイズ管理者*または*正規ユーザー*に影響を与え、変更を加えることはできません。*</span><span class="sxs-lookup"><span data-stu-id="52991-108">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="52991-109">以下の手順に従って、ドメインの追加、セットアップ、またはセットアップの続行を行います。</span><span class="sxs-lookup"><span data-stu-id="52991-109">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="52991-110"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> の管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="52991-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="52991-111"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> の管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="52991-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="52991-112"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> から管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="52991-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="52991-113">[**設定**]  >  [**ドメイン**] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="52991-113">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="52991-114">[**ドメインの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="52991-114">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="52991-115">追加するドメインの名前を入力し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="52991-115">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="52991-116">ドメインの所有を確認する方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="52991-116">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="52991-117">ドメインが GoDaddy または 1 1 で登録されている場合は &amp; 、[ **Sign in**  >  **次へ**] を選択すると、Microsoft に[よってレコードが自動的に設定され](../get-help-with-domains/domain-connect.md)ます。</span><span class="sxs-lookup"><span data-stu-id="52991-117">If your domain is registered at GoDaddy or 1&amp;1, select **Sign in** > **Next** and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="52991-118">ドメインに登録している連絡先に、検証コードを含むメールを送信できます。</span><span class="sxs-lookup"><span data-stu-id="52991-118">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="52991-119">レコードのメールに見覚えがない、またはメールにアクセスできない場合、3 番目のオプションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="52991-119">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="52991-120">TXT レコードを使用し、ドメインを検証できます。</span><span class="sxs-lookup"><span data-stu-id="52991-120">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="52991-121">これを選択し、**[次へ]** を選択すると、この DNS レコードをレジストラーの Web サイトに追加する方法が表示されます。</span><span class="sxs-lookup"><span data-stu-id="52991-121">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="52991-122">レコードを追加すると、検証に最大 30 分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="52991-122">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    
6. <span data-ttu-id="52991-123">Office でドメインを使用するために必要な DNS 変更の方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="52991-123">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="52991-124">DNS を Office に自動構成させる場合、**[DNS レコードを追加してもらう]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="52991-124">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="52991-125">特定の Microsoft 365 サービスのみをドメインに接続する場合、またはこれを今後スキップする場合は **、[自分で DNS レコードを追加**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="52991-125">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="52991-126">**次のように、操作内容を正確に把握している場合に、このオプションを選択します。**</span><span class="sxs-lookup"><span data-stu-id="52991-126">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="52991-127">*DNS レコードを自分で追加する*を選択した場合、**[次へ]** を選択します。そして、ドメインを設定するために、レジストラー Web サイトに追加する必要があるすべてのレコードが含まれるページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="52991-127">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="52991-128">ポータルでレジストラーが認識されない場合、[一般的な方法に従うことができます](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="52991-128">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="52991-129">[ホスト固有の命令](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)の一覧からお使いのホストを見つけ、手順に従って必要なすべてのレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="52991-129">Check our list of [host-specific instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="52991-130">ドメインの DNS ホスティング プロバイダーまたはドメイン レジストラーがわからない場合は、「[ドメイン レジストラーまたは DNS ホスティング プロバイダーを探す](../get-help-with-domains/find-your-domain-registrar.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52991-130">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="52991-131">後で行う場合、下にスクロールして **[この手順をスキップ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="52991-131">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="52991-132">**[完了]** を選択します。これで完了です!</span><span class="sxs-lookup"><span data-stu-id="52991-132">Select **Finish** - you're done!</span></span> 

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="52991-133">カスタムの DNS レコードを追加または編集する</span><span class="sxs-lookup"><span data-stu-id="52991-133">Add or edit custom DNS records</span></span>

<span data-ttu-id="52991-134">Web サイトまたはサードパーティサービスのカスタムレコードを追加するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="52991-134">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="52991-135">Microsoft 管理センターにサインイン <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> します。</span><span class="sxs-lookup"><span data-stu-id="52991-135">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="52991-136">[**設定**]   >  [**ドメイン**] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="52991-136">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="52991-137">[ **ドメイン**] ページで、ドメインを選びます。</span><span class="sxs-lookup"><span data-stu-id="52991-137">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="52991-138">[ **DNS 設定**] で、[**カスタムレコード**] を選択します。次に、[**新しいカスタムレコード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="52991-138">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="52991-139">追加する DNS レコードの種類を選択し、新しいレコードの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="52991-139">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="52991-140">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="52991-140">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="52991-141">レジストラーとドメイン接続</span><span class="sxs-lookup"><span data-stu-id="52991-141">Registrars with Domain Connect</span></span>

<span data-ttu-id="52991-142">[ドメイン接続](https://www.domainconnect.org/)が有効な登録機関は、数分かかる3つのステップのプロセスで、ドメインを Microsoft 365 に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="52991-142">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="52991-143">このウィザードでは、ドメインを所有していることを確認し、ドメインのレコードを自動的に設定することを確認します。そのため、Microsoft 365 およびその他の Microsoft 365 サービス (Teams など) が自分のドメインで作業します。</span><span class="sxs-lookup"><span data-stu-id="52991-143">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="52991-144">セットアップ ウィザードを開始する前に、ブラウザーのポップアップ ブロック機能が無効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="52991-144">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="52991-145">Microsoft 365 と統合するドメイン接続レジストラー</span><span class="sxs-lookup"><span data-stu-id="52991-145">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="52991-146">1 &amp; IONOS</span><span class="sxs-lookup"><span data-stu-id="52991-146">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="52991-147">123Reg</span><span class="sxs-lookup"><span data-stu-id="52991-147">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="52991-148">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="52991-148">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="52991-149">WordPress</span><span class="sxs-lookup"><span data-stu-id="52991-149">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="52991-150">Plesk</span><span class="sxs-lookup"><span data-stu-id="52991-150">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="52991-151">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="52991-151">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="52991-152">SecureServer または WildWestDomains (SecureServer DNS ホスティングを使用する GoDaddy 販売店)</span><span class="sxs-lookup"><span data-stu-id="52991-152">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="52991-153">MadDog ドメイン</span><span class="sxs-lookup"><span data-stu-id="52991-153">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="52991-154">不正名</span><span class="sxs-lookup"><span data-stu-id="52991-154">CheapNames</span></span>](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="52991-155">電子メールと web サイトはどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="52991-155">What happens to my email and website?</span></span>

<span data-ttu-id="52991-156">セットアップが完了すると、ドメインの MX レコードが更新され、Microsoft 365 をポイントするようになり、ドメインのすべての電子メールが Microsoft 365 に送られ始めます。</span><span class="sxs-lookup"><span data-stu-id="52991-156">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="52991-157">自分のドメインで電子メールを取得するすべてのユーザーについて、Microsoft 365 でユーザーを追加し、メールボックスを設定していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="52991-157">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="52991-158">ビジネスで使用している Web サイトがある場合は、そのままの場所で稼働し続けます。</span><span class="sxs-lookup"><span data-stu-id="52991-158">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="52991-159">ドメイン接続のセットアップ手順は、web サイトには影響しません。</span><span class="sxs-lookup"><span data-stu-id="52991-159">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="52991-160">関連記事</span><span class="sxs-lookup"><span data-stu-id="52991-160">Related articles</span></span>

[<span data-ttu-id="52991-161">ドメイン FAQ</span><span class="sxs-lookup"><span data-stu-id="52991-161">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="52991-162">ドメインとは</span><span class="sxs-lookup"><span data-stu-id="52991-162">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="52991-163">Microsoft 365 でドメイン名を購入する</span><span class="sxs-lookup"><span data-stu-id="52991-163">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="52991-164">ドメインを設定する (ホストに固有の手順)</span><span class="sxs-lookup"><span data-stu-id="52991-164">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[<span data-ttu-id="52991-165">ドメインに関するヘルプを取得する</span><span class="sxs-lookup"><span data-stu-id="52991-165">Get help with domains</span></span>](../get-help-with-domains/get-help-with-domains.md)
