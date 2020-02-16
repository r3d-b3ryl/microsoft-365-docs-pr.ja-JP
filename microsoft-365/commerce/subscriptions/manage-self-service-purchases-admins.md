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
ms.openlocfilehash: f3ccd1f8ab5f2f9fc78e2920182155ef7f6f16e3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080334"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="3ebc0-103">セルフサービス購入を管理する (管理者)</span><span class="sxs-lookup"><span data-stu-id="3ebc0-103">Manage self-service purchases (Admin)</span></span>

<span data-ttu-id="3ebc0-104">管理者は、組織内のユーザーによって作成されたセルフサービスの購入を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-104">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="3ebc0-105">セルフサービスの各購入について、製品、購入者名、購入したサブスクリプション、有効期限、購入価格、割り当てられたユーザーを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-105">You can see the product, purchaser name, subscriptions purchased, expiry date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="3ebc0-106">組織に必要な場合は、PowerShell を使用して製品ごとにセルフサービス購入を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-106">If required for your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="3ebc0-107">セルフサービス購入または一元的に購入した製品に対して、同じデータ管理とアクセスポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-107">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="3ebc0-108">組織内のユーザーがセルフサービス購入を行うことができるかどうかを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-108">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="3ebc0-109">詳細については、「 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-109">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="3ebc0-110">セルフサービスサブスクリプションを表示する</span><span class="sxs-lookup"><span data-stu-id="3ebc0-110">View self-service subscriptions</span></span>

1. <span data-ttu-id="3ebc0-111">管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">製品とサービス</a>] のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="3ebc0-112">[**結果の絞り込み**] の横にある [**アカウントの種類**] ドロップダウンから、[**セルフサービス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-112">Next to **Refine results**, from the **Account type** drop-down, choose **Self-service**.</span></span>

3. <span data-ttu-id="3ebc0-113">サブスクリプションの詳細を表示するには、一覧から1つを選択します。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-113">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="3ebc0-114">セルフサービス購入サブスクリプションのライセンスを持っているユーザーを表示する</span><span class="sxs-lookup"><span data-stu-id="3ebc0-114">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="3ebc0-115">管理センターで、[**課金** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-115">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

2. <span data-ttu-id="3ebc0-116">[フィルター] アイコンを選択し、[**セルフサービス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-116">Choose the filter icon, then choose **Self-service**.</span></span>

3. <span data-ttu-id="3ebc0-117">ユーザーに割り当てられているライセンスを確認するには、製品を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-117">Select a product to see licenses assigned to people.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3ebc0-118">製品に対して複数の購入がある場合、その製品は一度だけ表示され、[**利用可能な数量**] 列には、その製品に対して購入されたすべてのサブスクリプションの合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-118">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>

4. <span data-ttu-id="3ebc0-119">**ユーザー**リストは、セルフサービス購入を行ったユーザーの名前によってグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-119">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>

5. <span data-ttu-id="3ebc0-120">これらのサブスクリプションのライセンスを持つユーザーの一覧をエクスポートするには、エクスポートするサブスクリプションを選択し、[**ユーザーのエクスポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-120">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="3ebc0-121">セルフサービス購入を無効または有効にする</span><span class="sxs-lookup"><span data-stu-id="3ebc0-121">Disable or enable self-service purchases</span></span>

<span data-ttu-id="3ebc0-122">組織内のユーザーに対してセルフサービス購入を無効または有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-122">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="3ebc0-123">**MSCommerce** PowerShell モジュールには、組織内のユーザーがセルフサービス購入を行うことができるかどうかを制御できる、 **Allowselfservicepurchase**の**policyid**パラメーターの値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-123">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="3ebc0-124">**MSCommerce** PowerShell モジュールを使用して、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-124">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="3ebc0-125">**Allowselfservicepurchase**パラメーター値&mdash;の既定の状態を表示する (製品によって有効または無効にする)</span><span class="sxs-lookup"><span data-stu-id="3ebc0-125">View the default state of the **AllowSelfServicePurchase** parameter value &mdash; whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="3ebc0-126">適用可能な製品の一覧、およびセルフサービス購入が有効か無効かを表示する</span><span class="sxs-lookup"><span data-stu-id="3ebc0-126">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="3ebc0-127">特定の製品の現在の設定を表示または変更して、有効にするか無効にするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-127">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="3ebc0-128">詳細については、「 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-128">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="3ebc0-129">1つのサブスクリプションでライセンスを一元管理する</span><span class="sxs-lookup"><span data-stu-id="3ebc0-129">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="3ebc0-130">セルフサービス購入に割り当てられているユーザーの既存のライセンスを割り当てたり、既存の契約を使用して追加のサブスクリプションを購入したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-130">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="3ebc0-131">これらの集中的に購入したライセンスを割り当てた後、purchasers に既存のサブスクリプションをキャンセルするよう要求することができます。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-131">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="3ebc0-132">グローバル管理者または課金管理者アカウントを使用して、<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>にサインインします。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-132">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> with your Global admin or Billing admin account.</span></span>

2. <span data-ttu-id="3ebc0-133">[**請求** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">書サービス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-133">Go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

3. <span data-ttu-id="3ebc0-134">購入する製品を見つけて選択し、[**購入**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-134">Find and choose the product that you want to buy, then choose **Buy**.</span></span>

4. <span data-ttu-id="3ebc0-135">残りの手順を実行して、購入を完了します。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-135">Complete the remaining steps to complete your purchase.</span></span>

5. <span data-ttu-id="3ebc0-136">手順6で参照するユーザーの一覧をエクスポートするには、「[セルフサービスで購入したサブスクリプションのライセンスを表示](#view-who-has-licenses-for-a-self-service-purchase-subscription)する」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-136">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in step 6.</span></span>

6. <span data-ttu-id="3ebc0-137">他のサブスクリプションにライセンスを持つすべてのユーザーにライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-137">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="3ebc0-138">詳細な手順については、「[ユーザーへのライセンスの割り当て](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-138">For full steps, see [Assign licenses to users](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span></span>

7. <span data-ttu-id="3ebc0-139">セルフサービス購入サブスクリプションを購入したユーザーに連絡して、それを取り消すように依頼します。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-139">Contact the person who bought the self-service purchase subscription and ask them to cancel it.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="3ebc0-140">ヘルプが必要な場合</span><span class="sxs-lookup"><span data-stu-id="3ebc0-140">Need help?</span></span> <span data-ttu-id="3ebc0-141">ご連絡ください。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-141">Contact us.</span></span>

<span data-ttu-id="3ebc0-142">セルフサービス購入に関してよく寄せられる質問については、「[セルフサービス購入](self-service-purchase-faq.md)に関する FAQ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-142">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="3ebc0-143">ご質問がある場合やセルフサービス購入に関するヘルプが必要な場合は、[サポートにお問い合わせください](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="3ebc0-143">If you have questions or need help with self-service purchases, [contact support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>
