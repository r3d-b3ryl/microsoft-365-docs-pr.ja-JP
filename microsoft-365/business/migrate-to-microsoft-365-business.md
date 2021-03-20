---
title: Microsoft 365 Business Standard から Microsoft 365 Business Premium にアップグレードする
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Microsoft 365 Business Standard と Microsoft 365 Business Premium の違いと、Microsoft 365 Business Premium にアップグレードする方法について説明します。
ms.openlocfilehash: ef3d929164f83d4e48157065eb1ae1d2a1a9452e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912924"
---
# <a name="upgrade-to-microsoft-365-business-premium-from-microsoft-365-business-standard"></a><span data-ttu-id="dd28d-103">Microsoft 365 Business Standard から Microsoft 365 Business Premium にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="dd28d-103">Upgrade to Microsoft 365 Business Premium from Microsoft 365 Business Standard</span></span>

<span data-ttu-id="dd28d-104">[Microsoft 365 for business サブスクリプション (Microsoft 365](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2)Business Standard など) がある場合は、Microsoft 365 Business Premium に簡単にアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="dd28d-104">If you have a [Microsoft 365 for business subscription](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), for example, Microsoft 365 Business Standard, you can easily upgrade to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="dd28d-105">追加する場合は、Microsoft 365 Business Premium にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="dd28d-105">Upgrade to Microsoft 365 Business Premium if you want to add:</span></span>

- <span data-ttu-id="dd28d-106">Windows 10 Pro (デバイスを実行している pc Windows 8以降)</span><span class="sxs-lookup"><span data-stu-id="dd28d-106">Windows 10 Pro (to PCs running Windows 8 or later)</span></span>

- <span data-ttu-id="dd28d-107">デバイス上のビジネス データを管理する簡単なコントロール</span><span class="sxs-lookup"><span data-stu-id="dd28d-107">Simple controls that manage business data on devices</span></span>

- <span data-ttu-id="dd28d-108">高度なセキュリティ機能。</span><span class="sxs-lookup"><span data-stu-id="dd28d-108">Advanced security capabilities.</span></span>
<span data-ttu-id="dd28d-109">Microsoft 365 Business Premium の詳細については [、Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span><span class="sxs-lookup"><span data-stu-id="dd28d-109">Find out more about Microsoft 365 Business Premium at [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span></span>

## <a name="whats-the-difference-between-microsoft-365-business-standard-and-microsoft-365-business-premium"></a><span data-ttu-id="dd28d-110">Microsoft 365 Business Standard と Microsoft 365 Business Premium の違いは何ですか?</span><span class="sxs-lookup"><span data-stu-id="dd28d-110">What's the difference between Microsoft 365 Business Standard and Microsoft 365 Business Premium?</span></span>

<span data-ttu-id="dd28d-111">Microsoft [365 Business Premium Service](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description)Description にこれら 2 つのプランを並べて比較しました。</span><span class="sxs-lookup"><span data-stu-id="dd28d-111">We've added a side-by-side comparison of these two plans to the [Microsoft 365 Business Premium Service Description](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span></span> 

## <a name="before-you-get-started"></a><span data-ttu-id="dd28d-112">使用を開始する前に</span><span class="sxs-lookup"><span data-stu-id="dd28d-112">Before you get started</span></span>

- <span data-ttu-id="dd28d-113">**アップグレードの選択が必要な場合**</span><span class="sxs-lookup"><span data-stu-id="dd28d-113">**When should I choose to upgrade?**</span></span> <span data-ttu-id="dd28d-114">1 つのプランに割り当てられているすべてのユーザーをアップグレードする場合は、アップグレードが適切な選択です。</span><span class="sxs-lookup"><span data-stu-id="dd28d-114">Upgrade is the right choice when you want to upgrade **all users** assigned to a single plan.</span></span> <span data-ttu-id="dd28d-115">アップグレードを選択すると、すべてのプラン ユーザーが同時に別のプランに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="dd28d-115">When you choose upgrade, all plan users get switched to another plan at the same time.</span></span> <span data-ttu-id="dd28d-116">1 つのプランに割り当てられているすべてのユーザーをアップグレードしない場合は、新しいプランのライセンス (この場合は Microsoft 365 Business Premium) を購入し、アップグレードする各ユーザーにそれらのライセンスを個別に割り当てる必要があります。 [](../admin/manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="dd28d-116">If you don't want to upgrade everyone assigned to a single plan, buy licenses for the new plan (in this case Microsoft 365 Business Premium), and [assign those licenses individually](../admin/manage/assign-licenses-to-users.md) to each user that you want to upgrade.</span></span>

- <span data-ttu-id="dd28d-117">**一部のアドオンでアップグレードが妨げる場合があります** アップグレードを開始しようとして、続行を妨げるアドオンがある場合は、最初にアドオンを削除してから、必要な場合は後で追加し直します。</span><span class="sxs-lookup"><span data-stu-id="dd28d-117">**Some add-ons might prevent the upgrade** If you try to start an upgrade and you have an add-on that prevents you from continuing, you can remove the add-on first, and then add it back later if you still need it.</span></span>

- <span data-ttu-id="dd28d-118">**プランを前払いした場合** 前払いプランの簡単なアップグレード パスは提供されません。</span><span class="sxs-lookup"><span data-stu-id="dd28d-118">**If you prepaid your plan** There isn't a straightforward upgrade path for prepaid plans.</span></span> <span data-ttu-id="dd28d-119">ストアで購入した可能性がある製品 ID を使用してプランをセットアップした場合に、プリペイド プランを持っているかどうかが分かっています。</span><span class="sxs-lookup"><span data-stu-id="dd28d-119">You'll know if you have a prepaid plan because you set up your plan using a product ID that you might have purchased in a store.</span></span> <span data-ttu-id="dd28d-120">パートナーに問い合わせ、Microsoft Store にアクセスするか、プリペイド プランの有効期限が切れるまで待って、新しいプランに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="dd28d-120">Contact a partner, go to the Microsoft Store, or wait until your prepaid plan expires to switch to a new plan.</span></span>

## <a name="upgrade-to-microsoft-365-business-premium"></a><span data-ttu-id="dd28d-121">Microsoft 365 Business Premium へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="dd28d-121">Upgrade to Microsoft 365 Business Premium</span></span>

1. <span data-ttu-id="dd28d-122">で管理センターにサインインします <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="dd28d-122">Sign into the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="dd28d-123">ナビゲーション ウィンドウに移動し、[製品の請求 **]** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dd28d-123">Go to the navigation pane and select **Billing** \> **Your products**.</span></span> <span data-ttu-id="dd28d-124">現在のサブスクリプションを検索し、選択して詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="dd28d-124">Find your current subscription and select it to view the details.</span></span>

3. <span data-ttu-id="dd28d-125">次のページで、[アップグレード] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="dd28d-125">On the next page, select **Upgrade**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="dd28d-126">**Azure Active Directory** でのグループ ベースのライセンスではサブスクリプションのアップグレードがサポートされていないというメッセージが表示される場合は、非常に大規模な組織を持たない限り、これを無視しても問題なく無視できます。</span><span class="sxs-lookup"><span data-stu-id="dd28d-126">If you see a message that says **Upgrading your subscription is not supported with group-based licensing in Azure Active Directory**, you can safely ignore this unless you have a very large organization.</span></span> <span data-ttu-id="dd28d-127">このオプションを選択した組織は、グループ ベースのライセンスを使用しているのを認識します。</span><span class="sxs-lookup"><span data-stu-id="dd28d-127">Organizations who have selected this option will be aware that they're using group-based licensing.</span></span>

4. <span data-ttu-id="dd28d-128">次に、アップグレードできるプランの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="dd28d-128">Next, you can view a list of plans that you can upgrade to.</span></span> <span data-ttu-id="dd28d-129">この場合は、Microsoft 365 Business Premium プランを探します。</span><span class="sxs-lookup"><span data-stu-id="dd28d-129">In this case, find the Microsoft 365 Business Premium plan.</span></span> <span data-ttu-id="dd28d-130">このプランに含まれるすべてのアプリとサービスを表示する場合は、下にスクロールできます。</span><span class="sxs-lookup"><span data-stu-id="dd28d-130">You can scroll down if you want to see all the apps and services that are included with this plan.</span></span> <span data-ttu-id="dd28d-131">[Microsoft **365 Business Premium] で**、[アップグレード] **を選択して** 、Microsoft 365 Business Premium をカートに追加します。</span><span class="sxs-lookup"><span data-stu-id="dd28d-131">Under **Microsoft 365 Business Premium**, select **Upgrade** to add Microsoft 365 Business Premium to your cart.</span></span>

5. <span data-ttu-id="dd28d-132">カート内:</span><span class="sxs-lookup"><span data-stu-id="dd28d-132">In the cart:</span></span>

    1. <span data-ttu-id="dd28d-133">現在のすべてのユーザーのライセンスが自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="dd28d-133">We'll automatically include licenses for all your current users.</span></span> <span data-ttu-id="dd28d-134">複数または少ないライセンスが必要な場合は、それらのライセンスを個別に購入 [して割り当てる必要があります](../admin/manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="dd28d-134">If you need more or fewer licenses, you need to [buy and assign those licenses individually](../admin/manage/assign-licenses-to-users.md).</span></span>  
    2. <span data-ttu-id="dd28d-135">支払い方法を調整できます(月次または年払い)。</span><span class="sxs-lookup"><span data-stu-id="dd28d-135">You can adjust how you'd like to pay: monthly or yearly.</span></span> <span data-ttu-id="dd28d-136">ドロップダウン メニューを選択して選択します。</span><span class="sxs-lookup"><span data-stu-id="dd28d-136">Select the drop-down menu to make your choice.</span></span>

6. <span data-ttu-id="dd28d-137">[ **チェックアウトに移動]** を選択すると、このアカウントの支払い方法を含む購入の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd28d-137">Select **Go to Checkout** where you'll see a summary of your purchase, including the payment method for this account.</span></span> <span data-ttu-id="dd28d-138">プロモーション コードがある場合は、ここにプロモーション コードを追加できます。</span><span class="sxs-lookup"><span data-stu-id="dd28d-138">You can also add a promo code here if you have one.</span></span>

7. <span data-ttu-id="dd28d-139">[ **注文の発注]** を選択して購入を完了します。</span><span class="sxs-lookup"><span data-stu-id="dd28d-139">Select **Place order** to complete your purchase.</span></span>\
<span data-ttu-id="dd28d-140">Microsoft が新しいサービス プランをセットアップするのに数分かかります。</span><span class="sxs-lookup"><span data-stu-id="dd28d-140">It takes Microsoft a few minutes to set up your new service plans.</span></span> <span data-ttu-id="dd28d-141">進行状況を確認するには、[アップグレードの状態を **確認する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dd28d-141">To check on progress, select **Check upgrade status**.</span></span>

8. <span data-ttu-id="dd28d-142">プランの準備ができたら、管理センターで追加のセットアップ手順を完了する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="dd28d-142">When your plan is ready, you might need to complete some additional setup steps in the admin center.</span></span> <span data-ttu-id="dd28d-143">ナビゲーション ウィンドウで、[ホーム] を **選択** して、追加のセットアップ手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="dd28d-143">In the navigation pane, select **Home** to complete any additional setup steps.</span></span>

> [!NOTE]
> <span data-ttu-id="dd28d-144">不要になった Microsoft 365 ライセンスに対して日割り払い払いを受け取る。</span><span class="sxs-lookup"><span data-stu-id="dd28d-144">You'll receive a prorated refund for the Microsoft 365 licenses that you no longer need.</span></span> <span data-ttu-id="dd28d-145">新しいプランを設定した約 2 日後に、銀行口座またはクレジット カードに課金されます。</span><span class="sxs-lookup"><span data-stu-id="dd28d-145">Your bank account or credit card will be charged about two days after you set up the new plan.</span></span>
  
## <a name="protect-user-devices-and-files"></a><span data-ttu-id="dd28d-146">ユーザー デバイスとファイルを保護する</span><span class="sxs-lookup"><span data-stu-id="dd28d-146">Protect user devices and files</span></span>

<span data-ttu-id="dd28d-147">Microsoft 365 Business Premium ライセンスが割り当てられたので、デバイスとファイルの保護を開始する手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="dd28d-147">Now that Microsoft 365 Business Premium licenses have been assigned, complete steps to start protecting devices and files.</span></span> <span data-ttu-id="dd28d-148">管理センターのナビゲーション ウィンドウに含まれるいくつかの新しいオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd28d-148">You'll use some new options included in the admin center navigation pane.</span></span>
  
1. <span data-ttu-id="dd28d-149">管理センターのナビゲーション ウィンドウで、[デバイス ポリシー] **に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="dd28d-149">In the admin center, in the navigation pane, go to **Devices** \> **Policies**.</span></span>

2. <span data-ttu-id="dd28d-150">[デバイス ポリシー **] ページで、[** 追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="dd28d-150">On the **Device policies** page, select **Add**.</span></span>

3. <span data-ttu-id="dd28d-151">[ポリシーの **追加]** ウィンドウで、ポリシーに名前 ([作業ファイルの保護] など) を指定し、ドロップダウン リストから [ポリシーの種類] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dd28d-151">In the **Add policy** pane give the policy a name (for example, Protect work files), and then choose a **Policy type** from the drop-down list.</span></span>

    <span data-ttu-id="dd28d-152">Android デバイスと iPhone デバイス、および Windows 10 でファイルを保護するためのアプリケーション ポリシーを設定し、会社所有の Windows 10 デバイスのデバイス構成ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="dd28d-152">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="dd28d-153">詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd28d-153">See the following links for details:</span></span>

    - [<span data-ttu-id="dd28d-154">Android または iOS デバイスのアプリ保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="dd28d-154">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)

    - [<span data-ttu-id="dd28d-155">Windows 10 デバイスのアプリケーション保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="dd28d-155">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)

    - [<span data-ttu-id="dd28d-156">Windows 10 PC のデバイス保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="dd28d-156">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)

4. <span data-ttu-id="dd28d-157">ポリシーを設定した後、ユーザーと従業員は次のデバイスを設定できます。</span><span class="sxs-lookup"><span data-stu-id="dd28d-157">After you set up policies, you and your employees can set up devices:</span></span>

    - <span data-ttu-id="dd28d-158">Windows デバイスで Windows Pro Creator 更新プログラムをまだ使用していない場合は [、Windows Pro Creators Update にアップグレードする必要があります](upgrade-to-windows-pro-creators-update.md)。</span><span class="sxs-lookup"><span data-stu-id="dd28d-158">If your Windows devices aren't already using the Windows Pro Creator update, you'll need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

    - <span data-ttu-id="dd28d-159">Windows [デバイスの手順については、「Microsoft 365 Business Premium](set-up-windows-devices.md) ユーザー向け Windows デバイスのセットアップ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd28d-159">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span>

    - <span data-ttu-id="dd28d-160">Android スマートフォンと iPhone [の手順については、「Microsoft 365 Business Premium](set-up-mobile-devices.md) ユーザー用のモバイル デバイスをセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd28d-160">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span>