---
title: デスクトップを管理する Microsoft のアプリケーションを準備します。
description: ''
keywords: 管理されたデスクトップの Microsoft、Microsoft 365 サービス マニュアル
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: ebeb54bd5d1f50cbb6f78b1c8ad4a624c449b8c2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869202"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a><span data-ttu-id="49701-103">デスクトップを管理する Microsoft のアプリケーションを準備します。</span><span class="sxs-lookup"><span data-stu-id="49701-103">Preparing apps for Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
<span data-ttu-id="49701-104">マイクロソフトおよびマイクロソフトの管理されたデスクトップの顧客は、Microsoft 管理されたデスクトップで使用するアプリケーションに重要なまだ別の責任である均等にします。</span><span class="sxs-lookup"><span data-stu-id="49701-104">Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.</span></span>

## <a name="microsoft-responsibilites"></a><span data-ttu-id="49701-105">Microsoft responsibilites</span><span class="sxs-lookup"><span data-stu-id="49701-105">Microsoft responsibilites</span></span>
<span data-ttu-id="49701-p101">**Office 365 アプリケーション**マイクロソフトでは、展開、更新、および特定の Office 365 アプリケーションのサポートの完全なサービスが提供されます。ユーザーが生産性を迅速にするために、デバイスのイメージに含まれるアプリケーションの 64 ビット バージョンを実行する] をクリックを Office 365 の基本セットは、すべてのユーザーが表示されます。Office 365 製品ファミリの内のプロジェクトおよび Visio のアプリケーションは個別にライセンスされています。 Microsoft 管理されたデスクトップ展開グループがライセンスを管理し、各組織に適切にこれらのアプリケーションを展開する IT 管理者が提供されます。マイクロソフトは、Microsoft 管理されたデスクトップのサポート チャネルを通じてこれらのアプリケーションのエンド ・ ユーザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="49701-p101">**Office 365 apps** Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.</span></span>

<span data-ttu-id="49701-p102">**基幹業務アプリケーション**マイクロソフトでは、IT 管理者の管理および Intune 製品の一部として、基幹業務アプリケーションをエンドユーザーに展開するためのツールを提供します。マイクロソフトをサポートする[基幹業務アプリケーション](#line-of-business-applications)を「アプリケーションの展開に関する問題</span><span class="sxs-lookup"><span data-stu-id="49701-p102">**Line-of-business apps** Microsoft provides tooling for IT Administrators to manage and deploy their Line of Business applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications)</span></span> 

<span data-ttu-id="49701-p103">**Intune と展開**Intune は、Intune によって展開される調達されたアプリケーションを許可する管理されたデスクトップのマイクロソフトの契約時の中に**ビジネスのためのマイクロソフト ストア**にリンクされます。IT 管理者は、エンド ・ ユーザーのセルフ サービス エクスペリエンスを提供できるように Microsoft はエンド ・ ユーザーにも企業ポータルの web ベースのバージョンを展開します。</span><span class="sxs-lookup"><span data-stu-id="49701-p103">**Deploy with Intune** Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.</span></span>

<span data-ttu-id="49701-p104">**アプリケーションの管理**マイクロソフトでは、システムに対する影響があるため、現代の職場に適したない制限されたアプリケーションを識別可能性があります。指定は、このようなアプリケーションと Microsoft を顧客に通知がそのアプリケーションはテナントから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49701-p104">**App management** Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant.</span></span> 

## <a name="customer-responsibilities"></a><span data-ttu-id="49701-117">お客様の責任範囲</span><span class="sxs-lookup"><span data-stu-id="49701-117">Customer responsibilities</span></span>
<span data-ttu-id="49701-p105">Office 365 製品ファミリは、マイクロソフトの生産性ソリューションの中核し、Microsoft 管理されたデスクトップのすべてのユーザーの Microsoft 365 ライセンスに含まれています。マイクロソフトの展開、更新、およびデスクトップ管理されているデバイスを Microsoft Office アプリケーションをサポートしているときに、お客様の責任の一部の領域はまだあります.</span><span class="sxs-lookup"><span data-stu-id="49701-p105">The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.</span></span>
- <span data-ttu-id="49701-120">**ライセンスを割り当てる**には、お客様の Office 365 のエンド ・ ユーザーへの適切なライセンスの割り当てを担当します。</span><span class="sxs-lookup"><span data-stu-id="49701-120">**Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365.</span></span> 
- <span data-ttu-id="49701-p106">**セキュリティ グループにユーザーの追加**のプロジェクトまたは Visio を必要としているユーザーとお客様の IT 管理者する必要がありますそれらのユーザー グループに追加、適切な展開。IT 管理者も、それらのユーザーの寿命の最後の管理を担当します。</span><span class="sxs-lookup"><span data-stu-id="49701-p106">**Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for managing end of life for those users.</span></span> 
- <span data-ttu-id="49701-123">**Office 365 に追加のアドオンの導入**のお客様は、任意のプラグインを必要と判断した場合は、Office 365 製品ファミリに展開を担当します。</span><span class="sxs-lookup"><span data-stu-id="49701-123">**Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary.</span></span> 

<span data-ttu-id="49701-p107">基幹業務 (LOB) アプリケーションが顧客ごとに一意であるために、お客様はマイクロソフトが展開していない組織内のすべてのアプリケーションを管理する責任者です。これが含まれています。</span><span class="sxs-lookup"><span data-stu-id="49701-p107">Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:</span></span>
- <span data-ttu-id="49701-126">どのアプリが必要し、それらが必要なユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="49701-126">Deciding which apps are needed and who needs them</span></span>
- <span data-ttu-id="49701-127">それらのユーザーにアプリケーションを割り当てる</span><span class="sxs-lookup"><span data-stu-id="49701-127">Assigning apps to those users</span></span>
- <span data-ttu-id="49701-128">作成し、アプリケーションの割り当てを管理するための Azure Active Directory (AD) のグループの管理</span><span class="sxs-lookup"><span data-stu-id="49701-128">Create and maintain Azure Active Directory (AD) groups for managing app assignments</span></span> 

<span data-ttu-id="49701-p108">LOB アプリケーションのコア セットを特定したらお客様は調達、ライセンスを取得、パッケージ化、および Microsoft 管理されたデスクトップ環境でアプリケーションをテストします。お客様は、アップロードし、Intune 展開、更新、および LOB アプリケーションを非コミッションにするアプリケーションを配置する必要があります。お客様は、LOB アプリケーションのサポートのユーザーの管理を担当します。</span><span class="sxs-lookup"><span data-stu-id="49701-p108">Once the core set of LOB apps has been identified the customer will procure, license, package, and test those applications in the Microsoft Managed Desktop environment. The customer must upload and deploy applications to Intune to deploy, update, and decommission their LOB applications. Customers are responsible for managing LOB apps support for their users.</span></span>
 

## <a name="office-applications"></a><span data-ttu-id="49701-132">Office アプリケーション</span><span class="sxs-lookup"><span data-stu-id="49701-132">Office applications</span></span>
<span data-ttu-id="49701-133">365 E5 のマイクロソフト ライセンスの一部として、microsoft Office 365 の標準的なスイート (64 ビット) が配置されます。</span><span class="sxs-lookup"><span data-stu-id="49701-133">As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft.</span></span> 

<span data-ttu-id="49701-134">詳細については、[管理されたデスクトップの Microsoft テクノロジ](../intro/technologies.md)を参照してください。<!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.--></span><span class="sxs-lookup"><span data-stu-id="49701-134">For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.--></span></span>

## <a name="line-of-business-applications"></a><span data-ttu-id="49701-135">基幹業務アプリケーション</span><span class="sxs-lookup"><span data-stu-id="49701-135">Line-of-business applications</span></span>
<span data-ttu-id="49701-136">このテーブルでは、基幹業務 (LOB) アプリケーションのさまざまなフェーズの間で責任の範囲をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="49701-136">This table summarizes responsibilities across the different phases for line-of-business (LOB) applications.</span></span> 

<span data-ttu-id="49701-137">アプリケーション作業項目</span><span class="sxs-lookup"><span data-stu-id="49701-137">Application work items</span></span> |    <span data-ttu-id="49701-138">顧客</span><span class="sxs-lookup"><span data-stu-id="49701-138">Customer</span></span>    | <span data-ttu-id="49701-139">Microsoft</span><span class="sxs-lookup"><span data-stu-id="49701-139">Microsoft</span></span>
--- | --- | ---
<span data-ttu-id="49701-140">**契約時のアプリケーション**</span><span class="sxs-lookup"><span data-stu-id="49701-140">**Onboarding apps**</span></span> |  |
<span data-ttu-id="49701-141">対象となるユーザー グループに必要なアプリケーションを特定します。</span><span class="sxs-lookup"><span data-stu-id="49701-141">Identify applications needed for targeted user groups</span></span>   | ![はい](images/checkmark.png)  |
<span data-ttu-id="49701-143">作成および管理アプリケーションの展開の Azure AD グループ</span><span class="sxs-lookup"><span data-stu-id="49701-143">Create and manage Azure AD groups for app deployment</span></span> | ![はい](images/checkmark.png) |   
<span data-ttu-id="49701-145">**アプリケーションのパッケージ化**</span><span class="sxs-lookup"><span data-stu-id="49701-145">**App Packaging**</span></span> |  |
<span data-ttu-id="49701-146">Intune 展開の標準に準拠してアプリケーションをパッケージ</span><span class="sxs-lookup"><span data-stu-id="49701-146">Package apps to meet Intune deployment standards</span></span> |  ![はい](images/checkmark.png) |  
<span data-ttu-id="49701-148">Intune にアプリケーションをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="49701-148">Upload apps to Intune</span></span> | ![はい](images/checkmark.png)     |
<span data-ttu-id="49701-150">Microsoft 管理されたデスクトップ環境でアプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="49701-150">Test apps in Microsoft Managed Desktop environment</span></span> |    ![はい](images/checkmark.png) |  
<span data-ttu-id="49701-152">エンド ・ ユーザーによるアプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="49701-152">Test apps with end users</span></span>    | ![はい](images/checkmark.png) |    
<span data-ttu-id="49701-154">**展開**</span><span class="sxs-lookup"><span data-stu-id="49701-154">**Deployment**</span></span> | |
<span data-ttu-id="49701-155">管理し、ユーザーをアプリケーションに割り当てる</span><span class="sxs-lookup"><span data-stu-id="49701-155">Manage and assign users to applications</span></span>  | ![はい](images/checkmark.png)  |
<span data-ttu-id="49701-157">Intune 展開ツールは、リモート クライアントにアプリケーションを提供します。</span><span class="sxs-lookup"><span data-stu-id="49701-157">Intune deployment tools delivers application to remote clients</span></span>| |   ![はい](images/checkmark.png)
<span data-ttu-id="49701-159">識別し、Intune によってアプリケーションの更新プログラムの展開</span><span class="sxs-lookup"><span data-stu-id="49701-159">Identify and deploy application updates through Intune</span></span> | ![はい](images/checkmark.png)    |
<span data-ttu-id="49701-161">それらが使用されなくなったときにアプリケーションをアンインストールし、削除</span><span class="sxs-lookup"><span data-stu-id="49701-161">Unistall and remove applications when they have been retired</span></span>    | ![はい](images/checkmark.png) |    
<span data-ttu-id="49701-163">**管理**</span><span class="sxs-lookup"><span data-stu-id="49701-163">**Management**</span></span> | |
<span data-ttu-id="49701-164">調達し、ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="49701-164">Procure and assign licenses</span></span> |   ![はい](images/checkmark.png)     |
<span data-ttu-id="49701-166">基幹業務アプリケーションのエンド ユーザー サポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="49701-166">Provide end-user support for line-of-business apps</span></span>  | ![はい](images/checkmark.png) |
<span data-ttu-id="49701-168">アプリケーション設定を管理するリモート</span><span class="sxs-lookup"><span data-stu-id="49701-168">Manage app settings remotely</span></span>    | ![はい](images/checkmark.png) |

<span data-ttu-id="49701-170">LOB アプリケーションの要件については、[マイクロソフトの管理されたデスクトップ アプリケーションの要件](../service-description/mmd-app-requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49701-170">For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)</span></span>

## <a name="resources"></a><span data-ttu-id="49701-171">リソース</span><span class="sxs-lookup"><span data-stu-id="49701-171">Resources</span></span>
<span data-ttu-id="49701-172">多くのサービスは、Microsoft の管理されたデスクトップの操作の範囲を超えている間は、お客様の助けとなる、Microsoft は、アプリケーションを管理するサービスがあります。</span><span class="sxs-lookup"><span data-stu-id="49701-172">While many services are out of scope for Microsoft Managed Desktop operations there are services which Microsoft offers which may help the customer manage their applications.</span></span>

### <a name="windows-upgrade-readiness"></a><span data-ttu-id="49701-173">Windows アップグレードの準備完了</span><span class="sxs-lookup"><span data-stu-id="49701-173">Windows Upgrade Readiness</span></span>
<span data-ttu-id="49701-p109">新しい Microsoft 管理されているデバイスの設定の重要な部分は、どのアプリケーションがデバイスのユーザーに必要な理解することです。Windows のアップグレードの準備は、マイクロソフトのツールにより、企業は、企業内アプリケーション ・ ランドス ケープを理解すると、次のようにそれらのアプリケーションに関する重要なデータを確認する際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="49701-p109">A key part of setting up new Microsoft Managed Devices is understanding which apps are needed for device users. Windows Upgrade Readiness is a Microsoft tool which helps enterprises understand the application landscape inside their company, and helps them to review key data about those applications, such as:</span></span>

- <span data-ttu-id="49701-176">**アプリケーションの使用状況**の遠隔測定データは、アプリケーションの使用状況を監視するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="49701-176">**Application usage** - Telemetry data is used to monitor application usage.</span></span>
- <span data-ttu-id="49701-p110">**アプリケーションの互換性**のアップグレードの準備は各アプリケーションには次の 10 の Windows の最新バージョンで展開されている範囲を表示し、"準備完了"Windows 用である場合を識別する方法を評価します。このデータには、テスト作業は、既に広く採用されているアプリケーションにフォーカスが役立ちます。</span><span class="sxs-lookup"><span data-stu-id="49701-p110">**Application compatibility** - Upgrade Readiness looks at each application and sees how broadly it has been deployed on the latest version of Windows 10 and assesses how to identify if it is “Ready for Windows”. This data helps focus testing efforts on applications which aren’t already broadly adopted.</span></span>

### <a name="intune-application-deployment"></a><span data-ttu-id="49701-179">Intune アプリケーションの配置</span><span class="sxs-lookup"><span data-stu-id="49701-179">Intune application deployment</span></span>
<span data-ttu-id="49701-p111">Microsoft デスクトップ管理の管理ポータル、または Intune ポータルを通じて、アプリケーションの管理を処理できます。Intune のアプリケーションの管理ポータルは、Windows、Android、iOS の配置されたアプリケーションを示しています。マイクロソフト デスクトップ管理の管理ポータルでは、10 の Windows アプリケーションに表示を制限します。両方は、Azure ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="49701-p111">Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal.</span></span> 
- [<span data-ttu-id="49701-184">Intune アプリケーション管理の基礎</span><span class="sxs-lookup"><span data-stu-id="49701-184">Intune app management basics</span></span>](https://docs.microsoft.com/intune/app-management)
- [<span data-ttu-id="49701-185">32 の Windows アプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="49701-185">Add a Windows 32 application</span></span>](https://docs.microsoft.com/intune/lob-apps-windows)
- [<span data-ttu-id="49701-186">Web アプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="49701-186">Add web applications</span></span>](https://docs.microsoft.com/intune/web-app)
- [<span data-ttu-id="49701-187">割り当てるし、グループにアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="49701-187">Assign and deploy apps to groups</span></span>](https://docs.microsoft.com/intune/apps-deploy)

### <a name="application-packaging-standards"></a><span data-ttu-id="49701-188">アプリケーション パッケージ化の基準</span><span class="sxs-lookup"><span data-stu-id="49701-188">Application packaging standards</span></span>
<span data-ttu-id="49701-p112">Intune の必要があるから 32 の Windows アプリケーションを配置するには、パッケージ化されたいずれかの方法として 1 つ。Msi ファイルを .appx、または。MSIX。Intune の最も一般的なパッケージの種類は、現在です。MSI。</span><span class="sxs-lookup"><span data-stu-id="49701-p112">To deploy Windows 32 applications through Intune they must be packaged as either a single .MSI, an .appx, or .MSIX. The most common package type for Intune is currently .MSI.</span></span>
