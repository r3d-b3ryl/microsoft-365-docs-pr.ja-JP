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
description: Microsoft 365 Business Premium から Microsoft 365 E3 にビジネスを移行する方法について説明します。
ms.openlocfilehash: 3f1bb9591e1bd2bac49326325ce6c8c2d6778497
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558241"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a><span data-ttu-id="9e257-103">Microsoft 365 Business Premium から Microsoft 365 E3 への移行</span><span class="sxs-lookup"><span data-stu-id="9e257-103">Migrate from Microsoft 365 Business Premium to Microsoft 365 E3</span></span>

<span data-ttu-id="9e257-104">Microsoft 365 Business Premium は、お客様の中小企業に必要なすべての機能を備えており、クラスを持つクラウドベースの生産性向上アプリをシンプルなデバイス管理およびセキュリティと組み合わせることにより、従業員が最高の作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9e257-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security that enable your employees to do their best work.</span></span> <span data-ttu-id="9e257-105">ただし、場合によっては、Microsoft 365 Business Premium サブスクリプションを Microsoft 365 E3 に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e257-105">In some cases, however, you may need to migrate your Microsoft 365 Business Premium subscription to Microsoft 365 E3.</span></span> 

<span data-ttu-id="9e257-106">たとえば、ビジネスの成長が増え、300個を超えるライセンスが必要になりました (ご利用おめでとうございます)。</span><span class="sxs-lookup"><span data-stu-id="9e257-106">For example, your business has grown and needs more than 300 licenses (congratulations, by the way).</span></span>

<span data-ttu-id="9e257-107">または、ビジネスには、Microsoft 365 Apps for enterprise、Windows 10 Enterprise E3、エンタープライズクライアントアクセスライセンス (Cal) などのエンタープライズ機能が必要です。</span><span class="sxs-lookup"><span data-stu-id="9e257-107">Or, your business needs enterprise features, such as Microsoft 365 Apps for enterprise, Windows 10 Enterprise E3, or Enterprise Client Access Licenses (CALs).</span></span>

<span data-ttu-id="9e257-108">アップグレードは簡単です。 [管理センターから](../commerce/subscriptions/upgrade-to-different-plan.md)アップグレードを開始できます。</span><span class="sxs-lookup"><span data-stu-id="9e257-108">Upgrading is easy: you can start the upgrade [from the Admin center](../commerce/subscriptions/upgrade-to-different-plan.md).</span></span> <span data-ttu-id="9e257-109">現在のサブスクリプションのすべてのデータと構成が保持されます。</span><span class="sxs-lookup"><span data-stu-id="9e257-109">All your data and configuration in your current subscription is maintained.</span></span> <span data-ttu-id="9e257-110">移行を準備するために実行する必要はありません。その後は、新しい機能を利用する以外に何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9e257-110">There's nothing for you to do to prepare for the migration and nothing to do afterward, except take advantage of the new features.</span></span>

>[!Note]
><span data-ttu-id="9e257-111">また、Microsoft 365 Business Premium サブスクリプションを最大300の席で使用することもできます。また、Microsoft 365 E3 サブスクリプションは、300さらに多くのユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="9e257-111">You can also use a Microsoft 365 Business Premium subscription for up to 300 seats and get a Microsoft 365 E3 subscription for more than 300 seats.</span></span> <span data-ttu-id="9e257-112">ただし、Microsoft Defender for Office 365 は、Microsoft 365 E3 には含まれていません。</span><span class="sxs-lookup"><span data-stu-id="9e257-112">However, Microsoft Defender for Office 365 is not included with Microsoft 365 E3.</span></span> <span data-ttu-id="9e257-113">引き続き脅威を保護するには、office 365 ライセンス用の追加の Defender を追加して、Defender for Office 365 ポリシーの範囲内にあるすべてのユーザーがライセンスを付与されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e257-113">For continued threat protection, you should add additional Defender for Office 365 licenses so that all of the users in scope of your Defender for Office 365 polices are licensed.</span></span>
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a><span data-ttu-id="9e257-114">Microsoft 365 Business Premium と Microsoft 365 Enterprise の相違点</span><span class="sxs-lookup"><span data-stu-id="9e257-114">Differences between Microsoft 365 Business Premium and Microsoft 365 Enterprise</span></span>

<span data-ttu-id="9e257-115">次の表に、Microsoft 365 Business Premium と Microsoft 365 E3 の相違点を示します。</span><span class="sxs-lookup"><span data-stu-id="9e257-115">This table shows the differences between Microsoft 365 Business Premium and Microsoft 365 E3.</span></span>

| <span data-ttu-id="9e257-116">機能</span><span class="sxs-lookup"><span data-stu-id="9e257-116">Feature</span></span>    | <span data-ttu-id="9e257-117">Microsoft 365 Business Premium でのサポート</span><span class="sxs-lookup"><span data-stu-id="9e257-117">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="9e257-118">Microsoft 365 E3 のサポート</span><span class="sxs-lookup"><span data-stu-id="9e257-118">Support in Microsoft 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="9e257-119">**社内**</span><span class="sxs-lookup"><span data-stu-id="9e257-119">**On-premises**</span></span>        | | | 
| <span data-ttu-id="9e257-120">Windows 10</span><span class="sxs-lookup"><span data-stu-id="9e257-120">Windows 10</span></span>    | <span data-ttu-id="9e257-121">Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="9e257-121">Windows 10 Business</span></span>  |     <span data-ttu-id="9e257-122">Windows 10 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="9e257-122">Windows 10 Enterprise E3</span></span>| 
| <span data-ttu-id="9e257-123">Office アプリ \*</span><span class="sxs-lookup"><span data-stu-id="9e257-123">Office apps\*</span></span>    | [<span data-ttu-id="9e257-124">Microsoft 365 Apps for business</span><span class="sxs-lookup"><span data-stu-id="9e257-124">Microsoft 365 Apps for business</span></span>](#office-365-business)    | <span data-ttu-id="9e257-125">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="9e257-125">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="9e257-126">**クラウド生産性アプリ**</span><span class="sxs-lookup"><span data-stu-id="9e257-126">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="9e257-127">Exchange Online および Outlook</span><span class="sxs-lookup"><span data-stu-id="9e257-127">Exchange Online and Outlook</span></span>    | <span data-ttu-id="9e257-128">メールボックスごとに 50 GB の格納域の制限と無制限の Exchange Online アーカイブ</span><span class="sxs-lookup"><span data-stu-id="9e257-128">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>    | <span data-ttu-id="9e257-129">メールボックスごとに 100 GB の格納域の制限と無制限の Exchange Online アーカイブ</span><span class="sxs-lookup"><span data-stu-id="9e257-129">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> | 
| <span data-ttu-id="9e257-130">Teams</span><span class="sxs-lookup"><span data-stu-id="9e257-130">Teams</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="9e257-133">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="9e257-133">OneDrive for Business</span></span>    | <span data-ttu-id="9e257-134">ユーザーごとに 1 TB のストレージ制限</span><span class="sxs-lookup"><span data-stu-id="9e257-134">1 TB storage limit per user</span></span>    | <span data-ttu-id="9e257-135">無制限</span><span class="sxs-lookup"><span data-stu-id="9e257-135">Unlimited</span></span> | 
| <span data-ttu-id="9e257-136">Yammer、SharePoint Online、Planner、Stream</span><span class="sxs-lookup"><span data-stu-id="9e257-136">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="9e257-139">ミル Eiq</span><span class="sxs-lookup"><span data-stu-id="9e257-139">MileIQ</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | | 
| <span data-ttu-id="9e257-141">**脅威保護**</span><span class="sxs-lookup"><span data-stu-id="9e257-141">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="9e257-142">攻撃対象領域の削減機能</span><span class="sxs-lookup"><span data-stu-id="9e257-142">Attack surface reduction capabilities</span></span>    | [<span data-ttu-id="9e257-143">このリストを表示する</span><span class="sxs-lookup"><span data-stu-id="9e257-143">See this list</span></span>](#threat-protection) | <span data-ttu-id="9e257-144">Microsoft Edge のハードウェアベースの分離のエンタープライズ管理</span><span class="sxs-lookup"><span data-stu-id="9e257-144">Enterprise management of hardware-based isolation for Microsoft Edge</span></span> | 
| <span data-ttu-id="9e257-145">Office 用 Defender 365 プラン1</span><span class="sxs-lookup"><span data-stu-id="9e257-145">Defender for Office 365 Plan 1</span></span> | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | <span data-ttu-id="9e257-147">含まれていませんが、に追加できます。</span><span class="sxs-lookup"><span data-stu-id="9e257-147">Not included, but can be added on</span></span> | 
| <span data-ttu-id="9e257-148">**ID 管理**</span><span class="sxs-lookup"><span data-stu-id="9e257-148">**Identity management**</span></span>        | | | 
| <span data-ttu-id="9e257-149">ハイブリッド Azure Active Directory (Azure AD) アカウントのセルフサービスによるパスワードのリセット、Azure AD 多要素認証 (MFA)、条件付きアクセス、オンプレミス id のパスワードの書き戻し</span><span class="sxs-lookup"><span data-stu-id="9e257-149">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="9e257-152">Cloud App Discovery、Azure AD Connect Health</span><span class="sxs-lookup"><span data-stu-id="9e257-152">Cloud App Discovery, Azure AD Connect Health</span></span>    |     | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="9e257-154">Azure AD Office 365 apps Single Sign-On (SSO): ユーザーあたり10個のアプリ (Salesforce などのギャラリー SaaS アプリ) \*</span><span class="sxs-lookup"><span data-stu-id="9e257-154">Azure AD Office 365 apps Single Sign-On (SSO): 10 apps per user (Gallery SaaS apps such as Salesforce)\*</span></span> | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="9e257-157">Azure AD Premium 1 SSO: 制限なし (Self-Service アプリ統合テンプレートを使用した、Azure AD アプリケーションプロキシおよび非ギャラリーアプリからのオンプレミスアプリ)</span><span class="sxs-lookup"><span data-stu-id="9e257-157">Azure AD Premium 1 SSO: no limit (On-premises apps through Azure AD Application Proxy and non-gallery apps using Self-Service App Integration templates)</span></span>    |     | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="9e257-159">**デバイスとアプリの管理**</span><span class="sxs-lookup"><span data-stu-id="9e257-159">**Device and app management**</span></span>        | | | 
| <span data-ttu-id="9e257-160">Microsoft Intune、Windows 自動操縦</span><span class="sxs-lookup"><span data-stu-id="9e257-160">Microsoft Intune, Windows Autopilot</span></span>|     ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
|<span data-ttu-id="9e257-163">仮想デスクトップアクセス (VDA)</span><span class="sxs-lookup"><span data-stu-id="9e257-163">Virtual Desktop Access (VDA)</span></span>    |  |     ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
|<span data-ttu-id="9e257-165">Windows 仮想デスクトップ (WVD)</span><span class="sxs-lookup"><span data-stu-id="9e257-165">Windows Virtual Desktop (WVD)</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png) |     ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
|<span data-ttu-id="9e257-168">共有コンピューターのライセンス認証 (SCA)</span><span class="sxs-lookup"><span data-stu-id="9e257-168">Shared Computer Activation (SCA)</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png) |     ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="9e257-171">Microsoft デスクトップ最適化パッケージ</span><span class="sxs-lookup"><span data-stu-id="9e257-171">Microsoft Desktop Optimization Package</span></span>    | |     ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="9e257-173">**情報保護**</span><span class="sxs-lookup"><span data-stu-id="9e257-173">**Information protection**</span></span>        | | | 
| <span data-ttu-id="9e257-174">Office 365 データ損失防止、Azure Information Protection プラン1</span><span class="sxs-lookup"><span data-stu-id="9e257-174">Office 365 Data Loss Prevention, Azure Information Protection Plan 1</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="9e257-177">エンドポイント DLP のウィンドウ情報の保護</span><span class="sxs-lookup"><span data-stu-id="9e257-177">Window Information Protection for endpoint DLP</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="9e257-180">**クライアントアクセスライセンス (CAL 権限)**</span><span class="sxs-lookup"><span data-stu-id="9e257-180">**Client Access License (CAL rights)**</span></span>    | | |     
| <span data-ttu-id="9e257-181">エンタープライズ CAL スイート (Exchange、SharePoint、Skype、Windows、Microsoft エンドポイント構成マネージャー、Windows Rights Management)</span><span class="sxs-lookup"><span data-stu-id="9e257-181">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)</span></span>| |         ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="9e257-183">**コンプライアンス**</span><span class="sxs-lookup"><span data-stu-id="9e257-183">**Compliance**</span></span>        | | | 
| <span data-ttu-id="9e257-184">無制限のメールのアーカイブ</span><span class="sxs-lookup"><span data-stu-id="9e257-184">Unlimited email archiving</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="9e257-187">コンプライアンス マネージャー</span><span class="sxs-lookup"><span data-stu-id="9e257-187">Compliance Manager</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="9e257-190">電子情報開示</span><span class="sxs-lookup"><span data-stu-id="9e257-190">eDiscovery</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="9e257-193">インプレース保持と訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="9e257-193">In-place hold and litigation hold</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="9e257-196">メッセージング レコード管理 (MRM) 保持タグとアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="9e257-196">Messaging Records Management (MRM) retention tags and retention policies</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
||||

<span data-ttu-id="9e257-199">\* SaaS アプリへのアクセスが割り当てられているユーザーは、最大10個のアプリへの SSO アクセスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="9e257-199">\* Users who have been assigned access to SaaS apps can get SSO access to up to 10 apps.</span></span> <span data-ttu-id="9e257-200">管理者は SSO を構成し、さまざまな SaaS アプリへのユーザーアクセスを変更できますが、SSO アクセスは、一度に1ユーザーあたり10個のアプリに対してのみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="9e257-200">Admins can configure SSO and change user access to different SaaS apps, but SSO access is only allowed for 10 apps per user at a time.</span></span> <span data-ttu-id="9e257-201">すべての Office 365 アプリは、1つのアプリとして数えられます。</span><span class="sxs-lookup"><span data-stu-id="9e257-201">All Office 365 apps are counted as a single app.</span></span>

## <a name="migration"></a><span data-ttu-id="9e257-202">移行</span><span class="sxs-lookup"><span data-stu-id="9e257-202">Migration</span></span>

<span data-ttu-id="9e257-203">移行するには、パートナーと協力して、Microsoft 365 Business Premium サブスクリプションとライセンスを、そのライセンスを使用して適切な Microsoft 365 E3 サブスクリプションに移行します。</span><span class="sxs-lookup"><span data-stu-id="9e257-203">To migrate, work with your partner to move your Microsoft 365 Business Premium subscription and licenses to a suitable Microsoft 365 E3 subscription with its licenses.</span></span>

<span data-ttu-id="9e257-204">次のセクションでは、移行後に行う必要のある変更点と、その変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e257-204">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="microsoft-365-subscription-configuration-and-data"></a><span data-ttu-id="9e257-205">Microsoft 365 サブスクリプションの構成とデータ</span><span class="sxs-lookup"><span data-stu-id="9e257-205">Microsoft 365 subscription configuration and data</span></span>

<span data-ttu-id="9e257-206">移行する前に、現在のサブスクリプションまたはデータを変更する必要はありません。次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="9e257-206">You don't need to make any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="9e257-207">サブスクリプションの構成 (DNS ドメイン名など)。</span><span class="sxs-lookup"><span data-stu-id="9e257-207">Subscription configuration, such as DNS domain names.</span></span>
- <span data-ttu-id="9e257-208">ユーザーおよびグループのアカウントと、複数要素の認証や条件付きアクセスポリシーなどの認証設定。</span><span class="sxs-lookup"><span data-stu-id="9e257-208">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="9e257-209">プロダクティビティサービスの構成とそのデータ (Teams、Exchange Online メールボックス、SharePoint Online サイト、OneDrive for Business フォルダー、OneNote ノートブックなど)。</span><span class="sxs-lookup"><span data-stu-id="9e257-209">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

<span data-ttu-id="9e257-210">ユーザーは、Exchange Online メールボックスおよび OneDrive for Business フォルダーで無制限のストレージを利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9e257-210">Your users can now enjoy unlimited storage in the Exchange Online mailboxes and OneDrive for Business folders.</span></span>

<span data-ttu-id="9e257-211">最大10個のアプリに対して、クラウドアプリの検出、Azure AD Connect の正常性、および SSO の使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="9e257-211">You can begin using Cloud App Discovery, Azure AD Connect Health, and SSO for more than 10 apps.</span></span>

>[!Note]
><span data-ttu-id="9e257-212">Microsoft 365 E3 に移行されたユーザーは、ミル Eiq を使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="9e257-212">Users migrated to Microsoft 365 E3 can no longer use MileIQ.</span></span>
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a><span data-ttu-id="9e257-213">脅威保護</span><span class="sxs-lookup"><span data-stu-id="9e257-213">Threat protection</span></span>

<span data-ttu-id="9e257-214">Windows 10 Business には次のような保護が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9e257-214">Windows 10 Business includes these protections:</span></span>

- <span data-ttu-id="9e257-215">オペレーティングシステムの起動プロセスの整合性の適用</span><span class="sxs-lookup"><span data-stu-id="9e257-215">Integrity enforcement of operating system boot up process</span></span>
- <span data-ttu-id="9e257-216">機密性の高いオペレーティングコンポーネントの整合性の適用</span><span class="sxs-lookup"><span data-stu-id="9e257-216">Integrity enforcement of sensitive operating components</span></span>
- <span data-ttu-id="9e257-217">高度な脆弱性およびゼロ日の悪用対策</span><span class="sxs-lookup"><span data-stu-id="9e257-217">Advanced vulnerability and zero-day exploit mitigations</span></span>
- <span data-ttu-id="9e257-218">Microsoft Edge、Internet Explorer、および Chrome の評価ベースのネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="9e257-218">Reputation-based network protection for Microsoft Edge, Internet Explorer, and Chrome</span></span>
- <span data-ttu-id="9e257-219">ホストベースのファイアウォール</span><span class="sxs-lookup"><span data-stu-id="9e257-219">Host-based firewall</span></span>
- <span data-ttu-id="9e257-220">ランサムウェア対策</span><span class="sxs-lookup"><span data-stu-id="9e257-220">Ransomware mitigations</span></span>
- <span data-ttu-id="9e257-221">Microsoft Edge のハードウェアベースの分離</span><span class="sxs-lookup"><span data-stu-id="9e257-221">Hardware-based isolation for Microsoft Edge</span></span>
- <span data-ttu-id="9e257-222">インテリジェントセキュリティグラフが提供するアプリケーションコントロール</span><span class="sxs-lookup"><span data-stu-id="9e257-222">Application control powered by the Intelligent Security Graph</span></span>
- <span data-ttu-id="9e257-223">デバイスコントロール (USB)</span><span class="sxs-lookup"><span data-stu-id="9e257-223">Device control (USB)</span></span>
- <span data-ttu-id="9e257-224">Web ベースの脅威に対するネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="9e257-224">Network protection for web-based threats</span></span>
- <span data-ttu-id="9e257-225">ホスト侵入防止ルール</span><span class="sxs-lookup"><span data-stu-id="9e257-225">Host intrusion prevention rules</span></span>

<span data-ttu-id="9e257-226">Windows 10 Enterprise E3 には、Microsoft Edge のハードウェアベースの分離のエンタープライズ管理も含まれています。</span><span class="sxs-lookup"><span data-stu-id="9e257-226">Windows 10 Enterprise E3 also includes enterprise management of hardware-based isolation for Microsoft Edge.</span></span>

>[!Note]
><span data-ttu-id="9e257-227">Microsoft 365 E3 に移行されるユーザーは、引き続き脅威を防止するために Microsoft Defender for Office 365 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="9e257-227">Users migrated to Microsoft 365 E3 will each require a Microsoft Defender for Office 365 license for continued threat protection.</span></span> <span data-ttu-id="9e257-228">Office 365 ライセンスを使用する 365 Defender のすべてのユーザーにライセンスが付与されるように、Office の追加の Defender を購入してください。</span><span class="sxs-lookup"><span data-stu-id="9e257-228">Be sure to purchase additional Defender for Office 365 licenses so that all of the users in scope of your Defender for Office 365 polices are licensed.</span></span> 
>

### <a name="device-management-with-intune"></a><span data-ttu-id="9e257-229">Intune を使用したデバイス管理</span><span class="sxs-lookup"><span data-stu-id="9e257-229">Device management with Intune</span></span>

<span data-ttu-id="9e257-230">移行前に現在の Intune 構成を変更する必要はありません。これには、登録されたデバイスとデバイスおよびアプリの設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9e257-230">You don't need to make any changes to your current Intune configuration before migrating, which includes enrolled devices and device and app settings.</span></span>

### <a name="windows-10"></a><span data-ttu-id="9e257-231">Windows 10</span><span class="sxs-lookup"><span data-stu-id="9e257-231">Windows 10</span></span>

<span data-ttu-id="9e257-232">Microsoft 365 Business Premium には Windows 10 Business が含まれており、Windows 自動操縦を使用してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="9e257-232">Microsoft 365 Business Premium includes Windows 10 Business, which you can install with Windows AutoPilot.</span></span> <span data-ttu-id="9e257-233">Microsoft 365 E3 に移行する場合は、各ユーザーライセンスに Windows 10 Enterprise E3 が含まれており、Windows 自動操縦を使用してインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9e257-233">When you migrate to Microsoft 365 E3, each user license includes Windows 10 Enterprise E3, which you can also install with Windows Autopilot.</span></span>

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a><span data-ttu-id="9e257-234">Microsoft 365 Apps for business</span><span class="sxs-lookup"><span data-stu-id="9e257-234">Microsoft 365 Apps for business</span></span>

<span data-ttu-id="9e257-235">お客様のデバイスにインストールされている Microsoft 365 Apps for business クライアントは、エンタープライズ向けの Microsoft 365 アプリの機能を自動的に使用し始めます。</span><span class="sxs-lookup"><span data-stu-id="9e257-235">Your Microsoft 365 Apps for business client installed on your devices will automatically begin to use the features of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="9e257-236">移行後、次のものを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9e257-236">After migration, you can now use:</span></span>

 - <span data-ttu-id="9e257-237">グループポリシーを使用したボリュームライセンス認証</span><span class="sxs-lookup"><span data-stu-id="9e257-237">Volume activation through Group Policy</span></span>
 - <span data-ttu-id="9e257-238">アプリテレメトリ</span><span class="sxs-lookup"><span data-stu-id="9e257-238">App telemetry</span></span>
 - <span data-ttu-id="9e257-239">コントロールを更新する</span><span class="sxs-lookup"><span data-stu-id="9e257-239">Update controls</span></span>
 - <span data-ttu-id="9e257-240">スプレッドシートの比較と照会</span><span class="sxs-lookup"><span data-stu-id="9e257-240">Spreadsheet compare and inquire</span></span>
 - <span data-ttu-id="9e257-241">ビジネス インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="9e257-241">Business intelligence</span></span>

