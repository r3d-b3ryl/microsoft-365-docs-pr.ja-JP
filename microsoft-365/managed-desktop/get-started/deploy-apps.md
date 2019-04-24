---
title: Microsoft マネージドデスクトップデバイス用のアプリを展開する
description: Microsoft マネージドデスクトップデバイスへのアプリの追加および展開に関する情報。
keywords: microsoft マネージドデスクトップ、microsoft 365、サービス、ドキュメント、アプリ、基幹業務アプリ、LOB アプリ
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5ccb240460958d5978f4fd19e08652123790784e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282523"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a><span data-ttu-id="304d8-104">アプリを Microsoft マネージドデスクトップデバイスに展開する</span><span class="sxs-lookup"><span data-stu-id="304d8-104">Deploy apps to Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="304d8-105">Microsoft Managed Desktop へのオンボードの一部には、ユーザーのデバイスへのアプリの追加と展開が含まれます。</span><span class="sxs-lookup"><span data-stu-id="304d8-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user’s devices.</span></span> <span data-ttu-id="304d8-106">Microsoft マネージドデスクトップポータルを使用している場合は、アプリを追加して展開することができます。</span><span class="sxs-lookup"><span data-stu-id="304d8-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="304d8-107">全体的なプロセスは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="304d8-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="304d8-108">[microsoft マネージドデスクトップポータルへのアプリの追加](#1)-既存の基幹業務 (LOB) アプリ、または Intune と同期したビジネス向け Microsoft Store のアプリにすることができます。</span><span class="sxs-lookup"><span data-stu-id="304d8-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="304d8-109">[アプリの割り当て用に Azure Active Directory (AD) グループを作成](#2)する-これらのグループを使用して、アプリの割り当てを管理します。</span><span class="sxs-lookup"><span data-stu-id="304d8-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="304d8-110">ユーザーにアプリを割り当てる</span><span class="sxs-lookup"><span data-stu-id="304d8-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="304d8-111">手順 1: Microsoft マネージドデスクトップポータルにアプリを追加する</span><span class="sxs-lookup"><span data-stu-id="304d8-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="304d8-112">microsoft マネージドデスクトップには、 [Win32、Windows MSI ベースのアプリ](#lob-apps)、または[microsoft Store for Business アプリ](#msfb-apps)を追加し、それを microsoft マネージドデスクトップデバイスに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="304d8-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="304d8-113">Microsoft マネージドデスクトップへの Win32 または Windows MSI ベースのアプリ</span><span class="sxs-lookup"><span data-stu-id="304d8-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="304d8-114">基幹業務 (LOB) アプリを Microsoft マネージドデスクトップポータルに追加できます。</span><span class="sxs-lookup"><span data-stu-id="304d8-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="304d8-115">microsoft マネージドデスクトップデバイスにインストールされているアプリの要件の詳細については、「 [microsoft managed desktop app の要件](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="304d8-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="304d8-116">この手順では、追加するアプリの種類を選択してから、アプリソースを構成およびアップロードします。</span><span class="sxs-lookup"><span data-stu-id="304d8-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="304d8-117">**LOB アプリまたは Windows アプリを Microsoft マネージドデスクトップポータルに追加するには**</span><span class="sxs-lookup"><span data-stu-id="304d8-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="304d8-118">microsoft マネージドデスクトップポータルにサインインするか、Intune にサインインして、microsoft managed desktop を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="304d8-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="304d8-119">Microsoft マネージドデスクトップポータルへのサインインを表示します。</span><span class="sxs-lookup"><span data-stu-id="304d8-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.  <span data-ttu-id="304d8-120">[Microsoft Managed Desktop 管理ポータル](http://aka.ms/mmdportal)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="304d8-120">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span> 
2.  <span data-ttu-id="304d8-121">[**インベントリ**] で、[**アプリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="304d8-121">Under **Inventory**, select **Apps**.</span></span>
3.  <span data-ttu-id="304d8-122">[アプリのワークロード] で、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="304d8-122">In the Apps workload, select **Add**.</span></span>
4.  <span data-ttu-id="304d8-123">[**アプリの追加**] で、[**基幹業務アプリ**] または [ **Windows アプリ (Win32)-プレビュー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="304d8-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32) - preview**.</span></span>
    - <span data-ttu-id="304d8-124">基幹**業務アプリ**を選択した場合は、基幹業務アプリを追加して構成する手順については、「 [Windows の基幹業務アプリを Microsoft Intune に追加](https://docs.microsoft.com/intune/lob-apps-windows)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="304d8-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="304d8-125">**windows アプリ (Win32) プレビュー**を選択した場合は、「 [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) 」を参照してください。 windows アプリを追加および構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="304d8-125">If you selected **Windows app (Win32) - preview**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="304d8-126">ビジネス向け Microsoft Store アプリ</span><span class="sxs-lookup"><span data-stu-id="304d8-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="304d8-127">Microsoft Store for Business にサインアップしていない場合は、アプリの購入時にサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="304d8-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="304d8-128">アプリを用意したら、それらを Microsoft マネージドデスクトップと同期することができます。</span><span class="sxs-lookup"><span data-stu-id="304d8-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="304d8-129">**ビジネス向け Microsoft Store からアプリを購入するには**</span><span class="sxs-lookup"><span data-stu-id="304d8-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="304d8-130">business 管理者アカウントの microsoft store を使用して、 [microsoft store for business](https://businessstore.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="304d8-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="304d8-131">[**自分のグループのショッピング**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="304d8-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="304d8-132">検索を使用して目的のアプリを見つけ、アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="304d8-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="304d8-133">[製品の詳細] で、[**アプリの取得**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="304d8-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="304d8-134">Microsoft Store は、組織のためにアプリを**Products & サービス**に追加します。</span><span class="sxs-lookup"><span data-stu-id="304d8-134">Microsoft Store adds the app to **Products & services** for your organization.</span></span>

<span data-ttu-id="304d8-135">**ビジネス向けに Intune と Microsoft Store 間の同期を強制するには**</span><span class="sxs-lookup"><span data-stu-id="304d8-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="304d8-136">テナントのために Intune 管理者またはグローバル管理者として[Azure Portal](https://portal.azure.com/)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="304d8-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="304d8-137">[**すべてのサービス > Intune**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="304d8-137">Select **All services > Intune**.</span></span> <span data-ttu-id="304d8-138">Intune は、[監視 + 管理] セクションにあります。</span><span class="sxs-lookup"><span data-stu-id="304d8-138">Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="304d8-139">[Intune] ウィンドウで、[**クライアントアプリ**] を選択し、[**ビジネス向け Microsoft Store**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="304d8-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="304d8-140">[**有効**] を選択して、Microsoft Store for Business アプリを Intune と同期します。</span><span class="sxs-lookup"><span data-stu-id="304d8-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="304d8-141">まだ登録していない場合は、Microsoft Store for Business アカウントを Intune に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="304d8-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="304d8-142">Intune コンソールに Microsoft Store for Business のアプリが表示される言語を選択します</span><span class="sxs-lookup"><span data-stu-id="304d8-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="304d8-143">Microsoft Store for Business アプリを Intune と同期するには、[**同期**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="304d8-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="304d8-144">Microsoft Store for Business と Intune の間の同期がアクティブであることを確認します (次の手順)。</span><span class="sxs-lookup"><span data-stu-id="304d8-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="304d8-145">**Intune と Microsoft Store for Business の同期がアクティブであることを確認するには**</span><span class="sxs-lookup"><span data-stu-id="304d8-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="304d8-146">business 管理者アカウントの microsoft store を使用して、 [microsoft store for business](https://businessstore.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="304d8-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="304d8-147">[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="304d8-147">Select **Manage**.</span></span>
3. <span data-ttu-id="304d8-148">[**設定**] を選択し、[**配布**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="304d8-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="304d8-149">[**管理ツール**] で、Intune が表示され、状態が [**アクティブ**] になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="304d8-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="304d8-150">手順 2: Azure AD グループを作成する</span><span class="sxs-lookup"><span data-stu-id="304d8-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="304d8-151">アプリごとに3つの Azure AD グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="304d8-151">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="304d8-152">次の表に、必要なグループ (利用可能、必要、およびアンインストール) の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="304d8-152">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="304d8-153">アプリの割り当ての種類</span><span class="sxs-lookup"><span data-stu-id="304d8-153">App assignment type</span></span> |   <span data-ttu-id="304d8-154">グループの使用</span><span class="sxs-lookup"><span data-stu-id="304d8-154">Group use</span></span>   | <span data-ttu-id="304d8-155">Azure AD 名の例</span><span class="sxs-lookup"><span data-stu-id="304d8-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="304d8-156">Available</span><span class="sxs-lookup"><span data-stu-id="304d8-156">Available</span></span> |  <span data-ttu-id="304d8-157">アプリは、会社のポータルアプリまたは web サイトから入手できます。</span><span class="sxs-lookup"><span data-stu-id="304d8-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="304d8-158">MMD –*アプリ名*–利用可能</span><span class="sxs-lookup"><span data-stu-id="304d8-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="304d8-159">必須</span><span class="sxs-lookup"><span data-stu-id="304d8-159">Required</span></span> |  <span data-ttu-id="304d8-160">アプリは、選択したグループのデバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="304d8-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="304d8-161">MMD –*アプリ名*–必須</span><span class="sxs-lookup"><span data-stu-id="304d8-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="304d8-162">Uninstall</span><span class="sxs-lookup"><span data-stu-id="304d8-162">Uninstall</span></span> |  <span data-ttu-id="304d8-163">なアプリは、選択したグループのデバイスからアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="304d8-163">TThe app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="304d8-164">MMD –*アプリ名*–アンインストール</span><span class="sxs-lookup"><span data-stu-id="304d8-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="304d8-165">これらのグループにユーザーを追加して、アプリを利用できるようにするか、アプリをインストールするか、Microsoft マネージドデスクトップデバイスからアプリを削除します。</span><span class="sxs-lookup"><span data-stu-id="304d8-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="304d8-166">手順 3: ユーザーにアプリを割り当てる</span><span class="sxs-lookup"><span data-stu-id="304d8-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="304d8-167">**アプリをユーザーに割り当てるには**</span><span class="sxs-lookup"><span data-stu-id="304d8-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="304d8-168">[Microsoft Managed Desktop 管理ポータル](http://aka.ms/mmdportal)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="304d8-168">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="304d8-169">[管理されたデスクトップ] ウィンドウで、[**アプリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="304d8-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="304d8-170">[アプリのワークロード] で、ユーザーの割り当て先となるアプリを選択し、[**ユーザーグループの割り当て**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="304d8-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="304d8-171">特定のアプリについて、割り当ての種類 (利用可能、必須、アンインストール) を選択し、適切なグループを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="304d8-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="304d8-172">[アプリの割り当て] ウィンドウで、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="304d8-172">In the Assign Apps pane, select **OK**.</span></span>

<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

Applications: supported/onboard/deployment
 
Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.

## Microsoft responsibilities
**Office 365 apps**
Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.

**Line-of-business apps**
Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications) 

**Deploy with Intune**
Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.

**App management**
Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant. 

For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)

## Customer responsibilities
The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.
- **Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365. 
- **Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for managing end of life for those users. 
- **Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary. 

Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:
- Deciding which apps are needed and who needs them
- Assigning apps to those users
- Create and maintain Azure Active Directory (AD) groups for managing app assignments 

The customer must upload LOB apps to Intune. They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.

## Office applications
As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft. 

For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.

## Line-of-business applications
This table summarizes responsibilities across the different phases for line-of-business (LOB) applications. 

Application work items |    Customer    | Microsoft
--- | --- | ---
**Onboarding apps** |  |
Identify applications needed for targeted user groups   | ![yes](images/checkmark.png)  |
Create and manage Azure AD groups for app deployment | ![yes](images/checkmark.png) |   
**App Packaging** |  |
Package apps to meet Intune deployment standards |  ![yes](images/checkmark.png) |  
Upload apps to Intune | ![yes](images/checkmark.png)     |
Test apps in Microsoft Managed Desktop environment |    ![yes](images/checkmark.png) |  
Test apps with end users    | ![yes](images/checkmark.png) |    
**Deployment** | |
Manage and assign users to applications  | ![yes](images/checkmark.png)  |
Intune deployment tools delivers application to remote clients| |   ![yes](images/checkmark.png)
Identify and deploy application updates through Intune | ![yes](images/checkmark.png)    |
Unistall and remove applications when they have been retired    | ![yes](images/checkmark.png) |    
**Management** | |
Procure and assign licenses |   ![yes](images/checkmark.png)     |
Provide end-user support for line-of-business apps  | ![yes](images/checkmark.png) |
Manage app settings remotely    | ![yes](images/checkmark.png) |

For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)


## Intune application deployment
Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal. 
* [Intune app management basics](https://docs.microsoft.com/intune/app-management)
* [Add apps to Intune](https://docs.microsoft.com/intune/app-management)
   * [Add a line-of-business App](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Add Win32 apps to Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Add web applications](https://docs.microsoft.com/intune/web-app)
* [Deploy apps](https://docs.microsoft.com/intune/apps-deploy)
   * [Deploy apps to Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Company Portal
   * [Deploy the Company Portal](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Configure the Company Portal app](https://docs.microsoft.com/intune/company-portal-app)-->