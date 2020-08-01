---
title: アプリをデバイスに展開する
description: Microsoft マネージドデスクトップデバイスへのアプリの追加および展開に関する情報。
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント、アプリ、基幹業務アプリ、LOB アプリ
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 6d35ee7a4a7755a043136f33600abad424956032
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529399"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="28e2c-104">アプリをデバイスに展開する</span><span class="sxs-lookup"><span data-stu-id="28e2c-104">Deploy apps to devices</span></span>
<span data-ttu-id="28e2c-105">Microsoft Managed Desktop へのオンボードの一部には、ユーザーのデバイスへのアプリの追加と展開が含まれます。</span><span class="sxs-lookup"><span data-stu-id="28e2c-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="28e2c-106">Microsoft マネージドデスクトップポータルを使用している場合は、アプリを追加して展開することができます。</span><span class="sxs-lookup"><span data-stu-id="28e2c-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="28e2c-107">全体的なプロセスは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="28e2c-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="28e2c-108">[Microsoft マネージドデスクトップポータルへのアプリの追加](#1)-既存の基幹業務 (LOB) アプリ、または Intune と同期したビジネス向け Microsoft Store のアプリにすることができます。</span><span class="sxs-lookup"><span data-stu-id="28e2c-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="28e2c-109">[アプリの割り当て用に Azure Active Directory (AD) グループを作成](#2)する-これらのグループを使用して、アプリの割り当てを管理します。</span><span class="sxs-lookup"><span data-stu-id="28e2c-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="28e2c-110">ユーザーにアプリを割り当てる</span><span class="sxs-lookup"><span data-stu-id="28e2c-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="28e2c-111">手順 1: Microsoft マネージドデスクトップポータルにアプリを追加する</span><span class="sxs-lookup"><span data-stu-id="28e2c-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="28e2c-112">Microsoft マネージドデスクトップには、 [Win32、WINDOWS MSI ベースのアプリ](#lob-apps)、または[Microsoft Store for Business アプリ](#msfb-apps)を追加し、それを microsoft マネージドデスクトップデバイスに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="28e2c-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="28e2c-113">Microsoft マネージドデスクトップへの Win32 または Windows MSI ベースのアプリ</span><span class="sxs-lookup"><span data-stu-id="28e2c-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="28e2c-114">基幹業務 (LOB) アプリを Microsoft マネージドデスクトップポータルに追加できます。</span><span class="sxs-lookup"><span data-stu-id="28e2c-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="28e2c-115">Microsoft マネージドデスクトップデバイスにインストールされているアプリの要件の詳細については、「 [Microsoft Managed desktop app の要件](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28e2c-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="28e2c-116">この手順では、追加するアプリの種類を選択してから、アプリソースを構成およびアップロードします。</span><span class="sxs-lookup"><span data-stu-id="28e2c-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="28e2c-117">**LOB アプリまたは Windows アプリを Microsoft マネージドデスクトップポータルに追加するには**</span><span class="sxs-lookup"><span data-stu-id="28e2c-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="28e2c-118">Microsoft マネージドデスクトップポータルにサインインするか、Intune にサインインして、Microsoft Managed Desktop を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="28e2c-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="28e2c-119">Microsoft マネージドデスクトップポータルへのサインインを表示します。</span><span class="sxs-lookup"><span data-stu-id="28e2c-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="28e2c-120">[Microsoft Managed Desktop 管理ポータル](https://aka.ms/mmdportal)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="28e2c-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="28e2c-121">[**インベントリ**] で、[**アプリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="28e2c-121">Under **Inventory**, select **Apps**.</span></span>
3.    <span data-ttu-id="28e2c-122">[アプリのワークロード] で、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="28e2c-122">In the Apps workload, select **Add**.</span></span>
4.    <span data-ttu-id="28e2c-123">[**アプリの追加**] で、[**基幹業務アプリ**] または [ **Windows アプリ (Win32)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="28e2c-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32)**.</span></span>
    - <span data-ttu-id="28e2c-124">基幹**業務アプリ**を選択した場合は、基幹業務アプリを追加して構成する手順については、「 [Windows の基幹業務アプリを Microsoft Intune に追加](https://docs.microsoft.com/intune/lob-apps-windows)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28e2c-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="28e2c-125">**Windows アプリ (win32)** を選択した場合は、「 [win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) 」を参照してください。 windows アプリの追加および構成に関する指示については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28e2c-125">If you selected **Windows app (Win32)**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="28e2c-126">ビジネス向け Microsoft Store アプリ</span><span class="sxs-lookup"><span data-stu-id="28e2c-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="28e2c-127">Microsoft Store for Business にサインアップしていない場合は、アプリの購入時にサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="28e2c-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="28e2c-128">アプリを用意したら、それらを Microsoft マネージドデスクトップと同期することができます。</span><span class="sxs-lookup"><span data-stu-id="28e2c-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="28e2c-129">**ビジネス向け Microsoft Store からアプリを購入するには**</span><span class="sxs-lookup"><span data-stu-id="28e2c-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="28e2c-130">Business 管理者アカウントの Microsoft Store を使用して、 [Microsoft store For business](https://businessstore.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="28e2c-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="28e2c-131">[**自分のグループのショッピング**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="28e2c-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="28e2c-132">検索を使用して目的のアプリを見つけ、アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="28e2c-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="28e2c-133">[製品の詳細] で、[**アプリの取得**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="28e2c-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="28e2c-134">Microsoft Store では、組織の**製品**にアプリが追加されます。</span><span class="sxs-lookup"><span data-stu-id="28e2c-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="28e2c-135">**ビジネス向けに Intune と Microsoft Store 間の同期を強制するには**</span><span class="sxs-lookup"><span data-stu-id="28e2c-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="28e2c-136">テナントのために Intune 管理者またはグローバル管理者として[Azure portal](https://portal.azure.com/)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="28e2c-136">Sign in to [Azure portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="28e2c-137">[**すべてのサービス > Intune**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="28e2c-137">Select **All services > Intune**.</span></span> <span data-ttu-id="28e2c-138">Intune は、[監視 + 管理] セクションにあります。</span><span class="sxs-lookup"><span data-stu-id="28e2c-138">Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="28e2c-139">[Intune] ウィンドウで、[**クライアントアプリ**] を選択し、[**ビジネス向け Microsoft Store**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="28e2c-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="28e2c-140">[**有効**] を選択して、Microsoft Store for Business アプリを Intune と同期します。</span><span class="sxs-lookup"><span data-stu-id="28e2c-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="28e2c-141">まだ登録していない場合は、Microsoft Store for Business アカウントを Intune に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="28e2c-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="28e2c-142">Intune コンソールに Microsoft Store for Business のアプリが表示される言語を選択します</span><span class="sxs-lookup"><span data-stu-id="28e2c-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="28e2c-143">Microsoft Store for Business アプリを Intune と同期するには、[**同期**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="28e2c-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="28e2c-144">Microsoft Store for Business と Intune の間の同期がアクティブであることを確認します (次の手順)。</span><span class="sxs-lookup"><span data-stu-id="28e2c-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="28e2c-145">**Intune と Microsoft Store for Business の同期がアクティブであることを確認するには**</span><span class="sxs-lookup"><span data-stu-id="28e2c-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="28e2c-146">Business 管理者アカウントの Microsoft Store を使用して、 [Microsoft store For business](https://businessstore.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="28e2c-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="28e2c-147">[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="28e2c-147">Select **Manage**.</span></span>
3. <span data-ttu-id="28e2c-148">[**設定**] を選択し、[**配布**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="28e2c-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="28e2c-149">[**管理ツール**] で、Intune が表示され、状態が [**アクティブ**] になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="28e2c-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="28e2c-150">手順 2: Azure AD グループを作成する</span><span class="sxs-lookup"><span data-stu-id="28e2c-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="28e2c-151">アプリごとに3つの Azure AD グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="28e2c-151">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="28e2c-152">次の表に、必要なグループ (利用可能、必要、およびアンインストール) の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="28e2c-152">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="28e2c-153">アプリの割り当ての種類</span><span class="sxs-lookup"><span data-stu-id="28e2c-153">App assignment type</span></span> |    <span data-ttu-id="28e2c-154">グループの使用</span><span class="sxs-lookup"><span data-stu-id="28e2c-154">Group use</span></span>    | <span data-ttu-id="28e2c-155">Azure AD 名の例</span><span class="sxs-lookup"><span data-stu-id="28e2c-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="28e2c-156">Available</span><span class="sxs-lookup"><span data-stu-id="28e2c-156">Available</span></span> |  <span data-ttu-id="28e2c-157">アプリは、会社のポータルアプリまたは web サイトから入手できます。</span><span class="sxs-lookup"><span data-stu-id="28e2c-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="28e2c-158">MMD –*アプリ名*–利用可能</span><span class="sxs-lookup"><span data-stu-id="28e2c-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="28e2c-159">必須</span><span class="sxs-lookup"><span data-stu-id="28e2c-159">Required</span></span> |  <span data-ttu-id="28e2c-160">アプリは、選択したグループのデバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="28e2c-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="28e2c-161">MMD –*アプリ名*–必須</span><span class="sxs-lookup"><span data-stu-id="28e2c-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="28e2c-162">Uninstall</span><span class="sxs-lookup"><span data-stu-id="28e2c-162">Uninstall</span></span> |  <span data-ttu-id="28e2c-163">選択したグループのデバイスからアプリがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="28e2c-163">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="28e2c-164">MMD –*アプリ名*–アンインストール</span><span class="sxs-lookup"><span data-stu-id="28e2c-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="28e2c-165">これらのグループにユーザーを追加して、アプリを利用できるようにするか、アプリをインストールするか、Microsoft マネージドデスクトップデバイスからアプリを削除します。</span><span class="sxs-lookup"><span data-stu-id="28e2c-165">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="28e2c-166">手順 3: ユーザーにアプリを割り当てる</span><span class="sxs-lookup"><span data-stu-id="28e2c-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="28e2c-167">**アプリをユーザーに割り当てるには**</span><span class="sxs-lookup"><span data-stu-id="28e2c-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="28e2c-168">[Microsoft Managed Desktop 管理ポータル](https://aka.ms/mmdportal)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="28e2c-168">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="28e2c-169">[管理されたデスクトップ] ウィンドウで、[**アプリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="28e2c-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="28e2c-170">[アプリのワークロード] で、ユーザーの割り当て先となるアプリを選択し、[**ユーザーグループの割り当て**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="28e2c-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="28e2c-171">特定のアプリについて、割り当ての種類 (利用可能、必須、アンインストール) を選択し、適切なグループを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="28e2c-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="28e2c-172">[アプリの割り当て] ウィンドウで、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="28e2c-172">In the Assign Apps pane, select **OK**.</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="28e2c-173">Microsoft マネージドデスクトップの使用を開始する手順</span><span class="sxs-lookup"><span data-stu-id="28e2c-173">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="28e2c-174">管理ポータルで管理者の連絡先を追加および確認する</span><span class="sxs-lookup"><span data-stu-id="28e2c-174">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="28e2c-175">条件付きアクセスを調整する</span><span class="sxs-lookup"><span data-stu-id="28e2c-175">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="28e2c-176">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="28e2c-176">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="28e2c-177">Intune 会社ポータルを展開する</span><span class="sxs-lookup"><span data-stu-id="28e2c-177">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="28e2c-178">Enterprise State Roaming を有効にする</span><span class="sxs-lookup"><span data-stu-id="28e2c-178">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="28e2c-179">デバイスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="28e2c-179">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="28e2c-180">ユーザーがデバイスを使えるようにする</span><span class="sxs-lookup"><span data-stu-id="28e2c-180">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="28e2c-181">アプリを展開する (このトピック)</span><span class="sxs-lookup"><span data-stu-id="28e2c-181">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
