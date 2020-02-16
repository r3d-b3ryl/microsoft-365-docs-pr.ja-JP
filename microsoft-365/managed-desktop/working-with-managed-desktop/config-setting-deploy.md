---
title: Microsoft マネージドデスクトップで構成可能な設定を展開する
description: Microsoft マネージドデスクトップで構成の構成変更を展開し、追跡します。
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント、展開、段階的展開、構成可能な設定
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: e6946c138cb6fde15e35374b447038d5c302187e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085765"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="19f33-104">構成可能な設定を展開および追跡する-Microsoft マネージドデスクトップ</span><span class="sxs-lookup"><span data-stu-id="19f33-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="19f33-105">設定カテゴリを変更し、展開をステージした後、[展開の状態] ページで、グループへの設定の展開を開始できます。</span><span class="sxs-lookup"><span data-stu-id="19f33-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="19f33-106">このページには、各構成可能な設定の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="19f33-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="19f33-107">[設定] カテゴリを開くと、設定をグループに展開し、これらの展開の進行状況を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="19f33-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="19f33-108">展開の状態</span><span class="sxs-lookup"><span data-stu-id="19f33-108">Deployment statuses</span></span> 

<span data-ttu-id="19f33-109">展開ごとに表示される状態を次に示します。</span><span class="sxs-lookup"><span data-stu-id="19f33-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="19f33-110">状態</span><span class="sxs-lookup"><span data-stu-id="19f33-110">Status</span></span>  | <span data-ttu-id="19f33-111">説明</span><span class="sxs-lookup"><span data-stu-id="19f33-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="19f33-112">展開</span><span class="sxs-lookup"><span data-stu-id="19f33-112">Deploy</span></span> | <span data-ttu-id="19f33-113">変更は、このグループへの展開を待機しています。</span><span class="sxs-lookup"><span data-stu-id="19f33-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="19f33-114">処理中</span><span class="sxs-lookup"><span data-stu-id="19f33-114">In progress</span></span> | <span data-ttu-id="19f33-115">このグループ内のアクティブなデバイスに変更が適用されています。</span><span class="sxs-lookup"><span data-stu-id="19f33-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="19f33-116">完了</span><span class="sxs-lookup"><span data-stu-id="19f33-116">Complete</span></span> | <span data-ttu-id="19f33-117">このグループ内のすべてのアクティブなデバイスで変更が完了しました。</span><span class="sxs-lookup"><span data-stu-id="19f33-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="19f33-118">Failed</span><span class="sxs-lookup"><span data-stu-id="19f33-118">Failed</span></span> | <span data-ttu-id="19f33-119">グループ内のアクティブなデバイスの10% で変更が失敗したため、展開が停止されました。</span><span class="sxs-lookup"><span data-stu-id="19f33-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="19f33-120">展開のトラブルシューティングを行うために、サポート要求が Microsoft マネージドデスクトップ操作を使用して自動的に開かれます。</span><span class="sxs-lookup"><span data-stu-id="19f33-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="19f33-121">復帰</span><span class="sxs-lookup"><span data-stu-id="19f33-121">Reverted</span></span> | <span data-ttu-id="19f33-122">変更は、すべての展開グループに正常に展開された最後の変更に戻されました。</span><span class="sxs-lookup"><span data-stu-id="19f33-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="19f33-123">変更を展開する</span><span class="sxs-lookup"><span data-stu-id="19f33-123">Deploy changes</span></span>

<span data-ttu-id="19f33-124">これらの手順にデスクトップの背景画像が表示されます。</span><span class="sxs-lookup"><span data-stu-id="19f33-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="19f33-125">展開をステージングした後、[展開の状態] ページから変更を展開します。</span><span class="sxs-lookup"><span data-stu-id="19f33-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="19f33-126">**変更を展開するには**</span><span class="sxs-lookup"><span data-stu-id="19f33-126">**To deploy changes**</span></span>

1. <span data-ttu-id="19f33-127">[Microsoft Managed Desktop 管理ポータル](https://aka.ms/mwaasportal)にサインインする</span><span class="sxs-lookup"><span data-stu-id="19f33-127">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="19f33-128">[**設定**] で、[**構成可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19f33-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="19f33-129">[**展開状態**] ワークスペースで、展開する設定を選択し、展開する段階的展開を選択します。</span><span class="sxs-lookup"><span data-stu-id="19f33-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="19f33-130">展開グループのいずれかに変更を展開するには、[**展開**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19f33-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE] 
> <span data-ttu-id="19f33-131">オレンジ色の警告アイコンは、展開に使用できる前のグループがあることを示しています。これは、順序どおりに展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="19f33-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span> 

<span data-ttu-id="19f33-132">![展開状態ワークスペース。</span><span class="sxs-lookup"><span data-stu-id="19f33-132">![Deployment status workspace.</span></span> <span data-ttu-id="19f33-133">右側の [信頼済みサイト] ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="19f33-133">Trusted sites pane on the right.</span></span> <span data-ttu-id="19f33-134">[展開グループ] セクションには、[展開グループ]、[デバイス]、[状態] の3つの列があります。</span><span class="sxs-lookup"><span data-stu-id="19f33-134">In the Deployment groups section are three columns: deployment groups, devices, and status.</span></span> <span data-ttu-id="19f33-135">[状態] 列の [展開] が強調表示されています。](../../media/1deployedit.png)</span><span class="sxs-lookup"><span data-stu-id="19f33-135">In the status column, "deploy" is highlighted.](../../media/1deployedit.png)</span></span>
<span data-ttu-id="19f33-136">展開グループへの展開は、次の順序で行うことをお勧めします。 Test、First、Fast、および広義です。</span><span class="sxs-lookup"><span data-stu-id="19f33-136">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="19f33-137">各グループで変更が完了すると、状態が [**完了**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="19f33-137">When changes complete in each group, the status changes to **Complete**.</span></span>

![更新日、バージョン、テスト、最初、高速、および広範な列を含む展開状態ワークスペース。](../../media/2completeedit.png)

## <a name="revert-deployment"></a><span data-ttu-id="19f33-140">展開を元に戻す</span><span class="sxs-lookup"><span data-stu-id="19f33-140">Revert deployment</span></span>

<span data-ttu-id="19f33-141">変更を展開した後、**展開状態**から元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="19f33-141">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="19f33-142">**進行**中または**完了**した変更を元に戻すと、現在の展開は停止します。</span><span class="sxs-lookup"><span data-stu-id="19f33-142">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="19f33-143">この設定は、すべてのグループに展開された最新のバージョンに戻ります。</span><span class="sxs-lookup"><span data-stu-id="19f33-143">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="19f33-144">デスクトップの背景画像を使用して変更を元に戻す手順を示します。</span><span class="sxs-lookup"><span data-stu-id="19f33-144">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="19f33-145">**変更を元に戻すには**</span><span class="sxs-lookup"><span data-stu-id="19f33-145">**To revert a change**</span></span>
1. <span data-ttu-id="19f33-146">[Microsoft Managed Desktop 管理ポータル](https://aka.ms/mwaasportal)にサインインする</span><span class="sxs-lookup"><span data-stu-id="19f33-146">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="19f33-147">[**設定**] で、[**構成可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19f33-147">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="19f33-148">[**展開状態**] ワークスペースで、元に戻す設定を選択してから、元に戻す段階的な展開を選択します。</span><span class="sxs-lookup"><span data-stu-id="19f33-148">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="19f33-149">[**この変更を元に戻す必要がありますか?**] で、[**展開の取り消し**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19f33-149">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

![展開状態ワークスペース。](../../media/3revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="19f33-153">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="19f33-153">Additional resources</span></span>
- [<span data-ttu-id="19f33-154">構成可能な設定の概要</span><span class="sxs-lookup"><span data-stu-id="19f33-154">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="19f33-155">構成可能な設定のリファレンス</span><span class="sxs-lookup"><span data-stu-id="19f33-155">Configurable settings reference</span></span>](config-setting-ref.md) 
