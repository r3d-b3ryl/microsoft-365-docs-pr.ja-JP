---
title: Microsoft 365 Business をセットアップする
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Microsoft 365 Business をセットアップする方法について説明します。
ms.openlocfilehash: f29dbdb61636fdfe573a1a6920d0aed963b737ad
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2019
ms.locfileid: "38721491"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a><span data-ttu-id="e40d6-103">セットアップウィザードで Microsoft 365 Business をセットアップする</span><span class="sxs-lookup"><span data-stu-id="e40d6-103">Set up Microsoft 365 Business in the setup wizard</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="e40d6-104">ドメイン、ユーザーを追加し、ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="e40d6-104">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="e40d6-105">[![管理センターについて知らせるラベルが変更されていますので、詳細については、aka.ms/aboutM365preview を参照してください。](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="e40d6-105">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="e40d6-106">Microsoft 365 Business を購入する場合は、所有しているドメインを使用するか、[サインアップ](sign-up.md)中に購入するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-106">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="e40d6-107">サインアップ時に新しいドメインを購入した場合、ドメインはすべてセットアップされており、ユーザーを[追加してライセンスを割り当てる](#add-users-and-assign-licenses)ことができます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-107">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="e40d6-108">サインインを個人用に設定するためにドメインを追加する</span><span class="sxs-lookup"><span data-stu-id="e40d6-108">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="e40d6-109">グローバル管理者の資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="e40d6-109">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="e40d6-110">[**ドメインの追加**] または [**ユーザーの追加**] を選択して、ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="e40d6-110">Choose **Add a domain** or **Add users** to start the wizard.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="e40d6-111">サインアップ中にドメインを購入した場合は、ここに [**ドメインの追加**] 手順は表示されません。</span><span class="sxs-lookup"><span data-stu-id="e40d6-111">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="e40d6-112">代わりに、[[ユーザーの追加](#add-users-and-assign-licenses)] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e40d6-112">Go to [Add users ](#add-users-and-assign-licenses) instead.</span></span>

    ![[セットアップに移動] を選択します。](media/gotosetupinadmincenter.png)
    
3. <span data-ttu-id="e40d6-114">ウィザードで、使用するドメイン名 (contoso.com など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="e40d6-114">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![[サインインのカスタマイズ] ページのスクリーンショット。](media/personalizesignin.png)

    
4. <span data-ttu-id="e40d6-116">ウィザードの手順に従って、ドメインを所有していることを確認する[Office 365 用の任意の dns ホスティングプロバイダーで dns レコードを作成](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)します。</span><span class="sxs-lookup"><span data-stu-id="e40d6-116">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="e40d6-117">ドメインホストがわかっている場合は、「[ホスト固有の指示](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="e40d6-117">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="e40d6-118">ホスティングプロバイダーが GoDaddy、または[ドメイン接続](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)を使用して他のホストが有効になっている場合、このプロセスは簡単であり、サインインして Microsoft に代わって認証を行うように自動的に求められます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-118">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![[GoDaddy のアクセス確認] ページで、[承認] を選択します。](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="e40d6-120">ユーザーを追加して、ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e40d6-120">Add users and assign licenses</span></span>

<span data-ttu-id="e40d6-121">ウィザードでユーザーを追加することはできますが、[後](add-users-m365b.md)で管理センターでユーザーを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-121">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="e40d6-122">また、ローカルドメインコントローラーがある場合は、 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)を使用してユーザーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-122">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="e40d6-123">ウィザードでユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="e40d6-123">Add users in the wizard</span></span>

<span data-ttu-id="e40d6-124">ウィザードで追加したユーザーには、Microsoft 365 のビジネスライセンスが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-124">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>

![ウィザードの [新しいユーザーの追加] ページのスクリーンショット](media/addnewuserspage.png)

1. <span data-ttu-id="e40d6-126">Microsoft 365 Business サブスクリプションに既存のユーザーが存在する場合 (たとえば、Azure AD Connect を使用した場合)、すぐにライセンスを割り当てるオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-126">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="e40d6-127">続行して、これらのユーザーにもライセンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="e40d6-127">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="e40d6-128">ユーザーを追加すると、追加した新しいユーザーと資格情報を共有するためのオプションも表示されます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-128">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="e40d6-129">それらを印刷、メール、またはダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-129">You can choose to print them out, email them, or download them.</span></span>

3. <span data-ttu-id="e40d6-130">[組織のチームの作成] で、Teams を追加してユーザーを追加することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-130">On the Create Teams for your organization, you can choose to add Teams and add users to them.</span></span> <span data-ttu-id="e40d6-131">これは後で行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-131">You can also do this later.</span></span> <span data-ttu-id="e40d6-132">詳細については、「[会社全体のチームを作成する](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e40d6-132">For more information, see [create a company-wide Team](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3).</span></span>

4. <span data-ttu-id="e40d6-133">移行のメール メッセージをスキップして、[ **メール メッセージの移行**] ページで [ **次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-133">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="e40d6-134">別のメールプロバイダーから移行していて、後でデータをコピーする場合は、[メールと連絡先を Office 365 に移行](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)できます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-134">If you're moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>


### <a name="connect-your-domain"></a><span data-ttu-id="e40d6-135">ドメインを接続する</span><span class="sxs-lookup"><span data-stu-id="e40d6-135">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="e40d6-136">. Onmicrosoft ドメインを使用することを選択した場合、または Azure AD Connect を使用してユーザーを設定した場合は、この手順は表示されません。</span><span class="sxs-lookup"><span data-stu-id="e40d6-136">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="e40d6-137">サービスを設定するには、DNS ホストまたはドメイン レジストラーにあるレコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e40d6-137">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="e40d6-138">セットアップ ウィザードでは通常、ユーザーのレジストラーが検出され、レジストラーの Web サイトで NS レコードを更新するための詳しい操作手順へのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-138">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="e40d6-139">含まれていない場合は、ネームサーバーを[変更して、任意のドメインレジストラーで Office 365](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="e40d6-139">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="e40d6-140">既存の DNS レコード (既存の web サイトなど) があるが、DNS ホストが[ドメイン接続](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)に対して有効になっている場合は、[**レコードの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e40d6-140">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="e40d6-141">[**オンラインサービスの選択**] ページで、すべての既定値をそのまま使用し、[**次へ**] を選択して、DNS ホストのページで [**承認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e40d6-141">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="e40d6-142">他の DNS ホスト (ドメイン接続に対して有効になっていません) に既存の dns レコードがある場合は、独自の DNS レコードを管理して、既存のサービスが常に接続していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e40d6-142">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="e40d6-143">詳細については、「[ドメインの基礎](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e40d6-143">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![自分の DNS レコードを管理するドメインページに接続します。](media/connectyourdomainpage.png)

2. <span data-ttu-id="e40d6-145">ウィザードの手順を実行すると、電子メールとその他のサービスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-145">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-data-and-devices"></a><span data-ttu-id="e40d6-146">データとデバイスを保護する</span><span class="sxs-lookup"><span data-stu-id="e40d6-146">Protect data and devices</span></span> 

<span data-ttu-id="e40d6-147">ウィザードで設定したポリシーは、*すべてのユーザー*と呼ばれる[セキュリティグループ](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups)に自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-147">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="e40d6-148">管理センターで、ポリシーを割り当てるための追加のグループを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-148">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="e40d6-149">[**モバイルデバイス上の作業ファイルを保護**する] で、[**デバイスが失われたとき、または盗まれたときに作業ファイルを保護する**] オプションが既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="e40d6-149">On the **Protect your work files on mobile devices**, the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="e40d6-150">[**ユーザーがモバイルデバイスで Office ファイルにアクセスする方法を管理**する] をオンにすることもできます。これは推奨されています。</span><span class="sxs-lookup"><span data-stu-id="e40d6-150">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    ![[モバイルデバイスの作業ファイルを保護する] ページのスクリーンショット](media/protectworkfilesondevices.png)

     - <span data-ttu-id="e40d6-152">**デバイスが紛失または盗難時**に[既定値](protect-work-files-on-lost-or-stolen-device.md)を表示するように、[作業ファイルの保護] を展開します。</span><span class="sxs-lookup"><span data-stu-id="e40d6-152">Expand **Protect work files when devices are lost or stolen** to display the [default values](protect-work-files-on-lost-or-stolen-device.md):</span></span>

        ![失われたデバイスでファイルを保護するための既定値のスクリーンショット。](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="e40d6-154">[**ユーザーがモバイルデバイスで Office ファイルにアクセスする方法を管理**する] を選択し、これを展開して[既定値](manage-user-access-on-mobile-devices.md)を表示します。</span><span class="sxs-lookup"><span data-stu-id="e40d6-154">Select **Manage how users access Office files on mobile devices** and expand it to display the [default values](manage-user-access-on-mobile-devices.md).</span></span> <span data-ttu-id="e40d6-155">すべてのユーザーに適用される Android、iOS、Windows 10 のアプリケーションポリシーを作成するには、セットアップ時に既定値を受け入れることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e40d6-155">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="e40d6-156">セットアップが完了したら、追加のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-156">You can create more policies after setup completes.</span></span>

        ![モバイルでの Office ファイルの保護設定のスクリーンショット。](media/useraccessonmobile.png)

2. <span data-ttu-id="e40d6-158">データとデバイスを保護するための最後の手順では、Windows 10 デバイスをセキュリティで保護するためのポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-158">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="e40d6-159">これらの設定は、ユーザーの Windows 10 が組織に接続すると自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-159">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="e40d6-160">**セキュリティで保護された Windows 10 デバイス**を拡張して、[既定値](secure-windows-10-devices.md)を表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-160">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="e40d6-161">Windows 10 デバイスで[Office を自動的にインストール](install-office-on-windows-10-during-setup.md)するように選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-161">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    ![Windows 10 デバイス構成ページの設定のスクリーンショット。](media/setwin10config.png)


## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="e40d6-163">Office 365 クライアントアプリを展開する</span><span class="sxs-lookup"><span data-stu-id="e40d6-163">Deploy Office 365 client apps</span></span>

<span data-ttu-id="e40d6-164">セットアップ時に Office アプリを自動的にインストールすることを選択した場合、ユーザーが作業の資格情報を使用して、Windows デバイスから Azure AD にサインインすると、アプリが Windows 10 デバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-164">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="e40d6-165">モバイル iOS または Android デバイスに Office をインストールするには、「 [Microsoft 365 Business ユーザーのモバイルデバイスをセットアップ](set-up-mobile-devices.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e40d6-165">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="e40d6-166">Office を個別にインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e40d6-166">You can also install Office individually.</span></span> <span data-ttu-id="e40d6-167">手順について[は、「PC または Mac に Office をインストールする](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e40d6-167">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>
