---
title: Microsoft 365 Business Standard のセットアップ
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
description: Microsoft 365 Business Standard を購入するときに、所有するドメインを使用するか、サインアップ時に購入するかを選択することができます。
ms.openlocfilehash: 861a9e38f10f0cd654e2b10c1879811cd668bc1f
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393813"
---
# <a name="set-up-microsoft-business-standard"></a><span data-ttu-id="2b5a8-103">Microsoft Business Standard をセットアップする</span><span class="sxs-lookup"><span data-stu-id="2b5a8-103">Set up Microsoft Business Standard</span></span>



## <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="2b5a8-104">ドメインを追加してサインインをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="2b5a8-104">Add your domain to personalize sign-in</span></span>

<span data-ttu-id="2b5a8-105">Microsoft 365 Business Standard を購入するときに、所有するドメインを使用するか、サインアップ時に購入するかを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-105">When you purchase Microsoft 365 Business Standard, you have the option of using a domain you own, or buying one during the sign-up.</span></span>

- <span data-ttu-id="2b5a8-106">サインアップ時に新しいドメインを購入した場合、お客様のドメインはすべてセットアップされており、[[ユーザーを追加してライセンスを割り当てる](#add-users-and-assign-licenses)] に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-106">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

1. <span data-ttu-id="2b5a8-107">グローバル管理者の資格情報を使用して、[Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-107">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="2b5a8-108">[**セットアップに移動**] を選択して、ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-108">Choose **Go to setup** to start the wizard.</span></span>

3. <span data-ttu-id="2b5a8-109">[**Office アプリのインストール**] ページでは、オプションで自分のコンピューターにアプリをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-109">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="2b5a8-110">**ドメインの追加** ステップで、使用するドメイン名 (Contoso.com など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-110">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2b5a8-p101">サインアップ時にドメインを購入した場合、ここでは **ドメインの追加** ステップは表示されません。[ユーザーの追加](#add-users-and-assign-licenses) に進んでください。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-p101">If you purchased a domain during the sign-up, you will not see **Add a domain** step here. Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    
4. <span data-ttu-id="2b5a8-113">ウィザードの手順に従って[任意の DNS ホスティング プロバイダーで Office 365 用の DNS レコードを作成](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)し、ドメインの所有を確認します。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-113">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="2b5a8-114">ドメイン ホストがわかっている場合は、「[Microsoft 365 にドメインを追加する](/microsoft-365/admin/setup/add-domain)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-114">If you know your domain host, see also [Add a domain to Microsoft 365](/microsoft-365/admin/setup/add-domain).</span></span>

    <span data-ttu-id="2b5a8-115">ご利用のホスティング プロバイダーが GoDaddy または [Domain Connect](/office365/admin/get-help-with-domains/domain-connect) を有効にした別のホストである場合、プロセスは簡単です。サインインし、お客様に代わって Microsoft が認証するよう自動的に求められます。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-115">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![GoDaddy の [Confirm Access] (アクセスの確認) ページで、[承認] を選択します。](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a><span data-ttu-id="2b5a8-117">ユーザーを追加してライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="2b5a8-117">Add users and assign licenses</span></span>

<span data-ttu-id="2b5a8-118">ウィザードでユーザーを追加することもできますが、管理センターで[後からユーザーを追加](../add-users/add-users.md)することもできます。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-118">You can add users in the wizard, but you can also [add users later](../add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="2b5a8-119">さらに、ローカル ドメイン コントローラーを持っている場合には、[Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express) を使用してユーザーを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-119">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

## <a name="add-users-in-the-wizard"></a><span data-ttu-id="2b5a8-120">ウィザードでユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="2b5a8-120">Add users in the wizard</span></span>

<span data-ttu-id="2b5a8-121">ウィザードで追加したユーザーには、Microsoft 365 Business Standard ライセンスが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-121">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Standard license.</span></span>

1. <span data-ttu-id="2b5a8-p104">Microsoft 365 Business Basic のサブスクリプションに既存ユーザーがいる場合 (たとえば、Azure AD Connect を使用した場合)、すぐにこれらのユーザーにライセンスを割り当てるオプションが表示されます。続行して、これらのユーザーにもライセンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-p104">If your Microsoft 365 Business Standard subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="2b5a8-p105">ユーザーを追加した後、資格証明書をそれらの新規ユーザーに共有するオプションが提供されます。それらをプリントアウトや電子メールで通知、またはダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-p105">After you've added the users, you'll also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>

## <a name="connect-your-domain"></a><span data-ttu-id="2b5a8-126">ドメインを接続する</span><span class="sxs-lookup"><span data-stu-id="2b5a8-126">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="2b5a8-127">.onmicrosoft ドメインの使用を選択した場合、またはユーザーの設定に Azure AD Connect を使用した場合、このステップは表示されません。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-127">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="2b5a8-128">サービスを設定するには、DNS ホストまたはドメイン レジストラーにあるレコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-128">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="2b5a8-129">セットアップ ウィザードでは通常、ユーザーのレジストラーが検出され、レジストラーの Web サイトで NS レコードを更新するための詳しい操作手順へのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-129">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="2b5a8-130">表示されない場合には、[任意のドメイン レジストラーで Office 365 をセットアップするためにネームサーバーを変更](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md)します。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-130">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="2b5a8-131">既存の DNS レコード (たとえば、既存の Web サイト) を持っているのに、DNS ホストが [Domain Connect](/office365/admin/get-help-with-domains/domain-connect) に対して有効になっている場合には、[**レコードを追加してもらう**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-131">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="2b5a8-132">[**オンライン サービスの選択**] ページで、すべて規定値のまま [**次へ**] を選択し、DNS ホストのページで [**承認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-132">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="2b5a8-p108">他の DNS ホストとの間に既存の DNS レコードがある場合 (Domain Connect では有効になっていません)、既存のサービスが接続されたままになっていることを確認するために、自分の DNS レコードを管理したいと思うかもしれません。詳しくは [ドメインの基礎](/office365/admin/get-help-with-domains/dns-basics) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-p108">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected. See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

2. <span data-ttu-id="2b5a8-135">ウィザードの手順に従えば、メールやその他のサービスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-135">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

    <span data-ttu-id="2b5a8-136">サインアップ プロセスが完了すると、管理センターに移動します。ここでは、ウィザードを使用して Office アプリのインストール、ドメインの追加、ユーザーの追加、ライセンスの割り当てを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-136">When the signup process is complete, you'll be directed to the admin center, where you'll follow a wizard to install Office apps, add your domain, add users, and assign licenses.</span></span> <span data-ttu-id="2b5a8-137">初期セットアップが完了したら、管理センターの [**セットアップ**] ページを使用して、サブスクリプションに付属するサービスの設定と構成を継続できます。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-137">After you complete the initial setup, you can use the **Setup** page in the admin center to continue setting up and configuring the services that come with your subscriptions.</span></span>

    <span data-ttu-id="2b5a8-138">セットアップ ウィザードおよび管理センターの **[セットアップ]** ページの詳細については、「[セットアップ ウィザードと [セットアップ] ページの違い](o365-setup-wizard-and-setup-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-138">For more information about the setup wizard and the admin center **Setup** page, see [Difference between the setup wizard and the Setup page](o365-setup-wizard-and-setup-page.md).</span></span>

## <a name="finish-setting-up"></a><span data-ttu-id="2b5a8-139">セットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="2b5a8-139">Finish setting up</span></span>

### <a name="set-up-outlook-for-email"></a><span data-ttu-id="2b5a8-140">Outlook をメール用にセットアップする</span><span class="sxs-lookup"><span data-stu-id="2b5a8-140">Set up Outlook for email</span></span>

1. <span data-ttu-id="2b5a8-141">Windows の [スタート] メニューで、[Outlook] を検索し、選択します。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-141">On the Windows Start menu, search for Outlook, and select it.</span></span>

    <span data-ttu-id="2b5a8-142">(Mac を使用している場合は、ツールバーから Outlook を開くか、または Finder を使用して Outlook を検索します)。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-142">(If you're using a Mac, open Outlook from the toolbar or locate it using the Finder.)</span></span>

    <span data-ttu-id="2b5a8-143">Outlook をインストールしたばかりの場合は、[ようこそ] ページで、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-143">If you've just installed Outlook, on the Welcome page, select **Next**.</span></span>

2. <span data-ttu-id="2b5a8-144">[**ファイル**] \> [**情報**] \> [**アカウントの追加**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-144">Choose **File** \> **Info** \> **Add Account**.</span></span>

3. <span data-ttu-id="2b5a8-145">Microsoft のメール アドレスを入力して、**[接続]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-145">Enter your Microsoft email address and select **Connect**.</span></span>

## <a name="watch-set-up-outlook-for-email"></a><span data-ttu-id="2b5a8-146">注目 : Outlook を電子メール用にセットアップして下さい。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-146">Watch: Set up Outlook for email</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
<span data-ttu-id="2b5a8-147">詳細については、「[メール用に Outlook をセットアップする](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-147">More at [Set up Outlook for email](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span></span>
  
### <a name="import-email"></a><span data-ttu-id="2b5a8-148">メールをインポートする</span><span class="sxs-lookup"><span data-stu-id="2b5a8-148">Import email</span></span>

<span data-ttu-id="2b5a8-149">別のメール アカウントで Outlook を使用していた場合は、以前のメール、予定表、連絡先を新しい Microsoft アカウントにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-149">If you were using Outlook with another email account, you can import your previous email, calendar, and contacts into your new Microsoft account.</span></span>
  
1. <span data-ttu-id="2b5a8-150">**古いメールをエクスポートする**</span><span class="sxs-lookup"><span data-stu-id="2b5a8-150">**Export your old email**</span></span>

    <span data-ttu-id="2b5a8-151">Outlook で、[**ファイル**] \> [**開く&amp;エクスポート**] \> [**インポート/エクスポート**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-151">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>

    <span data-ttu-id="2b5a8-152">[**ファイルにエクスポート**] を選択し、手順に従って Outlook データ ファイル (.pst) およびすべてのサブフォルダーをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-152">Select **Export to a File** and then follow the steps to export your Outlook Data File (.pst) and any subfolders.</span></span>

2. <span data-ttu-id="2b5a8-153">**古いメールをインポートする**</span><span class="sxs-lookup"><span data-stu-id="2b5a8-153">**Import your old email**</span></span>

    <span data-ttu-id="2b5a8-154">Outlook で、[**ファイル**] \> [**開く&amp;エクスポート**] \> [**インポート/エクスポート**] を再度選択します。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-154">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.</span></span>

    <span data-ttu-id="2b5a8-155">今度は、[**他のプログラムまたはファイルからのインポート**] を選択し、古いメールをエクスポートしたときに作成したバックアップ ファイルを手順に従ってインポートします。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-155">This time, select **Import from another program or file** and follow the steps to import the backup file you created when you exported your old email.</span></span>

## <a name="watch-import-and-redirect-email"></a><span data-ttu-id="2b5a8-156">注目 : 電子メールをインポートして再配置しましょう。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-156">Watch: Import and redirect email</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
<span data-ttu-id="2b5a8-157">詳細については、「[Outlook でメールをインポートする](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-157">More at [Import email with Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span></span>

<span data-ttu-id="2b5a8-158">また、Exchange 管理センターを使用して、すべてのユーザーのメールをインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-158">You can also use Exchange admin center to import everyone's email.</span></span> <span data-ttu-id="2b5a8-159">詳細については、「[複数のメール アカウントを移行する](/Exchange/mailbox-migration/mailbox-migration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-159">For more information, see [migrate multiple email accounts](/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
### <a name="use-a-public-website"></a><span data-ttu-id="2b5a8-160">一般向け Web サイトを使用する</span><span class="sxs-lookup"><span data-stu-id="2b5a8-160">Use a public website</span></span>

<span data-ttu-id="2b5a8-161">Microsoft 365 には、ビジネスに使用するための一般向け Web サイトは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-161">Microsoft 365 doesn't include a public website for your business.</span></span> <span data-ttu-id="2b5a8-162">Web サイトをセットアップする場合は、GoDaddy や WIX などの Microsoft パートナーの使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-162">If you want to set one up, consider using a Microsoft partner, such as GoDaddy or WIX.</span></span>
  
1. <span data-ttu-id="2b5a8-163">管理センターから、[**リソース**] に移動し、[**一般向け Web サイト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-163">From the admin center, go to **Resources**, and then select **Public website**.</span></span>

2. <span data-ttu-id="2b5a8-164">いずれかのオプションの [**詳細情報**] を選択して、Web サイト パートナーにサインアップし、ツールを使用してサイトをセットアップおよびデザインします。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-164">Select **Learn more** under one of the options, and then sign up with a website partner and use their tools to set up and design your site.</span></span>

## <a name="watch-create-your-business-website"></a><span data-ttu-id="2b5a8-165">注目 : ビジネス用のWebサイト を作成しましょう。</span><span class="sxs-lookup"><span data-stu-id="2b5a8-165">Watch: Create your business website</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

## <a name="related-content"></a><span data-ttu-id="2b5a8-166">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="2b5a8-166">Related content</span></span>

<span data-ttu-id="2b5a8-167">[Web サイトを作成](../../business-video/create-web-site.md) (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="2b5a8-167">[Create a website](../../business-video/create-web-site.md) (video)</span></span>\
<span data-ttu-id="2b5a8-168">[一般法人向け Microsoft 365](../../business-video/index.yml) (リンク ページ)</span><span class="sxs-lookup"><span data-stu-id="2b5a8-168">[Microsoft 365 for your business](../../business-video/index.yml) (link page)</span></span>
