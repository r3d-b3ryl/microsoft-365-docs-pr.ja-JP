---
title: Microsoft 365 Business をセットアップする
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Microsoft 365 Business をセットアップする方法について説明します。
ms.openlocfilehash: e635b828609fc47cd8b92bb179a25bcc43cb0a1a
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660831"
---
# <a name="set-up-microsoft-365-business"></a><span data-ttu-id="7ac27-103">Microsoft 365 Business をセットアップする</span><span class="sxs-lookup"><span data-stu-id="7ac27-103">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="7ac27-104">開始する前に、「 [Microsoft 365 Business](get-microsoft-365-business.md)を使用してサインアップの詳細を取得する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ac27-104">Before you get started, see [Get Microsoft 365 Business](get-microsoft-365-business.md) for sign-up details.</span></span>

<span data-ttu-id="7ac27-105">セットアップウィザードを使用して[Microsoft 365 Business をセットアップする方法](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1)、およびオンプレミスの Active Directory を使用していない場合について、簡単なビデオを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-105">Watch a [short video on how to set up Microsoft 365 Business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) by using the set up wizard, and when you don't have an on-premises Active Directory</span></span>
  

## <a name="overview"></a><span data-ttu-id="7ac27-106">概要</span><span class="sxs-lookup"><span data-stu-id="7ac27-106">Overview</span></span>

<span data-ttu-id="7ac27-107">セットアップ手順のほとんどはセットアップウィザードで行うことができますが、その他のオプションも表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-107">Most of the set up steps can be done in the setup wizard, but the other options are also listed.</span></span>

1. <span data-ttu-id="7ac27-108">[ドメインを追加する](#add-your-domain-to-personalize-sign-in)([サインアップ](sign-up.md)中にドメインを購入した場合、この手順は既に完了しています。)</span><span class="sxs-lookup"><span data-stu-id="7ac27-108">[Add your domain](#add-your-domain-to-personalize-sign-in) (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>
2. <span data-ttu-id="7ac27-109">ユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="7ac27-109">Add users.</span></span> <span data-ttu-id="7ac27-110">これは、次の3つの方法のいずれかで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-110">You can do this in any of the three ways:</span></span>
    - <span data-ttu-id="7ac27-111">[セットアップウィザード](#add-users-in-the-wizard)で。</span><span class="sxs-lookup"><span data-stu-id="7ac27-111">In the [setup wizard](#add-users-in-the-wizard).</span></span>
    - <span data-ttu-id="7ac27-112">オンプレミスの Active directory を使用している場合は、ディレクトリ同期を使用して、 [AZURE AD Connect を使用してユーザーを追加](#add-users-by-using-azure-ad-connect)します。</span><span class="sxs-lookup"><span data-stu-id="7ac27-112">Use directory synchronization to [add users by using Azure AD Connect](#add-users-by-using-azure-ad-connect) if you have an on-premises Active directory.</span></span>
    - <span data-ttu-id="7ac27-113">後で管理センターで[ユーザーを追加](add-users-m365b.md)することもできます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-113">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
3. <span data-ttu-id="7ac27-114">セキュリティポリシーを設定し、デバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="7ac27-114">Set up security policies and configure devices.</span></span> <span data-ttu-id="7ac27-115">これは、次の3つの方法のいずれかで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-115">You can do this in any of the three ways:</span></span>
    - <span data-ttu-id="7ac27-116">[セットアップウィザード](#set-up-policies-in-the-wizard)で。</span><span class="sxs-lookup"><span data-stu-id="7ac27-116">In the [setup wizard](#set-up-policies-in-the-wizard).</span></span>  
    - <span data-ttu-id="7ac27-117">[管理センター](#modify-or-add-policies-in-the-admin-center)で。</span><span class="sxs-lookup"><span data-stu-id="7ac27-117">In the [admin center](#modify-or-add-policies-in-the-admin-center).</span></span>
    - <span data-ttu-id="7ac27-118">[Intune 管理センター](https://docs.microsoft.com/intune/what-is-device-management)で。</span><span class="sxs-lookup"><span data-stu-id="7ac27-118">In the [Intune admin center](https://docs.microsoft.com/intune/what-is-device-management).</span></span>
4. <span data-ttu-id="7ac27-119">Windows 10 デバイスをセットアップして管理します。</span><span class="sxs-lookup"><span data-stu-id="7ac27-119">Set up and manage Windows 10 devices.</span></span>

    <span data-ttu-id="7ac27-120">WIndows 10 デバイスを Azure AD に参加させると、すべてのポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-120">When you join a WIndows 10 device to Azure AD, all the policies get applied to it.</span></span>
    - <span data-ttu-id="7ac27-121">[セットアップウィザード](#set-up-policies-in-the-wizard)で Windows 10 デバイスの構成を設定します。</span><span class="sxs-lookup"><span data-stu-id="7ac27-121">Set up Windows 10 device configurations in the [setup wizard](#set-up-policies-in-the-wizard).</span></span>
    - <span data-ttu-id="7ac27-122">[新しい Windows 10 デバイス](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device)を Azure AD に参加させる。</span><span class="sxs-lookup"><span data-stu-id="7ac27-122">Join a [new Windows 10 device](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) to Azure AD.</span></span>
    - <span data-ttu-id="7ac27-123">既存の[Windows 10 デバイス](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro)を Azure AD に参加させる。</span><span class="sxs-lookup"><span data-stu-id="7ac27-123">Join an [existing Windows 10 device](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) to Azure AD.</span></span>
1. <span data-ttu-id="7ac27-124">Office 365 Business をインストールします。</span><span class="sxs-lookup"><span data-stu-id="7ac27-124">Install Office 365 Business.</span></span>
    - <span data-ttu-id="7ac27-125">[セットアップウィザード](#set-up-policies-in-the-wizard)を使用して、Windows デバイスに Office を自動的にインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-125">You can automatically install Office in the Windows devices by using the [setup wizard](#set-up-policies-in-the-wizard).</span></span>
    - <span data-ttu-id="7ac27-126">管理センターから Office を自動的に[インストール](auto-install-or-uninstall-office.md)します。</span><span class="sxs-lookup"><span data-stu-id="7ac27-126">Automatically [install Office](auto-install-or-uninstall-office.md) from the admin center.</span></span>
    - <span data-ttu-id="7ac27-127">ユーザーが Windows およびデバイス用の[Office アプリをインストール](https://docs.microsoft.com/office365/admin/setup/install-applications)できるようにします。</span><span class="sxs-lookup"><span data-stu-id="7ac27-127">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
1. <span data-ttu-id="7ac27-128">追加のセキュリティを設定します。</span><span class="sxs-lookup"><span data-stu-id="7ac27-128">Set up additional security.</span></span>
    - <span data-ttu-id="7ac27-129">セットアップウィザードは、デバイスをセキュリティで保護するためのポリシーを追加しますが、データ、アカウント、および電子メールのセキュリティ保護に役立つ[追加のセキュリティ](#additional-security-settings)機能を利用することもできます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-129">The setup wizard adds policies to secure your devices, but you can also take advantage of [additional security](#additional-security-settings) capabilities to helps secure your data, accounts, and emails.</span></span> 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="7ac27-130">ドメイン、ユーザーを追加して、ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="7ac27-130">Add your domain, users and set up policies</span></span>

![をhttps://aka.ms/aboutM365preview指すバナー。](media/m365admincenterchanging.png)

<span data-ttu-id="7ac27-132">Microsoft 365 Business を購入する場合は、所有しているドメインを使用するか、[サインアップ](sign-up.md)中に購入するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-132">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="7ac27-133">サインアップ時に新しいドメインを購入した場合、ドメインはすべてセットアップされており、ユーザーを[追加してライセンスを割り当てる](#add-users-and-assign-licenses)ことができます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-133">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="7ac27-134">サインインを個人用に設定するためにドメインを追加する</span><span class="sxs-lookup"><span data-stu-id="7ac27-134">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="7ac27-135">グローバル管理者の資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="7ac27-135">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="7ac27-136">[**ドメインの追加**] を選択してウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="7ac27-136">Choose **Add a domain** to start the wizard.</span></span>

    ![[ドメインの追加] を選択します。](media/addadomainadmincenter.png)
    
3. <span data-ttu-id="7ac27-138">ウィザードで、使用するドメイン名 (contoso.com など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="7ac27-138">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![[サインインのカスタマイズ] ページのスクリーンショット。](media/personalizesignin.png)

    
4. <span data-ttu-id="7ac27-140">ウィザードの手順に従って、ドメインを所有していることを確認する[Office 365 用の任意の dns ホスティングプロバイダーで dns レコードを作成](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)します。</span><span class="sxs-lookup"><span data-stu-id="7ac27-140">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="7ac27-141">ドメインホストがわかっている場合は、「[ホスト固有の指示](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ac27-141">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="7ac27-142">ホスティングプロバイダーが GoDaddy の場合、このプロセスは簡単であり、自動的にサインインして Microsoft に代わって認証を行うように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-142">If your hosting provider is GoDaddy, the process is easy and you will be automatically asked to sign in and let Microsoft authenticate on your behalf:</span></span>

    ![[GoDaddy のアクセス確認] ページで、[承認] を選択します。](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="7ac27-144">ユーザーを追加して、ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="7ac27-144">Add users and assign licenses</span></span>

<span data-ttu-id="7ac27-145">ウィザードでユーザーを追加することはできますが、[後](add-users-m365b.md)で管理センターでユーザーを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-145">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="7ac27-146">また、ローカルドメインコントローラーがある場合は、 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)を使用してユーザーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-146">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="7ac27-147">ウィザードでユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="7ac27-147">Add users in the wizard</span></span>

<span data-ttu-id="7ac27-148">ウィザードで追加したユーザーには、Microsoft 365 のビジネスライセンスが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-148">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>
<span data-ttu-id="7ac27-149">ローカルドメインコントローラーがあり、Active Directory を使用している場合は、「 [AZURE AD Connect を使用してユーザーを一時にする方法](#add-users-by-using-azure-ad-connect)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ac27-149">If you have a local domain controller, and are using Active Directory, see [how to ddd users by using Azure AD Connect](#add-users-by-using-azure-ad-connect).</span></span>

![ウィザードの [新しいユーザーの追加] ページのスクリーンショット](media/addnewuserspage.png)

1. <span data-ttu-id="7ac27-p106">Microsoft 365 Business のサブスクリプションに既存ユーザーがいる場合 (たとえば、Azure AD Connect を使用した場合)、今すぐこれらのユーザーにライセンスを割り当てるオプションが表示されます。続行して、これらのユーザーにもライセンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="7ac27-p106">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

3. <span data-ttu-id="7ac27-153">ユーザーを追加すると、追加した新しいユーザーと資格情報を共有するためのオプションも表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-153">After you have added the users, you will also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="7ac27-154">それらを印刷、メール、またはダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-154">You can choose to print them out, email them, or download them.</span></span>

4. <span data-ttu-id="7ac27-155">移行のメール メッセージをスキップして、[ **メール メッセージの移行**] ページで [ **次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-155">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="7ac27-156">別のメールプロバイダーから移行していて、後でデータをコピーする場合は、[メールと連絡先を Office 365 に移行](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)できます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-156">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>

#### <a name="add-users-by-using-azure-ad-connect"></a><span data-ttu-id="7ac27-157">Azure AD Connect を使用してユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="7ac27-157">Add users by using Azure AD Connect</span></span>

 <span data-ttu-id="7ac27-158">Active Directory を使用したローカルドメインコントローラーがある場合は、 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)を使用して、ユーザーを Microsoft 365 Business と同期させます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-158">If you have a local domain controller with Active Directory, you synchronize your users with Microsoft 365 Business by using [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span> <span data-ttu-id="7ac27-159">セットアップウィザードを開始する前に、この手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="7ac27-159">Complete this before you start the setup wizard.</span></span> <span data-ttu-id="7ac27-160">管理センターでダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-160">You can download it in the admin center:</span></span>

- <span data-ttu-id="7ac27-161">[**ユーザー** \>の**アクティブユーザー**] に移動して、ページの上部にある省略記号を選択し、[**ディレクトリ同期**] を選択して Azure AD Connect をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="7ac27-161">Go to **Users** \> **Active users**, select the ellipses on the top of the page and then select **Directory synchronization** to download Azure AD Connect.</span></span>

    ![[アクティブなユーザー] ページで、[省略 > Directory snchronization] を選択します。](media/setupdirsync.png)

    > [!IMPORTANT]
    > <span data-ttu-id="7ac27-163">この方法でユーザーを作成する場合でも、管理センターでライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ac27-163">If you create users this way, you will still have to assign licenses to them in the admin center.</span></span>

##### <a name="continue-to-access-domain-joined-apps-and-devices"></a><span data-ttu-id="7ac27-164">ドメインに参加しているアプリとデバイスへのアクセスを続行する</span><span class="sxs-lookup"><span data-stu-id="7ac27-164">Continue to access domain-joined apps and devices</span></span>

<span data-ttu-id="7ac27-165">ドメインに参加しているアプリとデバイスへのアクセスを継続する場合は、次の2つの方法で、これを有効にする方法について以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ac27-165">If you want to continue to access domain-joined apps and devices, read the following articles for two different way of enabling that:</span></span>
  
- [<span data-ttu-id="7ac27-166">Microsoft 365 Business で管理されるドメインに参加している Windows 10 デバイスを有効にする</span><span class="sxs-lookup"><span data-stu-id="7ac27-166">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    - <span data-ttu-id="7ac27-167">この方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7ac27-167">This is the recommended way.</span></span>

- [<span data-ttu-id="7ac27-168">Microsoft 365 Business で Azure AD に参加しているデバイスからオンプレミスのリソースにアクセスする</span><span class="sxs-lookup"><span data-stu-id="7ac27-168">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)

### <a name="connect-your-domain"></a><span data-ttu-id="7ac27-169">ドメインを接続する</span><span class="sxs-lookup"><span data-stu-id="7ac27-169">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="7ac27-170">. Onmicrosoft ドメインを使用することを選択した場合、または Azure AD Connect を使用してユーザーを設定した場合は、この手順は表示されません。</span><span class="sxs-lookup"><span data-stu-id="7ac27-170">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="7ac27-171">サービスを設定するには、DNS ホストまたはドメイン レジストラーにあるレコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ac27-171">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="7ac27-172">セットアップ ウィザードでは通常、ユーザーのレジストラーが検出され、レジストラーの Web サイトで NS レコードを更新するための詳しい操作手順へのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-172">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="7ac27-173">含まれていない場合は、ネームサーバーを[変更して、任意のドメインレジストラーで Office 365](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="7ac27-173">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="7ac27-174">既存の DNS レコード (既存の web サイトなど) がある場合は、自分の DNS レコードを管理して、既存のサービスが常に接続していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ac27-174">If you have existing DNS records, for example an existing web site, you will want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="7ac27-175">詳細については、「[ドメインの基礎](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ac27-175">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![自分の DNS レコードを管理するドメインページに接続します。](media/connectyourdomainpage.png)

2. <span data-ttu-id="7ac27-177">ウィザードの手順を実行すると、電子メールとその他のサービスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-177">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="set-up-security-policies-and-device-configurations"></a><span data-ttu-id="7ac27-178">セキュリティポリシーとデバイス構成を設定する</span><span class="sxs-lookup"><span data-stu-id="7ac27-178">Set up security policies and device configurations</span></span> 

<span data-ttu-id="7ac27-179">これらのポリシーは、ユーザーのセットに異なるポリシーを割り当てる場合は、ライセンスを付与するすべてのユーザー、またはユーザーのグループに適用されます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-179">These policies apply to every user you give a license to, or to a group of users if you decide to assign different policies to a set of users.</span></span>

#### <a name="set-up-policies-in-the-wizard"></a><span data-ttu-id="7ac27-180">ウィザードでポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="7ac27-180">Set up policies in the wizard</span></span>

<span data-ttu-id="7ac27-181">ウィザードで設定したポリシーは、*すべてのユーザー*と呼ばれる[セキュリティグループ](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups)に自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-181">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span>

1. <span data-ttu-id="7ac27-182">[**モバイルデバイスの作業ファイルを保護**する] で、[**デバイスが失われたとき、または盗まれたときに作業ファイルを保護する**] オプションが既定で選択されています。</span><span class="sxs-lookup"><span data-stu-id="7ac27-182">On the **Protect your work files on mobile devices** the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="7ac27-183">[**ユーザーがモバイルデバイスで Office ファイルにアクセスする方法を管理**する] をオンにすることもできます。これは推奨されています。</span><span class="sxs-lookup"><span data-stu-id="7ac27-183">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    ![[モバイルデバイスの作業ファイルを保護する] ページのスクリーンショット](media/protectworkfilesondevices.png)

     - <span data-ttu-id="7ac27-185">**デバイスが紛失または盗難になったときに作業ファイルの保護**を拡張すると、[既定値](protect-work-files-on-lost-or-stolen-device.md)が事前に選択されます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-185">If you expand **Protect work files when devices are lost or stolen**, the [default values](protect-work-files-on-lost-or-stolen-device.md) are pre-selected:</span></span>

        ![失われたデバイスでファイルを保護するための既定値のスクリーンショット。](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="7ac27-187">[ユーザーが**モバイルデバイスで Office ファイルにアクセスする方法を管理**する] を選択し、それを展開すると、[既定値](manage-user-access-on-mobile-devices.md)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-187">If you select **Manage how users access Office files on mobile devices** and expand it, the [default values](manage-user-access-on-mobile-devices.md) are shown.</span></span> <span data-ttu-id="7ac27-188">セットアップ時に既定値を受け入れて、すべてのユーザーに適用される、Android、iOS、Windows 10 のアプリケーション ポリシーを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7ac27-188">We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="7ac27-189">セットアップが完了したら、追加のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-189">You can create more policies after setup completes.</span></span>

        ![モバイルでの Office ファイルの保護設定のスクリーンショット。](media/useraccessonmobile.png)

2. <span data-ttu-id="7ac27-191">データとデバイスを保護するための最後の手順では、Windows 10 デバイスをセキュリティで保護するためのポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-191">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="7ac27-192">これらの設定は、ユーザーの Windows 10 が組織に接続すると自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-192">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="7ac27-193">**セキュリティで保護された Windows 10 デバイス**を拡張して、[既定値](secure-windows-10-devices.md)を表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-193">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="7ac27-194">Windows 10 デバイスで[Office を自動的にインストール](install-office-on-windows-10-during-setup.md)するように選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-194">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    ![Windows 10 デバイス構成ページの設定のスクリーンショット。](media/setwin10config.png)

#### <a name="modify-or-add-policies-in-the-admin-center"></a><span data-ttu-id="7ac27-196">管理センターでポリシーを変更または追加する</span><span class="sxs-lookup"><span data-stu-id="7ac27-196">Modify or add policies in the admin center</span></span>

<span data-ttu-id="7ac27-197">デバイスとアプリの保護ポリシーを表示および変更する方法、およびユーザーデバイスからデータを削除またはリセットする方法に関するトピックへのリンクは、「 [Microsoft 365 Business の管理](manage.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ac27-197">See [manage Microsoft 365 Business](manage.md) for links to topics on how to view and modify device and app protection polices, and how to remove data from, or reset user devices.</span></span>

## <a name="deploy-and-manage-windows-10"></a><span data-ttu-id="7ac27-198">Windows 10 を展開して管理する</span><span class="sxs-lookup"><span data-stu-id="7ac27-198">Deploy and manage Windows 10</span></span>
<span data-ttu-id="7ac27-199">新しいコンピューターのセットアップ時に、または既存のコンピューターのサインインプロファイルを変更することによって、Azure AD に手動で接続するには、「 [Microsoft 365 Business ユーザーの Windows デバイス](set-up-windows-devices.md)をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ac27-199">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) to manually connect to Azure AD, either during setup for new computers, or by changing sign-in profile for existing computers.</span></span> 

### <a name="use-autopilot-to-set-up-new-devices"></a><span data-ttu-id="7ac27-200">自動操縦を使用して新しいデバイスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="7ac27-200">Use Autopilot to set up new devices</span></span>

<span data-ttu-id="7ac27-201">[Windows 自動操縦](add-autopilot-devices-and-profile.md)を使用して、ユーザーに対して**新しい**windows 10 デバイスを自動的に事前構成することができますが、これを実行できる[パートナー](https://www.microsoft.com/solution-providers/search)を取得する方が簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="7ac27-201">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="7ac27-202">[Microsoft ストア](https://go.microsoft.com/fwlink/?linkid=874598)に移動して、クラウドテクノロジエキスパートに購入した新しいデバイスのセットアップを依頼することもできます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-202">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) and ask a cloud technology expert set up new devices you purchase for you.</span></span>

### <a name="access-on-premises-resources"></a><span data-ttu-id="7ac27-203">オンプレミスのリソースにアクセスする</span><span class="sxs-lookup"><span data-stu-id="7ac27-203">Access on-premises resources</span></span>

<span data-ttu-id="7ac27-204">組織がオンプレミスの Windows Server Active Directory を使用している場合は、Windows 10 のデバイスを保護するように Microsoft 365 Business をセットアップし、ローカル認証を必要とするオンプレミスのリソースへのアクセスを維持することができます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-204">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="7ac27-205">「[ドメインに参加している Windows 10 デバイスが Microsoft 365 Business で管理される](manage-windows-devices.md)ようにする」の手順に従って、これを設定します。</span><span class="sxs-lookup"><span data-stu-id="7ac27-205">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="7ac27-206">この方法は推奨されており、この状態のデバイスはハイブリッド Azure AD 参加デバイスと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-206">This is the preferred method and devices in this state are called Hybrid Azure AD joined devices.</span></span>

<span data-ttu-id="7ac27-207">オンプレミスのリソース (ファイル共有やプリンターなど) を含むローカルな Active Directory が企業にある場合は、次の手順に従って、Azure AD に参加しているデバイスにこれらのリソースへのアクセス権を付与できます。 [Microsoft 365 Business の Azure AD に参加しているデバイス](access-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="7ac27-207">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers) , you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="7ac27-208">Office 365 クライアントアプリを展開する</span><span class="sxs-lookup"><span data-stu-id="7ac27-208">Deploy Office 365 client apps</span></span>

<span data-ttu-id="7ac27-209">セットアップ時に Office アプリを自動的にインストールすることを選択した場合、ユーザーが作業の資格情報を使用して Windows デバイスから Azure AD にサインインすると、アプリが Windows 10 デバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-209">If you chose to automatically install Office apps in during the set up, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices with their work credentials.</span></span>
<span data-ttu-id="7ac27-210">モバイル iOS または Android デバイスに Office をインストールするには、「 [Microsoft 365 Business ユーザーのモバイルデバイスをセットアップ](set-up-mobile-devices.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ac27-210">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="7ac27-211">Office を個別にインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-211">You can also install Office individually.</span></span> <span data-ttu-id="7ac27-212">手順について[は、「PC または Mac に Office をインストールする](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ac27-212">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) for instructions.</span></span>

## <a name="additional-security-settings"></a><span data-ttu-id="7ac27-213">その他のセキュリティ設定</span><span class="sxs-lookup"><span data-stu-id="7ac27-213">Additional security settings</span></span>

<span data-ttu-id="7ac27-214">セットアップウィザードのセキュリティとコンプライアンスの設定に加えて、次の追加設定を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="7ac27-214">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="7ac27-215">**メールマルウェア対策**</span><span class="sxs-lookup"><span data-stu-id="7ac27-215">**Email malware protection**</span></span>
- <span data-ttu-id="7ac27-216">**Advanced Threat Protection (ATP) の安全な添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="7ac27-216">**Advanced Threat Protection (ATP) Safe Attachments**</span></span>
- <span data-ttu-id="7ac27-217">**ATP の安全なリンク**</span><span class="sxs-lookup"><span data-stu-id="7ac27-217">**ATP Safe Links**</span></span>
- <span data-ttu-id="7ac27-218">**APT フィッシング対策**</span><span class="sxs-lookup"><span data-stu-id="7ac27-218">**APT anti-phishing**</span></span>
- <span data-ttu-id="7ac27-219">**Exchange Online Archiving**</span><span class="sxs-lookup"><span data-stu-id="7ac27-219">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="7ac27-220">**データ損失防止 (DLP)**</span><span class="sxs-lookup"><span data-stu-id="7ac27-220">**Data loss prevention (DLP)**</span></span>
- <span data-ttu-id="7ac27-221">**Azure Information Protection**(プラン 1)</span><span class="sxs-lookup"><span data-stu-id="7ac27-221">**Azure Information Protection** (Plan 1)</span></span>
- <span data-ttu-id="7ac27-222">**Intune ポータルの可用性**</span><span class="sxs-lookup"><span data-stu-id="7ac27-222">**Intune portal availability**</span></span>

<span data-ttu-id="7ac27-223">開始するには、「 [advanced security policies をセットアップ](set-up-advanced-security.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ac27-223">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

<span data-ttu-id="7ac27-224">セキュリティに関するベストプラクティスのロードマップについては[、Microsoft 365 Business をセキュリティで保護するための10のトップの方法](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)も参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ac27-224">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>