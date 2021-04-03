---
title: Microsoft 365 Business Premium のセットアップ
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: ドメインとユーザーの追加、セキュリティ ポリシーの設定など、Microsoft 365 Business Premium のセットアップ手順について説明します。
ms.openlocfilehash: c8e2ca94f4947d4f9c69915d2fef410a6075bfed
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579916"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="d3963-103">セットアップ ウィザードで Microsoft 365 Business Premium をセットアップする</span><span class="sxs-lookup"><span data-stu-id="d3963-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="d3963-104">Microsoft 365 Business Premium のセットアップの概要については、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d3963-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="d3963-105">ドメイン、ユーザー、およびポリシーの設定を追加する</span><span class="sxs-lookup"><span data-stu-id="d3963-105">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="d3963-106">Microsoft 365 Business Premium を購入する場合は、所有するドメインを使用するか、サインアップ時に購入 [するかのオプションがあります](sign-up.md)。</span><span class="sxs-lookup"><span data-stu-id="d3963-106">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="d3963-107">サインアップ時に新しいドメインを購入した場合、お客様のドメインはすべてセットアップされており、[[ユーザーを追加してライセンスを割り当てる](#add-users-and-assign-licenses)] に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="d3963-107">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="d3963-108">ドメインを追加してサインインをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="d3963-108">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="d3963-109">グローバル管理者の資格情報を使用して、[Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="d3963-109">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="d3963-110">[**セットアップに移動**] を選択して、ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="d3963-110">Choose **Go to setup** to start the wizard.</span></span>

    ![[セットアップに移動] を選択します。](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="d3963-112">[**Office アプリのインストール**] ページでは、オプションで自分のコンピューターにアプリをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="d3963-112">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="d3963-113">**ドメインの追加** ステップで、使用するドメイン名 (Contoso.com など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="d3963-113">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d3963-114">サインアップ時にドメインを購入した場合、ここでは **ドメインの追加** ステップは表示されません。</span><span class="sxs-lookup"><span data-stu-id="d3963-114">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="d3963-115">代わりに [[ユーザーの追加](#add-users-and-assign-licenses)] に移動します。</span><span class="sxs-lookup"><span data-stu-id="d3963-115">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![[サインインのカスタマイズ] ページのスクリーンショット。](../media/adddomain.png)

    
4. <span data-ttu-id="d3963-117">ウィザードの手順に従って、ドメインを所有している Microsoft [365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) の任意の DNS ホスティング プロバイダーで DNS レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="d3963-117">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Microsoft 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="d3963-118">ドメイン ホストがわかっている場合は、「[ホスト特有の手順](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3963-118">If you know your domain host, see also the [host specific instructions](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="d3963-119">ご利用のホスティング プロバイダーが GoDaddy または [Domain Connect](/office365/admin/get-help-with-domains/domain-connect) を有効にした別のホストである場合、プロセスは簡単です。サインインし、お客様に代わって Microsoft が認証するよう自動的に求められます。</span><span class="sxs-lookup"><span data-stu-id="d3963-119">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![GoDaddy の [Confirm Access] (アクセスの確認) ページで、[承認] を選択します。](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="d3963-121">ユーザーを追加してライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="d3963-121">Add users and assign licenses</span></span>

<span data-ttu-id="d3963-122">ウィザードでユーザーを追加することもできますが、管理センターで[後からユーザーを追加](../admin/add-users/add-users.md)することもできます。</span><span class="sxs-lookup"><span data-stu-id="d3963-122">You can add users in the wizard, but you can also [add users later](../admin/add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="d3963-123">さらに、ローカル ドメイン コントローラーを持っている場合には、[Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express) を使用してユーザーを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="d3963-123">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="d3963-124">ウィザードでユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="d3963-124">Add users in the wizard</span></span>

<span data-ttu-id="d3963-125">ウィザードに追加したユーザーには、Microsoft 365 Business Premium ライセンスが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d3963-125">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![ウィザードの [新しいユーザーの追加] ページのスクリーンショット](../media/addnewuserspage.png)

1. <span data-ttu-id="d3963-127">Microsoft 365 Business Premium サブスクリプションに既存のユーザーが含まれています (たとえば、Azure AD Connect を使用した場合)、ライセンスを今すぐ割り当てるオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3963-127">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="d3963-128">続行して、これらのユーザーにもライセンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="d3963-128">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="d3963-129">ユーザーを追加すると、追加した新しいユーザーと資格情報を共有するためのオプションも表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3963-129">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="d3963-130">それらを印刷したり、メールで送信したり、ダウンロードしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="d3963-130">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="d3963-131">ドメインを接続する</span><span class="sxs-lookup"><span data-stu-id="d3963-131">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="d3963-132">.onmicrosoft ドメインの使用を選択した場合、またはユーザーの設定に Azure AD Connect を使用した場合、このステップは表示されません。</span><span class="sxs-lookup"><span data-stu-id="d3963-132">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="d3963-133">サービスを設定するには、DNS ホストまたはドメイン レジストラーにあるレコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3963-133">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="d3963-134">セットアップ ウィザードでは通常、ユーザーのレジストラーが検出され、レジストラーの Web サイトで NS レコードを更新するための詳しい操作手順へのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3963-134">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="d3963-135">設定しない場合は、任意のドメイン レジストラーを使用して [Microsoft 365](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md)をセットアップするためにネーム サーバーを変更します。</span><span class="sxs-lookup"><span data-stu-id="d3963-135">If it doesn't, [Change nameservers to set up Microsoft 365 with any domain registrar](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="d3963-136">既存の DNS レコード (たとえば、既存の Web サイト) を持っているのに、DNS ホストが [Domain Connect](/office365/admin/get-help-with-domains/domain-connect) に対して有効になっている場合には、[**レコードを追加してもらう**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3963-136">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="d3963-137">[**オンライン サービスの選択**] ページで、すべて規定値のまま [**次へ**] を選択し、DNS ホストのページで [**承認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3963-137">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="d3963-138">他の DNS ホストとの間に既存の DNS レコードがある場合 (Domain Connect では有効になっていません)、既存のサービスが接続されたままになっていることを確認するために、自分の DNS レコードを管理したいと思うかもしれません。</span><span class="sxs-lookup"><span data-stu-id="d3963-138">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="d3963-139">詳細については、「[domain basics (ドメインの基本)](/office365/admin/get-help-with-domains/dns-basics)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3963-139">See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![[レコードのアクティブ化] ページ。](../media/activaterecords.png)

2. <span data-ttu-id="d3963-141">ウィザードの手順に従えば、メールやその他のサービスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="d3963-141">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="d3963-142">組織を保護する</span><span class="sxs-lookup"><span data-stu-id="d3963-142">Protect your organization</span></span> 

<span data-ttu-id="d3963-143">ウィザードで設定したポリシーは、[すべてのユーザー] というセキュリティ [グループ](/office365/admin/create-groups/compare-groups#security-groups) に自動的 *に適用されます*。</span><span class="sxs-lookup"><span data-stu-id="d3963-143">The policies you set up in the wizard are applied automatically to a [Security group](/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="d3963-144">管理センターでポリシーを割り当てる追加のグループを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d3963-144">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="d3963-145">高度な **サイバー脅威** からの保護の強化では [、Office 365 Advance Threat Protection](../security/office-365-security/defender-for-office-365.md) スキャン ファイルとリンクを Office アプリで許可する既定値を受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3963-145">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](../security/office-365-security/defender-for-office-365.md) scan files and links in Office apps.</span></span>

    ![[保護の強化] ページのスクリーンショット。](../media/increasetreatprotection.png)


2. <span data-ttu-id="d3963-147">[機密データの漏洩を防ぐ] ページで、Office 365 データ損失防止 (DLP) を有効にする既定値を受け入れて、Office アプリの機密データを追跡し、組織外でこれらのデータを偶発的に共有しないようにします。</span><span class="sxs-lookup"><span data-stu-id="d3963-147">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="d3963-148">[モバイル 用 **データの保護] Office** ページで、モバイル アプリの管理をオンのままにし、設定を展開して確認し、[モバイル アプリ管理ポリシーの作成] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d3963-148">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![モバイル ページのデータを保護Officeのスクリーンショット。](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="d3963-150">Windows 10 PC をセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="d3963-150">Secure Windows 10 PCs</span></span>

<span data-ttu-id="d3963-151">左側のナビゲーションで、[セットアップ **]** を選択し、[サインインとセキュリティ] の下の **[Windows 10** コンピューターのセキュリティ保護] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3963-151">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="d3963-152">[表示 **] を** 選択して開始します。</span><span class="sxs-lookup"><span data-stu-id="d3963-152">Choose **View** to get started.</span></span> <span data-ttu-id="d3963-153">詳細 [な手順については、「Windows 10 コンピューターをセキュリティ](secure-win-10-pcs.md) で保護する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3963-153">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="d3963-154">365 Office アプリを展開する</span><span class="sxs-lookup"><span data-stu-id="d3963-154">Deploy Office 365 client apps</span></span>

<span data-ttu-id="d3963-155">セットアップ中に Office アプリを自動的にインストールすることを選択した場合、ユーザーが作業資格情報を使用して Windows デバイスから Azure AD にサインインすると、アプリは Windows 10 デバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d3963-155">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="d3963-156">モバイル iOS Office Android デバイスにインストールするには [、「Microsoft 365 Business Premium](set-up-mobile-devices.md)ユーザー向けモバイル デバイスのセットアップ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3963-156">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="d3963-157">また、個別にOfficeインストールできます。</span><span class="sxs-lookup"><span data-stu-id="d3963-157">You can also install Office individually.</span></span> <span data-ttu-id="d3963-158">手順 [については、「pc Office Mac にインストールする](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3963-158">See [install Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3963-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3963-159">See also</span></span>

[<span data-ttu-id="d3963-160">一般法人向け Microsoft 365 のトレーニング ビデオ</span><span class="sxs-lookup"><span data-stu-id="d3963-160">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
