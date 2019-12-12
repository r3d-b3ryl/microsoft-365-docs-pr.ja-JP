---
title: Microsoft マネージドデスクトップで構成可能な設定を展開する
description: Microsoft マネージドデスクトップで構成の構成変更を展開し、追跡します。
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント、展開、段階的展開、構成可能な設定
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 244070c7fd2d5c98f87990bcb4ef6de96ca5a90c
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962244"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="b8f53-104">構成可能な設定を展開および追跡する-Microsoft マネージドデスクトップ</span><span class="sxs-lookup"><span data-stu-id="b8f53-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="b8f53-105">設定カテゴリを変更し、展開をステージした後、[展開の状態] ページで、グループへの設定の展開を開始できます。</span><span class="sxs-lookup"><span data-stu-id="b8f53-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="b8f53-106">このページには、各構成可能な設定の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b8f53-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="b8f53-107">[設定] カテゴリを開くと、設定をグループに展開し、これらの展開の進行状況を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="b8f53-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="b8f53-108">展開の状態</span><span class="sxs-lookup"><span data-stu-id="b8f53-108">Deployment statuses</span></span> 

<span data-ttu-id="b8f53-109">展開ごとに表示される状態を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b8f53-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="b8f53-110">状態</span><span class="sxs-lookup"><span data-stu-id="b8f53-110">Status</span></span>  | <span data-ttu-id="b8f53-111">説明</span><span class="sxs-lookup"><span data-stu-id="b8f53-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="b8f53-112">展開</span><span class="sxs-lookup"><span data-stu-id="b8f53-112">Deploy</span></span> | <span data-ttu-id="b8f53-113">変更は、このグループへの展開を待機しています。</span><span class="sxs-lookup"><span data-stu-id="b8f53-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="b8f53-114">処理中</span><span class="sxs-lookup"><span data-stu-id="b8f53-114">In progress</span></span> | <span data-ttu-id="b8f53-115">このグループ内のアクティブなデバイスに変更が適用されています。</span><span class="sxs-lookup"><span data-stu-id="b8f53-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="b8f53-116">完了</span><span class="sxs-lookup"><span data-stu-id="b8f53-116">Complete</span></span> | <span data-ttu-id="b8f53-117">このグループ内のすべてのアクティブなデバイスで変更が完了しました。</span><span class="sxs-lookup"><span data-stu-id="b8f53-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="b8f53-118">失敗</span><span class="sxs-lookup"><span data-stu-id="b8f53-118">Failed</span></span> | <span data-ttu-id="b8f53-119">グループ内のアクティブなデバイスの10% で変更が失敗したため、展開が停止されました。</span><span class="sxs-lookup"><span data-stu-id="b8f53-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="b8f53-120">展開のトラブルシューティングを行うために、サポート要求が Microsoft マネージドデスクトップ操作を使用して自動的に開かれます。</span><span class="sxs-lookup"><span data-stu-id="b8f53-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="b8f53-121">復帰</span><span class="sxs-lookup"><span data-stu-id="b8f53-121">Reverted</span></span> | <span data-ttu-id="b8f53-122">変更は、すべての展開グループに正常に展開された最後の変更に戻されました。</span><span class="sxs-lookup"><span data-stu-id="b8f53-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="b8f53-123">変更を展開する</span><span class="sxs-lookup"><span data-stu-id="b8f53-123">Deploy changes</span></span>

<span data-ttu-id="b8f53-124">これらの手順にデスクトップの背景画像が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b8f53-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="b8f53-125">展開をステージングした後、[展開の状態] ページから変更を展開します。</span><span class="sxs-lookup"><span data-stu-id="b8f53-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="b8f53-126">**変更を展開するには**</span><span class="sxs-lookup"><span data-stu-id="b8f53-126">**To deploy changes**</span></span>

1. <span data-ttu-id="b8f53-127">[Microsoft Managed Desktop 管理ポータル](https://aka.ms/mwaasportal)にサインインする</span><span class="sxs-lookup"><span data-stu-id="b8f53-127">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="b8f53-128">[**設定**] で、[**構成可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8f53-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="b8f53-129">[**展開状態**] ワークスペースで、展開する設定を選択し、展開する段階的展開を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8f53-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="b8f53-130">展開グループのいずれかに変更を展開するには、[**展開**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8f53-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

<span data-ttu-id="b8f53-131">![展開状態ワークスペース。</span><span class="sxs-lookup"><span data-stu-id="b8f53-131">![Deployment status workspace.</span></span> <span data-ttu-id="b8f53-132">右側の [信頼済みサイト] ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="b8f53-132">Trusted sites pane on the right.</span></span> <span data-ttu-id="b8f53-133">[展開グループ] セクションには、[展開グループ]、[デバイス]、[状態] の3つの列があります。</span><span class="sxs-lookup"><span data-stu-id="b8f53-133">In the Deployment groups section are three columns: deployment groups, devices, and status.</span></span> <span data-ttu-id="b8f53-134">[状態] 列の [展開] が強調表示されています。](images/1deployedit.png)</span><span class="sxs-lookup"><span data-stu-id="b8f53-134">In the status column, "deploy" is highlighted.](images/1deployedit.png)</span></span>
<span data-ttu-id="b8f53-135">展開グループへの展開は、次の順序で行うことをお勧めします。 Test、First、Fast、および広義です。</span><span class="sxs-lookup"><span data-stu-id="b8f53-135">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="b8f53-136">各グループで変更が完了すると、状態が [**完了**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="b8f53-136">When changes complete in each group, the status changes to **Complete**.</span></span>

![更新日、バージョン、テスト、最初、高速、および広範な列を含む展開状態ワークスペース。](images/2completeedit.png)

## <a name="revert-deployment"></a><span data-ttu-id="b8f53-139">展開を元に戻す</span><span class="sxs-lookup"><span data-stu-id="b8f53-139">Revert deployment</span></span>

<span data-ttu-id="b8f53-140">変更を展開した後、**展開状態**から元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="b8f53-140">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="b8f53-141">**進行**中または**完了**した変更を元に戻すと、現在の展開は停止します。</span><span class="sxs-lookup"><span data-stu-id="b8f53-141">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="b8f53-142">この設定は、すべてのグループに展開された最新のバージョンに戻ります。</span><span class="sxs-lookup"><span data-stu-id="b8f53-142">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="b8f53-143">デスクトップの背景画像を使用して変更を元に戻す手順を示します。</span><span class="sxs-lookup"><span data-stu-id="b8f53-143">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="b8f53-144">**変更を元に戻すには**</span><span class="sxs-lookup"><span data-stu-id="b8f53-144">**To revert a change**</span></span>
1. <span data-ttu-id="b8f53-145">[Microsoft Managed Desktop 管理ポータル](https://aka.ms/mwaasportal)にサインインする</span><span class="sxs-lookup"><span data-stu-id="b8f53-145">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="b8f53-146">[**設定**] で、[**構成可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8f53-146">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="b8f53-147">[**展開状態**] ワークスペースで、元に戻す設定を選択してから、元に戻す段階的な展開を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8f53-147">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="b8f53-148">[**この変更を元に戻す必要がありますか?**] で、[**展開の取り消し**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8f53-148">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

![展開状態ワークスペース。](images/3revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="b8f53-152">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="b8f53-152">Additional resources</span></span>
- [<span data-ttu-id="b8f53-153">構成可能な設定の概要</span><span class="sxs-lookup"><span data-stu-id="b8f53-153">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="b8f53-154">構成可能な設定のリファレンス</span><span class="sxs-lookup"><span data-stu-id="b8f53-154">Configurable settings reference</span></span>](config-setting-ref.md) 
