---
title: 構成可能な設定を展開Microsoft マネージド デスクトップ
description: 構成可能な設定の変更を展開し、Microsoft マネージド デスクトップ。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント、展開、ステージ展開、構成可能な設定
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: aad4995f9c329b0fd8fcbcc8b1d13379453c2a76
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287802"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="8a46f-104">構成可能な設定の展開と追跡 - Microsoft マネージド デスクトップ</span><span class="sxs-lookup"><span data-stu-id="8a46f-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="8a46f-105">設定カテゴリに変更を加え、展開をステージした後、[展開状態] ページでは、グループへの設定の展開を開始できます。</span><span class="sxs-lookup"><span data-stu-id="8a46f-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="8a46f-106">このページには、構成可能な各設定の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a46f-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="8a46f-107">設定カテゴリを開いて、グループに設定を展開し、これらの展開の進行状況を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="8a46f-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="8a46f-108">展開の状態</span><span class="sxs-lookup"><span data-stu-id="8a46f-108">Deployment statuses</span></span>

<span data-ttu-id="8a46f-109">これらは、展開ごとに表示される状態です。</span><span class="sxs-lookup"><span data-stu-id="8a46f-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="8a46f-110">状態</span><span class="sxs-lookup"><span data-stu-id="8a46f-110">Status</span></span> | <span data-ttu-id="8a46f-111">説明</span><span class="sxs-lookup"><span data-stu-id="8a46f-111">Explanation</span></span>
--- | ---
<span data-ttu-id="8a46f-112">展開</span><span class="sxs-lookup"><span data-stu-id="8a46f-112">Deploy</span></span> | <span data-ttu-id="8a46f-113">変更がこのグループに展開されるのを待っています。</span><span class="sxs-lookup"><span data-stu-id="8a46f-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="8a46f-114">処理中</span><span class="sxs-lookup"><span data-stu-id="8a46f-114">In progress</span></span> | <span data-ttu-id="8a46f-115">変更は、このグループのアクティブ なデバイスに適用されています。</span><span class="sxs-lookup"><span data-stu-id="8a46f-115">The change is being applied to active devices in this group.</span></span>
<span data-ttu-id="8a46f-116">完了</span><span class="sxs-lookup"><span data-stu-id="8a46f-116">Complete</span></span> | <span data-ttu-id="8a46f-117">このグループ内のすべてのアクティブ なデバイスで変更が完了しました。</span><span class="sxs-lookup"><span data-stu-id="8a46f-117">The change completed on all active devices in this group.</span></span>
<span data-ttu-id="8a46f-118">失敗</span><span class="sxs-lookup"><span data-stu-id="8a46f-118">Failed</span></span> | <span data-ttu-id="8a46f-119">グループ内のアクティブ デバイスの 10% で変更が失敗し、展開が停止しました。</span><span class="sxs-lookup"><span data-stu-id="8a46f-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="8a46f-120">サポート要求は、展開のトラブルシューティングを行うMicrosoft マネージド デスクトップ操作で自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="8a46f-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span>
<span data-ttu-id="8a46f-121">元に戻す</span><span class="sxs-lookup"><span data-stu-id="8a46f-121">Reverted</span></span> | <span data-ttu-id="8a46f-122">この変更は、すべての展開グループに正常に展開された最後の変更に戻されました。</span><span class="sxs-lookup"><span data-stu-id="8a46f-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="8a46f-123">変更の展開</span><span class="sxs-lookup"><span data-stu-id="8a46f-123">Deploy changes</span></span>

<span data-ttu-id="8a46f-124">これらの手順では、デスクトップの背景画像を表示します。</span><span class="sxs-lookup"><span data-stu-id="8a46f-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="8a46f-125">展開をステージした後、[展開の状態] ページから変更を展開します。</span><span class="sxs-lookup"><span data-stu-id="8a46f-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span>

<span data-ttu-id="8a46f-126">**変更を展開するには**</span><span class="sxs-lookup"><span data-stu-id="8a46f-126">**To deploy changes**</span></span>

1. <span data-ttu-id="8a46f-127">サインインして [デバイス [Microsoft エンドポイント マネージャー]](https://endpoint.microsoft.com/)メニュー **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="8a46f-127">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="8a46f-128">[ファイル] セクションを探Microsoft マネージド デスクトップ、次を選択 **設定。**</span><span class="sxs-lookup"><span data-stu-id="8a46f-128">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="8a46f-129">[ **展開状態]** ワークスペースで、展開する設定を選択し、展開するステージ展開を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a46f-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="8a46f-130">[ **展開] を** 選択して、変更を展開グループの 1 つに展開します。</span><span class="sxs-lookup"><span data-stu-id="8a46f-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE]
> <span data-ttu-id="8a46f-131">オレンジ色の注意アイコンは、展開に使用できる以前のグループが用意されているのを示します。順番にロールアウトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a46f-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

<span data-ttu-id="8a46f-132">この順序で展開グループに展開することをお勧めします。Test、First、Fast、次に Broad。</span><span class="sxs-lookup"><span data-stu-id="8a46f-132">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="8a46f-133">各グループの変更が完了すると、状態は [完了] に **変わります**。</span><span class="sxs-lookup"><span data-stu-id="8a46f-133">When changes complete in each group, the status changes to **Complete**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a><span data-ttu-id="8a46f-134">展開を元に戻す</span><span class="sxs-lookup"><span data-stu-id="8a46f-134">Revert deployment</span></span>

<span data-ttu-id="8a46f-135">変更を展開した後、展開の状態から **元に戻します**。</span><span class="sxs-lookup"><span data-stu-id="8a46f-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="8a46f-136">[進行中] または [完了] **の変更を** 元に戻 **す** 場合、現在の展開は停止します。</span><span class="sxs-lookup"><span data-stu-id="8a46f-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="8a46f-137">この設定は、すべてのグループに展開された最後のバージョンに戻されます。</span><span class="sxs-lookup"><span data-stu-id="8a46f-137">The setting will revert to the last version that was deployed to all groups.</span></span>

<span data-ttu-id="8a46f-138">例として、デスクトップの背景画像を使用して変更を元に戻す手順を示します。</span><span class="sxs-lookup"><span data-stu-id="8a46f-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="8a46f-139">**変更を元に戻すには**</span><span class="sxs-lookup"><span data-stu-id="8a46f-139">**To revert a change**</span></span>

1. <span data-ttu-id="8a46f-140">サインインして [デバイス [Microsoft エンドポイント マネージャー]](https://endpoint.microsoft.com/)メニュー **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="8a46f-140">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="8a46f-141">[ファイル] セクションを探Microsoft マネージド デスクトップ、次を選択 **設定。**</span><span class="sxs-lookup"><span data-stu-id="8a46f-141">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="8a46f-142">[ **展開状態]** ワークスペースで、元に戻す設定を選択し、元に戻すステージ展開を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a46f-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="8a46f-143">[ **この変更を元に戻す必要がある] で、[** 展開を元に **戻す] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8a46f-143">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a><span data-ttu-id="8a46f-144">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="8a46f-144">Additional resources</span></span>

- [<span data-ttu-id="8a46f-145">構成可能な設定の概要</span><span class="sxs-lookup"><span data-stu-id="8a46f-145">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="8a46f-146">構成可能な設定のリファレンス</span><span class="sxs-lookup"><span data-stu-id="8a46f-146">Configurable settings reference</span></span>](config-setting-ref.md) 
