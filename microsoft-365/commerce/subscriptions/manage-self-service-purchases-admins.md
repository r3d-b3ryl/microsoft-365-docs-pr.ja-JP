---
title: セルフサービス購入を管理する (管理者)
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
search.appverid:
- MET150
description: 管理者は、組織内のユーザーによって作成されたセルフサービスの購入を管理する方法について説明します。
ms.openlocfilehash: 991dc87c40f41a6cbd2f1c08d4bc72bbb34d28f1
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141152"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="ebf79-103">セルフサービスによる購入を管理する (管理者)</span><span class="sxs-lookup"><span data-stu-id="ebf79-103">Manage self-service purchases (Admin)</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="ebf79-104">管理センターが変更されています。</span><span class="sxs-lookup"><span data-stu-id="ebf79-104">The admin center is changing.</span></span> <span data-ttu-id="ebf79-105">ここに示されている詳細情報とは異なる場合は、「[新しい Microsoft 365 管理センターについ](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebf79-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="ebf79-106">管理者は、組織内のユーザーによって作成されたセルフサービスの購入を表示できます。</span><span class="sxs-lookup"><span data-stu-id="ebf79-106">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="ebf79-107">セルフサービスの各購入について、製品、購入者名、購入したサブスクリプション、有効期限、購入価格、割り当てられたユーザーを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ebf79-107">You can see the product, purchaser name, subscriptions purchased, expiry date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="ebf79-108">組織に必要な場合は、PowerShell を使用して製品ごとにセルフサービス購入を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ebf79-108">If required for your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="ebf79-109">セルフサービス購入または一元的に購入した製品に対して、同じデータ管理とアクセスポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebf79-109">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="ebf79-110">組織内のユーザーがセルフサービス購入を行うことができるかどうかを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="ebf79-110">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="ebf79-111">詳細については、「 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebf79-111">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="ebf79-112">セルフサービスサブスクリプションを表示する</span><span class="sxs-lookup"><span data-stu-id="ebf79-112">View self-service subscriptions</span></span>

1. <span data-ttu-id="ebf79-113">管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">製品</a>の**請求** > ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="ebf79-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="ebf79-114">[**結果の絞り込み**] の横にある [**アカウントの種類**] ドロップダウンから、[**セルフサービス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ebf79-114">Next to **Refine results**, from the **Account type** drop-down, choose **Self-service**.</span></span>

3. <span data-ttu-id="ebf79-115">サブスクリプションの詳細を表示するには、一覧から1つを選択します。</span><span class="sxs-lookup"><span data-stu-id="ebf79-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="ebf79-116">セルフサービス購入サブスクリプションのライセンスを持っているユーザーを表示する</span><span class="sxs-lookup"><span data-stu-id="ebf79-116">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="ebf79-117">管理センターで、[**課金** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="ebf79-117">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

2. <span data-ttu-id="ebf79-118">[フィルター] アイコンを選択し、[**セルフサービス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ebf79-118">Choose the filter icon, then choose **Self-service**.</span></span>

3. <span data-ttu-id="ebf79-119">ユーザーに割り当てられているライセンスを確認するには、製品を選択します。</span><span class="sxs-lookup"><span data-stu-id="ebf79-119">Select a product to see licenses assigned to people.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ebf79-120">製品に対して複数の購入がある場合、その製品は一度だけ表示され、[**利用可能な数量**] 列には、その製品に対して購入されたすべてのサブスクリプションの合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ebf79-120">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>

4. <span data-ttu-id="ebf79-121">**ユーザー**リストは、セルフサービス購入を行ったユーザーの名前によってグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="ebf79-121">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>

5. <span data-ttu-id="ebf79-122">これらのサブスクリプションのライセンスを持つユーザーの一覧をエクスポートするには、エクスポートするサブスクリプションを選択し、[**ユーザーのエクスポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ebf79-122">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="ebf79-123">セルフサービス購入を無効または有効にする</span><span class="sxs-lookup"><span data-stu-id="ebf79-123">Disable or enable self-service purchases</span></span>

<span data-ttu-id="ebf79-124">組織内のユーザーに対してセルフサービス購入を無効または有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ebf79-124">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="ebf79-125">**MSCommerce** PowerShell モジュールには、組織内のユーザーがセルフサービス購入を行うことができるかどうかを制御できる、 **Allowselfservicepurchase**の**policyid**パラメーターの値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ebf79-125">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="ebf79-126">**MSCommerce** PowerShell モジュールを使用して、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ebf79-126">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="ebf79-127">**Allowselfservicepurchase**パラメーター値&mdash;の既定の状態を表示する (製品によって有効または無効にする)</span><span class="sxs-lookup"><span data-stu-id="ebf79-127">View the default state of the **AllowSelfServicePurchase** parameter value &mdash; whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="ebf79-128">適用可能な製品の一覧、およびセルフサービス購入が有効か無効かを表示する</span><span class="sxs-lookup"><span data-stu-id="ebf79-128">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="ebf79-129">特定の製品の現在の設定を表示または変更して、有効にするか無効にするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="ebf79-129">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="ebf79-130">詳細については、「 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebf79-130">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="ebf79-131">1つのサブスクリプションでライセンスを一元管理する</span><span class="sxs-lookup"><span data-stu-id="ebf79-131">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="ebf79-132">セルフサービス購入に割り当てられているユーザーの既存のライセンスを割り当てたり、既存の契約を使用して追加のサブスクリプションを購入したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="ebf79-132">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="ebf79-133">これらの集中的に購入したライセンスを割り当てた後、purchasers に既存のサブスクリプションをキャンセルするよう要求することができます。</span><span class="sxs-lookup"><span data-stu-id="ebf79-133">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="ebf79-134">グローバル管理者または課金管理者アカウントを使用して、<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>にサインインします。</span><span class="sxs-lookup"><span data-stu-id="ebf79-134">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> with your Global admin or Billing admin account.</span></span>

2. <span data-ttu-id="ebf79-135">[**請求** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">書サービス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="ebf79-135">Go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

3. <span data-ttu-id="ebf79-136">購入する製品を見つけて選択し、[**購入**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ebf79-136">Find and choose the product that you want to buy, then choose **Buy**.</span></span>

4. <span data-ttu-id="ebf79-137">残りの手順を実行して、購入を完了します。</span><span class="sxs-lookup"><span data-stu-id="ebf79-137">Complete the remaining steps to complete your purchase.</span></span>

5. <span data-ttu-id="ebf79-138">手順6で参照するユーザーの一覧をエクスポートするには、「[セルフサービスで購入したサブスクリプションのライセンスを表示](#view-who-has-licenses-for-a-self-service-purchase-subscription)する」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ebf79-138">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in step 6.</span></span>

6. <span data-ttu-id="ebf79-139">他のサブスクリプションにライセンスを持つすべてのユーザーにライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ebf79-139">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="ebf79-140">詳細な手順については、「[ユーザーへのライセンスの割り当て](../../admin/manage/assign-licenses-to-users.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebf79-140">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>

7. <span data-ttu-id="ebf79-141">セルフサービス購入サブスクリプションを購入したユーザーに連絡して、それを取り消すように依頼します。</span><span class="sxs-lookup"><span data-stu-id="ebf79-141">Contact the person who bought the self-service purchase subscription and ask them to cancel it.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="ebf79-142">サポートが必要な場合</span><span class="sxs-lookup"><span data-stu-id="ebf79-142">Need help?</span></span> <span data-ttu-id="ebf79-143">ご連絡ください。</span><span class="sxs-lookup"><span data-stu-id="ebf79-143">Contact us.</span></span>

<span data-ttu-id="ebf79-144">セルフサービス購入に関してよく寄せられる質問については、「[セルフサービス購入](self-service-purchase-faq.md)に関する FAQ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebf79-144">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="ebf79-145">ご質問がある場合やセルフサービス購入に関するヘルプが必要な場合は、[サポートにお問い合わせください](../../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="ebf79-145">If you have questions or need help with self-service purchases, [contact support](../../admin/contact-support-for-business-products.md).</span></span>
