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
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 4 つの手順を実行して Microsoft 365 のビジネスを設定する方法について説明します。
ms.openlocfilehash: f57239b884bd2e186c0bc01973130a10fa4cfe84
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869005"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a><span data-ttu-id="8e3f7-103">セットアップ ウィザードを使用して Microsoft 365 Business をセットアップする</span><span class="sxs-lookup"><span data-stu-id="8e3f7-103">Set up Microsoft 365 Business by using the setup wizard</span></span>

<span data-ttu-id="8e3f7-104">1 ~ 4 の次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-104">Complete steps 1-4 below.</span></span>
  
### <a name="set-up-microsoft-365-business"></a><span data-ttu-id="8e3f7-105">Microsoft 365 Business をセットアップする</span><span class="sxs-lookup"><span data-stu-id="8e3f7-105">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="8e3f7-106">オンプレミスの Active Directory がない場合は、Microsoft 365 のビジネスをセットアップする方法に関するビデオを視聴するには。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-106">Watch a video on how to set up Microsoft 365 Business when you don't have an on-premises Active Directory:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
<span data-ttu-id="8e3f7-p101">セットアップ手順には、ローカルの Active directory の設定に関する情報が含まれます。ドメインに参加しているデバイスへのアクセスを続行する場合は、次の記事を参照するには、有効にする別の方法を 2 つのと、セットアップ ウィザードを実行する前に手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-p101">The set-up steps include information for setups that include local Active Directory. If you want to continue to access domain-joined devices, read the following articles for two different way of enabling that, and complete the steps before you run the Setup wizard:</span></span>
  
- [<span data-ttu-id="8e3f7-109">Microsoft 365 のビジネスを管理する Windows 10 のドメインに参加しているデバイスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-109">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    
    <span data-ttu-id="8e3f7-110">-これは、推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-110">-This is the recommended way.</span></span>
    
- [<span data-ttu-id="8e3f7-111">アクセスは、オンプレミス マイクロソフト 365 ビジネスで Azure AD に参加しているデバイスからのリソース</span><span class="sxs-lookup"><span data-stu-id="8e3f7-111">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a><span data-ttu-id="8e3f7-112">サインインの手順 1: 個人用に設定します。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-112">Step 1: Personalize sign-in</span></span>

1. <span data-ttu-id="8e3f7-p102">グローバル管理者の資格情報を使用して、[Microsoft 365 Business](https://portal.microsoft.com) にサインインします。[ **管理者**] タイルを選び、管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-p102">Sign in to [Microsoft 365 Business](https://portal.microsoft.com) by using your global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="8e3f7-115">管理センターで [ **セットアップの開始**] (状態によっては、[ **セットアップの続行**] が代わりに表示される場合があります) を選び、ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-115">Choose **Start setup** (depending on your state you may see **Continue setup** instead) in the admin center to start the wizard.</span></span> 
    
3. <span data-ttu-id="8e3f7-116">使用するドメイン名 (Contoso.com など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-116">Enter the domain name you want to use (like contoso.com).</span></span>
    
    <span data-ttu-id="8e3f7-p103">たとえば Azure の AD 接続を使用中に確認した場合でも、ドメインを入力してください。自分のドメインを確認するのには Azure AD 接続を使用する場合、次の 2 つの手順は適用されません。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-p103">Go ahead and enter your domain even if you have verified it while using Azure AD Connect, for example. The following two steps do not apply to you if you used Azure AD Connect to verify your domain.</span></span>
    
4. <span data-ttu-id="8e3f7-119">[Office 365 のすべての DNS ホスティング プロバイダーを作成する DNS レコード](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166)のドメインを所有することを検証するにウィザードの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) that verifies you own the domain.</span></span> 
    
    <span data-ttu-id="8e3f7-p104">例のビデオを表示することができます[ビデオ: 新しい管理センターのセットアップの Office 365](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8)。このビデオに 365 ビジネスのマイクロソフトのデータ保護の手順が含まれていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-p104">You can view an example video of [Video: Setup Office 365 in the new Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Note that this video does not include the data protection steps of Microsoft 365 Business.</span></span>
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a><span data-ttu-id="8e3f7-123">手順 2: ユーザーを追加し、ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="8e3f7-123">Step 2: Add users and assign licenses</span></span>

1. <span data-ttu-id="8e3f7-124">ここではユーザーを追加することも、管理センターで[後からユーザーを追加](add-users-m365b.md)することもできます。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-124">You can add users here, or you can [add users later](add-users-m365b.md) in the admin center.</span></span> 
    
    <span data-ttu-id="8e3f7-125">追加するユーザーには、自動的に Microsoft 365 Business ライセンスが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-125">Any users you add get automatically assigned a Microsoft 365 Business license.</span></span>
    
2. <span data-ttu-id="8e3f7-p105">Microsoft 365 Business のサブスクリプションに既存ユーザーがいる場合 (たとえば、Azure AD Connect を使用した場合)、今すぐこれらのユーザーにライセンスを割り当てるオプションが表示されます。続行して、これらのユーザーにもライセンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-p105">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>
    
3. <span data-ttu-id="8e3f7-p106">追加した新しいユーザーと資格情報を共有するためのオプションも表示されます。それらを印刷、メール、またはダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-p106">You will also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>
    
4. <span data-ttu-id="8e3f7-130">移行のメール メッセージをスキップして、[ **メール メッセージの移行**] ページで [ **次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 
    
    <span data-ttu-id="8e3f7-131">別の電子メール プロバイダーからの移動は、後でデータをコピーする場合、[移行の電子メールと連絡先を Office 365 に](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)することができます。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a><span data-ttu-id="8e3f7-133">手順 3: 自分のドメインを接続します。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-133">Step 3: Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="8e3f7-134">.Onmicrosoft のドメインを使用することを選択した場合、または AD の Azure の接続を使用する場合は、この手順は表示されません。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect, you will not see this step.</span></span> 
  
<span data-ttu-id="8e3f7-135">サービスを設定するには、DNS ホストまたはドメイン レジストラーにあるレコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="8e3f7-p107">セットアップ ウィザードは、通常、レジストラーを検出し、レジストラーの web サイトにある NS レコードを更新するための詳細な手順へのリンクを使用します。インストールされていない場合、[任意のドメイン レジストラーに Office 365 をセットアップするネーム サーバーを変更](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)します。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-p107">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website. If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span>
    
2. <span data-ttu-id="8e3f7-138">メールとその他のサービスが自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-138">Email and other services will be set up for you</span></span>
    
### <a name="step-4-manage-devices-and-work-files"></a><span data-ttu-id="8e3f7-139">手順 4: デバイスを管理し、作業ファイル</span><span class="sxs-lookup"><span data-stu-id="8e3f7-139">Step 4: Manage devices and work files</span></span>

1. <span data-ttu-id="8e3f7-p108">**、モバイル デバイスの作業ファイルを保護する**には、ページは、**上**に**デバイスが紛失または盗難に遭ったときの保護の作業ファイル**と設定の**管理ユーザーがモバイル デバイス上の Office ファイルにアクセスする方法**の両方を設定します。各サブ設定で各設定の横の下向きの矢印をクリックしてアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-p108">On the **Protect work files on your mobile devices** page set both **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** settings to **On**. You can also access each sub-setting by clicking the chevrons next to each setting.</span></span>
  
  <span data-ttu-id="8e3f7-142">しだい、iOS および Android デバイスで保護するは今すぐすべての作業ファイルのライセンスを受けたユーザーの[Office アプリケーションのインストール](set-up-mobile-devices.md)(および Microsoft 365 ビジネス資格情報で認証)。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-142">All of your licensed users' work files are now protected on iOS and Android devices, as soon as they [install Office apps](set-up-mobile-devices.md) (and authenticate with their Microsoft 365 Business credentials).</span></span> 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. <span data-ttu-id="8e3f7-144">**Windows 10 の設定のデバイスの構成**] ページで [ **Windows 10 デバイスをセキュリティで保護された**設定を**オン**に設定します。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-144">On the **Set Windows 10 device configuration** page, set **Secure Windows 10 Devices** setting to **On**.</span></span>
  
   <span data-ttu-id="8e3f7-145">各サブ設定の横にある山形の記号をクリックしてアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-145">You can also access each sub-setting by clicking the chevron next to it.</span></span>
  
3. <span data-ttu-id="8e3f7-p109">**10 の Windows デバイス上の Office のインストール**設定を設定すると、 **[はい]** すべてのユーザー、コンピューターの Windows 10 があり、しないか、既存の Office をインストールする場合] または [Office のインストールを実行] をクリックします。大文字と小文字でない場合は、 **「いいえ**」をこのオプションを設定します。ユーザーのコンピューターを準備した後は管理センターから後で[自動的にインストールする Office](auto-install-or-uninstall-office.md)をできます。手順については、 [Office クライアントのインストールの準備](prepare-for-office-client-deployment.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-p109">Set the **Install Office on Windows 10 Devices** setting to **Yes** if all of your users have Windows 10 computers, and either no existing Office installs, or click-to-run Office installs. If this is not the case, set this option to **No**. You can [automatically install Office](auto-install-or-uninstall-office.md) later from the admin center after you have prepared the user computers. For instructions, see [prepare for Office client installation](prepare-for-office-client-deployment.md).</span></span>
  
    <span data-ttu-id="8e3f7-150">10 の Windows デバイス上のライセンスを受けたユーザーの作業ファイルがすぐに、投影する Microsoft 365 ビジネス Azure AD ドメインまたは Microsoft 365 に同時に参加するときに[新しいコンピューターに Windows の 10 をインストールする](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx)に[、10 の Windows デバイスへの参加](set-up-windows-devices.md)をビジネス Azure AD ドメインです。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-150">The licensed users' work files on Windows 10 devices will be projected as soon as they [join their Windows 10 device](set-up-windows-devices.md) to a Microsoft 365 Business Azure AD domain or [install Windows 10 on a new computer](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) while simultaneously joining the Microsoft 365 Business Azure AD domain.</span></span> 
  
4. <span data-ttu-id="8e3f7-151">[**次へ**] をクリックし、セットアップを終了します。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-151">Click **Next** and you are done with setup.</span></span> 
  
    <span data-ttu-id="8e3f7-152">くださいフィードバックを送信我々 エクスペリエンスを向上させるためには、この手順で。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-152">Please leave us feedback at this step to help us improve the experience.</span></span>
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a><span data-ttu-id="8e3f7-154">その他のセキュリティ設定</span><span class="sxs-lookup"><span data-stu-id="8e3f7-154">Additional security settings</span></span>

<span data-ttu-id="8e3f7-155">だけでなく、セキュリティとコンプライアンスの設定のセットアップ ウィザードで、次の追加設定を設定することも。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-155">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="8e3f7-p110">安全でない添付ファイルからの保護を設定します。**脅威保護の詳細**(ATP) は、悪意のあるコンテンツを識別し、フィッシング詐欺や ransomware のウイルス感染から保護するため、安全でない添付ファイルの配信をブロックします。添付ファイルの保護を有効にするのには[Office 365 ATP の安全な添付ファイルのポリシー設定](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-p110">Set up protection against unsafe attachments. **Advanced Threat Protection** (ATP) identifies malicious content and then blocks delivery of unsafe attachments, helping protect you against phishing schemes and ransomware infections. To activate attachment protection, see [Set up Office 365 ATP Safe Attachments policies](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span></span>
    
- <span data-ttu-id="8e3f7-p111">ユーザーが悪意のあるリンクをクリックしたときは、環境を保護します。ATP は、時に、ユーザーをクリックしてメール内のリンクを検証します。リンクが安全でない場合は、ユーザーがサイトにアクセスしないように警告またはサイトがブロックされたことを通知します。これにより、フィッシング詐欺から保護します。[Office 365 の ATP の安全なリンクのポリシーを設定](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc)または[ポリシーを Office 365 の ATP の安全なリンクを設定](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc)します。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-p111">Protect your environment when users click malicious links. ATP examines links in email at the time a user clicks them. If a link is unsafe, the user is warned not to visit the site or informed that the site has been blocked. This helps protect against phishing schemes. [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) or [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span></span>
    
- <span data-ttu-id="8e3f7-p112">**保持訴訟**でユーザーのメールボックスの全体を配置することで削除済みアイテムを含むすべてのメールボックスの内容を保持できます。手順については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-p112">You can preserve all mailbox content including deleted items by putting a user's entire mailbox on **litigation hold**. For instructions, see</span></span> 
- <span data-ttu-id="8e3f7-166">[Exchange Online Archiving の電子メールの保存期間を設定](security-features.md#set-up-email-retention-with-exchange-online-archiving)します。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-166">[Set up email retention with Exchange Online Archiving](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span></span>
    
- <span data-ttu-id="8e3f7-p113">設定 **・ リテンション ・ ポリシー**をカスタマイズしたなどの一定の時間を保持するか、保存期間の終了時にコンテンツを完全に削除します。カスタマイズされた保存ポリシーでは、セキュリティとコンプライアンス部門、**データ ・ ガバナンス**に移動させることができます\>**の保存**、し、ウィザードの手順です。詳細については、[保存ポリシーの概要](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-p113">Set up customized **retention policies**, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period. You can enable customized retention policies in the Securities and compliance center, go to **Data governance** \> **Retention**, and then follow the steps in the wizard. To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="8e3f7-170">次の手順</span><span class="sxs-lookup"><span data-stu-id="8e3f7-170">Next steps</span></span>

<span data-ttu-id="8e3f7-171">ライセンスがあるユーザーは、次の手順でデバイスをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-171">For the users that have their licenses, the next step is to set up devices.</span></span><br/> <span data-ttu-id="8e3f7-172">「[Microsoft 365 Business ユーザーの Windows デバイスをセットアップする](set-up-windows-devices.md)」と「[Microsoft 365 Business ユーザーのモバイル デバイスをセットアップする](set-up-mobile-devices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-172">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) and [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span> <br/><span data-ttu-id="8e3f7-173">デバイスとアプリの保護ポリシーを設定する方法、およびユーザーのデバイスからデータを削除する方法に関する記事へのリンクについては、「[Microsoft 365 Business を管理する](manage.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e3f7-173">See [Manage Microsoft 365 Business](manage.md) for links to topics on how to set device and app protection polices, and how to remove data from user devices.</span></span> 
  


