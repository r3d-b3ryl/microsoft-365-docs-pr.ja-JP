---
title: Microsoft マネージドデスクトップで構成可能な設定を展開する
description: Microsoft マネージドデスクトップで構成の構成変更を展開し、追跡します。
keywords: microsoft マネージドデスクトップ、microsoft 365、サービス、ドキュメント、展開、段階的展開、構成可能な設定
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4662373b926d07558ecedd05c9dfcf472ceb6357
ms.sourcegitcommit: d38c0ce846bac19e876a03a59ed4f268c7bae389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30900286"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="0a2a1-104">構成可能な設定を展開および追跡する-Microsoft マネージドデスクトップ</span><span class="sxs-lookup"><span data-stu-id="0a2a1-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="0a2a1-105">設定カテゴリを変更し、展開をステージした後、[展開の状態] ページで、グループへの設定の展開を開始できます。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="0a2a1-106">このページには、各構成可能な設定の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="0a2a1-107">[設定] カテゴリを開くと、設定をグループに展開し、これらの展開の進行状況を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="0a2a1-108">展開の状態</span><span class="sxs-lookup"><span data-stu-id="0a2a1-108">Deployment statuses</span></span> 

<span data-ttu-id="0a2a1-109">これらの statues は、展開ごとに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-109">These are the statues you’ll see for each deployment.</span></span>

<span data-ttu-id="0a2a1-110">状態</span><span class="sxs-lookup"><span data-stu-id="0a2a1-110">Status</span></span>  | <span data-ttu-id="0a2a1-111">説明</span><span class="sxs-lookup"><span data-stu-id="0a2a1-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="0a2a1-112">展開</span><span class="sxs-lookup"><span data-stu-id="0a2a1-112">Deploy</span></span> | <span data-ttu-id="0a2a1-113">変更は、このグループへの展開を待機しています。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="0a2a1-114">処理中</span><span class="sxs-lookup"><span data-stu-id="0a2a1-114">In progress</span></span> | <span data-ttu-id="0a2a1-115">このグループ内のアクティブなデバイスに変更が適用されています。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="0a2a1-116">完了</span><span class="sxs-lookup"><span data-stu-id="0a2a1-116">Complete</span></span> | <span data-ttu-id="0a2a1-117">このグループ内のすべてのアクティブなデバイスで変更が完了しました。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="0a2a1-118">Failed</span><span class="sxs-lookup"><span data-stu-id="0a2a1-118">Failed</span></span> | <span data-ttu-id="0a2a1-119">グループ内のアクティブなデバイスの 10% で変更が失敗したため、展開が停止されました。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="0a2a1-120">展開のトラブルシューティングを行うために、サポート要求が Microsoft マネージドデスクトップ操作を使用して自動的に開かれます。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="0a2a1-121">復帰</span><span class="sxs-lookup"><span data-stu-id="0a2a1-121">Reverted</span></span> | <span data-ttu-id="0a2a1-122">変更は、すべての展開グループに正常に展開された最後の変更に戻されました。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="0a2a1-123">変更を展開する</span><span class="sxs-lookup"><span data-stu-id="0a2a1-123">Deploy changes</span></span>

<span data-ttu-id="0a2a1-124">これらの手順にデスクトップの背景画像が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="0a2a1-125">展開をステージングした後、[展開の状態] ページから変更を展開します。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="0a2a1-126">**変更を展開するには**</span><span class="sxs-lookup"><span data-stu-id="0a2a1-126">**To deploy changes**</span></span>

1. <span data-ttu-id="0a2a1-127">[Microsoft Managed Desktop 管理ポータル](http://aka.ms/mwaasportal)にサインインする</span><span class="sxs-lookup"><span data-stu-id="0a2a1-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="0a2a1-128">[**設定**] で、[**構成可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="0a2a1-129">[**展開状態**] ワークスペースで、展開する設定を選択し、展開する段階的展開を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="0a2a1-130">展開グループのいずれかに変更を展開するには、[**展開**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

![構成可能な設定の展開状態の概要](images/deploy-cs-overview.png)

<span data-ttu-id="0a2a1-132">Microsoft マネージドデスクトップでは、次の順序で展開グループへの展開が推奨されます。テスト、ファースト、Fast、および広範。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-132">Microsoft Managed Desktop recommends deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="0a2a1-133">各グループで変更が完了すると、状態が [**完了**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-133">When changes complete in each group, the status changes to **Complete**.</span></span>

![構成可能な設定の展開の完了](images/config-setting-complete.png)

## <a name="revert-deployment"></a><span data-ttu-id="0a2a1-135">展開を元に戻す</span><span class="sxs-lookup"><span data-stu-id="0a2a1-135">Revert deployment</span></span>

<span data-ttu-id="0a2a1-136">変更を展開した後、**展開状態**から元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-136">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="0a2a1-137">**進行**中または**完了**した変更を元に戻すと、現在の展開は停止します。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-137">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="0a2a1-138">この設定は、すべてのグループに展開された最新のバージョンに戻ります。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-138">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="0a2a1-139">デスクトップの背景画像を使用して変更を元に戻す手順を示します。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-139">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="0a2a1-140">**変更を元に戻すには**</span><span class="sxs-lookup"><span data-stu-id="0a2a1-140">**To revert a change**</span></span>
1. <span data-ttu-id="0a2a1-141">[Microsoft Managed Desktop 管理ポータル](http://aka.ms/mwaasportal)にサインインする</span><span class="sxs-lookup"><span data-stu-id="0a2a1-141">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="0a2a1-142">[**設定**] で、[**構成可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-142">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="0a2a1-143">[**展開状態**] ワークスペースで、元に戻す設定を選択してから、元に戻す段階的な展開を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-143">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="0a2a1-144">**この変更を元に戻す必要がある**場合は、[**展開を元に戻す**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a2a1-144">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![構成可能な設定の展開の復元](images/config-setting-revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="0a2a1-146">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="0a2a1-146">Additional resources</span></span>
- [<span data-ttu-id="0a2a1-147">構成可能な設定の概要</span><span class="sxs-lookup"><span data-stu-id="0a2a1-147">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="0a2a1-148">構成可能な設定のリファレンス</span><span class="sxs-lookup"><span data-stu-id="0a2a1-148">Configurable settings reference</span></span>](config-setting-ref.md) 
