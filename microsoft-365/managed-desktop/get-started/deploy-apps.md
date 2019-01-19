---
title: Microsoft 管理デスクトップ デバイス用のアプリケーションを展開します。
description: 追加および管理されたデスクトップのマイクロソフトのデバイスにアプリケーションを展開するための情報です。
keywords: 管理されたデスクトップの Microsoft、Microsoft 365、サービス、ドキュメント、アプリケーション、基幹業務アプリケーション、LOB アプリケーション
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/17/2019
ms.openlocfilehash: 65d45be5ddb21d8f2cac876a1c8f93b2bbddf7b8
ms.sourcegitcommit: 0fc00286d7dc8cafddf9d17a98a375503b9551e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2019
ms.locfileid: "29341612"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a><span data-ttu-id="8e0ac-104">Microsoft 管理されたデスクトップのデバイスにアプリケーションを配備します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-104">Deploy apps to Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="8e0ac-p101">追加して、ユーザーのデバイスにアプリケーションを展開する、管理されたデスクトップのマイクロソフトに契約時の一部が含まれます。管理されたデスクトップの Microsoft のポータルを使用して後、は、追加し、アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-p101">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user’s devices. Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="8e0ac-107">プロセス全体は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="8e0ac-108">[管理されたデスクトップの Microsoft のポータルに追加のアプリケーション](#1)のこのことがでく既存の基幹業務 (LOB) アプリケーション、または Intune と同期しているビジネスのマイクロソフト ストアからのアプリです。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="8e0ac-109">[アプリケーションの割り当てのグループを作成 Azure Active Directory (AD)](#2) - アプリケーションの割り当てを管理するためにこれらのグループを使用します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="8e0ac-110">アプリケーションをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="8e0ac-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="8e0ac-111">手順 1: 管理されたデスクトップの Microsoft のポータルにアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="8e0ac-112">Microsoft 管理されたデスクトップでは、 [Win32 または Windows MSI ベースのアプリケーション](#lob-apps)、または[ビジネス アプリケーションのマイクロソフト ストア](#msfb-apps)に追加し、管理されたデスクトップのマイクロソフトのデバイスに配置できます。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="8e0ac-113">Win32 や Windows MSI ベースのアプリケーションを Microsoft デスクトップの管理</span><span class="sxs-lookup"><span data-stu-id="8e0ac-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="8e0ac-p102">管理されたデスクトップの Microsoft のポータルには、基幹業務 (LOB) アプリケーションを追加できます。Microsoft 管理デスクトップ デバイスにインストールされているアプリケーションの要件については、[マイクロソフトの管理されたデスクトップ アプリケーションの要件](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-p102">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal. For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="8e0ac-116">この手順では、どのようなアプリケーションの追加、および構成し、アプリケーションのソースをアップロードするを選択します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="8e0ac-117">**管理されたデスクトップの Microsoft のポータルに、LOB アプリケーションや Windows アプリケーションを追加するのには**</span><span class="sxs-lookup"><span data-stu-id="8e0ac-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="8e0ac-p103">管理されたデスクトップの Microsoft のポータルにサインインまたは Intune にサインインし、Microsoft の管理されたデスクトップを検索できます。管理されたデスクトップの Microsoft のポータルへのサインインをご紹介します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-p103">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop. We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.  <span data-ttu-id="8e0ac-120">[マイクロソフト デスクトップ管理の管理ポータル](http://aka.ms/mmdportal)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-120">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span> 
2.  <span data-ttu-id="8e0ac-121">**在庫**の下には、**アプリケーション**を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-121">Under **Inventory**, select **Apps**.</span></span>
3.  <span data-ttu-id="8e0ac-122">アプリケーション ・ ワークロードの**追加**を] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-122">In the Apps workload, select **Add**.</span></span>
4.  <span data-ttu-id="8e0ac-123">**追加のアプリケーション**では、**基幹業務アプリケーション**または**Windows アプリケーション (Win32) のプレビュー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32) - preview**.</span></span>
    - <span data-ttu-id="8e0ac-124">**基幹業務アプリケーション**を選択した場合の追加、および基幹業務アプリケーションを構成する方法について[Microsoft Intune に Windows の基幹業務アプリケーションの追加](https://docs.microsoft.com/intune/lob-apps-windows)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="8e0ac-125">**Windows アプリケーション (Win32) のプレビュー**を選択した場合を追加して、Windows アプリケーションを構成する手順の[Win32 アプリケーションの管理](https://docs.microsoft.com/intune/apps-win32-app-management)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-125">If you selected **Windows app (Win32) - preview**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="8e0ac-126">ビジネス アプリケーション用の Microsoft ストア</span><span class="sxs-lookup"><span data-stu-id="8e0ac-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="8e0ac-p104">ビジネス向けのマイクロソフト ストアにサインアップしていない場合は、アプリを買いに行くとき署名できます。アプリがある場合は後、は、Microsoft の管理されたデスクトップと同期できます。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-p104">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps. After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="8e0ac-129">**ビジネスのマイクロソフト ストアからアプリケーションを購入するには**</span><span class="sxs-lookup"><span data-stu-id="8e0ac-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="8e0ac-130">ビジネス管理者のアカウントに、マイクロソフトのストアを使用して[ビジネスのためのマイクロソフト ストア](https://businessstore.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="8e0ac-131">**ショップ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="8e0ac-132">検索を使用して、必要なアプリケーションを検索して、アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="8e0ac-p105">製品詳細については、**アプリケーションを取得する**を選択します。マイクロソフト ストアでは、組織の**製品の & サービス**にアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-p105">On the product details, select **Get the App**. Microsoft Store adds the app to **Products & services** for your organization.</span></span>

<span data-ttu-id="8e0ac-135">**Intune とビジネス向けのマイクロソフト ストア間で同期を強制するには**</span><span class="sxs-lookup"><span data-stu-id="8e0ac-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="8e0ac-136">テナントの Intune 管理者またはグローバル管理者として[Azure ポータル](https://portal.azure.com/)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="8e0ac-p106">**サービス _gt Intune のすべて**を選択します。Intune は、監視と管理のセクションです。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-p106">Select **All services > Intune**. Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="8e0ac-139">Intune ウィンドウは、**クライアント アプリケーション**を選択し、**ビジネス向けのマイクロソフト ストア**を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="8e0ac-140">Intune でのビジネス アプリケーションで、Microsoft ストアを同期する**を有効にする**を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="8e0ac-141">いない場合、記号と関連付け、Microsoft の格納 Intune とビジネス アカウント</span><span class="sxs-lookup"><span data-stu-id="8e0ac-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="8e0ac-142">Intune コンソールにビジネス向けのマイクロソフト ストアからのアプリが表示されます言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="8e0ac-143">Intune でのビジネス アプリケーションで、Microsoft ストアを同期する**同期**を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="8e0ac-144">ビジネス向けのマイクロソフト ストアと Intune の間で同期がアクティブであることを確認 (次の手順)。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="8e0ac-145">**Intune とビジネス向けのマイクロソフト ストア間で同期がアクティブであることを確認するのには**</span><span class="sxs-lookup"><span data-stu-id="8e0ac-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="8e0ac-146">ビジネス管理者のアカウントに、マイクロソフトのストアを使用して[ビジネスのためのマイクロソフト ストア](https://businessstore.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="8e0ac-147">**管理**を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-147">Select **Manage**.</span></span>
3. <span data-ttu-id="8e0ac-148">**設定**を選択し、**整列**を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="8e0ac-149">[**管理ツール**] には、Intune が表示されていることと、状態が**アクティブ**であるを確認します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="8e0ac-150">Azure AD グループを作成する手順 2。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="8e0ac-p107">各アプリケーションの 3 つの Azure AD グループを作成します。この表は、グループする必要があります (使用可能な必要な場合、およびアンインストール) します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-p107">Create three Azure AD groups for each app. This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="8e0ac-153">アプリケーションの割り当ての種類</span><span class="sxs-lookup"><span data-stu-id="8e0ac-153">App assignment type</span></span> |   <span data-ttu-id="8e0ac-154">グループの使用</span><span class="sxs-lookup"><span data-stu-id="8e0ac-154">Group use</span></span>   | <span data-ttu-id="8e0ac-155">Azure AD の例の名前</span><span class="sxs-lookup"><span data-stu-id="8e0ac-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="8e0ac-156">使用可能</span><span class="sxs-lookup"><span data-stu-id="8e0ac-156">Available</span></span> |  <span data-ttu-id="8e0ac-157">アプリケーションは企業ポータル アプリケーションまたは web サイトから利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="8e0ac-158">MMD:*アプリケーション名*: 利用可能</span><span class="sxs-lookup"><span data-stu-id="8e0ac-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="8e0ac-159">必須</span><span class="sxs-lookup"><span data-stu-id="8e0ac-159">Required</span></span> |  <span data-ttu-id="8e0ac-160">アプリケーションは、選択したグループ内のデバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="8e0ac-161">MMD:*アプリケーション名*: 必須</span><span class="sxs-lookup"><span data-stu-id="8e0ac-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="8e0ac-162">[アンインストール]</span><span class="sxs-lookup"><span data-stu-id="8e0ac-162">Uninstall</span></span> |  <span data-ttu-id="8e0ac-163">単位のアプリケーションは、選択したグループ内のデバイスからアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-163">TThe app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="8e0ac-164">MMD:*アプリケーション名*: アンインストール</span><span class="sxs-lookup"><span data-stu-id="8e0ac-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="8e0ac-165">アプリケーションの利用を行う、アプリケーションをインストールするか、管理されたデスクトップの Microsoft デバイスからアプリケーションを削除するこれらのグループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="8e0ac-166">手順 3: アプリケーションをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="8e0ac-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="8e0ac-167">**ユーザーにアプリケーションを割り当てるには**</span><span class="sxs-lookup"><span data-stu-id="8e0ac-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="8e0ac-168">[マイクロソフト デスクトップ管理の管理ポータル](http://aka.ms/mmdportal)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-168">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="8e0ac-169">デスクトップの管理ウィンドウで、**アプリケーション**を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="8e0ac-170">アプリケーションの作業負荷でアプリケーションをユーザーに割り当てるし、**ユーザー グループの割り当て**を選択するを選択します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="8e0ac-171">特定のアプリケーションでは、割り当ての種類 (利用可能な必要な場合、アンインストール) を選択し、適切なグループを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="8e0ac-172">割り当てるアプリケーション ウィンドウで、 **[ok]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e0ac-172">In the Assign Apps pane, select **OK**.</span></span>

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