---
title: Microsoft 365 Business Standard からの Microsoft 365 Business Premium へのアップグレード
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
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Microsoft 365 Business Standard と Microsoft 365 Business Premium の違いと、Microsoft 365 Business Premium にアップグレードする方法について説明します。
ms.openlocfilehash: 20a4162f74a9cb0e943195a589fd2d964f773f48
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44045982"
---
# <a name="upgrade-to-microsoft-365-business-premium-from-microsoft-365-business-standard"></a><span data-ttu-id="334e6-103">Microsoft 365 Business Standard からの Microsoft 365 Business Premium へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="334e6-103">Upgrade to Microsoft 365 Business Premium from Microsoft 365 Business Standard</span></span>

<span data-ttu-id="334e6-104">Microsoft [365 for business のサブスクリプション](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2)(たとえば、Microsoft 365 business Standard) をお持ちの場合は、Microsoft 365 business Premium へのアップグレードが容易にできます。</span><span class="sxs-lookup"><span data-stu-id="334e6-104">If you have a [Microsoft 365 for business subscription](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), for example, Microsoft 365 Business Standard, you can easily upgrade to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="334e6-105">次のものを追加する場合は、Microsoft 365 Business Premium にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="334e6-105">Upgrade to Microsoft 365 Business Premium if you want to add:</span></span>

- <span data-ttu-id="334e6-106">Windows 10 Pro (Windows 8 以降を実行している Pc に対して)</span><span class="sxs-lookup"><span data-stu-id="334e6-106">Windows 10 Pro (to PCs running Windows 8 or later)</span></span>

- <span data-ttu-id="334e6-107">デバイス上のビジネスデータを管理する単純なコントロール</span><span class="sxs-lookup"><span data-stu-id="334e6-107">Simple controls that manage business data on devices</span></span>

- <span data-ttu-id="334e6-108">高度なセキュリティ機能。</span><span class="sxs-lookup"><span data-stu-id="334e6-108">Advanced security capabilities.</span></span>
<span data-ttu-id="334e6-109">Microsoft 365 Business Premium の詳細については、 [Microsoft.com](https://www.microsoft.com/microsoft-365/business)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="334e6-109">Find out more about Microsoft 365 Business Premium at [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span></span>

## <a name="whats-the-difference-between-microsoft-365-business-standard-and-microsoft-365-business-premium"></a><span data-ttu-id="334e6-110">Microsoft 365 Business Standard と Microsoft 365 Business Premium の違いは何ですか。</span><span class="sxs-lookup"><span data-stu-id="334e6-110">What's the difference between Microsoft 365 Business Standard and Microsoft 365 Business Premium?</span></span>

<span data-ttu-id="334e6-111">Microsoft では、これら2つのプランを[Microsoft 365 Business Premium サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description)に並べた比較を追加しました。</span><span class="sxs-lookup"><span data-stu-id="334e6-111">We've added a side-by-side comparison of these two plans to the [Microsoft 365 Business Premium Service Description](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span></span> 

## <a name="before-you-get-started"></a><span data-ttu-id="334e6-112">使用を開始する前に</span><span class="sxs-lookup"><span data-stu-id="334e6-112">Before you get started</span></span>

- <span data-ttu-id="334e6-113">**いつアップグレードを選択する必要がありますか。**</span><span class="sxs-lookup"><span data-stu-id="334e6-113">**When should I choose to upgrade?**</span></span> <span data-ttu-id="334e6-114">アップグレードは、1つのプランに割り当てられた**すべてのユーザー**をアップグレードする場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="334e6-114">Upgrade is the right choice when you want to upgrade **all users** assigned to a single plan.</span></span> <span data-ttu-id="334e6-115">[アップグレード] を選択すると、すべてのプランユーザーが同時に別のプランに切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="334e6-115">When you choose upgrade, all plan users get switched to another plan at the same time.</span></span> <span data-ttu-id="334e6-116">1つのプランに割り当てられたすべてのユーザーをアップグレードしない場合は、新しいプランのライセンスを購入し (この場合は Microsoft 365 Business Premium)、アップグレードする各ユーザーに[個別にこれらのライセンスを割り当て](../admin/manage/assign-licenses-to-users.md)ます。</span><span class="sxs-lookup"><span data-stu-id="334e6-116">If you don't want to upgrade everyone assigned to a single plan, buy licenses for the new plan (in this case Microsoft 365 Business Premium), and [assign those licenses individually](../admin/manage/assign-licenses-to-users.md) to each user that you want to upgrade.</span></span>

- <span data-ttu-id="334e6-117">**一部のアドオンでアップグレードができない場合がある**アップグレードを開始しようとしていて、続行できないアドオンがある場合は、最初にアドオンを削除してから、後で必要になったときに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="334e6-117">**Some add-ons might prevent the upgrade** If you try to start an upgrade and you have an add-on that prevents you from continuing, you can remove the add-on first, and then add it back later if you still need it.</span></span>

- <span data-ttu-id="334e6-118">**プランを前払いした場合**プリペイドプランには、簡単なアップグレードパスはありません。</span><span class="sxs-lookup"><span data-stu-id="334e6-118">**If you prepaid your plan** There isn't a straightforward upgrade path for prepaid plans.</span></span> <span data-ttu-id="334e6-119">お客様は、ストアで購入したプロダクト ID を使用してプランを設定することにより、プリペイドプランを所有しているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="334e6-119">You'll know if you have a prepaid plan because you set up your plan using a product ID that you might have purchased in a store.</span></span> <span data-ttu-id="334e6-120">パートナーに連絡するか、Microsoft ストアに移動するか、プリペイドプランの期限が切れて新しいプランに切り替えるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="334e6-120">Contact a partner, go to the Microsoft Store, or wait until your prepaid plan expires to switch to a new plan.</span></span>

## <a name="upgrade-to-microsoft-365-business-premium"></a><span data-ttu-id="334e6-121">Microsoft 365 Business Premium へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="334e6-121">Upgrade to Microsoft 365 Business Premium</span></span>

1. <span data-ttu-id="334e6-122">で<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="334e6-122">Sign into the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="334e6-123">ナビゲーションウィンドウに移動して、[**製品の\*\*\*\*請求** \> ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="334e6-123">Go to the navigation pane and select **Billing** \> **Your products**.</span></span> <span data-ttu-id="334e6-124">現在のサブスクリプションを検索し、それを選択して詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="334e6-124">Find your current subscription and select it to view the details.</span></span>

3. <span data-ttu-id="334e6-125">次のページで、[**アップグレード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="334e6-125">On the next page, select **Upgrade**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="334e6-126">**Azure Active Directory でのグループベースのライセンスでサブスクリプションのアップグレードがサポート**されていないというメッセージが表示された場合は、非常に大規模な組織でない限り、これは無視しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="334e6-126">If you see a message that says **Upgrading your subscription is not supported with group-based licensing in Azure Active Directory**, you can safely ignore this unless you have a very large organization.</span></span> <span data-ttu-id="334e6-127">このオプションを選択した組織では、グループベースのライセンスを使用していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="334e6-127">Organizations who have selected this option will be aware that they're using group-based licensing.</span></span>

4. <span data-ttu-id="334e6-128">次に、アップグレード可能なプランの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="334e6-128">Next, you can view a list of plans that you can upgrade to.</span></span> <span data-ttu-id="334e6-129">この場合は、Microsoft 365 Business Premium プランを検索してください。</span><span class="sxs-lookup"><span data-stu-id="334e6-129">In this case, find the Microsoft 365 Business Premium plan.</span></span> <span data-ttu-id="334e6-130">このプランに含まれているすべてのアプリとサービスを表示するには、下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="334e6-130">You can scroll down if you want to see all the apps and services that are included with this plan.</span></span> <span data-ttu-id="334e6-131">[ **Microsoft 365 Business premium**] で、[**アップグレード**] を選択して、カートに microsoft 365 Business premium を追加します。</span><span class="sxs-lookup"><span data-stu-id="334e6-131">Under **Microsoft 365 Business Premium**, select **Upgrade** to add Microsoft 365 Business Premium to your cart.</span></span>

5. <span data-ttu-id="334e6-132">カート内:</span><span class="sxs-lookup"><span data-stu-id="334e6-132">In the cart:</span></span>

    1. <span data-ttu-id="334e6-133">すべての現在のユーザーのライセンスが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="334e6-133">We'll automatically include licenses for all your current users.</span></span> <span data-ttu-id="334e6-134">ライセンスの数が増える場合は、[それらのライセンスを個別に購入して割り当てる](../admin/manage/assign-licenses-to-users.md)必要があります。</span><span class="sxs-lookup"><span data-stu-id="334e6-134">If you need more or fewer licenses, you need to [buy and assign those licenses individually](../admin/manage/assign-licenses-to-users.md).</span></span>  
    2. <span data-ttu-id="334e6-135">支払い方法は、月単位または年単位で調整できます。</span><span class="sxs-lookup"><span data-stu-id="334e6-135">You can adjust how you'd like to pay: monthly or yearly.</span></span> <span data-ttu-id="334e6-136">ドロップダウンメニューから選択します。</span><span class="sxs-lookup"><span data-stu-id="334e6-136">Select the drop-down menu to make your choice.</span></span>

6. <span data-ttu-id="334e6-137">[**チェックアウトへ移動**] を選択すると、このアカウントの支払い方法など、購入の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="334e6-137">Select **Go to Checkout** where you'll see a summary of your purchase, including the payment method for this account.</span></span> <span data-ttu-id="334e6-138">また、プロモーションコードを用意している場合は、ここで追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="334e6-138">You can also add a promo code here if you have one.</span></span>

7. <span data-ttu-id="334e6-139">[**注文**] を選択して購入を完了します。</span><span class="sxs-lookup"><span data-stu-id="334e6-139">Select **Place order** to complete your purchase.\</span></span>
<span data-ttu-id="334e6-140">新しいサービスプランを設定するには、Microsoft に数分かかります。</span><span class="sxs-lookup"><span data-stu-id="334e6-140">It takes Microsoft a few minutes to set up your new service plans.</span></span> <span data-ttu-id="334e6-141">進行状況を確認するには、[**アップグレード状態の確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="334e6-141">To check on progress, select **Check upgrade status**.</span></span>

8. <span data-ttu-id="334e6-142">プランの準備が整ったら、管理センターで追加のセットアップ手順を完了する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="334e6-142">When your plan is ready, you might need to complete some additional setup steps in the admin center.</span></span> <span data-ttu-id="334e6-143">ナビゲーションウィンドウで、[**ホーム**] を選択して、追加のセットアップ手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="334e6-143">In the navigation pane, select **Home** to complete any additional setup steps.</span></span>

> [!NOTE]
> <span data-ttu-id="334e6-144">不要になった Microsoft 365 ライセンスに対して、日割り計算が行われます。</span><span class="sxs-lookup"><span data-stu-id="334e6-144">You'll receive a prorated refund for the Microsoft 365 licenses that you no longer need.</span></span> <span data-ttu-id="334e6-145">銀行口座またはクレジットカードは、新しいプランを設定してから2日後に課金されます。</span><span class="sxs-lookup"><span data-stu-id="334e6-145">Your bank account or credit card will be charged about two days after you set up the new plan.</span></span>
  
## <a name="protect-user-devices-and-files"></a><span data-ttu-id="334e6-146">ユーザーのデバイスとファイルを保護する</span><span class="sxs-lookup"><span data-stu-id="334e6-146">Protect user devices and files</span></span>

<span data-ttu-id="334e6-147">Microsoft 365 Business Premium ライセンスが割り当てられたので、デバイスとファイルの保護を開始するための手順をすべて完了しました。</span><span class="sxs-lookup"><span data-stu-id="334e6-147">Now that Microsoft 365 Business Premium licenses have been assigned, complete steps to start protecting devices and files.</span></span> <span data-ttu-id="334e6-148">管理センターのナビゲーションウィンドウには、いくつかの新しいオプションを追加します。</span><span class="sxs-lookup"><span data-stu-id="334e6-148">You'll use some new options included in the admin center navigation pane.</span></span>
  
1. <span data-ttu-id="334e6-149">管理センターのナビゲーションウィンドウで、[**デバイス** \> **ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="334e6-149">In the admin center, in the navigation pane, go to **Devices** \> **Policies**.</span></span>

2. <span data-ttu-id="334e6-150">[**デバイスポリシー** ] ページで、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="334e6-150">On the **Device policies** page, select **Add**.</span></span>

3. <span data-ttu-id="334e6-151">[**ポリシーの追加**] ウィンドウで、ポリシーに名前 (たとえば、作業ファイルを保護する) を指定し、ドロップダウンリストから**ポリシーの種類**を選択します。</span><span class="sxs-lookup"><span data-stu-id="334e6-151">In the **Add policy** pane give the policy a name (for example, Protect work files), and then choose a **Policy type** from the drop-down list.</span></span>

    <span data-ttu-id="334e6-152">Android および iPhone デバイス上のファイルを保護するためのアプリケーションポリシーおよび Windows 10 を設定し、会社が所有する Windows 10 デバイスのデバイス構成ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="334e6-152">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="334e6-153">詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="334e6-153">See the following links for details:</span></span>

    - [<span data-ttu-id="334e6-154">Android または iOS デバイスのアプリ保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="334e6-154">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)

    - [<span data-ttu-id="334e6-155">Windows 10 デバイスのアプリケーション保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="334e6-155">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)

    - [<span data-ttu-id="334e6-156">Windows 10 Pc のデバイス保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="334e6-156">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)

4. <span data-ttu-id="334e6-157">ポリシーを設定すると、ユーザーはデバイスをセットアップできるようになります。</span><span class="sxs-lookup"><span data-stu-id="334e6-157">After you set up policies, you and your employees can set up devices:</span></span>

    - <span data-ttu-id="334e6-158">Windows デバイスが Windows Pro Creator の更新プログラムを使用していない場合は、[それらを Windows Pro Creator update にアップグレード](upgrade-to-windows-pro-creators-update.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="334e6-158">If your Windows devices aren't already using the Windows Pro Creator update, you'll need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

    - <span data-ttu-id="334e6-159">Windows デバイスの手順については、「 [Microsoft 365 Business Premium ユーザー向けに windows デバイスをセットアップする](set-up-windows-devices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="334e6-159">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span>

    - <span data-ttu-id="334e6-160">Android フォンおよび iPhones の手順については、「 [Microsoft 365 Business Premium ユーザー向けのモバイルデバイスのセットアップ](set-up-mobile-devices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="334e6-160">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span>