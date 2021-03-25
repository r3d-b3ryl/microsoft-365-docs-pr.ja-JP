---
title: Microsoft 365 Business から Microsoft 365 E3 への移行
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: ビジネスを Microsoft 365 Business Premium から Microsoft 365 E3 に移行する方法について説明します。
ms.openlocfilehash: 10630671f3deb7eff0ad0f601d301b90743ee35f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164515"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a><span data-ttu-id="71d53-103">Microsoft 365 Business Premium から Microsoft 365 E3 への移行</span><span class="sxs-lookup"><span data-stu-id="71d53-103">Migrate from Microsoft 365 Business Premium to Microsoft 365 E3</span></span>

<span data-ttu-id="71d53-104">Microsoft 365 Business Premium には、クラス最高のクラウドベースの生産性アプリと、簡単なデバイス管理とセキュリティを組み合わせて、従業員が最善の作業を行える、小規模ビジネスに必要なすべてを備えています。</span><span class="sxs-lookup"><span data-stu-id="71d53-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security that enable your employees to do their best work.</span></span> <span data-ttu-id="71d53-105">ただし、Microsoft 365 Business Premium サブスクリプションを Microsoft 365 E3 に移行する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="71d53-105">In some cases, however, you may need to migrate your Microsoft 365 Business Premium subscription to Microsoft 365 E3.</span></span> 

<span data-ttu-id="71d53-106">たとえば、ビジネスが成長し、300 以上のライセンスが必要です (ところで、おめでとうございます)。</span><span class="sxs-lookup"><span data-stu-id="71d53-106">For example, your business has grown and needs more than 300 licenses (congratulations, by the way).</span></span>

<span data-ttu-id="71d53-107">または、エンタープライズ向け Microsoft 365 Apps、Windows 10 Enterprise E3、エンタープライズ クライアント アクセス ライセンス (CAL) などのエンタープライズ機能が必要です。</span><span class="sxs-lookup"><span data-stu-id="71d53-107">Or, your business needs enterprise features, such as Microsoft 365 Apps for enterprise, Windows 10 Enterprise E3, or Enterprise Client Access Licenses (CALs).</span></span>

<span data-ttu-id="71d53-108">アップグレードは簡単です。管理センターから [アップグレードを開始できます](../commerce/subscriptions/upgrade-to-different-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="71d53-108">Upgrading is easy: you can start the upgrade [from the Admin center](../commerce/subscriptions/upgrade-to-different-plan.md).</span></span> <span data-ttu-id="71d53-109">現在のサブスクリプションのすべてのデータと構成が維持されます。</span><span class="sxs-lookup"><span data-stu-id="71d53-109">All your data and configuration in your current subscription is maintained.</span></span> <span data-ttu-id="71d53-110">新しい機能を利用する以外に、移行の準備には何もする必要もありません。その後は何も行いません。</span><span class="sxs-lookup"><span data-stu-id="71d53-110">There's nothing for you to do to prepare for the migration and nothing to do afterward, except take advantage of the new features.</span></span>

>[!Note]
><span data-ttu-id="71d53-111">また、最大 300 シートの Microsoft 365 Business Premium サブスクリプションを使用し、300 シートを超える場合は Microsoft 365 E3 サブスクリプションを取得できます。</span><span class="sxs-lookup"><span data-stu-id="71d53-111">You can also use a Microsoft 365 Business Premium subscription for up to 300 seats and get a Microsoft 365 E3 subscription for more than 300 seats.</span></span> <span data-ttu-id="71d53-112">ただし、Microsoft Defender for Office 365 は Microsoft 365 E3 には含まれません。</span><span class="sxs-lookup"><span data-stu-id="71d53-112">However, Microsoft Defender for Office 365 is not included with Microsoft 365 E3.</span></span> <span data-ttu-id="71d53-113">脅威の保護を継続するには、Office 365 ライセンスに対して Defender を追加して、Office 365 ポリシーの Defender のスコープ内のすべてのユーザーがライセンスを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71d53-113">For continued threat protection, you should add additional Defender for Office 365 licenses so that all of the users in scope of your Defender for Office 365 polices are licensed.</span></span>
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a><span data-ttu-id="71d53-114">Microsoft 365 Business Premium と Microsoft 365 Enterprise の違い</span><span class="sxs-lookup"><span data-stu-id="71d53-114">Differences between Microsoft 365 Business Premium and Microsoft 365 Enterprise</span></span>

<span data-ttu-id="71d53-115">次の表に、Microsoft 365 Business Premium と Microsoft 365 E3 の違いを示します。</span><span class="sxs-lookup"><span data-stu-id="71d53-115">This table shows the differences between Microsoft 365 Business Premium and Microsoft 365 E3.</span></span>

| <span data-ttu-id="71d53-116">機能</span><span class="sxs-lookup"><span data-stu-id="71d53-116">Feature</span></span>    | <span data-ttu-id="71d53-117">Microsoft 365 Business Premium のサポート</span><span class="sxs-lookup"><span data-stu-id="71d53-117">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="71d53-118">Microsoft 365 E3 でのサポート</span><span class="sxs-lookup"><span data-stu-id="71d53-118">Support in Microsoft 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="71d53-119">**社内**</span><span class="sxs-lookup"><span data-stu-id="71d53-119">**On-premises**</span></span>        | | | 
| <span data-ttu-id="71d53-120">Windows 10</span><span class="sxs-lookup"><span data-stu-id="71d53-120">Windows 10</span></span>    | <span data-ttu-id="71d53-121">Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="71d53-121">Windows 10 Business</span></span>  |     <span data-ttu-id="71d53-122">Windows 10 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="71d53-122">Windows 10 Enterprise E3</span></span>| 
| <span data-ttu-id="71d53-123">Officeアプリ\*</span><span class="sxs-lookup"><span data-stu-id="71d53-123">Office apps\*</span></span>    | [<span data-ttu-id="71d53-124">Microsoft 365 Apps for business</span><span class="sxs-lookup"><span data-stu-id="71d53-124">Microsoft 365 Apps for business</span></span>](#office-365-business)    | <span data-ttu-id="71d53-125">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="71d53-125">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="71d53-126">**クラウド生産性アプリ**</span><span class="sxs-lookup"><span data-stu-id="71d53-126">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="71d53-127">Exchange Online と Outlook</span><span class="sxs-lookup"><span data-stu-id="71d53-127">Exchange Online and Outlook</span></span>    | <span data-ttu-id="71d53-128">メールボックスあたり 50 GB のストレージ制限と Exchange Online の無制限のアーカイブ</span><span class="sxs-lookup"><span data-stu-id="71d53-128">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>    | <span data-ttu-id="71d53-129">メールボックスあたり 100 GB のストレージ制限と Exchange Online の無制限のアーカイブ</span><span class="sxs-lookup"><span data-stu-id="71d53-129">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> | 
| <span data-ttu-id="71d53-130">Teams</span><span class="sxs-lookup"><span data-stu-id="71d53-130">Teams</span></span>    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| <span data-ttu-id="71d53-133">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="71d53-133">OneDrive for Business</span></span>    | <span data-ttu-id="71d53-134">ユーザーあたり 1 TB のストレージ制限</span><span class="sxs-lookup"><span data-stu-id="71d53-134">1 TB storage limit per user</span></span>    | <span data-ttu-id="71d53-135">無制限</span><span class="sxs-lookup"><span data-stu-id="71d53-135">Unlimited</span></span> | 
| <span data-ttu-id="71d53-136">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="71d53-136">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| <span data-ttu-id="71d53-139">**脅威の防止**</span><span class="sxs-lookup"><span data-stu-id="71d53-139">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="71d53-140">攻撃表面の縮小機能</span><span class="sxs-lookup"><span data-stu-id="71d53-140">Attack surface reduction capabilities</span></span>    | [<span data-ttu-id="71d53-141">この一覧を見る</span><span class="sxs-lookup"><span data-stu-id="71d53-141">See this list</span></span>](#threat-protection) | <span data-ttu-id="71d53-142">Microsoft Edge のハードウェア ベースの分離のエンタープライズ管理</span><span class="sxs-lookup"><span data-stu-id="71d53-142">Enterprise management of hardware-based isolation for Microsoft Edge</span></span> | 
| <span data-ttu-id="71d53-143">Microsoft Defender for Office 365 プラン 1</span><span class="sxs-lookup"><span data-stu-id="71d53-143">Defender for Office 365 Plan 1</span></span> | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | <span data-ttu-id="71d53-145">含まれていませんが、追加できます</span><span class="sxs-lookup"><span data-stu-id="71d53-145">Not included, but can be added on</span></span> | 
| <span data-ttu-id="71d53-146">**ID 管理**</span><span class="sxs-lookup"><span data-stu-id="71d53-146">**Identity management**</span></span>        | | | 
| <span data-ttu-id="71d53-147">ハイブリッド Azure Active Directory (Azure AD) アカウントのセルフサービス パスワードリセット、Azure AD 多要素認証 (MFA)、条件付きアクセス、オンプレミス ID のパスワード ライトバック</span><span class="sxs-lookup"><span data-stu-id="71d53-147">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| <span data-ttu-id="71d53-150">クラウド アプリの検出、Azure AD接続の正常性</span><span class="sxs-lookup"><span data-stu-id="71d53-150">Cloud App Discovery, Azure AD Connect Health</span></span>    |     | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| <span data-ttu-id="71d53-152">Azure AD Office 365 アプリ シングル Sign-On (SSO): 1 ユーザーあたり 10 アプリ (ギャラリー SaaS アプリ (Salesforce など)\*</span><span class="sxs-lookup"><span data-stu-id="71d53-152">Azure AD Office 365 apps Single Sign-On (SSO): 10 apps per user (Gallery SaaS apps such as Salesforce)\*</span></span> | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| <span data-ttu-id="71d53-155">Azure AD Premium 1 SSO: 制限なし (Azure AD アプリケーション プロキシ経由のオンプレミス アプリと、アプリ統合テンプレートを使用したギャラリー以外Self-Service)</span><span class="sxs-lookup"><span data-stu-id="71d53-155">Azure AD Premium 1 SSO: no limit (On-premises apps through Azure AD Application Proxy and non-gallery apps using Self-Service App Integration templates)</span></span>    |     | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| <span data-ttu-id="71d53-157">**デバイスおよびアプリの管理**</span><span class="sxs-lookup"><span data-stu-id="71d53-157">**Device and app management**</span></span>        | | | 
| <span data-ttu-id="71d53-158">Microsoft Intune、Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="71d53-158">Microsoft Intune, Windows Autopilot</span></span>|     ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
|<span data-ttu-id="71d53-161">仮想デスクトップ アクセス (VDA)</span><span class="sxs-lookup"><span data-stu-id="71d53-161">Virtual Desktop Access (VDA)</span></span>    |  |     ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
|<span data-ttu-id="71d53-163">Windows 仮想デスクトップ (WVD)</span><span class="sxs-lookup"><span data-stu-id="71d53-163">Windows Virtual Desktop (WVD)</span></span>    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png) |     ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
|<span data-ttu-id="71d53-166">共有コンピューターのライセンス認証 (SCA)</span><span class="sxs-lookup"><span data-stu-id="71d53-166">Shared Computer Activation (SCA)</span></span>    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png) |     ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| <span data-ttu-id="71d53-169">Microsoft デスクトップ最適化パッケージ</span><span class="sxs-lookup"><span data-stu-id="71d53-169">Microsoft Desktop Optimization Package</span></span>    | |     ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| <span data-ttu-id="71d53-171">**情報保護**</span><span class="sxs-lookup"><span data-stu-id="71d53-171">**Information protection**</span></span>        | | | 
| <span data-ttu-id="71d53-172">Office 365 データ損失防止、Azure Information Protection Plan 1</span><span class="sxs-lookup"><span data-stu-id="71d53-172">Office 365 Data Loss Prevention, Azure Information Protection Plan 1</span></span>    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| <span data-ttu-id="71d53-175">エンドポイント DLP のウィンドウ情報保護</span><span class="sxs-lookup"><span data-stu-id="71d53-175">Window Information Protection for endpoint DLP</span></span>    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| <span data-ttu-id="71d53-178">**クライアント アクセス ライセンス (CAL 権限)**</span><span class="sxs-lookup"><span data-stu-id="71d53-178">**Client Access License (CAL rights)**</span></span>    | | |     
| <span data-ttu-id="71d53-179">Enterprise CAL Suite (Exchange、SharePoint、Skype、Windows、Microsoft Endpoint Configuration Manager、Windows Rights Management)</span><span class="sxs-lookup"><span data-stu-id="71d53-179">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)</span></span>| |         ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| <span data-ttu-id="71d53-181">**コンプライアンス**</span><span class="sxs-lookup"><span data-stu-id="71d53-181">**Compliance**</span></span>        | | | 
| <span data-ttu-id="71d53-182">無制限のメール アーカイブ</span><span class="sxs-lookup"><span data-stu-id="71d53-182">Unlimited email archiving</span></span>    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| <span data-ttu-id="71d53-185">コンプライアンス マネージャー</span><span class="sxs-lookup"><span data-stu-id="71d53-185">Compliance Manager</span></span>    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| <span data-ttu-id="71d53-188">電子情報開示</span><span class="sxs-lookup"><span data-stu-id="71d53-188">eDiscovery</span></span>    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| <span data-ttu-id="71d53-191">インプレイスホールドと訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="71d53-191">In-place hold and litigation hold</span></span>    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
| <span data-ttu-id="71d53-194">メッセージング レコード管理 (MRM) 保持タグとアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="71d53-194">Messaging Records Management (MRM) retention tags and retention policies</span></span>    | ![Microsoft 365 Business Premium に含まれる](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれる](../media/check-mark.png) | 
||||

<span data-ttu-id="71d53-197">\* SaaS アプリへのアクセスが割り当てられているユーザーは、最大 10 のアプリへの SSO アクセスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="71d53-197">\* Users who have been assigned access to SaaS apps can get SSO access to up to 10 apps.</span></span> <span data-ttu-id="71d53-198">管理者は SSO を構成し、さまざまな SaaS アプリへのユーザー アクセスを変更できますが、SSO アクセスは一度に 1 ユーザーあたり 10 アプリに対してしか許可されません。</span><span class="sxs-lookup"><span data-stu-id="71d53-198">Admins can configure SSO and change user access to different SaaS apps, but SSO access is only allowed for 10 apps per user at a time.</span></span> <span data-ttu-id="71d53-199">すべてのOffice 365 アプリは、1 つのアプリとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="71d53-199">All Office 365 apps are counted as a single app.</span></span>

## <a name="migration"></a><span data-ttu-id="71d53-200">移行</span><span class="sxs-lookup"><span data-stu-id="71d53-200">Migration</span></span>

<span data-ttu-id="71d53-201">移行するには、パートナーと一緒に Microsoft 365 Business Premium サブスクリプションとライセンスを、そのライセンスを持つ適切な Microsoft 365 E3 サブスクリプションに移行します。</span><span class="sxs-lookup"><span data-stu-id="71d53-201">To migrate, work with your partner to move your Microsoft 365 Business Premium subscription and licenses to a suitable Microsoft 365 E3 subscription with its licenses.</span></span>

<span data-ttu-id="71d53-202">次のセクションでは、移行後に行う必要がある変更、変更がある場合、および実行できる操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="71d53-202">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="microsoft-365-subscription-configuration-and-data"></a><span data-ttu-id="71d53-203">Microsoft 365 サブスクリプションの構成とデータ</span><span class="sxs-lookup"><span data-stu-id="71d53-203">Microsoft 365 subscription configuration and data</span></span>

<span data-ttu-id="71d53-204">移行する前に、現在のサブスクリプションまたはデータに変更を加える必要は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="71d53-204">You don't need to make any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="71d53-205">サブスクリプションの構成 (名前DNS ドメインなど)。</span><span class="sxs-lookup"><span data-stu-id="71d53-205">Subscription configuration, such as DNS domain names.</span></span>
- <span data-ttu-id="71d53-206">多要素認証や条件付きアクセス ポリシーなどのユーザー アカウントとグループ アカウントと認証設定。</span><span class="sxs-lookup"><span data-stu-id="71d53-206">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="71d53-207">生産性サービスの構成とそのデータ (Teams、Exchange Online メールボックス、SharePoint Online サイト、OneDrive for Business フォルダー、OneNote ノートブックなど)。</span><span class="sxs-lookup"><span data-stu-id="71d53-207">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

<span data-ttu-id="71d53-208">これで、ユーザーは Exchange Online メールボックスと OneDrive for Business フォルダーで無制限のストレージを利用できます。</span><span class="sxs-lookup"><span data-stu-id="71d53-208">Your users can now enjoy unlimited storage in the Exchange Online mailboxes and OneDrive for Business folders.</span></span>

<span data-ttu-id="71d53-209">10 以上のアプリで、クラウド アプリの検出、Azure AD接続正常性、SSO の使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="71d53-209">You can begin using Cloud App Discovery, Azure AD Connect Health, and SSO for more than 10 apps.</span></span>

<a name="threat-protection"></a>
### <a name="threat-protection"></a><span data-ttu-id="71d53-210">脅威に対する保護</span><span class="sxs-lookup"><span data-stu-id="71d53-210">Threat protection</span></span>

<span data-ttu-id="71d53-211">Windows 10 Business には、次の保護が含まれています。</span><span class="sxs-lookup"><span data-stu-id="71d53-211">Windows 10 Business includes these protections:</span></span>

- <span data-ttu-id="71d53-212">オペレーティング システムの起動プロセスの整合性の適用</span><span class="sxs-lookup"><span data-stu-id="71d53-212">Integrity enforcement of operating system boot up process</span></span>
- <span data-ttu-id="71d53-213">機密性の高いオペレーティング コンポーネントの整合性の適用</span><span class="sxs-lookup"><span data-stu-id="71d53-213">Integrity enforcement of sensitive operating components</span></span>
- <span data-ttu-id="71d53-214">高度な脆弱性とゼロデイの悪用の軽減策</span><span class="sxs-lookup"><span data-stu-id="71d53-214">Advanced vulnerability and zero-day exploit mitigations</span></span>
- <span data-ttu-id="71d53-215">Microsoft Edge、Internet Explorer、および Chrome の評判ベースのネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="71d53-215">Reputation-based network protection for Microsoft Edge, Internet Explorer, and Chrome</span></span>
- <span data-ttu-id="71d53-216">ホスト ベースのファイアウォール</span><span class="sxs-lookup"><span data-stu-id="71d53-216">Host-based firewall</span></span>
- <span data-ttu-id="71d53-217">ランサムウェアの軽減策</span><span class="sxs-lookup"><span data-stu-id="71d53-217">Ransomware mitigations</span></span>
- <span data-ttu-id="71d53-218">Microsoft Edge のハードウェア ベースの分離</span><span class="sxs-lookup"><span data-stu-id="71d53-218">Hardware-based isolation for Microsoft Edge</span></span>
- <span data-ttu-id="71d53-219">インテリジェント セキュリティ グラフによるアプリケーション制御</span><span class="sxs-lookup"><span data-stu-id="71d53-219">Application control powered by the Intelligent Security Graph</span></span>
- <span data-ttu-id="71d53-220">デバイスコントロール (USB)</span><span class="sxs-lookup"><span data-stu-id="71d53-220">Device control (USB)</span></span>
- <span data-ttu-id="71d53-221">Web ベースの脅威に対するネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="71d53-221">Network protection for web-based threats</span></span>
- <span data-ttu-id="71d53-222">ホスト侵入防止ルール</span><span class="sxs-lookup"><span data-stu-id="71d53-222">Host intrusion prevention rules</span></span>

<span data-ttu-id="71d53-223">Windows 10 Enterprise E3 には、Microsoft Edge のハードウェア ベースの分離のエンタープライズ管理も含まれています。</span><span class="sxs-lookup"><span data-stu-id="71d53-223">Windows 10 Enterprise E3 also includes enterprise management of hardware-based isolation for Microsoft Edge.</span></span>

>[!Note]
><span data-ttu-id="71d53-224">Microsoft 365 E3 に移行されたユーザーは、継続的な脅威保護のために、Office 365 ライセンスの Microsoft Defender が必要です。</span><span class="sxs-lookup"><span data-stu-id="71d53-224">Users migrated to Microsoft 365 E3 will each require a Microsoft Defender for Office 365 license for continued threat protection.</span></span> <span data-ttu-id="71d53-225">Office 365 の警察の Defender のスコープ内のすべてのユーザーがライセンスを取得するには、Office 36 Office 5 ライセンスに対して追加の Defender を購入してください。</span><span class="sxs-lookup"><span data-stu-id="71d53-225">Be sure to purchase additional Defender for Office 365 licenses so that all of the users in scope of your Defender for Office 365 polices are licensed.</span></span> 
>

### <a name="device-management-with-intune"></a><span data-ttu-id="71d53-226">Intune を使用したデバイス管理</span><span class="sxs-lookup"><span data-stu-id="71d53-226">Device management with Intune</span></span>

<span data-ttu-id="71d53-227">移行する前に、現在の Intune 構成に変更を加える必要は一切ない。これには、登録済みデバイスとデバイスとアプリの設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="71d53-227">You don't need to make any changes to your current Intune configuration before migrating, which includes enrolled devices and device and app settings.</span></span>

### <a name="windows-10"></a><span data-ttu-id="71d53-228">Windows 10</span><span class="sxs-lookup"><span data-stu-id="71d53-228">Windows 10</span></span>

<span data-ttu-id="71d53-229">Microsoft 365 Business Premium には、Windows AutoPilot を使用してインストールできる Windows 10 Business が含まれています。</span><span class="sxs-lookup"><span data-stu-id="71d53-229">Microsoft 365 Business Premium includes Windows 10 Business, which you can install with Windows AutoPilot.</span></span> <span data-ttu-id="71d53-230">Microsoft 365 E3 に移行すると、各ユーザー ライセンスに Windows 10 Enterprise E3 が含まれます。Windows Autopilot を使用してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="71d53-230">When you migrate to Microsoft 365 E3, each user license includes Windows 10 Enterprise E3, which you can also install with Windows Autopilot.</span></span>

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a><span data-ttu-id="71d53-231">Microsoft 365 Apps for business</span><span class="sxs-lookup"><span data-stu-id="71d53-231">Microsoft 365 Apps for business</span></span>

<span data-ttu-id="71d53-232">デバイスにインストールされている Microsoft 365 Apps for Business クライアントは、Microsoft 365 Apps for enterprise の機能の使用を自動的に開始します。</span><span class="sxs-lookup"><span data-stu-id="71d53-232">Your Microsoft 365 Apps for business client installed on your devices will automatically begin to use the features of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="71d53-233">移行後、次のコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="71d53-233">After migration, you can now use:</span></span>

 - <span data-ttu-id="71d53-234">グループ ポリシーのサポート</span><span class="sxs-lookup"><span data-stu-id="71d53-234">Group Policy support</span></span>
 - <span data-ttu-id="71d53-235">スプレッドシートの比較と照会</span><span class="sxs-lookup"><span data-stu-id="71d53-235">Spreadsheet compare and inquire</span></span>
 - <span data-ttu-id="71d53-236">ビジネス インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="71d53-236">Business intelligence</span></span>

