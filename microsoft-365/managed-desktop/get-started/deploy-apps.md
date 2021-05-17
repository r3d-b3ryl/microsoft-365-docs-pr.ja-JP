---
title: アプリをデバイスに展開する
description: アプリをデバイスに追加および展開Microsoft マネージド デスクトップ。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント、アプリ、line-of-business アプリ、LOB アプリ
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8bfc53d46bdcb91c16e9f4a1ddbc8ab3f6dfb47e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922028"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="ddf7f-104">アプリをデバイスに展開する</span><span class="sxs-lookup"><span data-stu-id="ddf7f-104">Deploy apps to devices</span></span>
<span data-ttu-id="ddf7f-105">アプリのオンボーディングのMicrosoft マネージド デスクトップユーザーのデバイスへのアプリの追加と展開が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="ddf7f-106">アプリ ポータルを使用Microsoft マネージド デスクトップ、アプリを追加して展開できます。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="ddf7f-107">全体的なプロセスは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="ddf7f-108">[アプリを Microsoft マネージド デスクトップ](#1)ポータルに追加する - 既存の業務用 (LOB) アプリ、または Intune と同期した ビジネス向け Microsoft Store のアプリを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="ddf7f-109">[アプリAzure Active Directory (AD)](#2)グループを作成する - これらのグループを使用してアプリの割り当てを管理します。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="ddf7f-110">アプリをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="ddf7f-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="ddf7f-111">手順 1: アプリをポータルにMicrosoft マネージド デスクトップする</span><span class="sxs-lookup"><span data-stu-id="ddf7f-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="ddf7f-112">[Win32 を追加したり、MSI](#lob-apps)ベースのWindowsを追加したり、ビジネス向け Microsoft Store アプリMicrosoft マネージド デスクトップを追加したり、Microsoft マネージド デスクトップ デバイスに展開したりできます。 [](#msfb-apps)</span><span class="sxs-lookup"><span data-stu-id="ddf7f-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="ddf7f-113">Win32 Windows MSI ベースのアプリをインストールMicrosoft マネージド デスクトップ</span><span class="sxs-lookup"><span data-stu-id="ddf7f-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="ddf7f-114">ビジネスライン (LOB) アプリをポータルに追加Microsoft マネージド デスクトップできます。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="ddf7f-115">デバイスにインストールされているアプリの要件については、「Microsoft マネージド デスクトップ要件[」を参照Microsoft マネージド デスクトップしてください](../service-description/mmd-app-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>

<span data-ttu-id="ddf7f-116">この手順では、追加するアプリの種類を選択し、アプリ ソースを構成してアップロードします。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="ddf7f-117">**LOB アプリまたはアプリを WindowsポータルにMicrosoft マネージド デスクトップするには**</span><span class="sxs-lookup"><span data-stu-id="ddf7f-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="ddf7f-118">ポータルにサインインするかMicrosoft マネージド デスクトップ Intune にサインインして、ポータルを検索Microsoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="ddf7f-119">ポータルへのサインインをMicrosoft マネージド デスクトップします。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="ddf7f-120">管理者ポータルに[サインインMicrosoft マネージド デスクトップします](https://aka.ms/mmdportal)。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="ddf7f-121">[インベントリ **] で**、[アプリ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-121">Under **Inventory**, select **Apps**.</span></span>
3.    <span data-ttu-id="ddf7f-122">[アプリ] ワークロードで、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-122">In the Apps workload, select **Add**.</span></span>
4.    <span data-ttu-id="ddf7f-123">[**アプリの追加]** で **、[Line-of-business アプリ**] または [アプリWindows **(Win32) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32)**.</span></span>
    - <span data-ttu-id="ddf7f-124">[Line-of-business app] を選択した場合は、「Windows **line-of-business** アプリを [Microsoft Intune](/intune/lob-apps-windows)に追加して構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="ddf7f-125">アプリ **(Win32) Windows選択** した場合は [、「Win32](/intune/apps-win32-app-management)アプリの管理」を参照して、アプリの追加と構成Windowsしてください。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-125">If you selected **Windows app (Win32)**, see [Win32 app management](/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="ddf7f-126">ビジネス向け Microsoft Storeアプリ</span><span class="sxs-lookup"><span data-stu-id="ddf7f-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="ddf7f-127">アプリにサインアップしていないビジネス向け Microsoft Store、アプリを購入するときにサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="ddf7f-128">アプリを作成した後、アプリとアプリを同期Microsoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="ddf7f-129">**アプリをアプリから購入ビジネス向け Microsoft Store**</span><span class="sxs-lookup"><span data-stu-id="ddf7f-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="ddf7f-130">管理者アカウントで[ビジネス向け Microsoft Store](https://businessstore.microsoft.com)サインインビジネス向け Microsoft Storeします。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="ddf7f-131">[自分 **のグループのショップ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="ddf7f-132">検索を使用して、目的のアプリを検索し、アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="ddf7f-133">製品の詳細で、[アプリの取得 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="ddf7f-134">Microsoft Store、組織の **製品にアプリ** を追加します。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="ddf7f-135">**Intune とデバイス間の同期を強制的に行ビジネス向け Microsoft Store**</span><span class="sxs-lookup"><span data-stu-id="ddf7f-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="ddf7f-136">管理者センターに[サインインMicrosoft エンドポイント マネージャーします](https://go.microsoft.com/fwlink/?linkid=2109431)。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-136">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>
2. <span data-ttu-id="ddf7f-137">[**テナント管理**  >  **コネクタとトークン] を**  >  **選択** ビジネス向け Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-137">Select **Tenant administration** > **Connectors and tokens** > **Microsoft Store for Business**.</span></span>
3. <span data-ttu-id="ddf7f-138">[**同期]** を選択して、アプリから購入したアプリを Intune Microsoft Store取得します。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-138">Select **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

<span data-ttu-id="ddf7f-139">**Intune とデバイス間の同期がアクティブビジネス向け Microsoft Storeするには**</span><span class="sxs-lookup"><span data-stu-id="ddf7f-139">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="ddf7f-140">管理者アカウントで[ビジネス向け Microsoft Store](https://businessstore.microsoft.com)サインインビジネス向け Microsoft Storeします。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-140">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="ddf7f-141">[管理 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-141">Select **Manage**.</span></span>
3. <span data-ttu-id="ddf7f-142">[配布 **設定] を** 選択し、[配布] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-142">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="ddf7f-143">[ **管理ツール]** で、Intune が一覧に表示され、状態が [アクティブ] である必要 **があります**。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-143">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="ddf7f-144">手順 2: Azure ADグループを作成する</span><span class="sxs-lookup"><span data-stu-id="ddf7f-144">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="ddf7f-145">アプリごとに 3 つの Azure ADグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-145">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="ddf7f-146">次の表に、必要なグループ (利用可能、必須、アンインストール) の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-146">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="ddf7f-147">アプリの割り当ての種類</span><span class="sxs-lookup"><span data-stu-id="ddf7f-147">App assignment type</span></span> |    <span data-ttu-id="ddf7f-148">グループの使用</span><span class="sxs-lookup"><span data-stu-id="ddf7f-148">Group use</span></span>    | <span data-ttu-id="ddf7f-149">Azure の名前AD例</span><span class="sxs-lookup"><span data-stu-id="ddf7f-149">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="ddf7f-150">Available</span><span class="sxs-lookup"><span data-stu-id="ddf7f-150">Available</span></span> |  <span data-ttu-id="ddf7f-151">アプリは、アプリまたは web サイトポータル サイト利用できます。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-151">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="ddf7f-152">MMD – *アプリ名* – 使用可能</span><span class="sxs-lookup"><span data-stu-id="ddf7f-152">MMD – *app name* – Available</span></span>
<span data-ttu-id="ddf7f-153">必須</span><span class="sxs-lookup"><span data-stu-id="ddf7f-153">Required</span></span> |  <span data-ttu-id="ddf7f-154">アプリは、選択したグループ内のデバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-154">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="ddf7f-155">MMD – *アプリ名* – 必須</span><span class="sxs-lookup"><span data-stu-id="ddf7f-155">MMD – *app name* – Required</span></span>
<span data-ttu-id="ddf7f-156">アンインストール</span><span class="sxs-lookup"><span data-stu-id="ddf7f-156">Uninstall</span></span> |  <span data-ttu-id="ddf7f-157">アプリは、選択したグループ内のデバイスからアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-157">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="ddf7f-158">MMD – *アプリ名* – アンインストール</span><span class="sxs-lookup"><span data-stu-id="ddf7f-158">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="ddf7f-159">これらのグループにユーザーを追加して、アプリを利用可能にするか、アプリをインストールするか、アプリをデバイスから削除Microsoft マネージド デスクトップします。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-159">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="ddf7f-160">手順 3: ユーザーにアプリを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ddf7f-160">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="ddf7f-161">**アプリをユーザーに割り当てるには**</span><span class="sxs-lookup"><span data-stu-id="ddf7f-161">**To assign the app to your users**</span></span>

1. <span data-ttu-id="ddf7f-162">管理者ポータルに[サインインMicrosoft マネージド デスクトップします](https://aka.ms/mmdportal)。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-162">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="ddf7f-163">[管理デスクトップ] ウィンドウで、[アプリ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-163">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="ddf7f-164">[アプリ] ワークロードで、ユーザーを割り当てるアプリを選択し、[ユーザー グループの割り当て **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-164">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="ddf7f-165">特定のアプリで、割り当ての種類 (利用可能、必須、アンインストール) を選択し、適切なグループを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-165">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="ddf7f-166">[アプリの割り当て] ウィンドウで **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ddf7f-166">In the Assign Apps pane, select **OK**.</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="ddf7f-167">データの使用を開始するMicrosoft マネージド デスクトップ</span><span class="sxs-lookup"><span data-stu-id="ddf7f-167">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="ddf7f-168">管理ポータルで管理者の連絡先を追加および確認する</span><span class="sxs-lookup"><span data-stu-id="ddf7f-168">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="ddf7f-169">条件付きアクセスを調整する</span><span class="sxs-lookup"><span data-stu-id="ddf7f-169">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="ddf7f-170">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ddf7f-170">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="ddf7f-171">Intune 会社ポータルを展開する</span><span class="sxs-lookup"><span data-stu-id="ddf7f-171">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="ddf7f-172">Enterprise State Roaming を有効にする</span><span class="sxs-lookup"><span data-stu-id="ddf7f-172">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="ddf7f-173">デバイスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="ddf7f-173">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="ddf7f-174">ユーザーがデバイスを使えるようにする</span><span class="sxs-lookup"><span data-stu-id="ddf7f-174">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="ddf7f-175">アプリの展開 (このトピック)</span><span class="sxs-lookup"><span data-stu-id="ddf7f-175">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->