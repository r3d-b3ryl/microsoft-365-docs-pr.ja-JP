---
title: Microsoft 365 Business Basic のセットアップ
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
- BEA160
description: Microsoft 365 Business Basic サブスクリプションのセットアップ方法について説明します。
ms.openlocfilehash: f7569645753f292760f32ba932aac7b83c602b72
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393825"
---
# <a name="set-up-microsoft-365-business-basic"></a><span data-ttu-id="18b15-103">Microsoft 365 Business Basic のセットアップ</span><span class="sxs-lookup"><span data-stu-id="18b15-103">Set up Microsoft 365 Business Basic</span></span>

## <a name="watch-set-up-microsoft-365-business-basic"></a><span data-ttu-id="18b15-104">視聴する: Microsoft 365 Business Basic のセットアップ</span><span class="sxs-lookup"><span data-stu-id="18b15-104">Watch: Set up Microsoft 365 Business Basic</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vk3W]

<span data-ttu-id="18b15-105">このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](../../business-video/index.yml)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="18b15-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="18b15-106">ドメインを追加してサインインをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="18b15-106">Add your domain to personalize sign-in</span></span>

<span data-ttu-id="18b15-107">Microsoft 365 Business Basic を購入するときに、所有するドメインを使用するか、サインアップ時に購入するかを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="18b15-107">When you purchase Microsoft 365 Business Basic, you have the option of using a domain you own, or buying one during the sign-up.</span></span>

- <span data-ttu-id="18b15-108">サインアップ時に新しいドメインを購入した場合、お客様のドメインはすべてセットアップされており、[[ユーザーを追加してライセンスを割り当てる](#add-users-and-assign-licenses)] に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="18b15-108">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

 ::: moniker range="o365-worldwide"

1. <span data-ttu-id="18b15-109"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> から管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="18b15-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="18b15-110"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a> から管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="18b15-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="18b15-111"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> から管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="18b15-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end 

2. <span data-ttu-id="18b15-112">[**セットアップに移動**] を選択して、ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="18b15-112">Choose **Go to setup** to start the wizard.</span></span>
    
3. <span data-ttu-id="18b15-113">**ドメインの追加** ステップで、使用するドメイン名 (Contoso.com など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="18b15-113">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="18b15-p101">サインアップ時にドメインを購入した場合、ここでは **ドメインの追加** ステップは表示されません。[ユーザーの追加](#add-users-and-assign-licenses) に進んでください。</span><span class="sxs-lookup"><span data-stu-id="18b15-p101">If you purchased a domain during the sign-up, you will not see **Add a domain** step here. Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    
4. <span data-ttu-id="18b15-116">ウィザードの手順に従って[任意の DNS ホスティング プロバイダーで Office 365 用の DNS レコードを作成](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)し、ドメインの所有を確認します。</span><span class="sxs-lookup"><span data-stu-id="18b15-116">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="18b15-117">ドメイン ホストがわかっている場合は、「[Microsoft 365 にドメインを追加する](/microsoft-365/admin/setup/add-domain)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="18b15-117">If you know your domain host, see also [Add a domain to Microsoft 365](/microsoft-365/admin/setup/add-domain).</span></span>

    <span data-ttu-id="18b15-118">ご利用のホスティング プロバイダーが GoDaddy または [Domain Connect](/office365/admin/get-help-with-domains/domain-connect) を有効にした別のホストである場合、プロセスは簡単です。サインインし、お客様に代わって Microsoft が認証するよう自動的に求められます。</span><span class="sxs-lookup"><span data-stu-id="18b15-118">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![GoDaddy の [Confirm Access] (アクセスの確認) ページで、[承認] を選択します。](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a><span data-ttu-id="18b15-120">ユーザーを追加してライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="18b15-120">Add users and assign licenses</span></span>

<span data-ttu-id="18b15-121">ウィザードでユーザーを追加することもできますが、管理センターで[後からユーザーを追加](../add-users/add-users.md)することもできます。</span><span class="sxs-lookup"><span data-stu-id="18b15-121">You can add users in the wizard, but you can also [add users later](../add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="18b15-122">さらに、ローカル ドメイン コントローラーを持っている場合には、[Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express) を使用してユーザーを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="18b15-122">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

## <a name="add-users-in-the-wizard"></a><span data-ttu-id="18b15-123">ウィザードでユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="18b15-123">Add users in the wizard</span></span>

<span data-ttu-id="18b15-124">ウィザードで追加したユーザーには、Microsoft 365 Business Basic ライセンスが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="18b15-124">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Basic license.</span></span>

1. <span data-ttu-id="18b15-p104">Microsoft 365 Business Basic のサブスクリプションに既存ユーザーがいる場合 (たとえば、Azure AD Connect を使用した場合)、今すぐこれらのユーザーにライセンスを割り当てるオプションが表示されます。続行して、これらのユーザーにもライセンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="18b15-p104">If your Microsoft 365 Business Basic subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="18b15-p105">ユーザーを追加した後、資格証明書をそれらの新規ユーザーに共有するオプションが提供されます。それらをプリントアウトや電子メールで通知、またはダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="18b15-p105">After you've added the users, you'll also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>

## <a name="connect-your-domain"></a><span data-ttu-id="18b15-129">ドメインを接続する</span><span class="sxs-lookup"><span data-stu-id="18b15-129">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="18b15-130">.onmicrosoft ドメインの使用を選択した場合、またはユーザーの設定に Azure AD Connect を使用した場合、このステップは表示されません。</span><span class="sxs-lookup"><span data-stu-id="18b15-130">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="18b15-131">サービスを設定するには、DNS ホストまたはドメイン レジストラーにあるレコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18b15-131">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="18b15-132">セットアップ ウィザードでは通常、ユーザーのレジストラーが検出され、レジストラーの Web サイトで NS レコードを更新するための詳しい操作手順へのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="18b15-132">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="18b15-133">表示されない場合には、[任意のドメイン レジストラーで Office 365 をセットアップするためにネームサーバーを変更](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md)します。</span><span class="sxs-lookup"><span data-stu-id="18b15-133">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="18b15-134">既存の DNS レコード (たとえば、既存の Web サイト) を持っているのに、DNS ホストが [Domain Connect](/office365/admin/get-help-with-domains/domain-connect) に対して有効になっている場合には、[**レコードを追加してもらう**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="18b15-134">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="18b15-135">[**オンライン サービスの選択**] ページで、すべて規定値のまま [**次へ**] を選択し、DNS ホストのページで [**承認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="18b15-135">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="18b15-p108">他の DNS ホストとの間に既存の DNS レコードがある場合 (Domain Connect では有効になっていません)、既存のサービスが接続されたままになっていることを確認するために、自分の DNS レコードを管理したいと思うかもしれません。詳しくは [ドメインの基礎](/office365/admin/get-help-with-domains/dns-basics) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18b15-p108">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected. See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

2. <span data-ttu-id="18b15-138">ウィザードの手順に従えば、メールやその他のサービスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="18b15-138">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

    <span data-ttu-id="18b15-139">サインアップ プロセスが完了すると、管理センターに移動します。ここでは、ユーザーの追加やライセンスの割り当てを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="18b15-139">When the signup process is complete, you'll be directed to the admin center, where you can add users, and assign licenses.</span></span> <span data-ttu-id="18b15-140">初期セットアップが完了したら、管理センターの [**セットアップ**] ページを使用して、サブスクリプションに付属するサービスの設定と構成を継続できます。</span><span class="sxs-lookup"><span data-stu-id="18b15-140">After you complete the initial setup, you can use the **Setup** page in the admin center to continue setting up and configuring the services that come with your subscriptions.</span></span>

    <span data-ttu-id="18b15-141">セットアップ ウィザードおよび管理センターの **[セットアップ]** ページの詳細については、「[セットアップ ウィザードと [セットアップ] ページの違い](o365-setup-wizard-and-setup-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18b15-141">For more information about the setup wizard and the admin center **Setup** page, see [Difference between the setup wizard and the Setup page](o365-setup-wizard-and-setup-page.md).</span></span>