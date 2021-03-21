---
title: セルフサービス購入の管理 (管理者)
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: 管理者は、組織内のユーザーが行ったセルフサービス購入を管理する方法について学習できます。
ms.openlocfilehash: 2ce12b7dba4e765745a94fa10f4ba15e7013e3c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920182"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="fe0a9-103">セルフサービスによる購入を管理する (管理者)</span><span class="sxs-lookup"><span data-stu-id="fe0a9-103">Manage self-service purchases (Admin)</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="fe0a9-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-104">The admin center is changing.</span></span> <span data-ttu-id="fe0a9-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="fe0a9-106">管理者は、組織内のユーザーが行ったセルフサービス購入を確認できます。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-106">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="fe0a9-107">セルフサービス購入ごとに、製品名、購入者名、購入したサブスクリプション、有効期限、購入価格、割り当てられたユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-107">You see the product name, purchaser name, subscriptions purchased, expiration date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="fe0a9-108">組織で必要な場合は、PowerShell を介して製品ごとにセルフサービス購入をオフにできます。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-108">If required by your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="fe0a9-109">セルフサービス購入または一般購入で購入した製品と同じデータ管理ポリシーとアクセス ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-109">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="fe0a9-110">組織内のユーザーがセルフサービス購入を行うかどうかを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-110">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="fe0a9-111">詳細については [、「Use AllowSelfServicePurchase for the MSCommerce PowerShell モジュール」を参照してください](allowselfservicepurchase-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-111">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="fe0a9-112">セルフサービス サブスクリプションの表示</span><span class="sxs-lookup"><span data-stu-id="fe0a9-112">View self-service subscriptions</span></span>

1. <span data-ttu-id="fe0a9-113">管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="fe0a9-114">[製品 **] タブ** で、フィルター アイコンを選択し、[セルフサービス] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-114">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="fe0a9-115">サブスクリプションの詳細を表示するには、一覧から 1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="fe0a9-116">セルフサービス購入サブスクリプションのライセンスを持っているユーザーを表示する</span><span class="sxs-lookup"><span data-stu-id="fe0a9-116">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="fe0a9-117">管理センターで、[課金ライセンス]**ページ**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-117">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="fe0a9-118">フィルター アイコンを選択し、[セルフサービス] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-118">Select the filter icon, then choose **Self-service**.</span></span>
3. <span data-ttu-id="fe0a9-119">製品を選択すると、ユーザーに割り当てられたライセンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-119">Select a product to see licenses assigned to people.</span></span>
    > [!NOTE]
    > <span data-ttu-id="fe0a9-120">製品に複数の購入がある場合、その製品は 1 回だけ表示され、[利用可能な数量] 列には、その製品に対して購入されたサブスクリプションの合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-120">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>
4. <span data-ttu-id="fe0a9-121">[ **ユーザー]** リストは、セルフサービス購入を行ったユーザーの名前でグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-121">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>
5. <span data-ttu-id="fe0a9-122">これらのサブスクリプションのライセンスを持つユーザーの一覧をエクスポートするには、エクスポートするサブスクリプションを選択し、[ユーザーのエクスポート] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-122">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="fe0a9-123">セルフサービス購入を無効または有効にする</span><span class="sxs-lookup"><span data-stu-id="fe0a9-123">Disable or enable self-service purchases</span></span>

<span data-ttu-id="fe0a9-124">組織内のユーザーに対してセルフサービス購入を無効または有効にできます。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-124">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="fe0a9-125">**MSCommerce** PowerShell モジュールには **AllowSelfServicePurchase** の **PolicyID** パラメーター値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-125">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="fe0a9-126">**MSCommerce PowerShell** モジュールを使用すると、次の目的で使用できます。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-126">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="fe0a9-127">**AllowSelfServicePurchase** パラメーター値の既定の状態を表示する (製品によって有効または無効になっているかどうか)</span><span class="sxs-lookup"><span data-stu-id="fe0a9-127">View the default state of the **AllowSelfServicePurchase** parameter value—whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="fe0a9-128">該当する製品の一覧とセルフサービス購入が有効か無効かを表示する</span><span class="sxs-lookup"><span data-stu-id="fe0a9-128">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="fe0a9-129">特定の製品の現在の設定を表示または変更して、有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="fe0a9-129">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="fe0a9-130">詳細については [、「Use AllowSelfServicePurchase for the MSCommerce PowerShell モジュール」を参照してください](allowselfservicepurchase-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-130">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="fe0a9-131">1 つのサブスクリプションでライセンスを一元化する</span><span class="sxs-lookup"><span data-stu-id="fe0a9-131">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="fe0a9-132">セルフサービス購入に割り当てられたユーザーに対して、既存のライセンスを割り当てたり、既存の契約を通じて追加のサブスクリプションを購入することができます。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-132">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="fe0a9-133">これらの一般購入ライセンスを割り当てると、購入者に既存のサブスクリプションのキャンセルを要求できます。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-133">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="fe0a9-134">管理センターで、[課金の購入サービス **]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">ページに移動</a> します。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-134">In the admin center go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="fe0a9-135">購入する製品を見つけて選択し、[購入] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-135">Find and choose the product that you want to buy, then choose **Buy**.</span></span>
3. <span data-ttu-id="fe0a9-136">残りの手順を完了して購入を完了します。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-136">Complete the remaining steps to complete your purchase.</span></span>
4. <span data-ttu-id="fe0a9-137">「セルフサービス購入サブスクリプション[](#view-who-has-licenses-for-a-self-service-purchase-subscription)のライセンスを持っているユーザーを表示する」の手順に従って、次の手順で参照するユーザーのリストをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-137">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in the next step.</span></span>
5. <span data-ttu-id="fe0a9-138">他のサブスクリプションでライセンスを持っているすべてのユーザーにライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-138">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="fe0a9-139">完全な手順については、「ユーザーにライセンスを [割り当てる」を参照してください](../../admin/manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-139">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>
6. <span data-ttu-id="fe0a9-140">セルフサービス購入サブスクリプションを購入したユーザーに問い合わせ、キャンセルを [求める](manage-self-service-purchases-users.md#cancel-a-subscription)。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-140">Contact the person who bought the self-service purchase subscription and ask them to [cancel it](manage-self-service-purchases-users.md#cancel-a-subscription).</span></span>

## <a name="take-over-a-self-service-purchase-subscription"></a><span data-ttu-id="fe0a9-141">セルフサービス購入サブスクリプションの引き継ぎ</span><span class="sxs-lookup"><span data-stu-id="fe0a9-141">Take over a self-service purchase subscription</span></span>

<span data-ttu-id="fe0a9-142">組織内のユーザーが作成したセルフサービス購入サブスクリプションを引き継ぐ方法があります。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-142">You can take over a self-service purchase subscription made by a user in your organization.</span></span> <span data-ttu-id="fe0a9-143">セルフサービス購入サブスクリプションを引き継ぐ場合は、次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-143">When you take over a self-service purchase subscription, you have two options:</span></span>

1. <span data-ttu-id="fe0a9-144">ユーザーを別のサブスクリプションに移動し、元のサブスクリプションをキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-144">Move the users to a different subscription and cancel the original subscription.</span></span>
2. <span data-ttu-id="fe0a9-145">セルフサービス購入サブスクリプションをキャンセルし、割り当てられたユーザーからライセンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-145">Cancel the self-service purchase subscription and remove licenses from assigned users.</span></span>

### <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="fe0a9-146">ユーザーを別のサブスクリプションに移動する</span><span class="sxs-lookup"><span data-stu-id="fe0a9-146">Move users to a different subscription</span></span>

<span data-ttu-id="fe0a9-147">ユーザーを別のサブスクリプションに移動すると、古いサブスクリプションは自動的に取り消されます。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-147">When you move users to a different subscription, the old subscription is automatically canceled.</span></span> <span data-ttu-id="fe0a9-148">最初にセルフサービス購入サブスクリプションを購入したユーザーは、サブスクリプションがキャンセルされたというメールを受信します。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-148">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

> [!NOTE]
> <span data-ttu-id="fe0a9-149">ユーザーを移動するサブスクリプションで移動するユーザーごとに使用可能なライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-149">You must have an available license for each user you’re moving in the subscription that you’re moving users to.</span></span>

1. <span data-ttu-id="fe0a9-150">管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-150">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="fe0a9-151">[製品 **] タブ** で、フィルター アイコンを選択し、[セルフサービス] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-151">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="fe0a9-152">引き継ぐサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-152">Select the subscription that you want to take over.</span></span>
4. <span data-ttu-id="fe0a9-153">[サブスクリプションの詳細] ページの [ **サブスクリプションと設定** ] セクションで、[このサブスクリプションを制御 **する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-153">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="fe0a9-154">右側のウィンドウで、[ユーザーの移動] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-154">In the right pane, select **Move users**.</span></span>
6. <span data-ttu-id="fe0a9-155">ユーザーを移動する製品を選択し、[ユーザーの移動] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-155">Select the product that you want to move the users to, then select **Move users**.</span></span>
7. <span data-ttu-id="fe0a9-156">[ユーザーの **移動] ボックスで** 、[ユーザーの移動 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-156">In the **Move users to** box, select **Move users**.</span></span> <span data-ttu-id="fe0a9-157">移動プロセスには数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-157">The move process might take several minutes.</span></span> <span data-ttu-id="fe0a9-158">プロセスの実行中にブラウザーを閉じない。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-158">Don’t close your browser while the process runs.</span></span>
8. <span data-ttu-id="fe0a9-159">移動プロセスが完了したら、[完了した移動] **ウィンドウを閉じます**。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-159">When the move process is finished, close the **Move completed pane**.</span></span>
9. <span data-ttu-id="fe0a9-160">[サブスクリプションの詳細] ページで、セルフサービス購入サブスクリプションのサブスクリプションの状態が [削除済み]**と表示されます**。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-160">On the subscription details page, the **Subscription status** for the self-service purchased subscription shows as **Deleted**.</span></span>

### <a name="cancel-a-self-service-purchase-subscription"></a><span data-ttu-id="fe0a9-161">セルフサービス購入サブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="fe0a9-161">Cancel a self-service purchase subscription</span></span>

<span data-ttu-id="fe0a9-162">セルフサービス購入サブスクリプションをキャンセルすると、ライセンスを持つユーザーは製品へのアクセスを失います。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-162">When you choose to cancel a self-service purchase subscription, users with licenses lose access to the product.</span></span> <span data-ttu-id="fe0a9-163">最初にセルフサービス購入サブスクリプションを購入したユーザーは、サブスクリプションがキャンセルされたというメールを受信します。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-163">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

1. <span data-ttu-id="fe0a9-164">管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-164">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="fe0a9-165">[製品 **] タブ** で、フィルター アイコンを選択し、[セルフサービス] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-165">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="fe0a9-166">キャンセルするサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-166">Select the subscription that you want to cancel.</span></span>
4. <span data-ttu-id="fe0a9-167">[サブスクリプションの詳細] ページの [ **サブスクリプションと設定** ] セクションで、[このサブスクリプションを制御 **する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-167">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="fe0a9-168">右側のウィンドウで、[サブスクリプションのキャンセル] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-168">In the right pane, select **Cancel subscription**.</span></span>
6. <span data-ttu-id="fe0a9-169">ドロップダウン リストからキャンセルの理由を選択し、[サブスクリプションのキャンセル] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-169">Select a reason for your cancellation from the drop-down list, then select **Cancel subscription**.</span></span>
7. <span data-ttu-id="fe0a9-170">[キャンセル **しますか? ] ボックスで** 、[サブスクリプションのキャンセル] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-170">In the **Are you sure you want to cancel?** box, select **Cancel subscription**.</span></span>
8. <span data-ttu-id="fe0a9-171">右側のウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-171">Close the right pane.</span></span>
9. <span data-ttu-id="fe0a9-172">[サブスクリプションの詳細] ページで、[サブスクリプションの状態 **] が [** 削除済み] **と表示されます**。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-172">On the subscription details page, the **Subscription status** shows as **Deleted**.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="fe0a9-173">サポートが必要な場合</span><span class="sxs-lookup"><span data-stu-id="fe0a9-173">Need help?</span></span> <span data-ttu-id="fe0a9-174">お問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-174">Contact us.</span></span>

<span data-ttu-id="fe0a9-175">セルフサービス購入に関する一般的な質問については、「セルフサービス購入に関する [よく寄せられる質問」を参照してください](self-service-purchase-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-175">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="fe0a9-176">セルフサービス購入に関するご質問やサポートが必要な場合は、サポート [にお問い合わせください](../../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="fe0a9-176">If you have questions or need help with self-service purchases, [contact support](../../admin/contact-support-for-business-products.md).</span></span>