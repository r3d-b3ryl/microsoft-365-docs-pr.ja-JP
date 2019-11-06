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
ms.openlocfilehash: 1e337b908f848da1d33cbd8e662652550d302b14
ms.sourcegitcommit: 0fa897d06b664c0ed005817752da1426d4ee17cb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "38002129"
---
# <a name="upgrade-to-microsoft-365-business-from-office-365-business-premium"></a><span data-ttu-id="44d0a-103">Office 365 Business Premium からの Microsoft 365 Business へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="44d0a-103">Upgrade to Microsoft 365 Business from Office 365 Business Premium</span></span>

<span data-ttu-id="44d0a-104">Office [365 for business のサブスクリプション](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2)(たとえば、Office 365 business Premium) をご利用の場合は、Microsoft 365 business へのアップグレードが容易にできます。</span><span class="sxs-lookup"><span data-stu-id="44d0a-104">If you have an [Office 365 for business subscription](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), for example, Office 365 Business Premium, you can easily upgrade to Microsoft 365 Business.</span></span> <span data-ttu-id="44d0a-105">次のものを追加する場合は、Microsoft 365 Business にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="44d0a-105">Upgrade to Microsoft 365 Business if you want to add:</span></span> 
- <span data-ttu-id="44d0a-106">Windows 10 Pro (Windows 8 以降を実行している Pc に対して)</span><span class="sxs-lookup"><span data-stu-id="44d0a-106">Windows 10 Pro (to PCs running Windows 8 or later)</span></span>
- <span data-ttu-id="44d0a-107">デバイス上のビジネスデータを管理する単純なコントロール</span><span class="sxs-lookup"><span data-stu-id="44d0a-107">Simple controls that manage business data on devices</span></span>
- <span data-ttu-id="44d0a-108">高度なセキュリティ機能。</span><span class="sxs-lookup"><span data-stu-id="44d0a-108">Advanced security capabilities.</span></span>
<span data-ttu-id="44d0a-109">Microsoft 365 Business の詳細については、「 [Microsoft.com](https://www.microsoft.com/microsoft-365/business) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44d0a-109">Find out more about Microsoft 365 Business at [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span></span>

## <a name="whats-the-difference-between-office-365-business-premium-and-microsoft-365-business"></a><span data-ttu-id="44d0a-110">Office 365 Business Premium と Microsoft 365 Business の違いは何ですか。</span><span class="sxs-lookup"><span data-stu-id="44d0a-110">What's the difference between Office 365 Business Premium and Microsoft 365 Business?</span></span>
<span data-ttu-id="44d0a-111">これらの2つのプランを[Microsoft 365 Business service の説明](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description)に並べて比較しました。</span><span class="sxs-lookup"><span data-stu-id="44d0a-111">We've added a side-by-side comparison of these two plans to the [Microsoft 365 Business service description](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span></span> 

1. <span data-ttu-id="44d0a-112">新しいライセンスを購入すると、これが初めての場合は、Microsoft 365 Business のセットアップバナーが管理センターの一番上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="44d0a-112">Once you have purchased new licenses, and this is the first time you did, the setup banner for Microsoft 365 Business will display on top of the admin center.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="44d0a-113">セットアップバナーは新しいユーザーを追加し、新しいドメインを追加して、新しいユーザーのメールを移行する機会です。</span><span class="sxs-lookup"><span data-stu-id="44d0a-113">The setup banner is an opportunity to add new users, a new domain, and migrate email for new users.</span></span> <span data-ttu-id="44d0a-114">この操作を行わない場合でも、ウィザードを使用して [既定のオプション] を選択し、管理者のホームページから非表示にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="44d0a-114">If you don't plan to do any, you should still go through the wizard and choose default options to make it disappear from the admin home page.</span></span> 
  
   ![Microsoft 365 Business で [セットアップの開始] を選択して、バナーをセットアップする準備ができました。](media/8d3b0d97-7cca-497f-9364-4b00ad670209.png)
  
    <span data-ttu-id="44d0a-116">[ **セットアップの開始**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="44d0a-116">Choose **Start setup**.</span></span>
    
2. <span data-ttu-id="44d0a-117">[**サインインとメールのカスタマイズ**] ページで、この機会を使用してサブスクリプションに別のドメインを追加する場合は、[**既に所有し**ているドメインの接続] を選択してドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="44d0a-117">On the **Personalize your sign-in and email** page, you can add a domain by choosing **Connect a domain you already own** if you want to use this opportunity to add another domain to your subscription.</span></span> 
    
    <span data-ttu-id="44d0a-118">既にドメインを設定している場合は、2番目のフィールドには、**メールの**_ドメイン名_\> **を使用し続けて** \<サインインするように指示します。  </span><span class="sxs-lookup"><span data-stu-id="44d0a-118">If you have already set up a domain, the second field will indicate that and will say **Continue using** \<  _your domain name_\> **for email and signing in**.</span></span> <span data-ttu-id="44d0a-119">サブスクリプションを使用してドメインをセットアップしていない場合は **、引き続き** \<_会社の name.onmicrosoft.com_ \>を使用して**電子メールを送信**し、サインインしてください。  </span><span class="sxs-lookup"><span data-stu-id="44d0a-119">If you haven't set up a domain with you subscription, it will say **Continue using** \<  _your company name.onmicrosoft.com_\> **for email and signing in**.</span></span>
    
    <span data-ttu-id="44d0a-120">**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="44d0a-120">Choose **Next**.</span></span>
    
    ![[サインインとメールのカスタマイズ] ページで、ドメインを追加するか、使用しているドメインを使用するかを選択します。](media/c3f5cfb2-1189-4d2f-803b-c9feb008a7a3.png)
  
3. <span data-ttu-id="44d0a-122">[新しい**ユーザーの追加**] ページで、新しいユーザーを追加することができます。これには、Microsoft 365 Business のライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="44d0a-122">On the **Add new users** page, you can add new users, if you have new employees that you want to assign the Microsoft 365 Business licenses to.</span></span> 
    
    <span data-ttu-id="44d0a-123">新しい従業員を追加して、既存のユーザーにライセンスを割り当てる場合は、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="44d0a-123">If you don't have new employees to add and want to assign licences to existing users, choose **Next**.</span></span>
    
4. <span data-ttu-id="44d0a-124">[**メールメッセージの移行**] ページで、手順3で追加した新しいユーザーのいずれかに対して電子メールを移行することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="44d0a-124">On the **Migrate email messages** page you can choose to migrate email for any of the new users you added in step 3.</span></span> <span data-ttu-id="44d0a-125">この手順は省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="44d0a-125">You can skip this step also.</span></span> <span data-ttu-id="44d0a-126">**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="44d0a-126">Choose **Next**.</span></span>
    
5. <span data-ttu-id="44d0a-127">最後のページで [**管理センターに移動**します] を選択して、セットアップを続行します。</span><span class="sxs-lookup"><span data-stu-id="44d0a-127">On the last page, choose **go to the admin center**, and continue setup there.</span></span>
    
6. <span data-ttu-id="44d0a-128">管理センターで、[**ユーザー** \> ] [**アクティブなユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="44d0a-128">In the admin center, go to **Users** \> **Active users**.</span></span>
    
7. <span data-ttu-id="44d0a-129">**Microsoft 365 Business** license を割り当てるユーザーを選択し、[**製品ライセンス**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="44d0a-129">Select the user to whom you want to assign the **Microsoft 365 Business** license to, and then choose **Edit** next to **Product Licenses**.</span></span>
    
    ![ユーザーカードで、[製品ライセンス] の横にある [編集] を選択します。](media/be0fe2d8-7ff8-447c-88f6-d212ed78451c.png)
  
## <a name="before-you-get-started"></a><span data-ttu-id="44d0a-131">開始する前に</span><span class="sxs-lookup"><span data-stu-id="44d0a-131">Before you get started</span></span>

- <span data-ttu-id="44d0a-132">**いつアップグレードを選択する必要がありますか。**</span><span class="sxs-lookup"><span data-stu-id="44d0a-132">**When should I choose upgrade?**</span></span> <span data-ttu-id="44d0a-133">アップグレードは、1つのプランに割り当てられた**すべてのユーザー**をアップグレードする場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="44d0a-133">Upgrade is the right choice when you want to upgrade **all users** assigned to a single plan.</span></span> <span data-ttu-id="44d0a-134">[アップグレード] を選択すると、すべてのプランユーザーが同時に別のプランに切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="44d0a-134">When you choose upgrade, all plan users get switched to another plan at the same time.</span></span> <span data-ttu-id="44d0a-135">1つのプランに割り当てられたすべてのユーザーをアップグレードしない場合は、新しいプラン (この場合は Microsoft 365 Business) のライセンスを購入し、アップグレードするユーザーごとに[これらのライセンスを個別に割り当て](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users)ます。</span><span class="sxs-lookup"><span data-stu-id="44d0a-135">If you don't want to upgrade everyone assigned to a single plan, buy licenses for the new plan (in this case Microsoft 365 Business), and [assign those licenses individually](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) to each user that you want to upgrade.</span></span> 
- <span data-ttu-id="44d0a-136">**一部のアドオンはアップグレードを妨げる可能性があります**アップグレードを開始しようとしていて、続行できないアドオンがある場合は、最初にアドオンを削除してから、後で必要に応じて追加することができます。</span><span class="sxs-lookup"><span data-stu-id="44d0a-136">**Some add-ons might prevent upgrade** If you try to start an upgrade and you have an add-on that prevents you from continuing, you can remove the add-on first, and then add it back later - if you still need it.</span></span> 
- <span data-ttu-id="44d0a-137">**プランを前払いした場合**プリペイドプランには、簡単なアップグレードパスはありません。</span><span class="sxs-lookup"><span data-stu-id="44d0a-137">**If you prepaid your plan** There isn't a straightforward upgrade path for prepaid plans.</span></span> <span data-ttu-id="44d0a-138">お客様は、ストアで購入したプロダクト ID を使用してプランを設定することにより、プリペイドプランを所有しているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="44d0a-138">You'll know if you have a prepaid plan because you set up your plan using a product ID that you might have purchased in a store.</span></span> <span data-ttu-id="44d0a-139">パートナーに連絡するか、Microsoft ストアに移動するか、プリペイドプランの期限が切れて新しいプランに切り替えるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="44d0a-139">Contact a partner, go to the Microsoft store, or wait until your prepaid plan expires to switch to a new plan.</span></span>

## <a name="upgrade-to-microsoft-365-business"></a><span data-ttu-id="44d0a-140">Microsoft 365 Business へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="44d0a-140">Upgrade to Microsoft 365 Business</span></span>
<span data-ttu-id="44d0a-141">[新しい管理センター](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)で、次の手順を実行してライセンスを購入します。</span><span class="sxs-lookup"><span data-stu-id="44d0a-141">Buy your licenses by following these steps in the [new admin center](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview):</span></span>
1. <span data-ttu-id="44d0a-142">で<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="44d0a-142">Sign into the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="44d0a-143">ナビゲーションウィンドウに移動して、[ **Billing** \> **Products & Services**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="44d0a-143">Go to the navigation pane and select **Billing** \> **Products & Services**.</span></span> <span data-ttu-id="44d0a-144">Office 365 サブスクリプションを検索し、それを選択して詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="44d0a-144">Find your Office 365 subscription and select it to view the details.</span></span> 

    ![スクリーンショットは、管理センターでサブスクリプションを検索して選択する方法を示しています。](media/FindYourSubscription.png)

3. <span data-ttu-id="44d0a-146">次のページで、[**アップグレード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="44d0a-146">On the next page, select **Upgrade**.</span></span> 

      ![管理センターで、[アップグレード] を選択する場所がスクリーンショットに示されています。](media/SelectUpgrade.png)

  > [!NOTE]
  > <span data-ttu-id="44d0a-148">「Azure Active Directory でのサブスクリプションのアップグレードは、グループベースのライセンスでサポートされていません」というメッセージが表示される場合は、非常に大規模な組織でない限り、これは無視しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="44d0a-148">If you see a message that says "Upgrading your subscription is not supported with group-based licensing in Azure Active Directory", you can safely ignore this unless you have a very large organization.</span></span> <span data-ttu-id="44d0a-149">このオプションを選択した組織では、グループベースのライセンスを使用していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="44d0a-149">Organizations who have selected this option will be aware that they're using group-based licensing.</span></span>

4. <span data-ttu-id="44d0a-150">次に、アップグレード可能な Office プランの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="44d0a-150">Next, you can view a list of Office plans that you can upgrade to.</span></span> <span data-ttu-id="44d0a-151">この場合は、Microsoft 365 のビジネスプランを検索してください。</span><span class="sxs-lookup"><span data-stu-id="44d0a-151">In this case, find the Microsoft 365 Business plan.</span></span> <span data-ttu-id="44d0a-152">このプランに含まれているすべての Office アプリとサービスを表示するには、下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="44d0a-152">You can scroll down if you want to see all the Office apps and services that are included with this plan.</span></span> <span data-ttu-id="44d0a-153">[ **Microsoft 365 business**] で、[**アップグレード**] を選択して、カートに microsoft 365 Business を追加します。</span><span class="sxs-lookup"><span data-stu-id="44d0a-153">Under **Microsoft 365 Business**, select **Upgrade** to add Microsoft 365 Business to your cart.</span></span>
5. <span data-ttu-id="44d0a-154">カート内:</span><span class="sxs-lookup"><span data-stu-id="44d0a-154">In the cart:</span></span>
    1. <span data-ttu-id="44d0a-155">すべての現在のユーザーのライセンスがカートに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="44d0a-155">We'll automatically include licenses for all your current users to the cart.</span></span> <span data-ttu-id="44d0a-156">より多くのライセンスが必要な場合は、[これらのライセンスを個別に購入して割り当てる](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users)必要があります。</span><span class="sxs-lookup"><span data-stu-id="44d0a-156">If you need more, or less licenses, you'll need to [buy and assign those licenses individually](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users).</span></span>  
    2. <span data-ttu-id="44d0a-157">月々または年間の支払方法を調整できます。</span><span class="sxs-lookup"><span data-stu-id="44d0a-157">You can adjust how you'd like to pay - monthly or yearly.</span></span> <span data-ttu-id="44d0a-158">ドロップダウンメニューから選択します。</span><span class="sxs-lookup"><span data-stu-id="44d0a-158">Select the drop-down menu to make your choice.</span></span>
6. <span data-ttu-id="44d0a-159">[**チェックアウトへ移動**] を選択すると、このアカウントの支払い方法など、購入の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="44d0a-159">Select **Go to Checkout** where you'll see a summary of your purchase, including the payment method for this account.</span></span> <span data-ttu-id="44d0a-160">また、プロモーションコードを用意している場合は、ここで追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="44d0a-160">You can also add a promo code here if you have one.</span></span>
7. <span data-ttu-id="44d0a-161">[**注文**] を選択して購入を完了します。</span><span class="sxs-lookup"><span data-stu-id="44d0a-161">Select **Place order** to complete your purchase.</span></span>
<span data-ttu-id="44d0a-162">新しいサービスプランを設定するには、Microsoft に数分かかります。</span><span class="sxs-lookup"><span data-stu-id="44d0a-162">It takes Microsoft a few minutes to set up your new service plans.</span></span> <span data-ttu-id="44d0a-163">進行状況を確認するには、[**アップグレード状態の確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="44d0a-163">To check on progress, select **Check upgrade status**.</span></span> 
1. <span data-ttu-id="44d0a-164">プランの準備が整ったら、管理センターで追加のセットアップ手順を完了する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="44d0a-164">Once your plan is ready, you might need to complete some additional setup steps in the admin center.</span></span> <span data-ttu-id="44d0a-165">ナビゲーションウィンドウで、[**ホーム**] を選択して、追加のセットアップ手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="44d0a-165">In the navigation pane, select **Home** to complete any additional setup steps.</span></span>

> [!NOTE]
> <span data-ttu-id="44d0a-166">不要になった Ofifce 365 ライセンスに対して、日割り計算が行われます。</span><span class="sxs-lookup"><span data-stu-id="44d0a-166">You'll receive a prorated refund for the Ofifce 365 licenses that you no longer need.</span></span> <span data-ttu-id="44d0a-167">銀行口座またはクレジットカードは、新しいプランを設定してから2日後に課金されます。</span><span class="sxs-lookup"><span data-stu-id="44d0a-167">Your bank account or credit card will be charged about two days after you set up the new plan.</span></span>
  
## <a name="protect-user-devices-and-files"></a><span data-ttu-id="44d0a-168">ユーザーのデバイスとファイルを保護する</span><span class="sxs-lookup"><span data-stu-id="44d0a-168">Protect user devices and files</span></span>

<span data-ttu-id="44d0a-169">これで、Microsoft 365 Business のライセンスが割り当てられました。次に、デバイスとファイルの保護を開始するための手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="44d0a-169">Now that Microsoft 365 Business licenses have been assigned, complete steps to start protecting devices and files.</span></span> <span data-ttu-id="44d0a-170">管理センターのナビゲーションウィンドウには、新しいオプションがいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="44d0a-170">You'll be using some new options included in the admin center navigation pane.</span></span>
  
1. <span data-ttu-id="44d0a-171">管理センターのナビゲーションウィンドウで、[**デバイス** \> **ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="44d0a-171">In the admin center, in the navigation pane, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="44d0a-172">[**デバイスポリシー** ] ページで、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="44d0a-172">On the **Device policies** page, select **Add**.</span></span>
    
3. <span data-ttu-id="44d0a-173">[**ポリシーの追加**] ウィンドウで、ポリシーに名前 (たとえば、作業ファイルを保護する) を指定し、ドロップダウンから**ポリシーの種類**を選択します。</span><span class="sxs-lookup"><span data-stu-id="44d0a-173">In the **Add policy** pane give the policy a name (for example, Protect work files), and then choose a **Policy type** from the drop-down.</span></span> 
    
    <span data-ttu-id="44d0a-174">Android および iPhone デバイス上のファイルを保護するためのアプリケーションポリシーおよび Windows 10 を設定し、会社が所有する Windows 10 デバイスのデバイス構成ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="44d0a-174">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="44d0a-175">詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="44d0a-175">See the following links for details:</span></span>
    
  - [<span data-ttu-id="44d0a-176">Android または iOS デバイスのアプリ保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="44d0a-176">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="44d0a-177">Windows 10 デバイスのアプリケーション保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="44d0a-177">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="44d0a-178">Windows 10 Pc のデバイス保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="44d0a-178">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
    
  
4. <span data-ttu-id="44d0a-179">ポリシーを設定すると、ユーザーはデバイスをセットアップできるようになります。</span><span class="sxs-lookup"><span data-stu-id="44d0a-179">After you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="44d0a-180">Windows デバイスが Windows Pro Creator の更新プログラムを使用していない場合は、[それらを Windows Pro Creator update にアップグレード](upgrade-to-windows-pro-creators-update.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44d0a-180">If your Windows devices aren't already using the Windows Pro Creator update, you'll need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
    
  - <span data-ttu-id="44d0a-181">Windows デバイスの手順については、「 [Microsoft 365 Business ユーザーの windows デバイスをセットアップ](set-up-windows-devices.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44d0a-181">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="44d0a-182">Android フォンおよび iPhones の手順については、「 [Microsoft 365 Business ユーザー向けのモバイルデバイスのセットアップ](set-up-mobile-devices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44d0a-182">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 



