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
ms.openlocfilehash: 2eb8b984550f301af9d99e738f6db4623aa2cc86
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769108"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="b4c44-104">アプリをデバイスに展開する</span><span class="sxs-lookup"><span data-stu-id="b4c44-104">Deploy apps to devices</span></span>
<span data-ttu-id="b4c44-105">Microsoft Managed Desktop へのオンボードの一部には、ユーザーのデバイスへのアプリの追加と展開が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b4c44-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="b4c44-106">Microsoft マネージドデスクトップポータルを使用している場合は、アプリを追加して展開することができます。</span><span class="sxs-lookup"><span data-stu-id="b4c44-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="b4c44-107">全体的なプロセスは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b4c44-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="b4c44-108">[Microsoft マネージドデスクトップポータルへのアプリの追加](#1) -既存の基幹業務 (LOB) アプリ、または Intune と同期したビジネス向け Microsoft Store のアプリにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b4c44-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="b4c44-109">[アプリの割り当て用に Azure Active Directory (AD) グループを作成](#2) する-これらのグループを使用して、アプリの割り当てを管理します。</span><span class="sxs-lookup"><span data-stu-id="b4c44-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="b4c44-110">ユーザーにアプリを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b4c44-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="b4c44-111">手順 1: Microsoft マネージドデスクトップポータルにアプリを追加する</span><span class="sxs-lookup"><span data-stu-id="b4c44-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="b4c44-112">Microsoft マネージドデスクトップには、 [Win32、WINDOWS MSI ベースのアプリ](#lob-apps)、または [Microsoft Store for Business アプリ](#msfb-apps) を追加し、それを microsoft マネージドデスクトップデバイスに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="b4c44-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="b4c44-113">Microsoft マネージドデスクトップへの Win32 または Windows MSI ベースのアプリ</span><span class="sxs-lookup"><span data-stu-id="b4c44-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="b4c44-114">基幹業務 (LOB) アプリを Microsoft マネージドデスクトップポータルに追加できます。</span><span class="sxs-lookup"><span data-stu-id="b4c44-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="b4c44-115">Microsoft マネージドデスクトップデバイスにインストールされているアプリの要件の詳細については、「 [Microsoft Managed desktop app の要件](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4c44-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="b4c44-116">この手順では、追加するアプリの種類を選択してから、アプリソースを構成およびアップロードします。</span><span class="sxs-lookup"><span data-stu-id="b4c44-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="b4c44-117">**LOB アプリまたは Windows アプリを Microsoft マネージドデスクトップポータルに追加するには**</span><span class="sxs-lookup"><span data-stu-id="b4c44-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="b4c44-118">Microsoft マネージドデスクトップポータルにサインインするか、Intune にサインインして、Microsoft Managed Desktop を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="b4c44-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="b4c44-119">Microsoft マネージドデスクトップポータルへのサインインを表示します。</span><span class="sxs-lookup"><span data-stu-id="b4c44-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="b4c44-120">[Microsoft Managed Desktop 管理ポータル](https://aka.ms/mmdportal)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="b4c44-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="b4c44-121">[ **インベントリ** ] で、[ **アプリ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4c44-121">Under **Inventory** , select **Apps** .</span></span>
3.    <span data-ttu-id="b4c44-122">[アプリのワークロード] で、[ **追加** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4c44-122">In the Apps workload, select **Add** .</span></span>
4.    <span data-ttu-id="b4c44-123">[ **アプリの追加** ] で、[ **基幹業務アプリ** ] または [ **Windows アプリ (Win32)** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4c44-123">In **Add app** , select **Line-of-business app** or **Windows app (Win32)** .</span></span>
    - <span data-ttu-id="b4c44-124">基幹 **業務アプリ** を選択した場合は、基幹業務アプリを追加して構成する手順については、「 [Windows の基幹業務アプリを Microsoft Intune に追加](https://docs.microsoft.com/intune/lob-apps-windows) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4c44-124">If you selected **Line-of-business app** , see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="b4c44-125">**Windows アプリ (win32)** を選択した場合は、「 [win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) 」を参照してください。 windows アプリの追加および構成に関する指示については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4c44-125">If you selected **Windows app (Win32)** , see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="b4c44-126">ビジネス向け Microsoft Store アプリ</span><span class="sxs-lookup"><span data-stu-id="b4c44-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="b4c44-127">Microsoft Store for Business にサインアップしていない場合は、アプリの購入時にサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="b4c44-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="b4c44-128">アプリを用意したら、それらを Microsoft マネージドデスクトップと同期することができます。</span><span class="sxs-lookup"><span data-stu-id="b4c44-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="b4c44-129">**ビジネス向け Microsoft Store からアプリを購入するには**</span><span class="sxs-lookup"><span data-stu-id="b4c44-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="b4c44-130">Business 管理者アカウントの Microsoft Store を使用して、 [Microsoft store For business](https://businessstore.microsoft.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="b4c44-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="b4c44-131">[ **自分のグループのショッピング** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4c44-131">Select **Shop for my group** .</span></span>
3. <span data-ttu-id="b4c44-132">検索を使用して目的のアプリを見つけ、アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="b4c44-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="b4c44-133">[製品の詳細] で、[ **アプリの取得** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4c44-133">On the product details, select **Get the App** .</span></span> <span data-ttu-id="b4c44-134">Microsoft Store では、組織の **製品** にアプリが追加されます。</span><span class="sxs-lookup"><span data-stu-id="b4c44-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="b4c44-135">**ビジネス向けに Intune と Microsoft Store 間の同期を強制するには**</span><span class="sxs-lookup"><span data-stu-id="b4c44-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="b4c44-136">[Microsoft エンドポイントマネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="b4c44-136">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>
2. <span data-ttu-id="b4c44-137">**テナント管理**  >  **コネクタを選択し、**  >  **ビジネス用に Microsoft Store に** トークンを使用します。</span><span class="sxs-lookup"><span data-stu-id="b4c44-137">Select **Tenant administration** > **Connectors and tokens** > **Microsoft Store for Business** .</span></span>
3. <span data-ttu-id="b4c44-138">Microsoft Store から Intune に購入したアプリを取得するには、[ **同期** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4c44-138">Select **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

<span data-ttu-id="b4c44-139">**Intune と Microsoft Store for Business の同期がアクティブであることを確認するには**</span><span class="sxs-lookup"><span data-stu-id="b4c44-139">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="b4c44-140">Business 管理者アカウントの Microsoft Store を使用して、 [Microsoft store For business](https://businessstore.microsoft.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="b4c44-140">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="b4c44-141">[ **管理** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4c44-141">Select **Manage** .</span></span>
3. <span data-ttu-id="b4c44-142">[ **設定** ] を選択し、[ **配布** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4c44-142">Select **Settings** and then select **Distribute** .</span></span>
4. <span data-ttu-id="b4c44-143">[ **管理ツール** ] で、Intune が表示され、状態が [ **アクティブ** ] になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b4c44-143">Under **Management tools** , verify that Intune is listed and that the status is **Active** .</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="b4c44-144">手順 2: Azure AD グループを作成する</span><span class="sxs-lookup"><span data-stu-id="b4c44-144">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="b4c44-145">アプリごとに3つの Azure AD グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="b4c44-145">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="b4c44-146">次の表に、必要なグループ (利用可能、必要、およびアンインストール) の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="b4c44-146">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="b4c44-147">アプリの割り当ての種類</span><span class="sxs-lookup"><span data-stu-id="b4c44-147">App assignment type</span></span> |    <span data-ttu-id="b4c44-148">グループの使用</span><span class="sxs-lookup"><span data-stu-id="b4c44-148">Group use</span></span>    | <span data-ttu-id="b4c44-149">Azure AD 名の例</span><span class="sxs-lookup"><span data-stu-id="b4c44-149">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="b4c44-150">Available</span><span class="sxs-lookup"><span data-stu-id="b4c44-150">Available</span></span> |  <span data-ttu-id="b4c44-151">アプリは、会社のポータルアプリまたは web サイトから入手できます。</span><span class="sxs-lookup"><span data-stu-id="b4c44-151">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="b4c44-152">MMD – *アプリ名* –利用可能</span><span class="sxs-lookup"><span data-stu-id="b4c44-152">MMD – *app name* – Available</span></span>
<span data-ttu-id="b4c44-153">必須</span><span class="sxs-lookup"><span data-stu-id="b4c44-153">Required</span></span> |  <span data-ttu-id="b4c44-154">アプリは、選択したグループのデバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b4c44-154">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="b4c44-155">MMD – *アプリ名* –必須</span><span class="sxs-lookup"><span data-stu-id="b4c44-155">MMD – *app name* – Required</span></span>
<span data-ttu-id="b4c44-156">Uninstall</span><span class="sxs-lookup"><span data-stu-id="b4c44-156">Uninstall</span></span> |  <span data-ttu-id="b4c44-157">選択したグループのデバイスからアプリがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b4c44-157">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="b4c44-158">MMD – *アプリ名* –アンインストール</span><span class="sxs-lookup"><span data-stu-id="b4c44-158">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="b4c44-159">これらのグループにユーザーを追加して、アプリを利用できるようにするか、アプリをインストールするか、Microsoft マネージドデスクトップデバイスからアプリを削除します。</span><span class="sxs-lookup"><span data-stu-id="b4c44-159">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="b4c44-160">手順 3: ユーザーにアプリを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b4c44-160">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="b4c44-161">**アプリをユーザーに割り当てるには**</span><span class="sxs-lookup"><span data-stu-id="b4c44-161">**To assign the app to your users**</span></span>

1. <span data-ttu-id="b4c44-162">[Microsoft Managed Desktop 管理ポータル](https://aka.ms/mmdportal)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="b4c44-162">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="b4c44-163">[管理されたデスクトップ] ウィンドウで、[ **アプリ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4c44-163">In Managed Desktop pane, select **Apps** .</span></span>
3. <span data-ttu-id="b4c44-164">[アプリのワークロード] で、ユーザーの割り当て先となるアプリを選択し、[ **ユーザーグループの割り当て** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4c44-164">In the Apps workload, select the app you want to assign users to and select **Assign users groups** .</span></span>
4. <span data-ttu-id="b4c44-165">特定のアプリについて、割り当ての種類 (利用可能、必須、アンインストール) を選択し、適切なグループを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b4c44-165">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="b4c44-166">[アプリの割り当て] ウィンドウで、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4c44-166">In the Assign Apps pane, select **OK** .</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="b4c44-167">Microsoft マネージドデスクトップの使用を開始する手順</span><span class="sxs-lookup"><span data-stu-id="b4c44-167">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="b4c44-168">管理ポータルで管理者の連絡先を追加および確認する</span><span class="sxs-lookup"><span data-stu-id="b4c44-168">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="b4c44-169">条件付きアクセスを調整する</span><span class="sxs-lookup"><span data-stu-id="b4c44-169">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="b4c44-170">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b4c44-170">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="b4c44-171">Intune 会社ポータルを展開する</span><span class="sxs-lookup"><span data-stu-id="b4c44-171">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="b4c44-172">Enterprise State Roaming を有効にする</span><span class="sxs-lookup"><span data-stu-id="b4c44-172">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="b4c44-173">デバイスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="b4c44-173">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="b4c44-174">ユーザーがデバイスを使えるようにする</span><span class="sxs-lookup"><span data-stu-id="b4c44-174">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="b4c44-175">アプリを展開する (このトピック)</span><span class="sxs-lookup"><span data-stu-id="b4c44-175">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
