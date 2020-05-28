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
ms.openlocfilehash: 6a795d96ccae7e054e7e52d4fd60a4e73b3c71dd
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401992"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a><span data-ttu-id="db59f-103">Microsoft 365 Business Premium から Microsoft 365 E3 への移行</span><span class="sxs-lookup"><span data-stu-id="db59f-103">Migrate from Microsoft 365 Business Premium to Microsoft 365 E3</span></span>

<span data-ttu-id="db59f-104">Microsoft 365 Business Premium は、お客様の中小企業に必要なすべての機能を備えており、クラスを持つクラウドベースの生産性向上アプリをシンプルなデバイス管理およびセキュリティと組み合わせることにより、従業員が最高の作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="db59f-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security that enable your employees to do their best work.</span></span> <span data-ttu-id="db59f-105">ただし、場合によっては、Microsoft 365 Business Premium サブスクリプションを Microsoft 365 E3 に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db59f-105">In some cases, however, you may need to migrate your Microsoft 365 Business Premium subscription to Microsoft 365 E3.</span></span> 

<span data-ttu-id="db59f-106">たとえば、ビジネスの成長が増え、300個を超えるライセンスが必要になりました (ご利用おめでとうございます)。</span><span class="sxs-lookup"><span data-stu-id="db59f-106">For example, your business has grown and needs more than 300 licenses (congratulations, by the way).</span></span>

<span data-ttu-id="db59f-107">または、ビジネスには、Microsoft 365 Apps for enterprise、Windows 10 Enterprise E3、エンタープライズクライアントアクセスライセンス (Cal) などのエンタープライズ機能が必要です。</span><span class="sxs-lookup"><span data-stu-id="db59f-107">Or, your business needs enterprise features, such as Microsoft 365 Apps for enterprise, Windows 10 Enterprise E3, or Enterprise Client Access Licenses (CALs).</span></span>

<span data-ttu-id="db59f-108">アップグレードは簡単です。[管理センターから](../commerce/subscriptions/upgrade-to-different-plan.md)アップグレードを開始できます。</span><span class="sxs-lookup"><span data-stu-id="db59f-108">Upgrading is easy: you can start the upgrade [from the Admin center](../commerce/subscriptions/upgrade-to-different-plan.md).</span></span> <span data-ttu-id="db59f-109">現在のサブスクリプションのすべてのデータと構成が保持されます。</span><span class="sxs-lookup"><span data-stu-id="db59f-109">All your data and configuration in your current subscription is maintained.</span></span> <span data-ttu-id="db59f-110">移行を準備するために実行する必要はありません。その後は、新しい機能を利用する以外に何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="db59f-110">There's nothing for you to do to prepare for the migration and nothing to do afterward, except take advantage of the new features.</span></span>

>[!Note]
><span data-ttu-id="db59f-111">また、Microsoft 365 Business Premium サブスクリプションを最大300の席で使用することもできます。また、Microsoft 365 E3 サブスクリプションは、300さらに多くのユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="db59f-111">You can also use a Microsoft 365 Business Premium subscription for up to 300 seats and get a Microsoft 365 E3 subscription for more than 300 seats.</span></span> <span data-ttu-id="db59f-112">ただし、Office 365 ATP は Microsoft 365 E3 には含まれていません。</span><span class="sxs-lookup"><span data-stu-id="db59f-112">However, Office 365 ATP is not included with Microsoft 365 E3.</span></span> <span data-ttu-id="db59f-113">引き続き脅威を保護するには、office 365 ATP のライセンスを追加して、Office 365 ATP ポリシーの範囲内のすべてのユーザーがライセンスを持つようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="db59f-113">For continued threat protection, you should add additional Office 365 ATP licenses so that all of the users in scope of your Office 365 ATP polices are licensed.</span></span>
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a><span data-ttu-id="db59f-114">Microsoft 365 Business Premium と Microsoft 365 Enterprise の相違点</span><span class="sxs-lookup"><span data-stu-id="db59f-114">Differences between Microsoft 365 Business Premium and Microsoft 365 Enterprise</span></span>

<span data-ttu-id="db59f-115">次の表に、Microsoft 365 Business Premium と Microsoft 365 E3 の相違点を示します。</span><span class="sxs-lookup"><span data-stu-id="db59f-115">This table shows the differences between Microsoft 365 Business Premium and Microsoft 365 E3.</span></span>

| <span data-ttu-id="db59f-116">機能</span><span class="sxs-lookup"><span data-stu-id="db59f-116">Feature</span></span>    | <span data-ttu-id="db59f-117">Microsoft 365 Business Premium でのサポート</span><span class="sxs-lookup"><span data-stu-id="db59f-117">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="db59f-118">Microsoft 365 E3 のサポート</span><span class="sxs-lookup"><span data-stu-id="db59f-118">Support in Microsoft 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="db59f-119">**社内**</span><span class="sxs-lookup"><span data-stu-id="db59f-119">**On-premises**</span></span>        | | | 
| <span data-ttu-id="db59f-120">Windows 10</span><span class="sxs-lookup"><span data-stu-id="db59f-120">Windows 10</span></span>    | <span data-ttu-id="db59f-121">Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="db59f-121">Windows 10 Business</span></span>  |     <span data-ttu-id="db59f-122">Windows 10 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="db59f-122">Windows 10 Enterprise E3</span></span>| 
| <span data-ttu-id="db59f-123">Office アプリ \*</span><span class="sxs-lookup"><span data-stu-id="db59f-123">Office apps\*</span></span>    | [<span data-ttu-id="db59f-124">Microsoft 365 Apps for business</span><span class="sxs-lookup"><span data-stu-id="db59f-124">Microsoft 365 Apps for business</span></span>](#office-365-business)    | <span data-ttu-id="db59f-125">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="db59f-125">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="db59f-126">**クラウド生産性アプリ**</span><span class="sxs-lookup"><span data-stu-id="db59f-126">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="db59f-127">Exchange Online および Outlook</span><span class="sxs-lookup"><span data-stu-id="db59f-127">Exchange Online and Outlook</span></span>    | <span data-ttu-id="db59f-128">メールボックスごとに 50 GB の格納域の制限と無制限の Exchange Online アーカイブ</span><span class="sxs-lookup"><span data-stu-id="db59f-128">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>    | <span data-ttu-id="db59f-129">メールボックスごとに 100 GB の格納域の制限と無制限の Exchange Online アーカイブ</span><span class="sxs-lookup"><span data-stu-id="db59f-129">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> | 
| <span data-ttu-id="db59f-130">Teams</span><span class="sxs-lookup"><span data-stu-id="db59f-130">Teams</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="db59f-133">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="db59f-133">OneDrive for Business</span></span>    | <span data-ttu-id="db59f-134">ユーザーごとに 1 TB のストレージ制限</span><span class="sxs-lookup"><span data-stu-id="db59f-134">1 TB storage limit per user</span></span>    | <span data-ttu-id="db59f-135">無制限</span><span class="sxs-lookup"><span data-stu-id="db59f-135">Unlimited</span></span> | 
| <span data-ttu-id="db59f-136">Yammer、SharePoint Online、Planner、Stream</span><span class="sxs-lookup"><span data-stu-id="db59f-136">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="db59f-139">Outlook カスタマーマネージャー、ミル Eiq</span><span class="sxs-lookup"><span data-stu-id="db59f-139">Outlook Customer Manager, MileIQ</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | | 
| <span data-ttu-id="db59f-141">**脅威保護**</span><span class="sxs-lookup"><span data-stu-id="db59f-141">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="db59f-142">攻撃対象領域の削減機能</span><span class="sxs-lookup"><span data-stu-id="db59f-142">Attack surface reduction capabilities</span></span>    | [<span data-ttu-id="db59f-143">このリストを表示する</span><span class="sxs-lookup"><span data-stu-id="db59f-143">See this list</span></span>](#threat-protection) | <span data-ttu-id="db59f-144">Microsoft Edge のハードウェアベースの分離のエンタープライズ管理</span><span class="sxs-lookup"><span data-stu-id="db59f-144">Enterprise management of hardware-based isolation for Microsoft Edge</span></span> | 
| <span data-ttu-id="db59f-145">Office 365 Advanced Threat Protection (ATP) プラン1</span><span class="sxs-lookup"><span data-stu-id="db59f-145">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | <span data-ttu-id="db59f-147">含まれていませんが、に追加できます。</span><span class="sxs-lookup"><span data-stu-id="db59f-147">Not included, but can be added on</span></span> | 
| <span data-ttu-id="db59f-148">**ID 管理**</span><span class="sxs-lookup"><span data-stu-id="db59f-148">**Identity management**</span></span>        | | | 
| <span data-ttu-id="db59f-149">ハイブリッド Azure Active Directory (Azure AD) アカウントのセルフサービスによるパスワードのリセット、Azure 多要素認証 (MFA)、条件付きアクセス、オンプレミス id のパスワードの書き戻し</span><span class="sxs-lookup"><span data-stu-id="db59f-149">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="db59f-152">Cloud App Discovery、Azure AD Connect Health</span><span class="sxs-lookup"><span data-stu-id="db59f-152">Cloud App Discovery, Azure AD Connect Health</span></span>    |     | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="db59f-154">Azure AD Office 365 apps シングルサインオン (SSO): ユーザーごとに10個のアプリ (Salesforce などのギャラリー SaaS アプリ) \*</span><span class="sxs-lookup"><span data-stu-id="db59f-154">Azure AD Office 365 apps Single Sign-On (SSO): 10 apps per user (Gallery SaaS apps such as Salesforce)\*</span></span> | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="db59f-157">Azure AD Premium 1 SSO: 制限なし (Azure AD アプリケーションプロキシと、セルフサービスアプリ統合テンプレートを使用したギャラリー以外のアプリを使用したオンプレミスアプリ)</span><span class="sxs-lookup"><span data-stu-id="db59f-157">Azure AD Premium 1 SSO: no limit (On-premises apps through Azure AD Application Proxy and non-gallery apps using Self-Service App Integration templates)</span></span>    |     | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="db59f-159">**デバイスとアプリの管理**</span><span class="sxs-lookup"><span data-stu-id="db59f-159">**Device and app management**</span></span>        | | | 
| <span data-ttu-id="db59f-160">Microsoft Intune、Windows 自動操縦</span><span class="sxs-lookup"><span data-stu-id="db59f-160">Microsoft Intune, Windows Autopilot</span></span>|     ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
|<span data-ttu-id="db59f-163">仮想デスクトップアクセス (VDA)</span><span class="sxs-lookup"><span data-stu-id="db59f-163">Virtual Desktop Access (VDA)</span></span>    |  |     ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
|<span data-ttu-id="db59f-165">Windows 仮想デスクトップ (WVD)</span><span class="sxs-lookup"><span data-stu-id="db59f-165">Windows Virtual Desktop (WVD)</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png) |     ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
|<span data-ttu-id="db59f-168">共有コンピューターのライセンス認証 (SCA)</span><span class="sxs-lookup"><span data-stu-id="db59f-168">Shared Computer Activation (SCA)</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png) |     ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="db59f-171">Microsoft デスクトップ最適化パッケージ</span><span class="sxs-lookup"><span data-stu-id="db59f-171">Microsoft Desktop Optimization Package</span></span>    | |     ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="db59f-173">**情報保護**</span><span class="sxs-lookup"><span data-stu-id="db59f-173">**Information protection**</span></span>        | | | 
| <span data-ttu-id="db59f-174">Office 365 データ損失防止、Azure Information Protection プラン1</span><span class="sxs-lookup"><span data-stu-id="db59f-174">Office 365 Data Loss Prevention, Azure Information Protection Plan 1</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="db59f-177">エンドポイント DLP のウィンドウ情報の保護</span><span class="sxs-lookup"><span data-stu-id="db59f-177">Window Information Protection for endpoint DLP</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="db59f-180">**クライアントアクセスライセンス (CAL 権限)**</span><span class="sxs-lookup"><span data-stu-id="db59f-180">**Client Access License (CAL rights)**</span></span>    | | |     
| <span data-ttu-id="db59f-181">エンタープライズ CAL スイート (Exchange、SharePoint、Skype、Windows、Microsoft エンドポイント構成マネージャー、Windows Rights Management)</span><span class="sxs-lookup"><span data-stu-id="db59f-181">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)</span></span>| |         ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="db59f-183">**コンプライアンス**</span><span class="sxs-lookup"><span data-stu-id="db59f-183">**Compliance**</span></span>        | | | 
| <span data-ttu-id="db59f-184">無制限のメールのアーカイブ</span><span class="sxs-lookup"><span data-stu-id="db59f-184">Unlimited email archiving</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="db59f-187">コンプライアンススコア/コンプライアンスマネージャー</span><span class="sxs-lookup"><span data-stu-id="db59f-187">Compliance Score/Compliance Manager</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="db59f-190">電子情報開示</span><span class="sxs-lookup"><span data-stu-id="db59f-190">eDiscovery</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="db59f-193">インプレース保持と訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="db59f-193">In-place hold and litigation hold</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
| <span data-ttu-id="db59f-196">メッセージング レコード管理 (MRM) 保持タグとアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="db59f-196">Messaging Records Management (MRM) retention tags and retention policies</span></span>    | ![Microsoft 365 Business Premium に含まれている](../media/check-mark.png)    | ![Microsoft 365 E3 に含まれています](../media/check-mark.png) | 
||||

<span data-ttu-id="db59f-199">\*SaaS アプリへのアクセスが割り当てられているユーザーは、最大10個のアプリへの SSO アクセスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="db59f-199">\* Users who have been assigned access to SaaS apps can get SSO access to up to 10 apps.</span></span> <span data-ttu-id="db59f-200">管理者は SSO を構成し、さまざまな SaaS アプリへのユーザーアクセスを変更できますが、SSO アクセスは、一度に1ユーザーあたり10個のアプリに対してのみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="db59f-200">Admins can configure SSO and change user access to different SaaS apps, but SSO access is only allowed for 10 apps per user at a time.</span></span> <span data-ttu-id="db59f-201">すべての Office 365 アプリは、1つのアプリとして数えられます。</span><span class="sxs-lookup"><span data-stu-id="db59f-201">All Office 365 apps are counted as a single app.</span></span>

## <a name="migration"></a><span data-ttu-id="db59f-202">移行</span><span class="sxs-lookup"><span data-stu-id="db59f-202">Migration</span></span>

<span data-ttu-id="db59f-203">移行するには、パートナーと協力して、Microsoft 365 Business Premium サブスクリプションとライセンスを、そのライセンスを使用して適切な Microsoft 365 E3 サブスクリプションに移行します。</span><span class="sxs-lookup"><span data-stu-id="db59f-203">To migrate, work with your partner to move your Microsoft 365 Business Premium subscription and licenses to a suitable Microsoft 365 E3 subscription with its licenses.</span></span>

<span data-ttu-id="db59f-204">次のセクションでは、移行後に行う必要のある変更点と、その変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="db59f-204">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="microsoft-365-subscription-configuration-and-data"></a><span data-ttu-id="db59f-205">Microsoft 365 サブスクリプションの構成とデータ</span><span class="sxs-lookup"><span data-stu-id="db59f-205">Microsoft 365 subscription configuration and data</span></span>

<span data-ttu-id="db59f-206">移行する前に、現在のサブスクリプションまたはデータを変更する必要はありません。次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="db59f-206">You don't need to make any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="db59f-207">サブスクリプションの構成 (DNS ドメイン名など)。</span><span class="sxs-lookup"><span data-stu-id="db59f-207">Subscription configuration, such as DNS domain names.</span></span>
- <span data-ttu-id="db59f-208">ユーザーおよびグループのアカウントと、複数要素の認証や条件付きアクセスポリシーなどの認証設定。</span><span class="sxs-lookup"><span data-stu-id="db59f-208">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="db59f-209">プロダクティビティサービスの構成とそのデータ (Teams、Exchange Online メールボックス、SharePoint Online サイト、OneDrive for Business フォルダー、OneNote ノートブックなど)。</span><span class="sxs-lookup"><span data-stu-id="db59f-209">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

<span data-ttu-id="db59f-210">ユーザーは、Exchange Online メールボックスおよび OneDrive for Business フォルダーで無制限のストレージを利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="db59f-210">Your users can now enjoy unlimited storage in the Exchange Online mailboxes and OneDrive for Business folders.</span></span>

<span data-ttu-id="db59f-211">最大10個のアプリに対して、クラウドアプリの検出、Azure AD Connect の正常性、および SSO の使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="db59f-211">You can begin using Cloud App Discovery, Azure AD Connect Health, and SSO for more than 10 apps.</span></span>

>[!Note]
><span data-ttu-id="db59f-212">Microsoft 365 E3 に移行されたユーザーは、Outlook カスタマーマネージャーおよびミル Eiq を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="db59f-212">Users migrated to Microsoft 365 E3 can no longer use Outlook Customer Manager and MileIQ.</span></span>
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a><span data-ttu-id="db59f-213">脅威保護</span><span class="sxs-lookup"><span data-stu-id="db59f-213">Threat protection</span></span>

<span data-ttu-id="db59f-214">Windows 10 Business には次のような保護が含まれています。</span><span class="sxs-lookup"><span data-stu-id="db59f-214">Windows 10 Business includes these protections:</span></span>

- <span data-ttu-id="db59f-215">オペレーティングシステムの起動プロセスの整合性の適用</span><span class="sxs-lookup"><span data-stu-id="db59f-215">Integrity enforcement of operating system boot up process</span></span>
- <span data-ttu-id="db59f-216">機密性の高いオペレーティングコンポーネントの整合性の適用</span><span class="sxs-lookup"><span data-stu-id="db59f-216">Integrity enforcement of sensitive operating components</span></span>
- <span data-ttu-id="db59f-217">高度な脆弱性およびゼロ日の悪用対策</span><span class="sxs-lookup"><span data-stu-id="db59f-217">Advanced vulnerability and zero-day exploit mitigations</span></span>
- <span data-ttu-id="db59f-218">Microsoft Edge、Internet Explorer、および Chrome の評価ベースのネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="db59f-218">Reputation-based network protection for Microsoft Edge, Internet Explorer, and Chrome</span></span>
- <span data-ttu-id="db59f-219">ホストベースのファイアウォール</span><span class="sxs-lookup"><span data-stu-id="db59f-219">Host-based firewall</span></span>
- <span data-ttu-id="db59f-220">ランサムウェア対策</span><span class="sxs-lookup"><span data-stu-id="db59f-220">Ransomware mitigations</span></span>
- <span data-ttu-id="db59f-221">Microsoft Edge のハードウェアベースの分離</span><span class="sxs-lookup"><span data-stu-id="db59f-221">Hardware-based isolation for Microsoft Edge</span></span>
- <span data-ttu-id="db59f-222">インテリジェントセキュリティグラフが提供するアプリケーションコントロール</span><span class="sxs-lookup"><span data-stu-id="db59f-222">Application control powered by the Intelligent Security Graph</span></span>
- <span data-ttu-id="db59f-223">デバイスコントロール (USB)</span><span class="sxs-lookup"><span data-stu-id="db59f-223">Device control (USB)</span></span>
- <span data-ttu-id="db59f-224">Web ベースの脅威に対するネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="db59f-224">Network protection for web-based threats</span></span>
- <span data-ttu-id="db59f-225">ホスト侵入防止ルール</span><span class="sxs-lookup"><span data-stu-id="db59f-225">Host intrusion prevention rules</span></span>

<span data-ttu-id="db59f-226">Windows 10 Enterprise E3 には、Microsoft Edge のハードウェアベースの分離のエンタープライズ管理も含まれています。</span><span class="sxs-lookup"><span data-stu-id="db59f-226">Windows 10 Enterprise E3 also includes enterprise management of hardware-based isolation for Microsoft Edge.</span></span>

>[!Note]
><span data-ttu-id="db59f-227">Microsoft 365 E3 に移行されるユーザーには、継続的な脅威保護のために Office 365 ATP ライセンスが必要になります。</span><span class="sxs-lookup"><span data-stu-id="db59f-227">Users migrated to Microsoft 365 E3 will each require an Office 365 ATP license for continued threat protection.</span></span> <span data-ttu-id="db59f-228">Office 365 ATP ポリシーの範囲内のすべてのユーザーがライセンスを受けられるように、追加の Office 365 ATP ライセンスを購入してください。</span><span class="sxs-lookup"><span data-stu-id="db59f-228">Be sure to purchase additional Office 365 ATP licenses so that all of the users in scope of your Office 365 ATP polices are licensed.</span></span> 
>

### <a name="device-management-with-intune"></a><span data-ttu-id="db59f-229">Intune を使用したデバイス管理</span><span class="sxs-lookup"><span data-stu-id="db59f-229">Device management with Intune</span></span>

<span data-ttu-id="db59f-230">移行前に現在の Intune 構成を変更する必要はありません。これには、登録されたデバイスとデバイスおよびアプリの設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="db59f-230">You don't need to make any changes to your current Intune configuration before migrating, which includes enrolled devices and device and app settings.</span></span>

### <a name="windows-10"></a><span data-ttu-id="db59f-231">Windows 10</span><span class="sxs-lookup"><span data-stu-id="db59f-231">Windows 10</span></span>

<span data-ttu-id="db59f-232">Microsoft 365 Business Premium には Windows 10 Business が含まれており、Windows 自動操縦を使用してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="db59f-232">Microsoft 365 Business Premium includes Windows 10 Business, which you can install with Windows AutoPilot.</span></span> <span data-ttu-id="db59f-233">Microsoft 365 E3 に移行する場合は、各ユーザーライセンスに Windows 10 Enterprise E3 が含まれており、Windows 自動操縦を使用してインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="db59f-233">When you migrate to Microsoft 365 E3, each user license includes Windows 10 Enterprise E3, which you can also install with Windows Autopilot.</span></span>

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a><span data-ttu-id="db59f-234">Microsoft 365 Apps for business</span><span class="sxs-lookup"><span data-stu-id="db59f-234">Microsoft 365 Apps for business</span></span>

<span data-ttu-id="db59f-235">お客様のデバイスにインストールされている Microsoft 365 Apps for business クライアントは、エンタープライズ向けの Microsoft 365 アプリの機能を自動的に使用し始めます。</span><span class="sxs-lookup"><span data-stu-id="db59f-235">Your Microsoft 365 Apps for business client installed on your devices will automatically begin to use the features of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="db59f-236">移行後、次のものを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="db59f-236">After migration, you can now use:</span></span>

 - <span data-ttu-id="db59f-237">グループポリシーを使用したボリュームライセンス認証</span><span class="sxs-lookup"><span data-stu-id="db59f-237">Volume activation through Group Policy</span></span>
 - <span data-ttu-id="db59f-238">アプリテレメトリ</span><span class="sxs-lookup"><span data-stu-id="db59f-238">App telemetry</span></span>
 - <span data-ttu-id="db59f-239">コントロールを更新する</span><span class="sxs-lookup"><span data-stu-id="db59f-239">Update controls</span></span>
 - <span data-ttu-id="db59f-240">スプレッドシートの比較と照会</span><span class="sxs-lookup"><span data-stu-id="db59f-240">Spreadsheet compare and inquire</span></span>
 - <span data-ttu-id="db59f-241">ビジネス インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="db59f-241">Business intelligence</span></span>

