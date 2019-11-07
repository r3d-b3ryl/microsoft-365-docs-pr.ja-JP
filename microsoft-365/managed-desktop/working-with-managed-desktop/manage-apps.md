---
title: Microsoft マネージドデスクトップでのアプリの管理
description: Microsoft マネージドデスクトップデバイスに展開されている基幹業務アプリを更新する方法に関する情報
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 425ba674ca9911e4c93bda4fc9ad61cec7fb85b7
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012412"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="5973f-104">Microsoft マネージドデスクトップで基幹業務アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="5973f-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="5973f-105">Microsoft マネージドデスクトップに利用したアプリのアプリの更新を管理するには、いくつかの方法があります。また、Microsoft マネージドデスクトップデバイスに展開されています。</span><span class="sxs-lookup"><span data-stu-id="5973f-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="5973f-106">Microsoft 管理デスクトップポータルまたは Intune でアプリの更新を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5973f-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="5973f-107">Microsoft マネージドデスクトップで基幹業務アプリを更新する</span><span class="sxs-lookup"><span data-stu-id="5973f-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="5973f-108">**Microsoft マネージドデスクトップポータルで基幹業務アプリを更新するには**</span><span class="sxs-lookup"><span data-stu-id="5973f-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="5973f-109">[Microsoft Managed Desktop 管理ポータル](https://aka.ms/mmdportal)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="5973f-109">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="5973f-110">[**インベントリ**] で、[**アプリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5973f-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="5973f-111">更新するアプリを選択し、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5973f-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="5973f-112">[**管理**] で、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5973f-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="5973f-113">[**アプリパッケージファイル**] をクリックし、新しいアプリパッケージファイルを参照してアップロードします。</span><span class="sxs-lookup"><span data-stu-id="5973f-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="5973f-114">[**アプリパッケージファイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5973f-114">Select **App package file**.</span></span>
7. <span data-ttu-id="5973f-115">フォルダーアイコンを選択し、更新されたアプリファイルの場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="5973f-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="5973f-116">[**開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5973f-116">Select **Open**.</span></span> <span data-ttu-id="5973f-117">アプリ情報がパッケージ情報で更新されます。</span><span class="sxs-lookup"><span data-stu-id="5973f-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="5973f-118">アプリの**バージョン**が更新されたアプリパッケージを反映していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5973f-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="5973f-119">更新したアプリは、ユーザーのデバイスに展開されます。</span><span class="sxs-lookup"><span data-stu-id="5973f-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="5973f-120">Intune で基幹業務アプリを更新する</span><span class="sxs-lookup"><span data-stu-id="5973f-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="5973f-121">**Intune で基幹業務アプリを更新するには**</span><span class="sxs-lookup"><span data-stu-id="5973f-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="5973f-122">[Azure portal](https://azure.portal.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="5973f-122">Sign in to [Azure portal](https://azure.portal.com).</span></span>
2. <span data-ttu-id="5973f-123">[**すべてのサービス** > ]**Intune**を選択します。</span><span class="sxs-lookup"><span data-stu-id="5973f-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="5973f-124">Intune は、[**監視 + 管理**] セクションにあります。</span><span class="sxs-lookup"><span data-stu-id="5973f-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="5973f-125">[**クライアントアプリ > アプリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5973f-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="5973f-126">アプリの一覧でアプリを見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="5973f-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="5973f-127">**概要**ブレードで、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5973f-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="5973f-128">[**アプリパッケージファイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5973f-128">Select **App package file**.</span></span>
7. <span data-ttu-id="5973f-129">フォルダーアイコンを選択し、更新されたアプリファイルの場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="5973f-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="5973f-130">[**開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5973f-130">Select **Open**.</span></span> <span data-ttu-id="5973f-131">アプリ情報がパッケージ情報で更新されます。</span><span class="sxs-lookup"><span data-stu-id="5973f-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="5973f-132">アプリの**バージョン**が更新されたアプリパッケージを反映していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5973f-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="5973f-133">アプリを以前のバージョンにロールバックする</span><span class="sxs-lookup"><span data-stu-id="5973f-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="5973f-134">新しいバージョンのアプリを展開したときにエラーが検出された場合は、以前のバージョンにロールバックできます。</span><span class="sxs-lookup"><span data-stu-id="5973f-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="5973f-135">ここで説明するプロセスは、種類が**WINDOWS MSI 基幹業務アプリ**または windows アプリとしてリストされているアプリ **(Win 32) です。**</span><span class="sxs-lookup"><span data-stu-id="5973f-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="5973f-136">**基幹業務アプリを以前のバージョンにロールバックするには**</span><span class="sxs-lookup"><span data-stu-id="5973f-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="5973f-137">[Microsoft Managed Desktop 管理ポータル](https://aka.ms/mmdportal)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="5973f-137">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="5973f-138">[**インベントリ**] で、[**アプリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5973f-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="5973f-139">ロールバックする必要のあるアプリを選択し、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5973f-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="5973f-140">[**管理**] で、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5973f-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="5973f-141">**WINDOWS MSI 基幹業務アプリ**アプリの場合は、[**アプリ情報**] を選択し、[**アプリのバージョンを無視**する] で [**はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5973f-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="5973f-142">**Windows アプリの場合 (Win 32)-** アプリのプレビューを表示するには、[**アプリ情報**] を選択し、[**検出ルール**] を選択してから [**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5973f-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="5973f-143">MSI ルールがある場合は、[ **msi 製品バージョン] チェック**が [**いいえ**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5973f-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="5973f-144">[以前のバージョンのアプリソースファイル](../get-started/deploy-apps.md)を Microsoft Managed Desktop 管理ポータルにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="5973f-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

