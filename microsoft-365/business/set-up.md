---
title: Microsoft 365 Business Premium のセットアップ
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: ドメインとユーザーの追加、セキュリティポリシーの設定など、Microsoft 365 Business Premium のセットアップ手順について説明します。
ms.openlocfilehash: efa7934ece0dfeac3c4b20daa37da6f1160901e7
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079811"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="a5bf1-103">セットアップウィザードで Microsoft 365 Business Premium をセットアップする</span><span class="sxs-lookup"><span data-stu-id="a5bf1-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="a5bf1-104">Microsoft 365 Business Premium のセットアップの概要については、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

<span data-ttu-id="a5bf1-105">このビデオがお役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="a5bf1-106">ドメイン、ユーザーを追加し、ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="a5bf1-106">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="a5bf1-107">Microsoft 365 Business Premium を購入する場合は、所有しているドメインを使用するか、[サインアップ](sign-up.md)中に1つ購入するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-107">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="a5bf1-108">サインアップ時に新しいドメインを購入した場合、お客様のドメインはすべてセットアップされており、[[ユーザーを追加してライセンスを割り当てる](#add-users-and-assign-licenses)] に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-108">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="a5bf1-109">ドメインを追加してサインインをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="a5bf1-109">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="a5bf1-110">グローバル管理者の資格情報を使用して、[Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-110">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="a5bf1-111">[**セットアップに移動**] を選択して、ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-111">Choose **Go to setup** to start the wizard.</span></span>

    ![[セットアップに移動] を選択します。](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="a5bf1-113">[**Office アプリのインストール**] ページでは、オプションで自分のコンピューターにアプリをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-113">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="a5bf1-114">**ドメインの追加**ステップで、使用するドメイン名 (Contoso.com など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-114">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a5bf1-115">サインアップ時にドメインを購入した場合、ここでは**ドメインの追加**ステップは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-115">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="a5bf1-116">代わりに [[ユーザーの追加](#add-users-and-assign-licenses)] に移動します。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-116">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![[サインインのカスタマイズ] ページのスクリーンショット。](../media/adddomain.png)

    
4. <span data-ttu-id="a5bf1-118">ウィザードの手順に従って、ドメインを所有していることを確認する[Microsoft 365 の任意の dns ホスティングプロバイダーで dns レコードを作成](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)します。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-118">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Microsoft 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="a5bf1-119">ドメイン ホストがわかっている場合は、「[ホスト特有の手順](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-119">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="a5bf1-120">ご利用のホスティング プロバイダーが GoDaddy または [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect) を有効にした別のホストである場合、プロセスは簡単です。サインインし、お客様に代わって Microsoft が認証するよう自動的に求められます。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-120">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![GoDaddy の [Confirm Access] (アクセスの確認) ページで、[承認] を選択します。](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="a5bf1-122">ユーザーを追加してライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a5bf1-122">Add users and assign licenses</span></span>

<span data-ttu-id="a5bf1-123">ウィザードでユーザーを追加することもできますが、管理センターで[後からユーザーを追加](add-users-m365b.md)することもできます。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-123">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="a5bf1-124">さらに、ローカル ドメイン コントローラーを持っている場合には、[Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) を使用してユーザーを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-124">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="a5bf1-125">ウィザードでユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="a5bf1-125">Add users in the wizard</span></span>

<span data-ttu-id="a5bf1-126">ウィザードで追加したユーザーには、Microsoft 365 Business Premium ライセンスが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-126">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![ウィザードの [新しいユーザーの追加] ページのスクリーンショット](../media/addnewuserspage.png)

1. <span data-ttu-id="a5bf1-128">Microsoft 365 Business Premium サブスクリプションに既存のユーザーが含まれている場合 (たとえば、Azure AD Connect を使用した場合)、すぐにライセンスを割り当てるオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-128">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="a5bf1-129">続行して、これらのユーザーにもライセンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-129">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="a5bf1-130">ユーザーを追加すると、追加した新しいユーザーと資格情報を共有するためのオプションも表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-130">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="a5bf1-131">それらを印刷したり、メールで送信したり、ダウンロードしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-131">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="a5bf1-132">ドメインを接続する</span><span class="sxs-lookup"><span data-stu-id="a5bf1-132">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="a5bf1-133">.onmicrosoft ドメインの使用を選択した場合、またはユーザーの設定に Azure AD Connect を使用した場合、このステップは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-133">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="a5bf1-134">サービスを設定するには、DNS ホストまたはドメイン レジストラーにあるレコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-134">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="a5bf1-135">セットアップ ウィザードでは通常、ユーザーのレジストラーが検出され、レジストラーの Web サイトで NS レコードを更新するための詳しい操作手順へのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-135">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="a5bf1-136">含まれていない場合は、ネームサーバーを[変更して、Microsoft 365 を任意のドメインレジストラーで](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar)セットアップします。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-136">If it doesn't, [Change nameservers to set up Microsoft 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span></span> 

    - <span data-ttu-id="a5bf1-137">既存の DNS レコード (たとえば、既存の Web サイト) を持っているのに、DNS ホストが [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect) に対して有効になっている場合には、[**レコードを追加してもらう**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-137">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="a5bf1-138">[**オンライン サービスの選択**] ページで、すべて規定値のまま [**次へ**] を選択し、DNS ホストのページで [**承認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-138">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="a5bf1-139">他の DNS ホストとの間に既存の DNS レコードがある場合 (Domain Connect では有効になっていません)、既存のサービスが接続されたままになっていることを確認するために、自分の DNS レコードを管理したいと思うかもしれません。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-139">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="a5bf1-140">詳細については、「[domain basics (ドメインの基本)](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-140">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![レコードのアクティブ化ページ。](../media/activaterecords.png)

2. <span data-ttu-id="a5bf1-142">ウィザードの手順に従えば、メールやその他のサービスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-142">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="a5bf1-143">組織を保護する</span><span class="sxs-lookup"><span data-stu-id="a5bf1-143">Protect your organization</span></span> 

<span data-ttu-id="a5bf1-144">ウィザードで設定したポリシーは、*すべてのユーザー*と呼ばれる[セキュリティグループ](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups)に自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-144">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="a5bf1-145">管理センターで、ポリシーを割り当てるための追加のグループを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-145">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="a5bf1-146">**高度なサイバー脅威からの保護を強化**するには、office [365 の事前の脅威保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)で office アプリのファイルとリンクをスキャンできるように、既定値をそのまま使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-146">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) scan files and links in Office apps.</span></span>

    ![保護ページの拡大のスクリーンショット。](../media/increasetreatprotection.png)


2. <span data-ttu-id="a5bf1-148">[**機密データのリークを防止**する] ページで、既定値をそのまま使用して Office 365 データ損失防止 (DLP) を有効にし、office アプリの機密データを追跡し、誤って組織外で共有されないようにします。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-148">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="a5bf1-149">[ **Office for mobile のデータを保護**する] ページで、[モバイルアプリの管理] を選択したまま、設定を展開して確認し、[**モバイルアプリ管理ポリシーの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-149">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![[Office for mobile のデータを保護する] ページのスクリーンショット](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="a5bf1-151">Windows 10 Pc をセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="a5bf1-151">Secure Windows 10 PCs</span></span>

<span data-ttu-id="a5bf1-152">左側のナビゲーションで、[**セットアップ**] を選択し、[**サインインとセキュリティ**] で [ **Windows 10 コンピューターのセキュリティ保護**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-152">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="a5bf1-153">[**表示**] を選んで開始します。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-153">Choose **View** to get started.</span></span> <span data-ttu-id="a5bf1-154">詳細な手順については[、「Windows 10 コンピューターのセキュリティ保護](secure-win-10-pcs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-154">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="a5bf1-155">Office 365 クライアントアプリを展開する</span><span class="sxs-lookup"><span data-stu-id="a5bf1-155">Deploy Office 365 client apps</span></span>

<span data-ttu-id="a5bf1-156">セットアップ時に Office アプリを自動的にインストールすることを選択した場合、ユーザーが作業の資格情報を使用して、Windows デバイスから Azure AD にサインインすると、アプリが Windows 10 デバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-156">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="a5bf1-157">モバイル iOS または Android デバイスに Office をインストールするには、「 [Microsoft 365 Business Premium ユーザーのモバイルデバイスのセットアップ](set-up-mobile-devices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-157">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="a5bf1-158">Office を個別にインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-158">You can also install Office individually.</span></span> <span data-ttu-id="a5bf1-159">手順について[は、「PC または Mac に Office をインストールする](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5bf1-159">See [install Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5bf1-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5bf1-160">See also</span></span>

[<span data-ttu-id="a5bf1-161">一般法人向け Microsoft 365 のトレーニング ビデオ</span><span class="sxs-lookup"><span data-stu-id="a5bf1-161">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
