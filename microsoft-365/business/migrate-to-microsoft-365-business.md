---
title: アップグレードして、Microsoft 365 Business PremiumからMicrosoft 365 Business Standard
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
description: ユーザーとユーザーのMicrosoft 365 Business StandardとMicrosoft 365 Business Premiumアップグレードする方法について説明Microsoft 365 Business Premium。
ms.openlocfilehash: 0968b877820590987f6f3ceca3efbd106b62cbd1
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2021
ms.locfileid: "52705492"
---
# <a name="upgrade-to-microsoft-365-business-premium-from-microsoft-365-business-standard"></a><span data-ttu-id="e48f0-103">アップグレードして、Microsoft 365 Business PremiumからMicrosoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="e48f0-103">Upgrade to Microsoft 365 Business Premium from Microsoft 365 Business Standard</span></span>

<span data-ttu-id="e48f0-104">たとえば、ビジネス サブスクリプションMicrosoft 365がある[場合は](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2)、Microsoft 365 Business Standardに簡単にアップグレードMicrosoft 365 Business Premium。</span><span class="sxs-lookup"><span data-stu-id="e48f0-104">If you have a [Microsoft 365 for business subscription](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), for example, Microsoft 365 Business Standard, you can easily upgrade to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="e48f0-105">追加する場合Microsoft 365 Business Premiumにアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="e48f0-105">Upgrade to Microsoft 365 Business Premium if you want to add:</span></span>

- <span data-ttu-id="e48f0-106">Windows 10 Pro (Windows 8以降を実行している PC へ)</span><span class="sxs-lookup"><span data-stu-id="e48f0-106">Windows 10 Pro (to PCs running Windows 8 or later)</span></span>

- <span data-ttu-id="e48f0-107">デバイス上のビジネス データを管理する簡単なコントロール</span><span class="sxs-lookup"><span data-stu-id="e48f0-107">Simple controls that manage business data on devices</span></span>

- <span data-ttu-id="e48f0-108">高度なセキュリティ機能。</span><span class="sxs-lookup"><span data-stu-id="e48f0-108">Advanced security capabilities.</span></span>
<span data-ttu-id="e48f0-109">詳細については、Microsoft 365 Business Premiumを参照[Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span><span class="sxs-lookup"><span data-stu-id="e48f0-109">Find out more about Microsoft 365 Business Premium at [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span></span>

## <a name="whats-the-difference-between-microsoft-365-business-standard-and-microsoft-365-business-premium"></a><span data-ttu-id="e48f0-110">データとデータの違いは何Microsoft 365 Business Standard Microsoft 365 Business Premium?</span><span class="sxs-lookup"><span data-stu-id="e48f0-110">What's the difference between Microsoft 365 Business Standard and Microsoft 365 Business Premium?</span></span>

<span data-ttu-id="e48f0-111">これら 2 つのプランのサイド バイ サイド比較を、サービスの説明にMicrosoft 365 Business Premium[しました](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description)。</span><span class="sxs-lookup"><span data-stu-id="e48f0-111">We've added a side-by-side comparison of these two plans to the [Microsoft 365 Business Premium Service Description](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="e48f0-112">始める前に</span><span class="sxs-lookup"><span data-stu-id="e48f0-112">Before you begin</span></span>

- <span data-ttu-id="e48f0-113">**アップグレードの選択が必要な場合**</span><span class="sxs-lookup"><span data-stu-id="e48f0-113">**When should I choose to upgrade?**</span></span> <span data-ttu-id="e48f0-114">1 つのプランに割り当てられているすべてのユーザーをアップグレードする場合は、アップグレードが適切な選択です。</span><span class="sxs-lookup"><span data-stu-id="e48f0-114">Upgrade is the right choice when you want to upgrade **all users** assigned to a single plan.</span></span> <span data-ttu-id="e48f0-115">アップグレードを選択すると、すべてのプラン ユーザーが同時に別のプランに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="e48f0-115">When you choose upgrade, all plan users get switched to another plan at the same time.</span></span> <span data-ttu-id="e48f0-116">1 つのプランに割り当てられているすべてのユーザーをアップグレードしない場合は、新しいプランのライセンス (この場合は Microsoft 365 Business Premium)[](../admin/manage/assign-licenses-to-users.md)を購入し、アップグレードする各ユーザーにライセンスを個別に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e48f0-116">If you don't want to upgrade everyone assigned to a single plan, buy licenses for the new plan (in this case Microsoft 365 Business Premium), and [assign those licenses individually](../admin/manage/assign-licenses-to-users.md) to each user that you want to upgrade.</span></span>

- <span data-ttu-id="e48f0-117">**一部のアドオンでアップグレードが妨げる場合があります** アップグレードを開始しようとして、続行を妨げるアドオンがある場合は、最初にアドオンを削除してから、必要な場合は後で追加し直します。</span><span class="sxs-lookup"><span data-stu-id="e48f0-117">**Some add-ons might prevent the upgrade** If you try to start an upgrade and you have an add-on that prevents you from continuing, you can remove the add-on first, and then add it back later if you still need it.</span></span>

- <span data-ttu-id="e48f0-118">**プランを前払いした場合** 前払いプランの簡単なアップグレード パスは提供されません。</span><span class="sxs-lookup"><span data-stu-id="e48f0-118">**If you prepaid your plan** There isn't a straightforward upgrade path for prepaid plans.</span></span> <span data-ttu-id="e48f0-119">ストアで購入した可能性がある製品 ID を使用してプランをセットアップした場合に、プリペイド プランを持っているかどうかが分かっています。</span><span class="sxs-lookup"><span data-stu-id="e48f0-119">You'll know if you have a prepaid plan because you set up your plan using a product ID that you might have purchased in a store.</span></span> <span data-ttu-id="e48f0-120">パートナーに連絡するか、Microsoft Storeに移動するか、プリペイド プランの有効期限が切れるまで待って新しいプランに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="e48f0-120">Contact a partner, go to the Microsoft Store, or wait until your prepaid plan expires to switch to a new plan.</span></span>

## <a name="upgrade-to-microsoft-365-business-premium"></a><span data-ttu-id="e48f0-121">アップグレードしてMicrosoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="e48f0-121">Upgrade to Microsoft 365 Business Premium</span></span>

1. <span data-ttu-id="e48f0-122">で管理センターにサインインします <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="e48f0-122">Sign into the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="e48f0-123">ナビゲーション ウィンドウに移動し、[製品の請求 **]** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e48f0-123">Go to the navigation pane and select **Billing** \> **Your products**.</span></span> <span data-ttu-id="e48f0-124">現在のサブスクリプションを検索し、選択して詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="e48f0-124">Find your current subscription and select it to view the details.</span></span>

3. <span data-ttu-id="e48f0-125">次のページで、[アップグレード] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e48f0-125">On the next page, select **Upgrade**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e48f0-126">Azure Active Directory でグループ ベースのライセンスでサブスクリプションのアップグレードがサポートされていないというメッセージ **が** 表示される場合は、非常に大規模な組織を持たない限り、これを無視しても問題なく無視できます。</span><span class="sxs-lookup"><span data-stu-id="e48f0-126">If you see a message that says **Upgrading your subscription is not supported with group-based licensing in Azure Active Directory**, you can safely ignore this unless you have a very large organization.</span></span> <span data-ttu-id="e48f0-127">このオプションを選択した組織は、グループ ベースのライセンスを使用しているのを認識します。</span><span class="sxs-lookup"><span data-stu-id="e48f0-127">Organizations who have selected this option will be aware that they're using group-based licensing.</span></span>

4. <span data-ttu-id="e48f0-128">次に、アップグレードできるプランの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e48f0-128">Next, you can view a list of plans that you can upgrade to.</span></span> <span data-ttu-id="e48f0-129">この場合は、次のプランMicrosoft 365 Business Premiumします。</span><span class="sxs-lookup"><span data-stu-id="e48f0-129">In this case, find the Microsoft 365 Business Premium plan.</span></span> <span data-ttu-id="e48f0-130">このプランに含まれるすべてのアプリとサービスを表示する場合は、下にスクロールできます。</span><span class="sxs-lookup"><span data-stu-id="e48f0-130">You can scroll down if you want to see all the apps and services that are included with this plan.</span></span> <span data-ttu-id="e48f0-131">**[Microsoft 365 Business Premium] で**、[**アップグレード] を** 選択してMicrosoft 365 Business Premiumカートに追加します。</span><span class="sxs-lookup"><span data-stu-id="e48f0-131">Under **Microsoft 365 Business Premium**, select **Upgrade** to add Microsoft 365 Business Premium to your cart.</span></span>

5. <span data-ttu-id="e48f0-132">カート内:</span><span class="sxs-lookup"><span data-stu-id="e48f0-132">In the cart:</span></span>

    1. <span data-ttu-id="e48f0-133">現在のすべてのユーザーのライセンスが自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="e48f0-133">We'll automatically include licenses for all your current users.</span></span> <span data-ttu-id="e48f0-134">複数または少ないライセンスが必要な場合は、それらのライセンスを個別に購入 [して割り当てる必要があります](../admin/manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="e48f0-134">If you need more or fewer licenses, you need to [buy and assign those licenses individually](../admin/manage/assign-licenses-to-users.md).</span></span>  
    2. <span data-ttu-id="e48f0-135">支払い方法を調整できます(月次または年払い)。</span><span class="sxs-lookup"><span data-stu-id="e48f0-135">You can adjust how you'd like to pay: monthly or yearly.</span></span> <span data-ttu-id="e48f0-136">ドロップダウン メニューを選択して選択します。</span><span class="sxs-lookup"><span data-stu-id="e48f0-136">Select the drop-down menu to make your choice.</span></span>

6. <span data-ttu-id="e48f0-137">[ **チェックアウトに移動]** を選択すると、このアカウントの支払い方法を含む購入の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e48f0-137">Select **Go to Checkout** where you'll see a summary of your purchase, including the payment method for this account.</span></span> <span data-ttu-id="e48f0-138">プロモーション コードがある場合は、ここにプロモーション コードを追加できます。</span><span class="sxs-lookup"><span data-stu-id="e48f0-138">You can also add a promo code here if you have one.</span></span>

7. <span data-ttu-id="e48f0-139">[ **注文の発注]** を選択して購入を完了します。</span><span class="sxs-lookup"><span data-stu-id="e48f0-139">Select **Place order** to complete your purchase.</span></span>\
<span data-ttu-id="e48f0-140">Microsoft が新しいサービス プランをセットアップするのに数分かかります。</span><span class="sxs-lookup"><span data-stu-id="e48f0-140">It takes Microsoft a few minutes to set up your new service plans.</span></span> <span data-ttu-id="e48f0-141">進行状況を確認するには、[アップグレードの状態を **確認する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e48f0-141">To check on progress, select **Check upgrade status**.</span></span>

8. <span data-ttu-id="e48f0-142">プランの準備ができたら、管理センターで追加のセットアップ手順を完了する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e48f0-142">When your plan is ready, you might need to complete some additional setup steps in the admin center.</span></span> <span data-ttu-id="e48f0-143">ナビゲーション ウィンドウで、[ホーム] を **選択** して、追加のセットアップ手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="e48f0-143">In the navigation pane, select **Home** to complete any additional setup steps.</span></span>

> [!NOTE]
> <span data-ttu-id="e48f0-144">不要になったライセンスに対して、日割Microsoft 365払い戻しを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="e48f0-144">You'll receive a prorated refund for the Microsoft 365 licenses that you no longer need.</span></span> <span data-ttu-id="e48f0-145">新しいプランを設定した約 2 日後に、銀行口座またはクレジット カードに課金されます。</span><span class="sxs-lookup"><span data-stu-id="e48f0-145">Your bank account or credit card will be charged about two days after you set up the new plan.</span></span>
  
## <a name="protect-user-devices-and-files"></a><span data-ttu-id="e48f0-146">ユーザー デバイスとファイルを保護する</span><span class="sxs-lookup"><span data-stu-id="e48f0-146">Protect user devices and files</span></span>

<span data-ttu-id="e48f0-147">ライセンスがMicrosoft 365 Business Premiumされたので、デバイスとファイルの保護を開始する手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="e48f0-147">Now that Microsoft 365 Business Premium licenses have been assigned, complete steps to start protecting devices and files.</span></span> <span data-ttu-id="e48f0-148">管理センターのナビゲーション ウィンドウに含まれるいくつかの新しいオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="e48f0-148">You'll use some new options included in the admin center navigation pane.</span></span>
  
1. <span data-ttu-id="e48f0-149">管理センターのナビゲーション ウィンドウで、[デバイス ポリシー] **に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="e48f0-149">In the admin center, in the navigation pane, go to **Devices** \> **Policies**.</span></span>

2. <span data-ttu-id="e48f0-150">[デバイス ポリシー **] ページで、[** 追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e48f0-150">On the **Device policies** page, select **Add**.</span></span>

3. <span data-ttu-id="e48f0-151">[ポリシーの **追加]** ウィンドウで、ポリシーに名前 ([作業ファイルの保護] など) を指定し、ドロップダウン リストから [ポリシーの種類] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e48f0-151">In the **Add policy** pane give the policy a name (for example, Protect work files), and then choose a **Policy type** from the drop-down list.</span></span>

    <span data-ttu-id="e48f0-152">Android デバイスと iPhone デバイス、および Windows 10 でファイルを保護するためのアプリケーション ポリシーを設定し、会社所有の Windows 10 デバイスのデバイス構成ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e48f0-152">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="e48f0-153">詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e48f0-153">See the following links for details:</span></span>

    - [<span data-ttu-id="e48f0-154">Android または iOS デバイスのアプリ保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="e48f0-154">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)

    - [<span data-ttu-id="e48f0-155">Windows 10 デバイスのアプリケーション保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="e48f0-155">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)

    - [<span data-ttu-id="e48f0-156">Pc のデバイス保護設定をWindows 10する</span><span class="sxs-lookup"><span data-stu-id="e48f0-156">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)

4. <span data-ttu-id="e48f0-157">ポリシーを設定した後、ユーザーと従業員は次のデバイスを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e48f0-157">After you set up policies, you and your employees can set up devices:</span></span>

    - <span data-ttu-id="e48f0-158">デバイスが Windows Creator 更新プログラムをまだ使用していない場合は、Windows Pro [Creators Update](upgrade-to-windows-pro-creators-update.md)にアップグレードWindows Pro必要があります。</span><span class="sxs-lookup"><span data-stu-id="e48f0-158">If your Windows devices aren't already using the Windows Pro Creator update, you'll need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

    - <span data-ttu-id="e48f0-159">デバイス[の手順については、「Windowsユーザー Microsoft 365 Business Premiumデバイス](set-up-windows-devices.md)をセットアップする」をWindowsしてください。</span><span class="sxs-lookup"><span data-stu-id="e48f0-159">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span>

    - <span data-ttu-id="e48f0-160">Android スマートフォンと iPhone[の手順については、「Microsoft 365 Business Premiumユーザー](set-up-mobile-devices.md)向けモバイル デバイスのセットアップ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e48f0-160">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span>