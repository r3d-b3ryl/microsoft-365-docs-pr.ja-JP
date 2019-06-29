---
title: Microsoft マネージドデスクトップで構成可能な設定を展開する
description: Microsoft マネージドデスクトップで構成の構成変更を展開し、追跡します。
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント、展開、段階的展開、構成可能な設定
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: bfa769cab9f8d812fa2533232f66b0d4f8a4edb7
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390514"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="68d88-104">構成可能な設定を展開および追跡する-Microsoft マネージドデスクトップ</span><span class="sxs-lookup"><span data-stu-id="68d88-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="68d88-105">設定カテゴリを変更し、展開をステージした後、[展開の状態] ページで、グループへの設定の展開を開始できます。</span><span class="sxs-lookup"><span data-stu-id="68d88-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="68d88-106">このページには、各構成可能な設定の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="68d88-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="68d88-107">[設定] カテゴリを開くと、設定をグループに展開し、これらの展開の進行状況を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="68d88-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="68d88-108">展開の状態</span><span class="sxs-lookup"><span data-stu-id="68d88-108">Deployment statuses</span></span> 

<span data-ttu-id="68d88-109">これらの statues は、展開ごとに表示されます。</span><span class="sxs-lookup"><span data-stu-id="68d88-109">These are the statues you’ll see for each deployment.</span></span>

<span data-ttu-id="68d88-110">状態</span><span class="sxs-lookup"><span data-stu-id="68d88-110">Status</span></span>  | <span data-ttu-id="68d88-111">説明</span><span class="sxs-lookup"><span data-stu-id="68d88-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="68d88-112">展開</span><span class="sxs-lookup"><span data-stu-id="68d88-112">Deploy</span></span> | <span data-ttu-id="68d88-113">変更は、このグループへの展開を待機しています。</span><span class="sxs-lookup"><span data-stu-id="68d88-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="68d88-114">処理中</span><span class="sxs-lookup"><span data-stu-id="68d88-114">In progress</span></span> | <span data-ttu-id="68d88-115">このグループ内のアクティブなデバイスに変更が適用されています。</span><span class="sxs-lookup"><span data-stu-id="68d88-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="68d88-116">完了</span><span class="sxs-lookup"><span data-stu-id="68d88-116">Complete</span></span> | <span data-ttu-id="68d88-117">このグループ内のすべてのアクティブなデバイスで変更が完了しました。</span><span class="sxs-lookup"><span data-stu-id="68d88-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="68d88-118">Failed</span><span class="sxs-lookup"><span data-stu-id="68d88-118">Failed</span></span> | <span data-ttu-id="68d88-119">グループ内のアクティブなデバイスの 10% で変更が失敗したため、展開が停止されました。</span><span class="sxs-lookup"><span data-stu-id="68d88-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="68d88-120">展開のトラブルシューティングを行うために、サポート要求が Microsoft マネージドデスクトップ操作を使用して自動的に開かれます。</span><span class="sxs-lookup"><span data-stu-id="68d88-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="68d88-121">復帰</span><span class="sxs-lookup"><span data-stu-id="68d88-121">Reverted</span></span> | <span data-ttu-id="68d88-122">変更は、すべての展開グループに正常に展開された最後の変更に戻されました。</span><span class="sxs-lookup"><span data-stu-id="68d88-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="68d88-123">変更を展開する</span><span class="sxs-lookup"><span data-stu-id="68d88-123">Deploy changes</span></span>

<span data-ttu-id="68d88-124">これらの手順にデスクトップの背景画像が表示されます。</span><span class="sxs-lookup"><span data-stu-id="68d88-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="68d88-125">展開をステージングした後、[展開の状態] ページから変更を展開します。</span><span class="sxs-lookup"><span data-stu-id="68d88-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="68d88-126">**変更を展開するには**</span><span class="sxs-lookup"><span data-stu-id="68d88-126">**To deploy changes**</span></span>

1. <span data-ttu-id="68d88-127">[Microsoft Managed Desktop 管理ポータル](http://aka.ms/mwaasportal)にサインインする</span><span class="sxs-lookup"><span data-stu-id="68d88-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="68d88-128">[**設定**] で、[**構成可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d88-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="68d88-129">[**展開状態**] ワークスペースで、展開する設定を選択し、展開する段階的展開を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d88-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="68d88-130">展開グループのいずれかに変更を展開するには、[**展開**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d88-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

![構成可能な設定の展開状態の概要](images/deploy-cs-overview.png)

<span data-ttu-id="68d88-132">Microsoft マネージドデスクトップでは、次の順序で展開グループへの展開が推奨されます。テスト、ファースト、Fast、および広範。</span><span class="sxs-lookup"><span data-stu-id="68d88-132">Microsoft Managed Desktop recommends deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="68d88-133">各グループで変更が完了すると、状態が [**完了**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="68d88-133">When changes complete in each group, the status changes to **Complete**.</span></span>

![構成可能な設定の展開の完了](images/config-setting-complete.png)

## <a name="revert-deployment"></a><span data-ttu-id="68d88-135">展開を元に戻す</span><span class="sxs-lookup"><span data-stu-id="68d88-135">Revert deployment</span></span>

<span data-ttu-id="68d88-136">変更を展開した後、**展開状態**から元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="68d88-136">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="68d88-137">**進行**中または**完了**した変更を元に戻すと、現在の展開は停止します。</span><span class="sxs-lookup"><span data-stu-id="68d88-137">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="68d88-138">この設定は、すべてのグループに展開された最新のバージョンに戻ります。</span><span class="sxs-lookup"><span data-stu-id="68d88-138">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="68d88-139">デスクトップの背景画像を使用して変更を元に戻す手順を示します。</span><span class="sxs-lookup"><span data-stu-id="68d88-139">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="68d88-140">**変更を元に戻すには**</span><span class="sxs-lookup"><span data-stu-id="68d88-140">**To revert a change**</span></span>
1. <span data-ttu-id="68d88-141">[Microsoft Managed Desktop 管理ポータル](http://aka.ms/mwaasportal)にサインインする</span><span class="sxs-lookup"><span data-stu-id="68d88-141">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="68d88-142">[**設定**] で、[**構成可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d88-142">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="68d88-143">[**展開状態**] ワークスペースで、元に戻す設定を選択してから、元に戻す段階的な展開を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d88-143">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="68d88-144">**この変更を元に戻す必要がある**場合は、[**展開を元に戻す**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d88-144">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![構成可能な設定の展開の復元](images/config-setting-revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="68d88-146">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="68d88-146">Additional resources</span></span>
- [<span data-ttu-id="68d88-147">構成可能な設定の概要</span><span class="sxs-lookup"><span data-stu-id="68d88-147">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="68d88-148">構成可能な設定のリファレンス</span><span class="sxs-lookup"><span data-stu-id="68d88-148">Configurable settings reference</span></span>](config-setting-ref.md) 
