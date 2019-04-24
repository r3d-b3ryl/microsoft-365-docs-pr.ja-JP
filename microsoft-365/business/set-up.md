---
title: セットアップ ウィザードを使用して Microsoft 365 Business をセットアップする
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
description: 4つの手順を完了して Microsoft 365 Business をセットアップする方法について説明します。
ms.openlocfilehash: a1c8a41c3e291983276280a063248bdd10a7f85a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283921"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a><span data-ttu-id="f512d-103">セットアップ ウィザードを使用して Microsoft 365 Business をセットアップする</span><span class="sxs-lookup"><span data-stu-id="f512d-103">Set up Microsoft 365 Business by using the setup wizard</span></span>

<span data-ttu-id="f512d-104">以下の手順1-4 を完了します。</span><span class="sxs-lookup"><span data-stu-id="f512d-104">Complete steps 1-4 below.</span></span>
  
### <a name="set-up-microsoft-365-business"></a><span data-ttu-id="f512d-105">Microsoft 365 Business をセットアップする</span><span class="sxs-lookup"><span data-stu-id="f512d-105">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="f512d-106">オンプレミスの Active Directory がインストールされていない場合に Microsoft 365 Business をセットアップする方法についてのビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f512d-106">Watch a video on how to set up Microsoft 365 Business when you don't have an on-premises Active Directory:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
<span data-ttu-id="f512d-107">セットアップ手順には、ローカルの Active Directory を含む設定に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f512d-107">The set-up steps include information for setups that include local Active Directory.</span></span> <span data-ttu-id="f512d-108">ドメインに参加しているデバイスへのアクセスを継続する場合は、次に示す2つの異なる方法について以下の記事を読んで、セットアップウィザードを実行する前に手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="f512d-108">If you want to continue to access domain-joined devices, read the following articles for two different way of enabling that, and complete the steps before you run the Setup wizard:</span></span>
  
- [<span data-ttu-id="f512d-109">Microsoft 365 Business で管理されるドメインに参加している Windows 10 デバイスを有効にする</span><span class="sxs-lookup"><span data-stu-id="f512d-109">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    
    <span data-ttu-id="f512d-110">-これは推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="f512d-110">-This is the recommended way.</span></span>
    
- [<span data-ttu-id="f512d-111">Microsoft 365 Business で Azure AD に参加しているデバイスからオンプレミスのリソースにアクセスする</span><span class="sxs-lookup"><span data-stu-id="f512d-111">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a><span data-ttu-id="f512d-112">手順 1: サインインをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="f512d-112">Step 1: Personalize sign-in</span></span>

1. <span data-ttu-id="f512d-p102">グローバル管理者の資格情報を使用して、[Microsoft 365 Business](https://portal.microsoft.com) にサインインします。[ **管理者**] タイルを選び、管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="f512d-p102">Sign in to [Microsoft 365 Business](https://portal.microsoft.com) by using your global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="f512d-115">管理センターで [ **セットアップの開始**] (状態によっては、[ **セットアップの続行**] が代わりに表示される場合があります) を選び、ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="f512d-115">Choose **Start setup** (depending on your state you may see **Continue setup** instead) in the admin center to start the wizard.</span></span> 
    
3. <span data-ttu-id="f512d-116">使用するドメイン名 (Contoso.com など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="f512d-116">Enter the domain name you want to use (like contoso.com).</span></span>
    
    <span data-ttu-id="f512d-117">続けて自分のドメインを入力します。Azure AD Connect などを使用している間にドメインを確認した場合でも入力します。</span><span class="sxs-lookup"><span data-stu-id="f512d-117">Go ahead and enter your domain even if you have verified it while using Azure AD Connect, for example.</span></span> <span data-ttu-id="f512d-118">Azure AD Connect を使用してドメインを確認した場合、次の2つの手順は適用されません。</span><span class="sxs-lookup"><span data-stu-id="f512d-118">The following two steps do not apply to you if you used Azure AD Connect to verify your domain.</span></span>
    
4. <span data-ttu-id="f512d-119">ウィザードの手順に従って、ドメインを所有していることを確認する[Office 365 用の任意の dns ホスティングプロバイダーで dns レコードを作成](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166)します。</span><span class="sxs-lookup"><span data-stu-id="f512d-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) that verifies you own the domain.</span></span> 
    
    <span data-ttu-id="f512d-120">ビデオの例については、[新しい管理センターで Office 365 をセットアップ](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8)するを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f512d-120">You can view an example video of [Video: Setup Office 365 in the new Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8).</span></span> <span data-ttu-id="f512d-121">このビデオには、Microsoft 365 Business のデータ保護手順は含まれていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f512d-121">Note that this video does not include the data protection steps of Microsoft 365 Business.</span></span>
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a><span data-ttu-id="f512d-123">手順 2: ユーザーを追加してライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="f512d-123">Step 2: Add users and assign licenses</span></span>

1. <span data-ttu-id="f512d-124">ここではユーザーを追加することも、管理センターで[後からユーザーを追加](add-users-m365b.md)することもできます。</span><span class="sxs-lookup"><span data-stu-id="f512d-124">You can add users here, or you can [add users later](add-users-m365b.md) in the admin center.</span></span> 
    
    <span data-ttu-id="f512d-125">追加するユーザーには、自動的に Microsoft 365 Business ライセンスが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f512d-125">Any users you add get automatically assigned a Microsoft 365 Business license.</span></span>
    
2. <span data-ttu-id="f512d-p105">Microsoft 365 Business のサブスクリプションに既存ユーザーがいる場合 (たとえば、Azure AD Connect を使用した場合)、今すぐこれらのユーザーにライセンスを割り当てるオプションが表示されます。続行して、これらのユーザーにもライセンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="f512d-p105">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>
    
3. <span data-ttu-id="f512d-p106">追加した新しいユーザーと資格情報を共有するためのオプションも表示されます。それらを印刷、メール、またはダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f512d-p106">You will also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>
    
4. <span data-ttu-id="f512d-130">移行のメール メッセージをスキップして、[ **メール メッセージの移行**] ページで [ **次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f512d-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 
    
    <span data-ttu-id="f512d-131">別のメールプロバイダーから移行していて、後でデータをコピーする場合は、[メールと連絡先を Office 365 に移行](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)できます。</span><span class="sxs-lookup"><span data-stu-id="f512d-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a><span data-ttu-id="f512d-133">手順 3: ドメインを接続する</span><span class="sxs-lookup"><span data-stu-id="f512d-133">Step 3: Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="f512d-134">. onmicrosoft ドメインを使用するか、Azure AD Connect を使用することを選択した場合は、この手順は表示されません。</span><span class="sxs-lookup"><span data-stu-id="f512d-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect, you will not see this step.</span></span> 
  
<span data-ttu-id="f512d-135">サービスを設定するには、DNS ホストまたはドメイン レジストラーにあるレコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f512d-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="f512d-136">セットアップ ウィザードでは通常、ユーザーのレジストラーが検出され、レジストラーの Web サイトで NS レコードを更新するための詳しい操作手順へのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f512d-136">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="f512d-137">含まれていない場合は、ネームサーバーを[変更して、任意のドメインレジストラーで Office 365](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="f512d-137">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span>
    
2. <span data-ttu-id="f512d-138">メールとその他のサービスが自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f512d-138">Email and other services will be set up for you</span></span>
    
### <a name="step-4-manage-devices-and-work-files"></a><span data-ttu-id="f512d-139">手順 4: デバイスと作業ファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="f512d-139">Step 4: Manage devices and work files</span></span>

1. <span data-ttu-id="f512d-140">[**モバイルデバイスの作業ファイルを保護**する] ページで、[**デバイスの紛失または盗難時に作業ファイルを保護**する] と [**ユーザーがモバイルデバイスの設定で Office ファイルにアクセスする方法**を**オン**にする方法を管理する] の両方を設定します。</span><span class="sxs-lookup"><span data-stu-id="f512d-140">On the **Protect work files on your mobile devices** page set both **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** settings to **On**.</span></span> <span data-ttu-id="f512d-141">各サブ設定にアクセスするには、各設定の横にある山かっこをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f512d-141">You can also access each sub-setting by clicking the chevrons next to each setting.</span></span>
  
  <span data-ttu-id="f512d-142">ユーザーが[Office アプリをインストール](set-up-mobile-devices.md)し、Microsoft 365 Business の資格情報を使用して認証を行うとすぐに、ライセンスが付与されたすべてのユーザーの作業ファイルが iOS および Android デバイスで保護されるようになります。</span><span class="sxs-lookup"><span data-stu-id="f512d-142">All of your licensed users' work files are now protected on iOS and Android devices, as soon as they [install Office apps](set-up-mobile-devices.md) (and authenticate with their Microsoft 365 Business credentials).</span></span> 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. <span data-ttu-id="f512d-144">[ **windows 10 デバイス構成の設定**] ページで、[**セキュリティで保護された windows 10 デバイス**の設定] を **[オン**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="f512d-144">On the **Set Windows 10 device configuration** page, set **Secure Windows 10 Devices** setting to **On**.</span></span>
  
   <span data-ttu-id="f512d-145">また、各サブ設定にアクセスするには、その横の山形記号をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f512d-145">You can also access each sub-setting by clicking the chevron next to it.</span></span>
  
3. <span data-ttu-id="f512d-146">すべてのユーザーが windows 10 台のコンピューターを持ち、既存の office インストールがない場合、またはクイック実行 office インストールを使用している場合は、[ **windows 10 デバイスに Office をインストール**する **] を [はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="f512d-146">Set the **Install Office on Windows 10 Devices** setting to **Yes** if all of your users have Windows 10 computers, and either no existing Office installs, or click-to-run Office installs.</span></span> <span data-ttu-id="f512d-147">そうでない場合は、このオプションを [**いいえ**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="f512d-147">If this is not the case, set this option to **No**.</span></span> <span data-ttu-id="f512d-148">ユーザーのコンピューターの準備が完了すると、後で管理センターから[Office を自動的にインストール](auto-install-or-uninstall-office.md)することができます。</span><span class="sxs-lookup"><span data-stu-id="f512d-148">You can [automatically install Office](auto-install-or-uninstall-office.md) later from the admin center after you have prepared the user computers.</span></span> <span data-ttu-id="f512d-149">手順については、「 [Office クライアントのインストールを準備する](prepare-for-office-client-deployment.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f512d-149">For instructions, see [prepare for Office client installation](prepare-for-office-client-deployment.md).</span></span>
  
    <span data-ttu-id="f512d-150">windows 10 デバイスのライセンスユーザーの作業ファイルは、windows 10 デバイスを microsoft 365 Business Azure AD ドメインに[参加](set-up-windows-devices.md)させるとすぐに、または microsoft 365 に同時に参加している間に[新しいコンピューターに windows 10 をインストール](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx)すると、直ちに投影されます。Business Azure AD ドメイン。</span><span class="sxs-lookup"><span data-stu-id="f512d-150">The licensed users' work files on Windows 10 devices will be projected as soon as they [join their Windows 10 device](set-up-windows-devices.md) to a Microsoft 365 Business Azure AD domain or [install Windows 10 on a new computer](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) while simultaneously joining the Microsoft 365 Business Azure AD domain.</span></span> 
  
4. <span data-ttu-id="f512d-151">[**次へ**] をクリックして、セットアップを終了します。</span><span class="sxs-lookup"><span data-stu-id="f512d-151">Click **Next** and you are done with setup.</span></span> 
  
    <span data-ttu-id="f512d-152">この手順でフィードバックをお寄せください。</span><span class="sxs-lookup"><span data-stu-id="f512d-152">Please leave us feedback at this step to help us improve the experience.</span></span>
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a><span data-ttu-id="f512d-154">その他のセキュリティ設定</span><span class="sxs-lookup"><span data-stu-id="f512d-154">Additional security settings</span></span>

<span data-ttu-id="f512d-155">セットアップウィザードのセキュリティとコンプライアンスの設定に加えて、次の追加設定を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f512d-155">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="f512d-156">安全でない添付ファイルに対する保護を設定します。</span><span class="sxs-lookup"><span data-stu-id="f512d-156">Set up protection against unsafe attachments.</span></span> <span data-ttu-id="f512d-157">**Advanced Threat Protection**(ATP) 悪意のあるコンテンツを特定し、安全でない添付ファイルの配信をブロックすることで、フィッシング詐欺やランサムウェアによる感染に対する保護を促進します。</span><span class="sxs-lookup"><span data-stu-id="f512d-157">**Advanced Threat Protection** (ATP) identifies malicious content and then blocks delivery of unsafe attachments, helping protect you against phishing schemes and ransomware infections.</span></span> <span data-ttu-id="f512d-158">添付ファイル保護をアクティブにするには、「 [Office 365 ATP の安全な添付ファイルのポリシーを](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy)セットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f512d-158">To activate attachment protection, see [Set up Office 365 ATP Safe Attachments policies](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span></span>
    
- <span data-ttu-id="f512d-159">ユーザーが悪意のあるリンクをクリックしたときに環境を保護します。</span><span class="sxs-lookup"><span data-stu-id="f512d-159">Protect your environment when users click malicious links.</span></span> <span data-ttu-id="f512d-160">ATP は、ユーザーがクリックしたときに電子メール内のリンクを調べます。</span><span class="sxs-lookup"><span data-stu-id="f512d-160">ATP examines links in email at the time a user clicks them.</span></span> <span data-ttu-id="f512d-161">リンクが安全でない場合、ユーザーはサイトにアクセスしないように警告が出されるか、サイトがブロックされていることが通知されます。</span><span class="sxs-lookup"><span data-stu-id="f512d-161">If a link is unsafe, the user is warned not to visit the site or informed that the site has been blocked.</span></span> <span data-ttu-id="f512d-162">これにより、フィッシングを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="f512d-162">This helps protect against phishing schemes.</span></span> <span data-ttu-id="f512d-163">[office 365 atp safe links ポリシーを](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc)セットアップするか、 [office 365 atp safe links ポリシーを](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc)セットアップします。</span><span class="sxs-lookup"><span data-stu-id="f512d-163">[Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) or [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span></span>
    
- <span data-ttu-id="f512d-164">ユーザーのメールボックスを**訴訟ホールド**の対象にすることで、削除されたアイテムを含むすべてのメールボックスのコンテンツを保持できます。</span><span class="sxs-lookup"><span data-stu-id="f512d-164">You can preserve all mailbox content including deleted items by putting a user's entire mailbox on **litigation hold**.</span></span> <span data-ttu-id="f512d-165">手順については、</span><span class="sxs-lookup"><span data-stu-id="f512d-165">For instructions, see</span></span> 
- <span data-ttu-id="f512d-166">[Exchange Online アーカイブを使用してメールの保存期間を設定](security-features.md#set-up-email-retention-with-exchange-online-archiving)します。</span><span class="sxs-lookup"><span data-stu-id="f512d-166">[Set up email retention with Exchange Online Archiving](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span></span>
    
- <span data-ttu-id="f512d-167">保持期間の終了時に特定の時間だけ保持したり、コンテンツを完全に削除したりするために、カスタマイズされた**アイテム保持ポリシー**を設定します。</span><span class="sxs-lookup"><span data-stu-id="f512d-167">Set up customized **retention policies**, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="f512d-168">カスタマイズされたアイテム保持ポリシーは、セキュリティセンターとコンプライアンスセンターで有効にし、[**データガバナンス** \>の**保持**] に移動して、ウィザードの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f512d-168">You can enable customized retention policies in the Securities and compliance center, go to **Data governance** \> **Retention**, and then follow the steps in the wizard.</span></span> <span data-ttu-id="f512d-169">詳細については、「[アイテム保持ポリシーの概要](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f512d-169">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="f512d-170">次のステップ</span><span class="sxs-lookup"><span data-stu-id="f512d-170">Next steps</span></span>

<span data-ttu-id="f512d-171">ライセンスがあるユーザーは、次の手順でデバイスをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="f512d-171">For the users that have their licenses, the next step is to set up devices.</span></span><br/> <span data-ttu-id="f512d-172">「[Microsoft 365 Business ユーザーの Windows デバイスをセットアップする](set-up-windows-devices.md)」と「[Microsoft 365 Business ユーザーのモバイル デバイスをセットアップする](set-up-mobile-devices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f512d-172">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) and [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span> <br/><span data-ttu-id="f512d-173">デバイスとアプリの保護ポリシーを設定する方法、およびユーザーのデバイスからデータを削除する方法に関する記事へのリンクについては、「[Microsoft 365 Business を管理する](manage.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f512d-173">See [Manage Microsoft 365 Business](manage.md) for links to topics on how to set device and app protection polices, and how to remove data from user devices.</span></span> 
  


