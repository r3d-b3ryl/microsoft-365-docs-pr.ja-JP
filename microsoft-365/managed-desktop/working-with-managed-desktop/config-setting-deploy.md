---
title: Microsoft マネージドデスクトップで構成可能な設定を展開する
description: Microsoft マネージドデスクトップで構成の構成変更を展開し、追跡します。
keywords: microsoft マネージドデスクトップ、microsoft 365、サービス、ドキュメント、展開、段階的展開、構成可能な設定
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/12/2019
ms.openlocfilehash: fd0e0750332fa8f650cfc4756f8eb108be2a71df
ms.sourcegitcommit: 59bc66eaa2575bad8ecb34d45b1172cda23a729b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "30051128"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="9b96d-104">構成可能な設定を展開および追跡する-Microsoft マネージドデスクトップ</span><span class="sxs-lookup"><span data-stu-id="9b96d-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="9b96d-p101">設定カテゴリを変更し、展開をステージすると、展開の状態に応じて展開の進行状況を展開し、追跡することができます。このページには、各構成可能な設定の概要が表示されます。[設定] カテゴリを開き、各展開とその詳細を表示して、変更を展開します。</span><span class="sxs-lookup"><span data-stu-id="9b96d-p101">After you make changes to your setting categories and stage a deployment, you can deploy and track progress for the deployment on Deployment status. This page shows a summary of each configurable setting. Open a setting category to see each deployment and their details, to deploy the changes.</span></span> 

## <a name="deployment-statuses"></a><span data-ttu-id="9b96d-108">展開の状態</span><span class="sxs-lookup"><span data-stu-id="9b96d-108">Deployment statuses</span></span> 

<span data-ttu-id="9b96d-109">これらの statues は、展開ごとに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b96d-109">These are the statues you’ll see for each deployment.</span></span>

<span data-ttu-id="9b96d-110">状態</span><span class="sxs-lookup"><span data-stu-id="9b96d-110">Status</span></span>  | <span data-ttu-id="9b96d-111">説明</span><span class="sxs-lookup"><span data-stu-id="9b96d-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="9b96d-112">展開</span><span class="sxs-lookup"><span data-stu-id="9b96d-112">Deploy</span></span> | <span data-ttu-id="9b96d-113">変更は、このリングへの展開を待機しています。</span><span class="sxs-lookup"><span data-stu-id="9b96d-113">Your change is waiting to be deployed to this ring.</span></span>
<span data-ttu-id="9b96d-114">進行中</span><span class="sxs-lookup"><span data-stu-id="9b96d-114">In progress</span></span> | <span data-ttu-id="9b96d-115">このリングのデバイスに変更が適用されています。</span><span class="sxs-lookup"><span data-stu-id="9b96d-115">The change is being applied to devices in this ring.</span></span> 
<span data-ttu-id="9b96d-116">完全</span><span class="sxs-lookup"><span data-stu-id="9b96d-116">Complete</span></span> | <span data-ttu-id="9b96d-117">このリングのデバイスに変更が適用されています。</span><span class="sxs-lookup"><span data-stu-id="9b96d-117">The change is being applied to devices in this ring.</span></span> 
<span data-ttu-id="9b96d-118">Failed</span><span class="sxs-lookup"><span data-stu-id="9b96d-118">Failed</span></span> | <span data-ttu-id="9b96d-119">この変更は、着信が停止されたため、リング内のデバイスの 10% で失敗しました。</span><span class="sxs-lookup"><span data-stu-id="9b96d-119">The change failed on a 10 percent of devices in the ring, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="9b96d-120">展開のトラブルシューティングを行うために、サポート要求が Microsoft マネージドデスクトップ操作を使用して自動的に開かれます。</span><span class="sxs-lookup"><span data-stu-id="9b96d-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="9b96d-121">復帰</span><span class="sxs-lookup"><span data-stu-id="9b96d-121">Reverted</span></span> | <span data-ttu-id="9b96d-122">変更は、すべての展開リングに正常に展開された最後の変更に戻されました。</span><span class="sxs-lookup"><span data-stu-id="9b96d-122">The change was reverted to the last change that was successfully deployed to all deployment rings.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="9b96d-123">変更を展開する</span><span class="sxs-lookup"><span data-stu-id="9b96d-123">Deploy changes</span></span>

<span data-ttu-id="9b96d-p102">これらの手順にデスクトップの背景画像が表示されます。展開をステージングした後、展開状態から変更を展開します。</span><span class="sxs-lookup"><span data-stu-id="9b96d-p102">We’ll show Desktop background picture in these instructions. After you’ve staged a deployment, you deploy changes from Deployment status.</span></span> 

<span data-ttu-id="9b96d-126">**変更を展開するには**</span><span class="sxs-lookup"><span data-stu-id="9b96d-126">**To deploy changes**</span></span>

1. <span data-ttu-id="9b96d-127">[Microsoft Managed Desktop 管理ポータル](http://aka.ms/mwaasportal)にサインインする</span><span class="sxs-lookup"><span data-stu-id="9b96d-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="9b96d-128">[**設定**] で、[**構成可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b96d-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="9b96d-129">[**展開状態**] ワークスペースで、展開する設定を選択し、展開する段階的展開を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b96d-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="9b96d-130">展開リングのいずれかに変更を展開するには、[**展開**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b96d-130">Select **Deploy** to deploy the change to one of the deployment rings.</span></span>

![構成可能な設定の展開状態の概要](images/deploy-cs-overview.png)

<span data-ttu-id="9b96d-132">Microsoft マネージドデスクトップでは、次の順序で展開リングに展開することをお勧めします。 Test、First、Fast、および広範。</span><span class="sxs-lookup"><span data-stu-id="9b96d-132">Microsoft Managed Desktop recommends deploying to deployment rings in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="9b96d-133">各リングで変更が完了すると、状態は [**完了**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="9b96d-133">When changes complete in each ring, the status changes to **Complete**.</span></span>

![構成可能な設定の展開の完了](images/config-setting-complete.png)

## <a name="revert-deployment"></a><span data-ttu-id="9b96d-135">展開を元に戻す</span><span class="sxs-lookup"><span data-stu-id="9b96d-135">Revert deployment</span></span>

<span data-ttu-id="9b96d-136">これらの手順にデスクトップの背景画像が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b96d-136">We’ll show Desktop background picture in these instructions.</span></span> 

<span data-ttu-id="9b96d-p103">変更を展開した後、**展開状態**から元に戻すことができます。**進行**中または**完了**した変更を元に戻すと、現在の展開は停止します。この設定は、すべてのリングに展開された最新のバージョンに戻ります。</span><span class="sxs-lookup"><span data-stu-id="9b96d-p103">After you’ve deployed a change, you can revert from **Deployment status**. When you revert a change that is **In progress** or **Complete**, the current deployment stops. The setting will revert to the last version that was deployed to all rings.</span></span> 

<span data-ttu-id="9b96d-140">**変更を元に戻すには**</span><span class="sxs-lookup"><span data-stu-id="9b96d-140">**To revert a change**</span></span>
1. <span data-ttu-id="9b96d-141">[Microsoft Managed Desktop 管理ポータル](http://aka.ms/mwaasportal)にサインインする</span><span class="sxs-lookup"><span data-stu-id="9b96d-141">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="9b96d-142">[**設定**] で、[**構成可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b96d-142">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="9b96d-143">[**展開状態**] ワークスペースで、元に戻す設定を選択してから、元に戻す段階的な展開を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b96d-143">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="9b96d-144">**この変更を元に戻す必要がある**場合は、[**展開を元に戻す**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b96d-144">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![構成可能な設定の展開の復元](images/config-setting-revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="9b96d-146">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="9b96d-146">Additional resources</span></span>
- [<span data-ttu-id="9b96d-147">構成可能な設定の概要</span><span class="sxs-lookup"><span data-stu-id="9b96d-147">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="9b96d-148">構成可能な設定のリファレンス</span><span class="sxs-lookup"><span data-stu-id="9b96d-148">Configurable settings reference</span></span>](config-setting-ref.md) 