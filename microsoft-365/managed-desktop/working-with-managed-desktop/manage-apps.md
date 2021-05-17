---
title: Microsoft Managed Desktop でアプリを管理する
description: Microsoft Managed Desktop デバイスに展開されている業務用アプリを更新する方法について説明します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1a6b91ab5b4523f4b980dab0c25af41a9d614189
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600684"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="03813-104">Microsoft マネージド デスクトップでの基幹業務アプリの管理</span><span class="sxs-lookup"><span data-stu-id="03813-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="03813-105">Microsoft Managed Desktop にオンボードし、Microsoft Managed Desktop デバイスに展開したアプリのアプリ更新プログラムを管理するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="03813-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="03813-106">アプリの更新は、Microsoft Managed Desktop ポータルまたは Intune で行います。</span><span class="sxs-lookup"><span data-stu-id="03813-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="03813-107">Microsoft Managed Desktop で業務用アプリを更新する</span><span class="sxs-lookup"><span data-stu-id="03813-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="03813-108">**Microsoft Managed Desktop ポータルで業務用アプリを更新するには**</span><span class="sxs-lookup"><span data-stu-id="03813-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="03813-109">[Microsoft Managed Desktop Admin ポータルにサインインします](https://aka.ms/mmdportal)。</span><span class="sxs-lookup"><span data-stu-id="03813-109">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="03813-110">[インベントリ **] で**、[アプリ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="03813-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="03813-111">更新するアプリを選択し、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="03813-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="03813-112">[管理 **] で**、[プロパティ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="03813-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="03813-113">[ **アプリ パッケージ ファイル] を** クリックし、新しいアプリ パッケージ ファイルをアップロードするために参照します。</span><span class="sxs-lookup"><span data-stu-id="03813-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="03813-114">[アプリ **パッケージ ファイル] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="03813-114">Select **App package file**.</span></span>
7. <span data-ttu-id="03813-115">フォルダー アイコンを選択し、更新されたアプリ ファイルの場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="03813-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="03813-116">[**開く**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="03813-116">Select **Open**.</span></span> <span data-ttu-id="03813-117">アプリ情報はパッケージ情報で更新されます。</span><span class="sxs-lookup"><span data-stu-id="03813-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="03813-118">アプリの **バージョンに更新** されたアプリ パッケージが反映されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="03813-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="03813-119">更新されたアプリは、ユーザーのデバイスに展開されます。</span><span class="sxs-lookup"><span data-stu-id="03813-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="03813-120">Intune で業務用アプリを更新する</span><span class="sxs-lookup"><span data-stu-id="03813-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="03813-121">**Intune で業務用アプリを更新するには**</span><span class="sxs-lookup"><span data-stu-id="03813-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="03813-122">Azure portal に [サインインします](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="03813-122">Sign in to [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="03813-123">[すべての **サービス]**  >  **Intune を選択します**。</span><span class="sxs-lookup"><span data-stu-id="03813-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="03813-124">Intune は [監視と管理 **] セクションに** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="03813-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="03813-125">[クライアント **アプリとアプリ] >選択します**。</span><span class="sxs-lookup"><span data-stu-id="03813-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="03813-126">アプリの一覧でアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="03813-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="03813-127">[概要] **ブレードで** 、[プロパティ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="03813-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="03813-128">[アプリ **パッケージ ファイル] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="03813-128">Select **App package file**.</span></span>
7. <span data-ttu-id="03813-129">フォルダー アイコンを選択し、更新されたアプリ ファイルの場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="03813-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="03813-130">[**開く**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="03813-130">Select **Open**.</span></span> <span data-ttu-id="03813-131">アプリ情報はパッケージ情報で更新されます。</span><span class="sxs-lookup"><span data-stu-id="03813-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="03813-132">アプリの **バージョンに更新** されたアプリ パッケージが反映されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="03813-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="03813-133">アプリを以前のバージョンにロールバックする</span><span class="sxs-lookup"><span data-stu-id="03813-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="03813-134">新しいバージョンのアプリを展開するときにエラーが見つかった場合は、以前のバージョンにロールバックできます。</span><span class="sxs-lookup"><span data-stu-id="03813-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="03813-135">ここで説明するプロセスは **、Windows MSI line-of-business** アプリまたは Windows アプリ **(Win 32) - プレビュー** として種類が一覧表示されるアプリ向けです。</span><span class="sxs-lookup"><span data-stu-id="03813-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="03813-136">**line-of-business アプリを以前のバージョンにロールバックするには**</span><span class="sxs-lookup"><span data-stu-id="03813-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="03813-137">[Microsoft Managed Desktop Admin ポータルにサインインします](https://aka.ms/mmdportal)。</span><span class="sxs-lookup"><span data-stu-id="03813-137">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="03813-138">[インベントリ **] で**、[アプリ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="03813-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="03813-139">ロールバックする必要があるアプリを選択し、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="03813-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="03813-140">[管理 **] で**、[プロパティ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="03813-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="03813-141">**Windows MSI line-of-business** アプリアプリの場合は、[アプリ情報] を選択し、[アプリのバージョンを無視する] で、[はい] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="03813-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="03813-142">**Windows アプリ (Win 32) の場合は**、アプリをプレビューし、[アプリ情報] を選択し、[検出ルール] を選択し、[追加] を **選択します**。 </span><span class="sxs-lookup"><span data-stu-id="03813-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="03813-143">MSI ルールがある場合は、MSI **製品の** バージョン チェックが [いいえ] **に設定されています**。</span><span class="sxs-lookup"><span data-stu-id="03813-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="03813-144">[以前のバージョンのアプリ ソース ファイルを](../get-started/deploy-apps.md) Microsoft Managed Desktop Admin ポータルにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="03813-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

