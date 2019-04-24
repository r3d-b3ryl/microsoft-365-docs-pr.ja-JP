---
title: Microsoft マネージドデスクトップのアプリの準備
description: ''
keywords: microsoft マネージドデスクトップ、microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: be28760fc3facdb21643943ace11deda378d437c
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289069"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a><span data-ttu-id="97009-103">Microsoft マネージドデスクトップのアプリの準備</span><span class="sxs-lookup"><span data-stu-id="97009-103">Preparing apps for Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
<span data-ttu-id="97009-104">microsoft および microsoft の管理されたデスクトップのお客様は、microsoft マネージドデスクトップで使用されるアプリケーションに関して、同じように重要な責任を持っています。</span><span class="sxs-lookup"><span data-stu-id="97009-104">Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.</span></span>

## <a name="microsoft-responsibilities"></a><span data-ttu-id="97009-105">Microsoft の責任</span><span class="sxs-lookup"><span data-stu-id="97009-105">Microsoft responsibilities</span></span>
<span data-ttu-id="97009-106">**Office 365 アプリ**Microsoft は、特定の Office 365 アプリの展開、更新、およびサポートに対して完全なサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="97009-106">**Office 365 apps** Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps.</span></span> <span data-ttu-id="97009-107">すべてのユーザーは、ユーザーがすぐに生産性を向上させることができるように、デバイスの画像に含まれているアプリケーションの64ビットバージョンの Office 365 を実行するための基本セットを受信します。</span><span class="sxs-lookup"><span data-stu-id="97009-107">All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive.</span></span> <span data-ttu-id="97009-108">Office 365 スイートのプロジェクトと Visio アプリケーションは個別にライセンスされています。</span><span class="sxs-lookup"><span data-stu-id="97009-108">The Project and Visio applications in of the Office 365 suite are licensed separately.</span></span>  <span data-ttu-id="97009-109">Microsoft マネージドデスクトップは、IT 管理者がライセンスを管理して、組織に適したアプリケーションを展開できるようにする展開グループを提供します。</span><span class="sxs-lookup"><span data-stu-id="97009-109">Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization.</span></span> <span data-ttu-id="97009-110">microsoft は、microsoft マネージドデスクトップサポートチャネルを使用して、これらのアプリケーションのエンドユーザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="97009-110">Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.</span></span>

<span data-ttu-id="97009-111">**基幹業務アプリ**Microsoft は、IT 管理者が、基幹業務 (LOB) アプリケーションを管理し、Intune 製品の一部としてエンドユーザーに展開するためのツールを提供しています。</span><span class="sxs-lookup"><span data-stu-id="97009-111">**Line-of-business apps** Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product.</span></span> <span data-ttu-id="97009-112">Microsoft は、[基幹業務アプリケーション](#line-of-business-applications)で詳細なアプリケーション展開の問題をサポートします。</span><span class="sxs-lookup"><span data-stu-id="97009-112">Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications)</span></span> 

<span data-ttu-id="97009-113">**Intune を使用して展開**するintune は、microsoft**の**管理デスクトップオンボードにリンクされており、intune を使用して、調達アプリを展開できます。</span><span class="sxs-lookup"><span data-stu-id="97009-113">**Deploy with Intune** Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune.</span></span> <span data-ttu-id="97009-114">また、microsoft Store からエンドユーザーに会社のポータルアプリケーションを展開することで、IT 管理者がエンドユーザーに対してセルフサービスを提供できるようにします。</span><span class="sxs-lookup"><span data-stu-id="97009-114">Microsoft will also deploy the Company Portal application from the Microsoft Store to end users so that IT Administrators can provide a self-service experience for their end users.</span></span>

<span data-ttu-id="97009-115">**アプリ管理**Microsoft は、システムに影響を与えるため、モダンワークプレースに適さない制限付きアプリケーションを特定することができます。</span><span class="sxs-lookup"><span data-stu-id="97009-115">**App management** Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact.</span></span> <span data-ttu-id="97009-116">このようなアプリケーションが検出されると、お客様に通知され、そのアプリケーションをテナントから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97009-116">When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant.</span></span> 

<span data-ttu-id="97009-117">制限されたアプリの動作とアプリの要件の詳細については、「 [Microsoft Managed Desktop app の要件](../service-description/mmd-app-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97009-117">For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)</span></span>

## <a name="customer-responsibilities"></a><span data-ttu-id="97009-118">お客様の責任</span><span class="sxs-lookup"><span data-stu-id="97009-118">Customer responsibilities</span></span>
<span data-ttu-id="97009-119">Office 365 スイートは、microsoft の生産性向上のための中核であり、microsoft のすべての管理対象デスクトップユーザーの microsoft 365 ライセンスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="97009-119">The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users.</span></span> <span data-ttu-id="97009-120">microsoft が管理するデスクトップデバイスに対して office アプリケーションを展開、更新、サポートする一方で、お客様が責任を持ついくつかの分野があります。</span><span class="sxs-lookup"><span data-stu-id="97009-120">While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.</span></span>
- <span data-ttu-id="97009-121">**ライセンスの割り当て**-お客様は、Office 365 のエンドユーザーに適切なライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="97009-121">**Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365.</span></span> 
- <span data-ttu-id="97009-122">**ユーザーをセキュリティグループに追加する**-プロジェクトまたは Visio を必要とするユーザーを持つ顧客の場合、IT 管理者は、それらのユーザーを適切な展開グループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97009-122">**Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="97009-123">IT 管理者は、これらのユーザーの有効期限の管理も担当します。</span><span class="sxs-lookup"><span data-stu-id="97009-123">IT administrators are also responsible for managing end of life for those users.</span></span> 
- <span data-ttu-id="97009-124">**office 365 アドオンを展開**する-お客様は必要と思われる office 365 スイートにプラグインを展開する責任があります。</span><span class="sxs-lookup"><span data-stu-id="97009-124">**Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary.</span></span> 

<span data-ttu-id="97009-125">基幹業務 (LOB) アプリは顧客ごとに一意であるため、お客様は Microsoft によって展開されていない組織内のすべてのアプリケーションを管理する責任があります。</span><span class="sxs-lookup"><span data-stu-id="97009-125">Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft.</span></span> <span data-ttu-id="97009-126">これには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="97009-126">This includes:</span></span>
- <span data-ttu-id="97009-127">必要なアプリとそれらを必要とするアプリを決定する</span><span class="sxs-lookup"><span data-stu-id="97009-127">Deciding which apps are needed and who needs them</span></span>
- <span data-ttu-id="97009-128">これらのユーザーにアプリを割り当てる</span><span class="sxs-lookup"><span data-stu-id="97009-128">Assigning apps to those users</span></span>
- <span data-ttu-id="97009-129">アプリの割り当てを管理するための Azure Active Directory (AD) グループを作成して管理する</span><span class="sxs-lookup"><span data-stu-id="97009-129">Create and maintain Azure Active Directory (AD) groups for managing app assignments</span></span> 

<span data-ttu-id="97009-130">お客様は LOB アプリを Intune にアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="97009-130">The customer must upload LOB apps to Intune.</span></span> <span data-ttu-id="97009-131">その後、それらのアプリケーションをそれぞれのライフサイクルを通じて展開、更新、および使用停止し、ユーザー用のこれらのアプリのサポートを管理する責任があります。</span><span class="sxs-lookup"><span data-stu-id="97009-131">They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.</span></span>

## <a name="office-applications"></a><span data-ttu-id="97009-132">Office アプリケーション</span><span class="sxs-lookup"><span data-stu-id="97009-132">Office applications</span></span>
<span data-ttu-id="97009-133">microsoft 365 E5 ライセンスの一部として、Office 365 Standard Suite (64 ビット) は microsoft によって展開されています。</span><span class="sxs-lookup"><span data-stu-id="97009-133">As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft.</span></span> 

<span data-ttu-id="97009-134">詳細については、「 [Microsoft Managed Desktop technologies](../intro/technologies.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97009-134">For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md)</span></span> <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.-->

## <a name="line-of-business-applications"></a><span data-ttu-id="97009-135">基幹業務アプリケーション</span><span class="sxs-lookup"><span data-stu-id="97009-135">Line-of-business applications</span></span>
<span data-ttu-id="97009-136">この表は、基幹業務 (LOB) アプリケーションのさまざまなフェーズにおける責任を要約しています。</span><span class="sxs-lookup"><span data-stu-id="97009-136">This table summarizes responsibilities across the different phases for line-of-business (LOB) applications.</span></span> 

<span data-ttu-id="97009-137">アプリケーション作業項目</span><span class="sxs-lookup"><span data-stu-id="97009-137">Application work items</span></span> |    <span data-ttu-id="97009-138">顧客</span><span class="sxs-lookup"><span data-stu-id="97009-138">Customer</span></span>    | <span data-ttu-id="97009-139">Microsoft</span><span class="sxs-lookup"><span data-stu-id="97009-139">Microsoft</span></span>
--- | --- | ---
<span data-ttu-id="97009-140">**オンボードアプリ**</span><span class="sxs-lookup"><span data-stu-id="97009-140">**Onboarding apps**</span></span> |  |
<span data-ttu-id="97009-141">対象ユーザーグループに必要なアプリケーションを特定する</span><span class="sxs-lookup"><span data-stu-id="97009-141">Identify applications needed for targeted user groups</span></span>   | ![はい](images/checkmark.png)  |
<span data-ttu-id="97009-143">アプリ展開用の Azure AD グループを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="97009-143">Create and manage Azure AD groups for app deployment</span></span> | ![はい](images/checkmark.png) |   
<span data-ttu-id="97009-145">**アプリのパッケージ化**</span><span class="sxs-lookup"><span data-stu-id="97009-145">**App Packaging**</span></span> |  |
<span data-ttu-id="97009-146">Intune の展開基準を満たすようにアプリをパッケージ化する</span><span class="sxs-lookup"><span data-stu-id="97009-146">Package apps to meet Intune deployment standards</span></span> |  ![はい](images/checkmark.png) |  
<span data-ttu-id="97009-148">アプリを Intune にアップロードする</span><span class="sxs-lookup"><span data-stu-id="97009-148">Upload apps to Intune</span></span> | ![はい](images/checkmark.png)     |
<span data-ttu-id="97009-150">Microsoft マネージドデスクトップ環境でアプリをテストする</span><span class="sxs-lookup"><span data-stu-id="97009-150">Test apps in Microsoft Managed Desktop environment</span></span> |    ![はい](images/checkmark.png) |  
<span data-ttu-id="97009-152">エンドユーザーとのアプリのテスト</span><span class="sxs-lookup"><span data-stu-id="97009-152">Test apps with end users</span></span>    | ![はい](images/checkmark.png) |    
<span data-ttu-id="97009-154">**展開**</span><span class="sxs-lookup"><span data-stu-id="97009-154">**Deployment**</span></span> | |
<span data-ttu-id="97009-155">アプリケーションに対するユーザーの管理と割り当て</span><span class="sxs-lookup"><span data-stu-id="97009-155">Manage and assign users to applications</span></span>  | ![はい](images/checkmark.png)  |
<span data-ttu-id="97009-157">Intune 展開ツールがリモートクライアントにアプリケーションを提供する</span><span class="sxs-lookup"><span data-stu-id="97009-157">Intune deployment tools delivers application to remote clients</span></span>| |   ![はい](images/checkmark.png)
<span data-ttu-id="97009-159">Intune を使用してアプリケーションの更新を識別して展開する</span><span class="sxs-lookup"><span data-stu-id="97009-159">Identify and deploy application updates through Intune</span></span> | ![はい](images/checkmark.png)    |
<span data-ttu-id="97009-161">Unistall が廃止されたときにアプリケーションを削除する</span><span class="sxs-lookup"><span data-stu-id="97009-161">Unistall and remove applications when they have been retired</span></span>    | ![はい](images/checkmark.png) |    
<span data-ttu-id="97009-163">**管理**</span><span class="sxs-lookup"><span data-stu-id="97009-163">**Management**</span></span> | |
<span data-ttu-id="97009-164">ライセンスの調達と割り当て</span><span class="sxs-lookup"><span data-stu-id="97009-164">Procure and assign licenses</span></span> |   ![はい](images/checkmark.png)     |
<span data-ttu-id="97009-166">基幹業務アプリのエンドユーザーサポートを提供する</span><span class="sxs-lookup"><span data-stu-id="97009-166">Provide end-user support for line-of-business apps</span></span>  | ![はい](images/checkmark.png) |
<span data-ttu-id="97009-168">アプリの設定をリモートで管理する</span><span class="sxs-lookup"><span data-stu-id="97009-168">Manage app settings remotely</span></span>    | ![はい](images/checkmark.png) |

<span data-ttu-id="97009-170">LOB アプリケーションの要件の詳細については、「 [Microsoft Managed Desktop application の要件](../service-description/mmd-app-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97009-170">For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)</span></span>


## <a name="intune-application-deployment"></a><span data-ttu-id="97009-171">Intune アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="97009-171">Intune application deployment</span></span>
<span data-ttu-id="97009-172">アプリケーション管理は、Microsoft Managed Desktop Admin portal または Intune ポータルを使用して処理できます。</span><span class="sxs-lookup"><span data-stu-id="97009-172">Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal.</span></span> <span data-ttu-id="97009-173">Intune のアプリ管理ポータルには、Windows、Android、iOS 用に展開されたアプリケーションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97009-173">Intune’s app management portal shows applications deployed for Windows, Android, and iOS.</span></span> <span data-ttu-id="97009-174">Microsoft Managed Desktop 管理ポータルでは、ビューが Windows 10 アプリケーションに制限されます。</span><span class="sxs-lookup"><span data-stu-id="97009-174">Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications.</span></span> <span data-ttu-id="97009-175">どちらも Azure ポータルから利用できます。</span><span class="sxs-lookup"><span data-stu-id="97009-175">Both are available through the Azure Portal.</span></span> 
* [<span data-ttu-id="97009-176">Intune アプリ管理の基本</span><span class="sxs-lookup"><span data-stu-id="97009-176">Intune app management basics</span></span>](https://docs.microsoft.com/intune/app-management)
* [<span data-ttu-id="97009-177">Intune にアプリを追加する</span><span class="sxs-lookup"><span data-stu-id="97009-177">Add apps to Intune</span></span>](https://docs.microsoft.com/intune/app-management)
   * [<span data-ttu-id="97009-178">基幹業務アプリを追加する</span><span class="sxs-lookup"><span data-stu-id="97009-178">Add a line-of-business App</span></span>](https://docs.microsoft.com/intune/lob-apps-windows)
   * [<span data-ttu-id="97009-179">Win32 アプリを Intune に追加する</span><span class="sxs-lookup"><span data-stu-id="97009-179">Add Win32 apps to Intune</span></span>](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [<span data-ttu-id="97009-180">web アプリケーションを追加する</span><span class="sxs-lookup"><span data-stu-id="97009-180">Add web applications</span></span>](https://docs.microsoft.com/intune/web-app)
* [<span data-ttu-id="97009-181">アプリを展開する</span><span class="sxs-lookup"><span data-stu-id="97009-181">Deploy apps</span></span>](https://docs.microsoft.com/intune/apps-deploy)
   * [<span data-ttu-id="97009-182">Windows 10 にアプリを展開する</span><span class="sxs-lookup"><span data-stu-id="97009-182">Deploy apps to Windows 10</span></span>](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* <span data-ttu-id="97009-183">会社のポータル</span><span class="sxs-lookup"><span data-stu-id="97009-183">Company Portal</span></span>
   * [<span data-ttu-id="97009-184">会社のポータルを展開する</span><span class="sxs-lookup"><span data-stu-id="97009-184">Deploy the Company Portal</span></span>](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [<span data-ttu-id="97009-185">ポータルサイトアプリを構成する</span><span class="sxs-lookup"><span data-stu-id="97009-185">Configure the Company Portal app</span></span>](https://docs.microsoft.com/intune/company-portal-app)
