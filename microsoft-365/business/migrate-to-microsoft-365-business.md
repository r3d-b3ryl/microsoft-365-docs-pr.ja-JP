---
title: Office 365 Business Premium からの Microsoft 365 Business へのアップグレード
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
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Office 365 Business Premium から Microsoft 365 Business にビジネスをアップグレードする手順。
ms.openlocfilehash: f3a25746cf123fa471c29084a62a6fcfc1542a02
ms.sourcegitcommit: f0a4290793e296474ecd3c6eb0ca96eae7faa434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2019
ms.locfileid: "38231413"
---
# <a name="upgrade-to-microsoft-365-business-from-office-365-business-premium"></a><span data-ttu-id="a1d43-103">Office 365 Business Premium からの Microsoft 365 Business へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="a1d43-103">Upgrade to Microsoft 365 Business from Office 365 Business Premium</span></span>

<span data-ttu-id="a1d43-104">Office [365 for business のサブスクリプション](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2)(たとえば、Office 365 business Premium) をご利用の場合は、Microsoft 365 business へのアップグレードが容易にできます。</span><span class="sxs-lookup"><span data-stu-id="a1d43-104">If you have an [Office 365 for business subscription](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), for example, Office 365 Business Premium, you can easily upgrade to Microsoft 365 Business.</span></span> <span data-ttu-id="a1d43-105">次のものを追加する場合は、Microsoft 365 Business にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="a1d43-105">Upgrade to Microsoft 365 Business if you want to add:</span></span> 
- <span data-ttu-id="a1d43-106">Windows 10 Pro (Windows 8 以降を実行している Pc に対して)</span><span class="sxs-lookup"><span data-stu-id="a1d43-106">Windows 10 Pro (to PCs running Windows 8 or later)</span></span>
- <span data-ttu-id="a1d43-107">デバイス上のビジネスデータを管理する単純なコントロール</span><span class="sxs-lookup"><span data-stu-id="a1d43-107">Simple controls that manage business data on devices</span></span>
- <span data-ttu-id="a1d43-108">高度なセキュリティ機能。</span><span class="sxs-lookup"><span data-stu-id="a1d43-108">Advanced security capabilities.</span></span>
<span data-ttu-id="a1d43-109">Microsoft 365 Business の詳細については、「 [Microsoft.com](https://www.microsoft.com/microsoft-365/business) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1d43-109">Find out more about Microsoft 365 Business at [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span></span>

## <a name="whats-the-difference-between-office-365-business-premium-and-microsoft-365-business"></a><span data-ttu-id="a1d43-110">Office 365 Business Premium と Microsoft 365 Business の違いは何ですか。</span><span class="sxs-lookup"><span data-stu-id="a1d43-110">What's the difference between Office 365 Business Premium and Microsoft 365 Business?</span></span>
<span data-ttu-id="a1d43-111">これらの2つのプランを[Microsoft 365 Business service の説明](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description)に並べて比較しました。</span><span class="sxs-lookup"><span data-stu-id="a1d43-111">We've added a side-by-side comparison of these two plans to the [Microsoft 365 Business service description](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span></span> 

## <a name="before-you-get-started"></a><span data-ttu-id="a1d43-112">開始する前に</span><span class="sxs-lookup"><span data-stu-id="a1d43-112">Before you get started</span></span>

- <span data-ttu-id="a1d43-113">**いつアップグレードを選択する必要がありますか。**</span><span class="sxs-lookup"><span data-stu-id="a1d43-113">**When should I choose upgrade?**</span></span> <span data-ttu-id="a1d43-114">アップグレードは、1つのプランに割り当てられた**すべてのユーザー**をアップグレードする場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="a1d43-114">Upgrade is the right choice when you want to upgrade **all users** assigned to a single plan.</span></span> <span data-ttu-id="a1d43-115">[アップグレード] を選択すると、すべてのプランユーザーが同時に別のプランに切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="a1d43-115">When you choose upgrade, all plan users get switched to another plan at the same time.</span></span> <span data-ttu-id="a1d43-116">1つのプランに割り当てられたすべてのユーザーをアップグレードしない場合は、新しいプラン (この場合は Microsoft 365 Business) のライセンスを購入し、アップグレードするユーザーごとに[これらのライセンスを個別に割り当て](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users)ます。</span><span class="sxs-lookup"><span data-stu-id="a1d43-116">If you don't want to upgrade everyone assigned to a single plan, buy licenses for the new plan (in this case Microsoft 365 Business), and [assign those licenses individually](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) to each user that you want to upgrade.</span></span> 
- <span data-ttu-id="a1d43-117">**一部のアドオンはアップグレードを妨げる可能性があります**アップグレードを開始しようとしていて、続行できないアドオンがある場合は、最初にアドオンを削除してから、後で必要に応じて追加することができます。</span><span class="sxs-lookup"><span data-stu-id="a1d43-117">**Some add-ons might prevent upgrade** If you try to start an upgrade and you have an add-on that prevents you from continuing, you can remove the add-on first, and then add it back later - if you still need it.</span></span> 
- <span data-ttu-id="a1d43-118">**プランを前払いした場合**プリペイドプランには、簡単なアップグレードパスはありません。</span><span class="sxs-lookup"><span data-stu-id="a1d43-118">**If you prepaid your plan** There isn't a straightforward upgrade path for prepaid plans.</span></span> <span data-ttu-id="a1d43-119">お客様は、ストアで購入したプロダクト ID を使用してプランを設定することにより、プリペイドプランを所有しているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a1d43-119">You'll know if you have a prepaid plan because you set up your plan using a product ID that you might have purchased in a store.</span></span> <span data-ttu-id="a1d43-120">パートナーに連絡するか、Microsoft ストアに移動するか、プリペイドプランの期限が切れて新しいプランに切り替えるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="a1d43-120">Contact a partner, go to the Microsoft store, or wait until your prepaid plan expires to switch to a new plan.</span></span>

## <a name="upgrade-to-microsoft-365-business"></a><span data-ttu-id="a1d43-121">Microsoft 365 Business へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="a1d43-121">Upgrade to Microsoft 365 Business</span></span>
<span data-ttu-id="a1d43-122">[新しい管理センター](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)で、次の手順を実行してライセンスを購入します。</span><span class="sxs-lookup"><span data-stu-id="a1d43-122">Buy your licenses by following these steps in the [new admin center](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview):</span></span>
1. <span data-ttu-id="a1d43-123">で<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="a1d43-123">Sign into the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="a1d43-124">ナビゲーションウィンドウに移動して、[ **Billing** \> **Products & Services**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a1d43-124">Go to the navigation pane and select **Billing** \> **Products & Services**.</span></span> <span data-ttu-id="a1d43-125">Office 365 サブスクリプションを検索し、それを選択して詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="a1d43-125">Find your Office 365 subscription and select it to view the details.</span></span> 

    ![スクリーンショットは、管理センターでサブスクリプションを検索して選択する方法を示しています。](media/FindYourSubscription.png)

3. <span data-ttu-id="a1d43-127">次のページで、[**アップグレード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a1d43-127">On the next page, select **Upgrade**.</span></span> 

      ![管理センターで、[アップグレード] を選択する場所がスクリーンショットに示されています。](media/SelectUpgrade.png)

  > [!NOTE]
  > <span data-ttu-id="a1d43-129">「Azure Active Directory でのサブスクリプションのアップグレードは、グループベースのライセンスでサポートされていません」というメッセージが表示される場合は、非常に大規模な組織でない限り、これは無視しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="a1d43-129">If you see a message that says "Upgrading your subscription is not supported with group-based licensing in Azure Active Directory", you can safely ignore this unless you have a very large organization.</span></span> <span data-ttu-id="a1d43-130">このオプションを選択した組織では、グループベースのライセンスを使用していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a1d43-130">Organizations who have selected this option will be aware that they're using group-based licensing.</span></span>

4. <span data-ttu-id="a1d43-131">次に、アップグレード可能な Office プランの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="a1d43-131">Next, you can view a list of Office plans that you can upgrade to.</span></span> <span data-ttu-id="a1d43-132">この場合は、Microsoft 365 のビジネスプランを検索してください。</span><span class="sxs-lookup"><span data-stu-id="a1d43-132">In this case, find the Microsoft 365 Business plan.</span></span> <span data-ttu-id="a1d43-133">このプランに含まれているすべての Office アプリとサービスを表示するには、下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="a1d43-133">You can scroll down if you want to see all the Office apps and services that are included with this plan.</span></span> <span data-ttu-id="a1d43-134">[ **Microsoft 365 business**] で、[**アップグレード**] を選択して、カートに microsoft 365 Business を追加します。</span><span class="sxs-lookup"><span data-stu-id="a1d43-134">Under **Microsoft 365 Business**, select **Upgrade** to add Microsoft 365 Business to your cart.</span></span>
5. <span data-ttu-id="a1d43-135">カート内:</span><span class="sxs-lookup"><span data-stu-id="a1d43-135">In the cart:</span></span>
    1. <span data-ttu-id="a1d43-136">すべての現在のユーザーのライセンスがカートに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="a1d43-136">We'll automatically include licenses for all your current users to the cart.</span></span> <span data-ttu-id="a1d43-137">より多くのライセンスが必要な場合は、[これらのライセンスを個別に購入して割り当てる](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users)必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1d43-137">If you need more, or less licenses, you'll need to [buy and assign those licenses individually](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users).</span></span>  
    2. <span data-ttu-id="a1d43-138">月々または年間の支払方法を調整できます。</span><span class="sxs-lookup"><span data-stu-id="a1d43-138">You can adjust how you'd like to pay - monthly or yearly.</span></span> <span data-ttu-id="a1d43-139">ドロップダウンメニューから選択します。</span><span class="sxs-lookup"><span data-stu-id="a1d43-139">Select the drop-down menu to make your choice.</span></span>
6. <span data-ttu-id="a1d43-140">[**チェックアウトへ移動**] を選択すると、このアカウントの支払い方法など、購入の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a1d43-140">Select **Go to Checkout** where you'll see a summary of your purchase, including the payment method for this account.</span></span> <span data-ttu-id="a1d43-141">また、プロモーションコードを用意している場合は、ここで追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="a1d43-141">You can also add a promo code here if you have one.</span></span>
7. <span data-ttu-id="a1d43-142">[**注文**] を選択して購入を完了します。</span><span class="sxs-lookup"><span data-stu-id="a1d43-142">Select **Place order** to complete your purchase.</span></span>
<span data-ttu-id="a1d43-143">新しいサービスプランを設定するには、Microsoft に数分かかります。</span><span class="sxs-lookup"><span data-stu-id="a1d43-143">It takes Microsoft a few minutes to set up your new service plans.</span></span> <span data-ttu-id="a1d43-144">進行状況を確認するには、[**アップグレード状態の確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a1d43-144">To check on progress, select **Check upgrade status**.</span></span> 
1. <span data-ttu-id="a1d43-145">プランの準備が整ったら、管理センターで追加のセットアップ手順を完了する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a1d43-145">Once your plan is ready, you might need to complete some additional setup steps in the admin center.</span></span> <span data-ttu-id="a1d43-146">ナビゲーションウィンドウで、[**ホーム**] を選択して、追加のセットアップ手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="a1d43-146">In the navigation pane, select **Home** to complete any additional setup steps.</span></span>

> [!NOTE]
> <span data-ttu-id="a1d43-147">不要になった Ofifce 365 ライセンスに対して、日割り計算が行われます。</span><span class="sxs-lookup"><span data-stu-id="a1d43-147">You'll receive a prorated refund for the Ofifce 365 licenses that you no longer need.</span></span> <span data-ttu-id="a1d43-148">銀行口座またはクレジットカードは、新しいプランを設定してから2日後に課金されます。</span><span class="sxs-lookup"><span data-stu-id="a1d43-148">Your bank account or credit card will be charged about two days after you set up the new plan.</span></span>
  
## <a name="protect-user-devices-and-files"></a><span data-ttu-id="a1d43-149">ユーザーのデバイスとファイルを保護する</span><span class="sxs-lookup"><span data-stu-id="a1d43-149">Protect user devices and files</span></span>

<span data-ttu-id="a1d43-150">これで、Microsoft 365 Business のライセンスが割り当てられました。次に、デバイスとファイルの保護を開始するための手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="a1d43-150">Now that Microsoft 365 Business licenses have been assigned, complete steps to start protecting devices and files.</span></span> <span data-ttu-id="a1d43-151">管理センターのナビゲーションウィンドウには、新しいオプションがいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="a1d43-151">You'll be using some new options included in the admin center navigation pane.</span></span>
  
1. <span data-ttu-id="a1d43-152">管理センターのナビゲーションウィンドウで、[**デバイス** \> **ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="a1d43-152">In the admin center, in the navigation pane, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="a1d43-153">[**デバイスポリシー** ] ページで、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a1d43-153">On the **Device policies** page, select **Add**.</span></span>
    
3. <span data-ttu-id="a1d43-154">[**ポリシーの追加**] ウィンドウで、ポリシーに名前 (たとえば、作業ファイルを保護する) を指定し、ドロップダウンから**ポリシーの種類**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a1d43-154">In the **Add policy** pane give the policy a name (for example, Protect work files), and then choose a **Policy type** from the drop-down.</span></span> 
    
    <span data-ttu-id="a1d43-155">Android および iPhone デバイス上のファイルを保護するためのアプリケーションポリシーおよび Windows 10 を設定し、会社が所有する Windows 10 デバイスのデバイス構成ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="a1d43-155">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="a1d43-156">詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1d43-156">See the following links for details:</span></span>
    
  - [<span data-ttu-id="a1d43-157">Android または iOS デバイスのアプリ保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="a1d43-157">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="a1d43-158">Windows 10 デバイスのアプリケーション保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="a1d43-158">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="a1d43-159">Windows 10 Pc のデバイス保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="a1d43-159">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
    
  
4. <span data-ttu-id="a1d43-160">ポリシーを設定すると、ユーザーはデバイスをセットアップできるようになります。</span><span class="sxs-lookup"><span data-stu-id="a1d43-160">After you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="a1d43-161">Windows デバイスが Windows Pro Creator の更新プログラムを使用していない場合は、[それらを Windows Pro Creator update にアップグレード](upgrade-to-windows-pro-creators-update.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1d43-161">If your Windows devices aren't already using the Windows Pro Creator update, you'll need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
    
  - <span data-ttu-id="a1d43-162">Windows デバイスの手順については、「 [Microsoft 365 Business ユーザーの windows デバイスをセットアップ](set-up-windows-devices.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1d43-162">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="a1d43-163">Android フォンおよび iPhones の手順については、「 [Microsoft 365 Business ユーザー向けのモバイルデバイスのセットアップ](set-up-mobile-devices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1d43-163">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 



