---
title: Microsoft 365 Business から Microsoft 365 Enterprise への移行
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
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Microsoft 365 Business から Microsoft 365 Enterprise E3 にビジネスを移行する方法について説明します。
ms.openlocfilehash: efdf4030a2a638a3fd56d1c415fcc6e6ac261c1a
ms.sourcegitcommit: 333ecfb8bfeb34f9f08d82d295b40d37de6ba8b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772722"
---
# <a name="migrate-from-microsoft-365-business-to-microsoft-365-enterprise-e3"></a><span data-ttu-id="d81fa-103">Microsoft 365 Business から Microsoft 365 Enterprise E3 への移行</span><span class="sxs-lookup"><span data-stu-id="d81fa-103">Migrate from Microsoft 365 Business to Microsoft 365 Enterprise E3</span></span>

<span data-ttu-id="d81fa-104">Microsoft 365 Business は、お客様の中小企業に必要なすべての機能を備えており、クラス最高のクラウドベースの生産性アプリとシンプルなデバイスの管理とセキュリティを組み合わせることにより、従業員が最高の作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d81fa-104">Microsoft 365 Business has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security that enable your employees to do their best work.</span></span> <span data-ttu-id="d81fa-105">ただし、場合によっては、Microsoft 365 Business サブスクリプションを Microsoft 365 Enterprise に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d81fa-105">In some cases, however, you may need to migrate your Microsoft 365 Business subscription to Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="d81fa-106">たとえば、ビジネスの成長が増え、300個を超えるライセンスが必要になりました (ご利用おめでとうございます)。</span><span class="sxs-lookup"><span data-stu-id="d81fa-106">For example, your business has grown and needs more than 300 licenses (congratulations, by the way).</span></span>

<span data-ttu-id="d81fa-107">また、ビジネスには、Office 365 ProPlus、Windows 10 Enterprise E3、エンタープライズクライアントアクセスライセンス (Cal) などのエンタープライズ機能が必要です。</span><span class="sxs-lookup"><span data-stu-id="d81fa-107">Or, your business needs enterprise features, such as Office 365 ProPlus, Windows 10 Enterprise E3, or Enterprise Client Access Licenses (CALs).</span></span>

<span data-ttu-id="d81fa-108">移行は簡単です。ライセンスの切り替えだけです。</span><span class="sxs-lookup"><span data-stu-id="d81fa-108">Migrating is easy: Just switch licenses.</span></span> <span data-ttu-id="d81fa-109">現在のサブスクリプションのすべてのデータと構成が保持されます。</span><span class="sxs-lookup"><span data-stu-id="d81fa-109">All your data and configuration in your current subscription is maintained.</span></span> <span data-ttu-id="d81fa-110">移行を準備するために実行する必要はありません。その後は、新しい機能を利用する以外に何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d81fa-110">There is nothing for you to do to prepare for the migration and nothing to do afterward, except take advantage of the new features.</span></span> 

>[!Note]
><span data-ttu-id="d81fa-111">また、Microsoft 365 Business のサブスクリプションを最大300の席で使用することもできます。また、Microsoft 365 Enterprise E3 サブスクリプションを使用して、より300多くのユーザーを対象にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d81fa-111">You can also use a Microsoft 365 Business subscription for up to 300 seats and get a Microsoft 365 Enterprise E3 subscription for more than 300 seats.</span></span> <span data-ttu-id="d81fa-112">ただし、Office 365 ATP は Microsoft 365 Enterprise E3 には含まれていません。</span><span class="sxs-lookup"><span data-stu-id="d81fa-112">However, Office 365 ATP is not included with Microsoft 365 Enterprise E3.</span></span> <span data-ttu-id="d81fa-113">Microsoft 365 Enterprise E3 サブスクリプションのユーザーには、追加の Office 365 ATP ライセンスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d81fa-113">You should add additional Office 365 ATP licenses for the users in your Microsoft 365 Enterprise E3 subscription.</span></span>
>

## <a name="differences-between-microsoft-365-business-and-microsoft-365-enterprise"></a><span data-ttu-id="d81fa-114">Microsoft 365 Business と Microsoft 365 Enterprise の相違点</span><span class="sxs-lookup"><span data-stu-id="d81fa-114">Differences between Microsoft 365 Business and Microsoft 365 Enterprise</span></span>

<span data-ttu-id="d81fa-115">次の表に、Microsoft 365 Business と Microsoft 365 Enterprise E3 の相違点を示します。</span><span class="sxs-lookup"><span data-stu-id="d81fa-115">This table shows the differences between Microsoft 365 Business and Microsoft 365 Enterprise E3.</span></span>

| <span data-ttu-id="d81fa-116">機能</span><span class="sxs-lookup"><span data-stu-id="d81fa-116">Feature</span></span>   | <span data-ttu-id="d81fa-117">Microsoft 365 Business でのサポート</span><span class="sxs-lookup"><span data-stu-id="d81fa-117">Support in Microsoft 365 Business</span></span> | <span data-ttu-id="d81fa-118">Microsoft 365 Enterprise E3 のサポート</span><span class="sxs-lookup"><span data-stu-id="d81fa-118">Support in Microsoft 365 Enterprise E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="d81fa-119">**社内**</span><span class="sxs-lookup"><span data-stu-id="d81fa-119">**On-premises**</span></span>       | | | 
| <span data-ttu-id="d81fa-120">Windows 10</span><span class="sxs-lookup"><span data-stu-id="d81fa-120">Windows 10</span></span>    | <span data-ttu-id="d81fa-121">Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="d81fa-121">Windows 10 Business</span></span>  |    <span data-ttu-id="d81fa-122">Windows 10 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="d81fa-122">Windows 10 Enterprise E3</span></span>| 
| <span data-ttu-id="d81fa-123">Office アプリ \*</span><span class="sxs-lookup"><span data-stu-id="d81fa-123">Office apps\*</span></span>  | [<span data-ttu-id="d81fa-124">Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="d81fa-124">Office 365 Business</span></span>](#office-365-business)   | <span data-ttu-id="d81fa-125">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="d81fa-125">Office 365 ProPlus</span></span> | 
| <span data-ttu-id="d81fa-126">**クラウド生産性アプリ**</span><span class="sxs-lookup"><span data-stu-id="d81fa-126">**Cloud productivity apps**</span></span>       | | | 
| <span data-ttu-id="d81fa-127">Exchange Online および Outlook</span><span class="sxs-lookup"><span data-stu-id="d81fa-127">Exchange Online and Outlook</span></span>   | <span data-ttu-id="d81fa-128">メールボックスごとに 50 GB の格納域の制限と無制限の Exchange Online アーカイブ</span><span class="sxs-lookup"><span data-stu-id="d81fa-128">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>   | <span data-ttu-id="d81fa-129">メールボックスごとに 100 GB の格納域の制限と無制限の Exchange Online アーカイブ</span><span class="sxs-lookup"><span data-stu-id="d81fa-129">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> | 
| <span data-ttu-id="d81fa-130">Teams</span><span class="sxs-lookup"><span data-stu-id="d81fa-130">Teams</span></span> | ![Microsoft 365 Business に含まれている](./media/check-mark.png)   | ![Microsoft 365 Enterprise E3 に含まれています](./media/check-mark.png) | 
| <span data-ttu-id="d81fa-133">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="d81fa-133">OneDrive for Business</span></span> | <span data-ttu-id="d81fa-134">ユーザーごとに 1 TB のストレージ制限</span><span class="sxs-lookup"><span data-stu-id="d81fa-134">1 TB storage limit per user</span></span>   | <span data-ttu-id="d81fa-135">無制限</span><span class="sxs-lookup"><span data-stu-id="d81fa-135">Unlimited</span></span> | 
| <span data-ttu-id="d81fa-136">Yammer、SharePoint Online、Planner、Stream</span><span class="sxs-lookup"><span data-stu-id="d81fa-136">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Microsoft 365 Business に含まれている](./media/check-mark.png)   | ![Microsoft 365 Enterprise E3 に含まれています](./media/check-mark.png) | 
| <span data-ttu-id="d81fa-139">StaffHub</span><span class="sxs-lookup"><span data-stu-id="d81fa-139">StaffHub</span></span>  | ![Microsoft 365 Business に含まれている](./media/check-mark.png)   | ![Microsoft 365 Enterprise E3 に含まれています](./media/check-mark.png) | 
| <span data-ttu-id="d81fa-142">Outlook カスタマーマネージャー、ミル Eiq</span><span class="sxs-lookup"><span data-stu-id="d81fa-142">Outlook Customer Manager, MileIQ</span></span>  | ![Microsoft 365 Business に含まれている](./media/check-mark.png)   | | 
| <span data-ttu-id="d81fa-144">**脅威保護**</span><span class="sxs-lookup"><span data-stu-id="d81fa-144">**Threat Protection**</span></span>     | | | 
| <span data-ttu-id="d81fa-145">攻撃対象領域の削減機能</span><span class="sxs-lookup"><span data-stu-id="d81fa-145">Attack surface reduction capabilities</span></span> | [<span data-ttu-id="d81fa-146">このリストを表示する</span><span class="sxs-lookup"><span data-stu-id="d81fa-146">See this list</span></span>](#threat-protection) | <span data-ttu-id="d81fa-147">Microsoft Edge のハードウェアベースの分離のエンタープライズ管理</span><span class="sxs-lookup"><span data-stu-id="d81fa-147">Enterprise management of hardware-based isolation for Microsoft Edge</span></span> | 
| <span data-ttu-id="d81fa-148">Office 365 Advanced Threat Protection (ATP) プラン1</span><span class="sxs-lookup"><span data-stu-id="d81fa-148">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Microsoft 365 Business に含まれている](./media/check-mark.png)  | <span data-ttu-id="d81fa-150">含まれていませんが、に追加できます。</span><span class="sxs-lookup"><span data-stu-id="d81fa-150">Not included, but can be added on</span></span> | 
| <span data-ttu-id="d81fa-151">**ID 管理**</span><span class="sxs-lookup"><span data-stu-id="d81fa-151">**Identity management**</span></span>       | | | 
| <span data-ttu-id="d81fa-152">ハイブリッド Azure Active Directory (Azure AD) アカウントのセルフサービスによるパスワードのリセット、Azure 多要素認証 (MFA)、条件付きアクセス、オンプレミス id のパスワードの書き戻し</span><span class="sxs-lookup"><span data-stu-id="d81fa-152">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|    ![Microsoft 365 Business に含まれている](./media/check-mark.png) | ![Microsoft 365 Enterprise E3 に含まれています](./media/check-mark.png) | 
| <span data-ttu-id="d81fa-155">Cloud App Discovery、Azure AD Connect Health</span><span class="sxs-lookup"><span data-stu-id="d81fa-155">Cloud App Discovery, Azure AD Connect Health</span></span>  |   | ![Microsoft 365 Enterprise E3 に含まれています](./media/check-mark.png) | 
| <span data-ttu-id="d81fa-157">Azure AD Office 365 apps シングルサインオン (SSO): ユーザーごとに10個のアプリ (Salesforce などのギャラリー SaaS アプリ) \*</span><span class="sxs-lookup"><span data-stu-id="d81fa-157">Azure AD Office 365 apps Single Sign-On (SSO): 10 apps per user (Gallery SaaS apps such as Salesforce)\*</span></span> | ![Microsoft 365 Business に含まれている](./media/check-mark.png) | ![Microsoft 365 Enterprise E3 に含まれています](./media/check-mark.png) | 
| <span data-ttu-id="d81fa-160">Azure AD Premium 1 SSO: 制限なし (Azure AD アプリケーションプロキシと、セルフサービスアプリ統合テンプレートを使用したギャラリー以外のアプリを使用したオンプレミスアプリ)</span><span class="sxs-lookup"><span data-stu-id="d81fa-160">Azure AD Premium 1 SSO: no limit (On-premises apps through Azure AD Application Proxy and non-gallery apps using Self-Service App Integration templates)</span></span>  |   | ![Microsoft 365 Enterprise E3 に含まれています](./media/check-mark.png) | 
| <span data-ttu-id="d81fa-162">**デバイスとアプリの管理**</span><span class="sxs-lookup"><span data-stu-id="d81fa-162">**Device and app management**</span></span>     | | | 
| <span data-ttu-id="d81fa-163">Microsoft Intune、Windows 自動操縦</span><span class="sxs-lookup"><span data-stu-id="d81fa-163">Microsoft Intune, Windows Autopilot</span></span>|  ![Microsoft 365 Business に含まれている](./media/check-mark.png) | ![Microsoft 365 Enterprise E3 に含まれています](./media/check-mark.png) | 
|<span data-ttu-id="d81fa-166">仮想デスクトップアクセス (VDA)</span><span class="sxs-lookup"><span data-stu-id="d81fa-166">Virtual Desktop Access (VDA)</span></span>   |  |    ![Microsoft 365 Enterprise E3 に含まれています](./media/check-mark.png) | 
|<span data-ttu-id="d81fa-168">Windows 仮想デスクトップ (WVD)</span><span class="sxs-lookup"><span data-stu-id="d81fa-168">Windows Virtual Desktop (WVD)</span></span>  | ![Microsoft 365 Business に含まれている](./media/check-mark.png) |     ![Microsoft 365 Enterprise E3 に含まれています](./media/check-mark.png) | 
|<span data-ttu-id="d81fa-171">共有コンピューターのライセンス認証 (SCA)</span><span class="sxs-lookup"><span data-stu-id="d81fa-171">Shared Computer Activation (SCA)</span></span>   | ![Microsoft 365 Business に含まれている](./media/check-mark.png) |     ![Microsoft 365 Enterprise E3 に含まれています](./media/check-mark.png) | 
| <span data-ttu-id="d81fa-174">Microsoft デスクトップ最適化パッケージ</span><span class="sxs-lookup"><span data-stu-id="d81fa-174">Microsoft Desktop Optimization Package</span></span>    | |     ![Microsoft 365 Enterprise E3 に含まれています](./media/check-mark.png) | 
| <span data-ttu-id="d81fa-176">**情報保護**</span><span class="sxs-lookup"><span data-stu-id="d81fa-176">**Information protection**</span></span>        | | | 
| <span data-ttu-id="d81fa-177">Office 365 データ損失防止、Azure Information Protection プラン1</span><span class="sxs-lookup"><span data-stu-id="d81fa-177">Office 365 Data Loss Prevention, Azure Information Protection Plan 1</span></span>  | ![Microsoft 365 Business に含まれている](./media/check-mark.png)   | ![Microsoft 365 Enterprise E3 に含まれています](./media/check-mark.png) | 
| <span data-ttu-id="d81fa-180">エンドポイント DLP のウィンドウ情報の保護</span><span class="sxs-lookup"><span data-stu-id="d81fa-180">Window Information Protection for endpoint DLP</span></span>    | ![Microsoft 365 Business に含まれている](./media/check-mark.png)   | ![Microsoft 365 Enterprise E3 に含まれています](./media/check-mark.png) | 
| <span data-ttu-id="d81fa-183">**クライアントアクセスライセンス (CAL 権限)**</span><span class="sxs-lookup"><span data-stu-id="d81fa-183">**Client Access License (CAL rights)**</span></span>    | | |   
| <span data-ttu-id="d81fa-184">エンタープライズ CAL スイート (Exchange、SharePoint、Skype、Windows、System Center Configuration Manager、Windows Rights Management)</span><span class="sxs-lookup"><span data-stu-id="d81fa-184">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, System Center Configuration Manager, Windows Rights Management)</span></span>| |        ![Microsoft 365 Enterprise E3 に含まれています](./media/check-mark.png) | 
| <span data-ttu-id="d81fa-186">**コンプライアンス**</span><span class="sxs-lookup"><span data-stu-id="d81fa-186">**Compliance**</span></span>        | | | 
| <span data-ttu-id="d81fa-187">無制限のメールのアーカイブ</span><span class="sxs-lookup"><span data-stu-id="d81fa-187">Unlimited email archiving</span></span> | ![Microsoft 365 Business に含まれている](./media/check-mark.png)   | ![Microsoft 365 Enterprise E3 に含まれています](./media/check-mark.png) | 
| <span data-ttu-id="d81fa-190">コンプライアンス マネージャー</span><span class="sxs-lookup"><span data-stu-id="d81fa-190">Compliance Manager</span></span>    | ![Microsoft 365 Business に含まれている](./media/check-mark.png)   | ![Microsoft 365 Enterprise E3 に含まれています](./media/check-mark.png) | 
| <span data-ttu-id="d81fa-193">電子情報開示</span><span class="sxs-lookup"><span data-stu-id="d81fa-193">eDiscovery</span></span>    | ![Microsoft 365 Business に含まれている](./media/check-mark.png)   | ![Microsoft 365 Enterprise E3 に含まれています](./media/check-mark.png) | 
| <span data-ttu-id="d81fa-196">インプレース保持と訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="d81fa-196">In-place hold and litigation hold</span></span> | ![Microsoft 365 Business に含まれている](./media/check-mark.png)   | ![Microsoft 365 Enterprise E3 に含まれています](./media/check-mark.png) | 
| <span data-ttu-id="d81fa-199">メッセージング レコード管理 (MRM) 保持タグとアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="d81fa-199">Messaging Records Management (MRM) retention tags and retention policies</span></span>  | ![Microsoft 365 Business に含まれている](./media/check-mark.png)   | ![Microsoft 365 Enterprise E3 に含まれています](./media/check-mark.png) | 
||||

<span data-ttu-id="d81fa-202">\*SaaS アプリへのアクセスが割り当てられているユーザーは、最大10個のアプリへの SSO アクセスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="d81fa-202">\* Users who have been assigned access to SaaS apps can get SSO access to up to 10 apps.</span></span> <span data-ttu-id="d81fa-203">管理者は SSO を構成し、さまざまな SaaS アプリへのユーザーアクセスを変更できますが、SSO アクセスは、一度に1ユーザーあたり10個のアプリに対してのみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="d81fa-203">Admins can configure SSO and change user access to different SaaS apps, but SSO access is only allowed for 10 apps per user at a time.</span></span> <span data-ttu-id="d81fa-204">すべての Office 365 アプリは、1つのアプリとして数えられます。</span><span class="sxs-lookup"><span data-stu-id="d81fa-204">All Office 365 apps are counted as a single app.</span></span>

## <a name="migration"></a><span data-ttu-id="d81fa-205">移行</span><span class="sxs-lookup"><span data-stu-id="d81fa-205">Migration</span></span>

<span data-ttu-id="d81fa-206">移行するには、パートナーと協力して microsoft 365 Business のサブスクリプションとライセンスを Microsoft 365 Enterprise E3 サブスクリプションに適切なライセンスで移行してください。</span><span class="sxs-lookup"><span data-stu-id="d81fa-206">To migrate, work with your partner to move your Microsoft 365 Business subscription and licenses to suitable a Microsoft 365 Enterprise E3 subscription with its licenses.</span></span>

<span data-ttu-id="d81fa-207">次のセクションでは、移行後に行う必要のある変更点と、その変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="d81fa-207">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="microsoft-365-subscription-configuration-and-data"></a><span data-ttu-id="d81fa-208">Microsoft 365 サブスクリプションの構成とデータ</span><span class="sxs-lookup"><span data-stu-id="d81fa-208">Microsoft 365 subscription configuration and data</span></span>

<span data-ttu-id="d81fa-209">移行する前に、現在のサブスクリプションまたはデータを変更する必要はありません。これには、以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d81fa-209">You don’t need to do any changes to your current subscription or data prior to migrating, which includes:</span></span>

- <span data-ttu-id="d81fa-210">サブスクリプションの構成 (DNS ドメイン名など)。</span><span class="sxs-lookup"><span data-stu-id="d81fa-210">Subscription configuration, such as DNS domain names.</span></span>
- <span data-ttu-id="d81fa-211">ユーザーおよびグループのアカウントと、複数要素の認証や条件付きアクセスポリシーなどの認証設定。</span><span class="sxs-lookup"><span data-stu-id="d81fa-211">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="d81fa-212">プロダクティビティサービスの構成とそのデータ (Teams、Exchange Online メールボックス、SharePoint Online サイト、OneDrive for Business フォルダー、OneNote ノートブックなど)。</span><span class="sxs-lookup"><span data-stu-id="d81fa-212">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

<span data-ttu-id="d81fa-213">ユーザーは、Exchange Online メールボックスおよび OneDrive for Business フォルダーで無制限のストレージを利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d81fa-213">Your users can now enjoy unlimited storage in the Exchange Online mailboxes and OneDrive for Business folders.</span></span>

<span data-ttu-id="d81fa-214">最大10個のアプリに対して、クラウドアプリの検出、Azure AD Connect の正常性、および SSO の使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="d81fa-214">You can begin using Cloud App Discovery, Azure AD Connect Health, and SSO for more than 10 apps.</span></span>

>[!Note]
><span data-ttu-id="d81fa-215">Microsoft 365 Enterprise E3 に移行した後は、Outlook カスタマーマネージャーおよびミル Eiq ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d81fa-215">After migrating to Microsoft 365 Enterprise E3, you no longer Outlook Customer Manager and MileIQ.</span></span>
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a><span data-ttu-id="d81fa-216">脅威保護</span><span class="sxs-lookup"><span data-stu-id="d81fa-216">Threat protection</span></span>

<span data-ttu-id="d81fa-217">Windows 10 Business には次のような保護が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d81fa-217">Windows 10 Business includes these protections:</span></span>

- <span data-ttu-id="d81fa-218">オペレーティングシステムの起動プロセスの整合性の適用</span><span class="sxs-lookup"><span data-stu-id="d81fa-218">Integrity enforcement of operating system boot up process</span></span>
- <span data-ttu-id="d81fa-219">機密性の高いオペレーティングコンポーネントの整合性の適用</span><span class="sxs-lookup"><span data-stu-id="d81fa-219">Integrity enforcement of sensitive operating components</span></span>
- <span data-ttu-id="d81fa-220">高度な脆弱性およびゼロ日の悪用対策</span><span class="sxs-lookup"><span data-stu-id="d81fa-220">Advanced vulnerability and zero-day exploit mitigations</span></span>
- <span data-ttu-id="d81fa-221">Microsoft Edge、Internet Explorer、および Chrome の評価ベースのネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="d81fa-221">Reputation-based network protection for Microsoft Edge, Internet Explorer, and Chrome</span></span>
- <span data-ttu-id="d81fa-222">ホストベースのファイアウォール</span><span class="sxs-lookup"><span data-stu-id="d81fa-222">Host-based firewall</span></span>
- <span data-ttu-id="d81fa-223">ランサムウェア対策</span><span class="sxs-lookup"><span data-stu-id="d81fa-223">Ransomware mitigations</span></span>
- <span data-ttu-id="d81fa-224">Microsoft Edge のハードウェアベースの分離</span><span class="sxs-lookup"><span data-stu-id="d81fa-224">Hardware-based isolation for Microsoft Edge</span></span>
- <span data-ttu-id="d81fa-225">インテリジェントセキュリティグラフが提供するアプリケーションコントロール</span><span class="sxs-lookup"><span data-stu-id="d81fa-225">Application control powered by the Intelligent Security Graph</span></span>
- <span data-ttu-id="d81fa-226">デバイスコントロール (USB)</span><span class="sxs-lookup"><span data-stu-id="d81fa-226">Device control (USB)</span></span>
- <span data-ttu-id="d81fa-227">Web ベースの脅威に対するネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="d81fa-227">Network protection for web-based threats</span></span>
- <span data-ttu-id="d81fa-228">ホスト侵入防止ルール</span><span class="sxs-lookup"><span data-stu-id="d81fa-228">Host intrusion prevention rules</span></span>

<span data-ttu-id="d81fa-229">Windows 10 Enterprise E3 には、Microsoft Edge のハードウェアベースの分離のエンタープライズ管理も含まれています。</span><span class="sxs-lookup"><span data-stu-id="d81fa-229">Windows 10 Enterprise E3 also includes enterprise management of hardware-based isolation for Microsoft Edge.</span></span>

>[!Note]
><span data-ttu-id="d81fa-230">Microsoft 365 Enterprise E3 に移行した後は、Office 365 ATP を使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d81fa-230">After migrating to Microsoft 365 Enterprise E3, you no longer have Office 365 ATP.</span></span> <span data-ttu-id="d81fa-231">Microsoft 365 Enterprise E3 サブスクリプションの追加の Office 365 ATP ライセンスを購入して、ユーザーアカウントに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d81fa-231">You can purchase additional Office 365 ATP licenses for your Microsoft 365 Enterprise E3 subscription and assign them to your user accounts.</span></span>
>

### <a name="device-management-with-intune"></a><span data-ttu-id="d81fa-232">Intune を使用したデバイス管理</span><span class="sxs-lookup"><span data-stu-id="d81fa-232">Device management with Intune</span></span>

<span data-ttu-id="d81fa-233">移行前に現在の Intune 構成を変更する必要はありません。これには、登録済みのデバイスとデバイスおよびアプリの設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d81fa-233">You don’t need to do any changes to your current Intune configuration prior to migrating, which includes enrolled devices and device and app settings.</span></span>

### <a name="windows-10"></a><span data-ttu-id="d81fa-234">Windows 10</span><span class="sxs-lookup"><span data-stu-id="d81fa-234">Windows 10</span></span>

<span data-ttu-id="d81fa-235">Microsoft 365 Business には Windows 10 Business が含まれており、Windows 自動操縦を使用してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="d81fa-235">Microsoft 365 Business includes Windows 10 Business, which you can install with Windows Autopilot.</span></span> <span data-ttu-id="d81fa-236">Microsoft 365 Enterprise E3 に移行すると、各ユーザーライセンスに Windows 10 Enterprise E3 が含まれるようになります。これは、Windows 自動操縦を使用してインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d81fa-236">When you migrate to Microsoft 365 Enterprise E3, each user license includes Windows 10 Enterprise E3, which you can also install with Windows Autopilot.</span></span>

<a name="office-365-business"></a>
### <a name="office-365-business"></a><span data-ttu-id="d81fa-237">Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="d81fa-237">Office 365 Business</span></span>

<span data-ttu-id="d81fa-238">デバイスにインストールされた Office 365 ビジネスクライアントは、自動的に Office 365 ProPlus の機能を使用するようになります。</span><span class="sxs-lookup"><span data-stu-id="d81fa-238">Your Office 365 Business client installed on your devices will automatically begin to use the features of Office 365 ProPlus.</span></span> <span data-ttu-id="d81fa-239">移行後、次のものを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d81fa-239">After migration, you can now use:</span></span>

 - <span data-ttu-id="d81fa-240">グループポリシーを使用したボリュームライセンス認証</span><span class="sxs-lookup"><span data-stu-id="d81fa-240">Volume activation through Group Policy</span></span>
 - <span data-ttu-id="d81fa-241">アプリテレメトリ</span><span class="sxs-lookup"><span data-stu-id="d81fa-241">App telemetry</span></span>
 - <span data-ttu-id="d81fa-242">コントロールを更新する</span><span class="sxs-lookup"><span data-stu-id="d81fa-242">Update controls</span></span>
 - <span data-ttu-id="d81fa-243">スプレッドシートの比較と照会</span><span class="sxs-lookup"><span data-stu-id="d81fa-243">Spreadsheet compare and inquire</span></span>
 - <span data-ttu-id="d81fa-244">ビジネス インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="d81fa-244">Business intelligence</span></span>

