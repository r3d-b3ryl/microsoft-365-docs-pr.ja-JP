---
title: デスクトップを管理する Microsoft のアプリケーションを準備します。
description: ''
keywords: 管理されたデスクトップの Microsoft、Microsoft 365 サービス マニュアル
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: b46e3de4a4cfe2140574ab9fc589e3a738bd2e17
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869202"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a><span data-ttu-id="f0eb9-103">デスクトップを管理する Microsoft のアプリケーションを準備します。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-103">Preparing apps for Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
<span data-ttu-id="f0eb9-104">マイクロソフトおよびマイクロソフトの管理されたデスクトップの顧客は、Microsoft 管理されたデスクトップで使用するアプリケーションに重要なまだ別の責任である均等にします。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-104">Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.</span></span>

## <a name="microsoft-responsibilities"></a><span data-ttu-id="f0eb9-105">Microsoft の責任</span><span class="sxs-lookup"><span data-stu-id="f0eb9-105">Microsoft responsibilities</span></span>
<span data-ttu-id="f0eb9-p101">**Office 365 アプリケーション**マイクロソフトでは、展開、更新、および特定の Office 365 アプリケーションのサポートの完全なサービスが提供されます。ユーザーが生産性を迅速にするために、デバイスのイメージに含まれるアプリケーションの 64 ビット バージョンを実行する] をクリックを Office 365 の基本セットは、すべてのユーザーが表示されます。Office 365 製品ファミリの内のプロジェクトおよび Visio のアプリケーションは個別にライセンスされています。 Microsoft 管理されたデスクトップ展開グループがライセンスを管理し、各組織に適切にこれらのアプリケーションを展開する IT 管理者が提供されます。マイクロソフトは、Microsoft 管理されたデスクトップのサポート チャネルを通じてこれらのアプリケーションのエンド ・ ユーザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-p101">**Office 365 apps** Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.</span></span>

<span data-ttu-id="f0eb9-p102">**基幹業務アプリケーション**マイクロソフトでは、IT 管理者の管理および Intune 製品の一部として、基幹業務 (LOB) アプリケーションをエンドユーザーに展開するためのツールを提供します。マイクロソフトをサポートする[基幹業務アプリケーション](#line-of-business-applications)を「アプリケーションの展開に関する問題</span><span class="sxs-lookup"><span data-stu-id="f0eb9-p102">**Line-of-business apps** Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications)</span></span> 

<span data-ttu-id="f0eb9-p103">**Intune と展開**Intune は、Intune によって展開される調達されたアプリケーションを許可する管理されたデスクトップのマイクロソフトの契約時の中に**ビジネスのためのマイクロソフト ストア**にリンクされます。IT 管理者は、エンド ・ ユーザーのセルフ サービス エクスペリエンスを提供できるように Microsoft はエンド ・ ユーザーにも企業ポータルの web ベースのバージョンを展開します。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-p103">**Deploy with Intune** Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.</span></span>

<span data-ttu-id="f0eb9-p104">**アプリケーションの管理**マイクロソフトでは、システムに対する影響があるため、現代の職場に適したない制限されたアプリケーションを識別可能性があります。指定は、このようなアプリケーションと Microsoft を顧客に通知がそのアプリケーションはテナントから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-p104">**App management** Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant.</span></span> 

<span data-ttu-id="f0eb9-117">制限されたアプリケーションの動作とアプリケーションの要件の詳細については、[マイクロソフトの管理されたデスクトップ アプリケーションの要件](../service-description/mmd-app-requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-117">For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)</span></span>

## <a name="customer-responsibilities"></a><span data-ttu-id="f0eb9-118">お客様の責任範囲</span><span class="sxs-lookup"><span data-stu-id="f0eb9-118">Customer responsibilities</span></span>
<span data-ttu-id="f0eb9-p105">Office 365 製品ファミリは、マイクロソフトの生産性ソリューションの中核し、Microsoft 管理されたデスクトップのすべてのユーザーの Microsoft 365 ライセンスに含まれています。マイクロソフトの展開、更新、およびデスクトップ管理されているデバイスを Microsoft Office アプリケーションをサポートしているときに、お客様の責任の一部の領域はまだあります.</span><span class="sxs-lookup"><span data-stu-id="f0eb9-p105">The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.</span></span>
- <span data-ttu-id="f0eb9-121">**ライセンスを割り当てる**には、お客様の Office 365 のエンド ・ ユーザーへの適切なライセンスの割り当てを担当します。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-121">**Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365.</span></span> 
- <span data-ttu-id="f0eb9-p106">**セキュリティ グループにユーザーの追加**のプロジェクトまたは Visio を必要としているユーザーとお客様の IT 管理者する必要がありますそれらのユーザー グループに追加、適切な展開。IT 管理者も、それらのユーザーの寿命の最後の管理を担当します。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-p106">**Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for managing end of life for those users.</span></span> 
- <span data-ttu-id="f0eb9-124">**Office 365 に追加のアドオンの導入**のお客様は、任意のプラグインを必要と判断した場合は、Office 365 製品ファミリに展開を担当します。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-124">**Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary.</span></span> 

<span data-ttu-id="f0eb9-p107">基幹業務 (LOB) アプリケーションが顧客ごとに一意であるために、お客様はマイクロソフトが展開していない組織内のすべてのアプリケーションを管理する責任者です。これが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-p107">Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:</span></span>
- <span data-ttu-id="f0eb9-127">どのアプリが必要し、それらが必要なユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-127">Deciding which apps are needed and who needs them</span></span>
- <span data-ttu-id="f0eb9-128">それらのユーザーにアプリケーションを割り当てる</span><span class="sxs-lookup"><span data-stu-id="f0eb9-128">Assigning apps to those users</span></span>
- <span data-ttu-id="f0eb9-129">作成し、アプリケーションの割り当てを管理するための Azure Active Directory (AD) のグループの管理</span><span class="sxs-lookup"><span data-stu-id="f0eb9-129">Create and maintain Azure Active Directory (AD) groups for managing app assignments</span></span> 

<span data-ttu-id="f0eb9-p108">お客様は、Intune に LOB アプリケーションをアップロードする必要があります。展開を更新して、それぞれのライフ サイクル上でそれらのアプリケーションの使用を停止として、これらのアプリケーションのユーザーのサポートを管理する責任は。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-p108">The customer must upload LOB apps to Intune. They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.</span></span>

## <a name="office-applications"></a><span data-ttu-id="f0eb9-132">Office アプリケーション</span><span class="sxs-lookup"><span data-stu-id="f0eb9-132">Office applications</span></span>
<span data-ttu-id="f0eb9-133">365 E5 のマイクロソフト ライセンスの一部として、microsoft Office 365 の標準的なスイート (64 ビット) が配置されます。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-133">As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft.</span></span> 

<span data-ttu-id="f0eb9-134">詳細については、[管理されたデスクトップの Microsoft テクノロジ](../intro/technologies.md)を参照してください。<!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.--></span><span class="sxs-lookup"><span data-stu-id="f0eb9-134">For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.--></span></span>

## <a name="line-of-business-applications"></a><span data-ttu-id="f0eb9-135">基幹業務アプリケーション</span><span class="sxs-lookup"><span data-stu-id="f0eb9-135">Line-of-business applications</span></span>
<span data-ttu-id="f0eb9-136">このテーブルでは、基幹業務 (LOB) アプリケーションのさまざまなフェーズの間で責任の範囲をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-136">This table summarizes responsibilities across the different phases for line-of-business (LOB) applications.</span></span> 

<span data-ttu-id="f0eb9-137">アプリケーション作業項目</span><span class="sxs-lookup"><span data-stu-id="f0eb9-137">Application work items</span></span> |    <span data-ttu-id="f0eb9-138">顧客</span><span class="sxs-lookup"><span data-stu-id="f0eb9-138">Customer</span></span>    | <span data-ttu-id="f0eb9-139">Microsoft</span><span class="sxs-lookup"><span data-stu-id="f0eb9-139">Microsoft</span></span>
--- | --- | ---
<span data-ttu-id="f0eb9-140">**契約時のアプリケーション**</span><span class="sxs-lookup"><span data-stu-id="f0eb9-140">**Onboarding apps**</span></span> |  |
<span data-ttu-id="f0eb9-141">対象となるユーザー グループに必要なアプリケーションを特定します。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-141">Identify applications needed for targeted user groups</span></span>   | ![はい](images/checkmark.png)  |
<span data-ttu-id="f0eb9-143">作成および管理アプリケーションの展開の Azure AD グループ</span><span class="sxs-lookup"><span data-stu-id="f0eb9-143">Create and manage Azure AD groups for app deployment</span></span> | ![はい](images/checkmark.png) |   
<span data-ttu-id="f0eb9-145">**アプリケーションのパッケージ化**</span><span class="sxs-lookup"><span data-stu-id="f0eb9-145">**App Packaging**</span></span> |  |
<span data-ttu-id="f0eb9-146">Intune 展開の標準に準拠してアプリケーションをパッケージ</span><span class="sxs-lookup"><span data-stu-id="f0eb9-146">Package apps to meet Intune deployment standards</span></span> |  ![はい](images/checkmark.png) |  
<span data-ttu-id="f0eb9-148">Intune にアプリケーションをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-148">Upload apps to Intune</span></span> | ![はい](images/checkmark.png)     |
<span data-ttu-id="f0eb9-150">Microsoft 管理されたデスクトップ環境でアプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-150">Test apps in Microsoft Managed Desktop environment</span></span> |    ![はい](images/checkmark.png) |  
<span data-ttu-id="f0eb9-152">エンド ・ ユーザーによるアプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="f0eb9-152">Test apps with end users</span></span>    | ![はい](images/checkmark.png) |    
<span data-ttu-id="f0eb9-154">**展開**</span><span class="sxs-lookup"><span data-stu-id="f0eb9-154">**Deployment**</span></span> | |
<span data-ttu-id="f0eb9-155">管理し、ユーザーをアプリケーションに割り当てる</span><span class="sxs-lookup"><span data-stu-id="f0eb9-155">Manage and assign users to applications</span></span>  | ![はい](images/checkmark.png)  |
<span data-ttu-id="f0eb9-157">Intune 展開ツールは、リモート クライアントにアプリケーションを提供します。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-157">Intune deployment tools delivers application to remote clients</span></span>| |   ![はい](images/checkmark.png)
<span data-ttu-id="f0eb9-159">識別し、Intune によってアプリケーションの更新プログラムの展開</span><span class="sxs-lookup"><span data-stu-id="f0eb9-159">Identify and deploy application updates through Intune</span></span> | ![はい](images/checkmark.png)    |
<span data-ttu-id="f0eb9-161">それらが使用されなくなったときにアプリケーションをアンインストールし、削除</span><span class="sxs-lookup"><span data-stu-id="f0eb9-161">Unistall and remove applications when they have been retired</span></span>    | ![はい](images/checkmark.png) |    
<span data-ttu-id="f0eb9-163">**管理**</span><span class="sxs-lookup"><span data-stu-id="f0eb9-163">**Management**</span></span> | |
<span data-ttu-id="f0eb9-164">調達し、ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="f0eb9-164">Procure and assign licenses</span></span> |   ![はい](images/checkmark.png)     |
<span data-ttu-id="f0eb9-166">基幹業務アプリケーションのエンド ユーザー サポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-166">Provide end-user support for line-of-business apps</span></span>  | ![はい](images/checkmark.png) |
<span data-ttu-id="f0eb9-168">アプリケーション設定を管理するリモート</span><span class="sxs-lookup"><span data-stu-id="f0eb9-168">Manage app settings remotely</span></span>    | ![はい](images/checkmark.png) |

<span data-ttu-id="f0eb9-170">LOB アプリケーションの要件については、[マイクロソフトの管理されたデスクトップ アプリケーションの要件](../service-description/mmd-app-requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-170">For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)</span></span>


## <a name="intune-application-deployment"></a><span data-ttu-id="f0eb9-171">Intune アプリケーションの配置</span><span class="sxs-lookup"><span data-stu-id="f0eb9-171">Intune application deployment</span></span>
<span data-ttu-id="f0eb9-p109">Microsoft デスクトップ管理の管理ポータル、または Intune ポータルを通じて、アプリケーションの管理を処理できます。Intune のアプリケーションの管理ポータルは、Windows、Android、iOS の配置されたアプリケーションを示しています。マイクロソフト デスクトップ管理の管理ポータルでは、10 の Windows アプリケーションに表示を制限します。両方は、Azure ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-p109">Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal.</span></span> 
* [<span data-ttu-id="f0eb9-176">Intune アプリケーション管理の基礎</span><span class="sxs-lookup"><span data-stu-id="f0eb9-176">Intune app management basics</span></span>](https://docs.microsoft.com/intune/app-management)
* [<span data-ttu-id="f0eb9-177">Intune にアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-177">Add apps to Intune</span></span>](https://docs.microsoft.com/intune/app-management)
   * [<span data-ttu-id="f0eb9-178">基幹業務アプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-178">Add a line-of-business App</span></span>](https://docs.microsoft.com/intune/lob-apps-windows)
   * [<span data-ttu-id="f0eb9-179">Intune に Win32 アプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-179">Add Win32 apps to Intune</span></span>](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [<span data-ttu-id="f0eb9-180">Web アプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-180">Add web applications</span></span>](https://docs.microsoft.com/intune/web-app)
* [<span data-ttu-id="f0eb9-181">アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-181">Deploy apps</span></span>](https://docs.microsoft.com/intune/apps-deploy)
   * <span data-ttu-id="f0eb9-182">[10 [Windows へのアプリケーションを展開します。](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)</span><span class="sxs-lookup"><span data-stu-id="f0eb9-182">[Deploy apps to Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)</span></span>
* <span data-ttu-id="f0eb9-183">企業ポータル</span><span class="sxs-lookup"><span data-stu-id="f0eb9-183">Company Portal</span></span>
   * [<span data-ttu-id="f0eb9-184">企業ポータルを展開します。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-184">Deploy the Company Portal</span></span>](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [<span data-ttu-id="f0eb9-185">会社のポータル アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="f0eb9-185">Configure the Company Portal app</span></span>](https://docs.microsoft.com/intune/company-portal-app)
