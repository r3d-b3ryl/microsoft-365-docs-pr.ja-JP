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
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: ドメインとユーザーの追加、セキュリティポリシーの設定など、Microsoft 365 Business Premium のセットアップ手順について説明します。
ms.openlocfilehash: cfc8523fe88ebca6b8c03db0ad0f6caeba662923
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048039"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="f8a0d-103">セットアップウィザードで Microsoft 365 Business Premium をセットアップする</span><span class="sxs-lookup"><span data-stu-id="f8a0d-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="f8a0d-104">Microsoft 365 Business Premium のセットアップの概要については、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

<span data-ttu-id="f8a0d-105">このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="f8a0d-106">ドメイン、ユーザーを追加し、ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="f8a0d-106">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="f8a0d-107">[![管理センターについて知らせるラベルが変更されていますので、詳細については、aka.ms/aboutM365preview を参照してください。](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="f8a0d-107">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="f8a0d-108">Microsoft 365 Business Premium を購入する場合は、所有しているドメインを使用するか、[サインアップ](sign-up.md)中に1つ購入するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-108">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="f8a0d-109">サインアップ時に新しいドメインを購入した場合、ドメインはすべてセットアップされており、ユーザーを[追加してライセンスを割り当てる](#add-users-and-assign-licenses)ことができます。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-109">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="f8a0d-110">サインインを個人用に設定するためにドメインを追加する</span><span class="sxs-lookup"><span data-stu-id="f8a0d-110">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="f8a0d-111">グローバル管理者の資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-111">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="f8a0d-112">[**セットアップに移動**] を選択してウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-112">Choose **Go to setup** to start the wizard.</span></span>

    ![[セットアップに移動] を選択します。](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="f8a0d-114">[ **Office アプリのインストール**] ページで、必要に応じて、自分のコンピューターにアプリをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-114">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="f8a0d-115">[**ドメインの追加**] ステップで、使用するドメイン名 (contoso.com など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-115">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f8a0d-116">サインアップ中にドメインを購入した場合は、ここに [**ドメインの追加**] 手順は表示されません。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-116">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="f8a0d-117">代わりに、[[ユーザーの追加](#add-users-and-assign-licenses)] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-117">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![[サインインのカスタマイズ] ページのスクリーンショット。](../media/adddomain.png)

    
4. <span data-ttu-id="f8a0d-119">ウィザードの手順に従って、ドメインを所有していることを確認する[Office 365 用の任意の dns ホスティングプロバイダーで dns レコードを作成](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)します。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="f8a0d-120">ドメインホストがわかっている場合は、「[ホスト固有の指示](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-120">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="f8a0d-121">ホスティングプロバイダーが GoDaddy、または[ドメイン接続](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)を使用して他のホストが有効になっている場合、このプロセスは簡単であり、サインインして Microsoft に代わって認証を行うように自動的に求められます。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-121">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![[GoDaddy のアクセス確認] ページで、[承認] を選択します。](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="f8a0d-123">ユーザーを追加して、ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="f8a0d-123">Add users and assign licenses</span></span>

<span data-ttu-id="f8a0d-124">ウィザードでユーザーを追加することはできますが、[後](add-users-m365b.md)で管理センターでユーザーを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-124">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="f8a0d-125">また、ローカルドメインコントローラーがある場合は、 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)を使用してユーザーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-125">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="f8a0d-126">ウィザードでユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="f8a0d-126">Add users in the wizard</span></span>

<span data-ttu-id="f8a0d-127">ウィザードで追加したユーザーには、Microsoft 365 Business Premium ライセンスが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-127">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![ウィザードの [新しいユーザーの追加] ページのスクリーンショット](../media/addnewuserspage.png)

1. <span data-ttu-id="f8a0d-129">Microsoft 365 Business Premium サブスクリプションに既存のユーザーが含まれている場合 (たとえば、Azure AD Connect を使用した場合)、すぐにライセンスを割り当てるオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-129">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="f8a0d-130">続行して、これらのユーザーにもライセンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-130">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="f8a0d-131">ユーザーを追加すると、追加した新しいユーザーと資格情報を共有するためのオプションも表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-131">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="f8a0d-132">それらを印刷、メール、またはダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-132">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="f8a0d-133">ドメインを接続する</span><span class="sxs-lookup"><span data-stu-id="f8a0d-133">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="f8a0d-134">. Onmicrosoft ドメインを使用することを選択した場合、または Azure AD Connect を使用してユーザーを設定した場合は、この手順は表示されません。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="f8a0d-135">サービスを設定するには、DNS ホストまたはドメイン レジストラーにあるレコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="f8a0d-136">セットアップ ウィザードでは通常、ユーザーのレジストラーが検出され、レジストラーの Web サイトで NS レコードを更新するための詳しい操作手順へのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-136">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="f8a0d-137">含まれていない場合は、ネームサーバーを[変更して、任意のドメインレジストラーで Office 365](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-137">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="f8a0d-138">既存の DNS レコード (既存の web サイトなど) があるが、DNS ホストが[ドメイン接続](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)に対して有効になっている場合は、[**レコードの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-138">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="f8a0d-139">[**オンラインサービスの選択**] ページで、すべての既定値をそのまま使用し、[**次へ**] を選択して、DNS ホストのページで [**承認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-139">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="f8a0d-140">他の DNS ホスト (ドメイン接続に対して有効になっていません) に既存の dns レコードがある場合は、独自の DNS レコードを管理して、既存のサービスが常に接続していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-140">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="f8a0d-141">詳細については、「[ドメインの基礎](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-141">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![レコードのアクティブ化ページ。](../media/activaterecords.png)

2. <span data-ttu-id="f8a0d-143">ウィザードの手順を実行すると、電子メールとその他のサービスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-143">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="f8a0d-144">組織を保護する</span><span class="sxs-lookup"><span data-stu-id="f8a0d-144">Protect your organization</span></span> 

<span data-ttu-id="f8a0d-145">ウィザードで設定したポリシーは、*すべてのユーザー*と呼ばれる[セキュリティグループ](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups)に自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-145">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="f8a0d-146">管理センターで、ポリシーを割り当てるための追加のグループを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-146">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="f8a0d-147">**高度なサイバー脅威からの保護を強化**するには、office [365 の事前の脅威保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)で office アプリのファイルとリンクをスキャンできるように、既定値をそのまま使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-147">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) scan files and links in Office apps.</span></span>

    ![保護ページの拡大のスクリーンショット。](../media/increasetreatprotection.png)


2. <span data-ttu-id="f8a0d-149">[**機密データのリークを防止**する] ページで、既定値をそのまま使用して Office 365 データ損失防止 (DLP) を有効にし、office アプリの機密データを追跡し、誤って組織外で共有されないようにします。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-149">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="f8a0d-150">[ **Office for mobile のデータを保護**する] ページで、[モバイルアプリの管理] を選択したまま、設定を展開して確認し、[**モバイルアプリ管理ポリシーの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-150">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![[Office for mobile のデータを保護する] ページのスクリーンショット](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="f8a0d-152">Windows 10 Pc をセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="f8a0d-152">Secure Windows 10 PCs</span></span>

<span data-ttu-id="f8a0d-153">左側のナビゲーションで、[**セットアップ**] を選択し、[**サインインとセキュリティ**] で [ **Windows 10 コンピューターのセキュリティ保護**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-153">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="f8a0d-154">[**表示**] を選んで開始します。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-154">Choose **View** to get started.</span></span> <span data-ttu-id="f8a0d-155">詳細な手順については[、「Windows 10 コンピューターのセキュリティ保護](secure-win-10-pcs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-155">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="f8a0d-156">Office 365 クライアントアプリを展開する</span><span class="sxs-lookup"><span data-stu-id="f8a0d-156">Deploy Office 365 client apps</span></span>

<span data-ttu-id="f8a0d-157">セットアップ時に Office アプリを自動的にインストールすることを選択した場合、ユーザーが作業の資格情報を使用して、Windows デバイスから Azure AD にサインインすると、アプリが Windows 10 デバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-157">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="f8a0d-158">モバイル iOS または Android デバイスに Office をインストールするには、「 [Microsoft 365 Business Premium ユーザーのモバイルデバイスのセットアップ](set-up-mobile-devices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-158">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="f8a0d-159">Office を個別にインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-159">You can also install Office individually.</span></span> <span data-ttu-id="f8a0d-160">手順について[は、「PC または Mac に Office をインストールする](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8a0d-160">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8a0d-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8a0d-161">See also</span></span>

[<span data-ttu-id="f8a0d-162">一般法人向け Microsoft 365 のトレーニング ビデオ</span><span class="sxs-lookup"><span data-stu-id="f8a0d-162">Microsoft 365 for business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
