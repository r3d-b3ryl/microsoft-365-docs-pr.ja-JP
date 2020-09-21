---
title: Microsoft マネージドデスクトップで構成可能な設定を展開する
description: Microsoft マネージドデスクトップで構成の構成変更を展開し、追跡します。
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント、展開、段階的展開、構成可能な設定
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a24d0dc64e2262a8b208119c45a4a6bade701c10
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104536"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="6900e-104">構成可能な設定を展開および追跡する-Microsoft マネージドデスクトップ</span><span class="sxs-lookup"><span data-stu-id="6900e-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="6900e-105">設定カテゴリを変更し、展開をステージした後、[展開の状態] ページで、グループへの設定の展開を開始できます。</span><span class="sxs-lookup"><span data-stu-id="6900e-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="6900e-106">このページには、各構成可能な設定の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6900e-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="6900e-107">[設定] カテゴリを開くと、設定をグループに展開し、これらの展開の進行状況を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="6900e-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="6900e-108">展開の状態</span><span class="sxs-lookup"><span data-stu-id="6900e-108">Deployment statuses</span></span> 

<span data-ttu-id="6900e-109">展開ごとに表示される状態を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6900e-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="6900e-110">状態</span><span class="sxs-lookup"><span data-stu-id="6900e-110">Status</span></span>  | <span data-ttu-id="6900e-111">説明</span><span class="sxs-lookup"><span data-stu-id="6900e-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="6900e-112">展開</span><span class="sxs-lookup"><span data-stu-id="6900e-112">Deploy</span></span> | <span data-ttu-id="6900e-113">変更は、このグループへの展開を待機しています。</span><span class="sxs-lookup"><span data-stu-id="6900e-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="6900e-114">処理中</span><span class="sxs-lookup"><span data-stu-id="6900e-114">In progress</span></span> | <span data-ttu-id="6900e-115">このグループ内のアクティブなデバイスに変更が適用されています。</span><span class="sxs-lookup"><span data-stu-id="6900e-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="6900e-116">完了</span><span class="sxs-lookup"><span data-stu-id="6900e-116">Complete</span></span> | <span data-ttu-id="6900e-117">このグループ内のすべてのアクティブなデバイスで変更が完了しました。</span><span class="sxs-lookup"><span data-stu-id="6900e-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="6900e-118">失敗</span><span class="sxs-lookup"><span data-stu-id="6900e-118">Failed</span></span> | <span data-ttu-id="6900e-119">グループ内のアクティブなデバイスの10% で変更が失敗したため、展開が停止されました。</span><span class="sxs-lookup"><span data-stu-id="6900e-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="6900e-120">展開のトラブルシューティングを行うために、サポート要求が Microsoft マネージドデスクトップ操作を使用して自動的に開かれます。</span><span class="sxs-lookup"><span data-stu-id="6900e-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="6900e-121">復帰</span><span class="sxs-lookup"><span data-stu-id="6900e-121">Reverted</span></span> | <span data-ttu-id="6900e-122">変更は、すべての展開グループに正常に展開された最後の変更に戻されました。</span><span class="sxs-lookup"><span data-stu-id="6900e-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="6900e-123">変更を展開する</span><span class="sxs-lookup"><span data-stu-id="6900e-123">Deploy changes</span></span>

<span data-ttu-id="6900e-124">これらの手順にデスクトップの背景画像が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6900e-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="6900e-125">展開をステージングした後、[展開の状態] ページから変更を展開します。</span><span class="sxs-lookup"><span data-stu-id="6900e-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="6900e-126">**変更を展開するには**</span><span class="sxs-lookup"><span data-stu-id="6900e-126">**To deploy changes**</span></span>

1. <span data-ttu-id="6900e-127">[Microsoft エンドポイントマネージャー](https://endpoint.microsoft.com/)にサインインして、[**デバイス**] メニューに移動します。</span><span class="sxs-lookup"><span data-stu-id="6900e-127">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="6900e-128">[Microsoft Managed Desktop] セクションを探し、[ **設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6900e-128">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="6900e-129">[ **展開状態** ] ワークスペースで、展開する設定を選択し、展開する段階的展開を選択します。</span><span class="sxs-lookup"><span data-stu-id="6900e-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="6900e-130">展開グループのいずれかに変更を展開するには、[ **展開** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6900e-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE] 
> <span data-ttu-id="6900e-131">オレンジ色の警告アイコンは、展開に使用できる前のグループがあることを示しています。これは、順序どおりに展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6900e-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span> 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

<span data-ttu-id="6900e-132">展開グループへの展開は、次の順序で行うことをお勧めします。 Test、First、Fast、および広義です。</span><span class="sxs-lookup"><span data-stu-id="6900e-132">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="6900e-133">各グループで変更が完了すると、状態が [ **完了**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="6900e-133">When changes complete in each group, the status changes to **Complete**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a><span data-ttu-id="6900e-134">展開を元に戻す</span><span class="sxs-lookup"><span data-stu-id="6900e-134">Revert deployment</span></span>

<span data-ttu-id="6900e-135">変更を展開した後、 **展開状態**から元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="6900e-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="6900e-136">**進行**中または**完了**した変更を元に戻すと、現在の展開は停止します。</span><span class="sxs-lookup"><span data-stu-id="6900e-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="6900e-137">この設定は、すべてのグループに展開された最新のバージョンに戻ります。</span><span class="sxs-lookup"><span data-stu-id="6900e-137">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="6900e-138">デスクトップの背景画像を使用して変更を元に戻す手順を示します。</span><span class="sxs-lookup"><span data-stu-id="6900e-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="6900e-139">**変更を元に戻すには**</span><span class="sxs-lookup"><span data-stu-id="6900e-139">**To revert a change**</span></span>
1. <span data-ttu-id="6900e-140">[Microsoft エンドポイントマネージャー](https://endpoint.microsoft.com/)にサインインして、[**デバイス**] メニューに移動します。</span><span class="sxs-lookup"><span data-stu-id="6900e-140">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="6900e-141">[Microsoft Managed Desktop] セクションを探し、[ **設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6900e-141">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="6900e-142">[ **展開状態** ] ワークスペースで、元に戻す設定を選択してから、元に戻す段階的な展開を選択します。</span><span class="sxs-lookup"><span data-stu-id="6900e-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="6900e-143">[ **この変更を元に戻す必要がありますか?**] で、[ **展開の取り消し**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6900e-143">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a><span data-ttu-id="6900e-144">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="6900e-144">Additional resources</span></span>
- [<span data-ttu-id="6900e-145">構成可能な設定の概要</span><span class="sxs-lookup"><span data-stu-id="6900e-145">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="6900e-146">構成可能な設定のリファレンス</span><span class="sxs-lookup"><span data-stu-id="6900e-146">Configurable settings reference</span></span>](config-setting-ref.md) 
