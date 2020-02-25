---
title: Office 365 for business プランを手動で変更する
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
- M365-subscription-management
- Adm_O365
- commerce
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ROBOTS: NOINDEX
description: 新しいサブスクリプションを購入し、サブスクリプションとアクティブの両方が表示されていることを確認して、手動でサブスクリプションを変更します。
ms.openlocfilehash: 0042e0fd2fa5ac10be512246c252bc1d0f679709
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241890"
---
# <a name="change-plans-manually"></a><span data-ttu-id="6df95-103">プランを手動で変更する</span><span class="sxs-lookup"><span data-stu-id="6df95-103">Change plans manually</span></span>

> [!NOTE]
> <span data-ttu-id="6df95-104">この記事は、新しい管理センターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6df95-104">This article applies to the new admin center.</span></span> <span data-ttu-id="6df95-105">新しい管理センターは、Microsoft 365 のすべての管理者が利用でき、ホームページの上部にある [**新しい管理センター**の切り替え] を選択して選択することができます。</span><span class="sxs-lookup"><span data-stu-id="6df95-105">The new admin center is available to all Microsoft 365 admins, and you can opt in by selecting **Try the new admin center** toggle located at the top of the Home page.</span></span> <span data-ttu-id="6df95-106">詳細については、「[新しい Microsoft 365 管理センターについて](../../admin/microsoft-365-admin-center-preview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6df95-106">For more information, see [About the new Microsoft 365 admin center](../../admin/microsoft-365-admin-center-preview.md).</span></span> <span data-ttu-id="6df95-107">以前の管理センターに関する記事を表示するには、「 [Office 365 for business プランを手動で切り替える](switch-plans-manually.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6df95-107">To view the article about the old admin center, see [Switch Office 365 for business plans manually](switch-plans-manually.md).</span></span>

## <a name="step-1-decide-how-to-change-plans"></a><span data-ttu-id="6df95-108">手順 1: プランの変更方法を決定する</span><span class="sxs-lookup"><span data-stu-id="6df95-108">Step 1: Decide how to change plans</span></span>

<span data-ttu-id="6df95-109">すべてのユーザーを1つのプランから別のプランに変更するには[、[アップグレード] タブを使用](upgrade-to-different-plan.md)するのが最善の方法です。この方法は使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="6df95-109">The best way to change all your users from one plan to another is to [use the Upgrade tab](upgrade-to-different-plan.md). Sometimes this isn't possible.</span></span> <span data-ttu-id="6df95-110">代わりに、プランを手動で変更します。</span><span class="sxs-lookup"><span data-stu-id="6df95-110">Change plans manually instead:</span></span>

- <span data-ttu-id="6df95-111">[**アップグレード**] タブが表示されている場合は、現在のプランをアップグレードできません。</span><span class="sxs-lookup"><span data-stu-id="6df95-111">If the **Upgrade** tab indicates you can't upgrade the current plan.</span></span>

- <span data-ttu-id="6df95-112">[**アップグレード**] タブを選択すると、必要なプランが一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="6df95-112">If, when you select the **Upgrade** tab, the plan you want isn't listed.</span></span>

- <span data-ttu-id="6df95-113">すべてのユーザーを同じ方法でアップグレードしない場合。</span><span class="sxs-lookup"><span data-stu-id="6df95-113">If you don't want to upgrade all your users in the same way.</span></span> <span data-ttu-id="6df95-114">一部の企業では、さまざまなユーザーを異なるプランに加入させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6df95-114">Some businesses need different users subscribed to different plans.</span></span> <span data-ttu-id="6df95-115">これには手動による変更を使用してください。</span><span class="sxs-lookup"><span data-stu-id="6df95-115">Use a manual change for this.</span></span>

<span data-ttu-id="6df95-116">手動による変更を続行するには、このトピックの「[手順 2: 新しいサブスクリプションを購入](#step-2-buy-a-new-subscription)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6df95-116">To continue with a manual change, read [Step 2: Buy a new subscription](#step-2-buy-a-new-subscription) in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6df95-117">現在のプラン (ダウングレード) よりもデータ関連サービス数が少ないプランに変更する場合は、保持するデータを手動でバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6df95-117">If you are changing to a plan with fewer data-related services than your current plan (downgrading), you need to manually back up any data you wish to keep.</span></span> <span data-ttu-id="6df95-118">詳細については、「[ビジネスプランで O365 を切り替える前にデータをバックアップする](back-up-data-before-switching-plans.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6df95-118">For more information, see [Back up data before switching O365 for business plans](back-up-data-before-switching-plans.md).</span></span>

## <a name="step-2-buy-a-new-subscription"></a><span data-ttu-id="6df95-119">手順 2: 新しいサブスクリプションを購入する</span><span class="sxs-lookup"><span data-stu-id="6df95-119">Step 2: Buy a new subscription</span></span>

<span data-ttu-id="6df95-120">**購入済みですか?**</span><span class="sxs-lookup"><span data-stu-id="6df95-120">**Already purchased?**</span></span> <span data-ttu-id="6df95-121">ユーザーを移動するサブスクリプションが既にある場合は、この手順を省略して、このトピックの「[新しいサブスクリプションとライセンスを確認](#step-3-check-your-new-subscription-and-licenses)する」に進みます。</span><span class="sxs-lookup"><span data-stu-id="6df95-121">If you already have a subscription you want to move users to, skip this step and go to [Step 3: Check your new subscription and licenses](#step-3-check-your-new-subscription-and-licenses) in this topic.</span></span>

<span data-ttu-id="6df95-122">または</span><span class="sxs-lookup"><span data-stu-id="6df95-122">OR</span></span>

<span data-ttu-id="6df95-123">**新しいサブスクリプションとライセンスを購入する:** 「 [別の一般法人向け Office 365 を購入する](../buy-another-subscription.md)」の手順に従って新しいサブスクリプションを購入します。</span><span class="sxs-lookup"><span data-stu-id="6df95-123">**Purchase a new subscription and licenses:** Follow the steps in [Buy another Office 365 for business subscription](../buy-another-subscription.md) to buy a new subscription.</span></span>

<span data-ttu-id="6df95-124">必ずユーザーが現在所属している組織と同じ組織のサブスクリプションを購入してください。</span><span class="sxs-lookup"><span data-stu-id="6df95-124">Make sure you purchase a subscription for the same organization that the users are in now.</span></span> <span data-ttu-id="6df95-125">たとえば、移動する Office 365 ユーザーのメール アドレスを確認します。</span><span class="sxs-lookup"><span data-stu-id="6df95-125">For example, check the email addresses for the Office 365 users you want to move.</span></span> <span data-ttu-id="6df95-126">メールアドレスに contoso.com が\@含まれている場合は、contoso.com の新しいサブスクリプションを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6df95-126">If their email addresses include \@contoso.com, you must purchase a new subscription for contoso.com.</span></span>
<span data-ttu-id="6df95-127">移動する各ユーザーのライセンスを含めます。</span><span class="sxs-lookup"><span data-stu-id="6df95-127">Include a license for each user that you want to move.</span></span>

## <a name="step-3-check-your-new-subscription-and-licenses"></a><span data-ttu-id="6df95-128">手順 3: 新しいサブスクリプションとライセンスを確認する</span><span class="sxs-lookup"><span data-stu-id="6df95-128">Step 3: Check your new subscription and licenses</span></span>

1. <span data-ttu-id="6df95-129">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">製品とサービス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="6df95-129">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="6df95-130">**両方のサブスクリプションが一覧表示され、アクティブであることを確認する**ユーザーを移行するサブスクリプションと、ユーザーを移動するサブスクリプションが一緒に表示されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6df95-130">**Verify that both subscriptions are listed and active** The subscription that you're moving users from and the subscription that you're moving users to must be listed together.</span></span> <span data-ttu-id="6df95-131">最初に確認したときに新しいサブスクリプションが表示されない場合は、後でもう一度確認してみてください。</span><span class="sxs-lookup"><span data-stu-id="6df95-131">If the new subscription isn't there when you first check, try again later.</span></span> <span data-ttu-id="6df95-132">両方のサブスクリプションがアクティブであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6df95-132">Check that both subscriptions are active.</span></span> <span data-ttu-id="6df95-133">新しいサブスクリプションが一覧に表示されない、またはアクティブではない場合は[新しいサブスクリプションが一覧に表示されない、またはアクティブではない](#the-new-subscription-isnt-listed-or-isnt-active)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6df95-133">[The new subscription isn't listed, or isn't active](#the-new-subscription-isnt-listed-or-isnt-active).</span></span>

3. <span data-ttu-id="6df95-134">**ユーザーごとに十分な数のライセンスがあることを確認する**各ユーザーには、サブスクリプションに一致するライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="6df95-134">**Check that you have enough licenses for each user** Each user needs a license that matches their subscription.</span></span> <span data-ttu-id="6df95-135">このため、10 ユーザーを Office 365 Enterprise E5 に移動する場合は、10 個のライセンスが使用可能であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6df95-135">So if you want to move ten users to Office 365 Enterprise E5, you'll need to make sure ten licenses are available.</span></span>

4. <span data-ttu-id="6df95-136">**新しいサブスクリプションのライセンスがさらに必要ですか?**</span><span class="sxs-lookup"><span data-stu-id="6df95-136">**Need more licenses for the new subscription?**</span></span>
   <span data-ttu-id="6df95-137">[ **Products & services** ] ページに移動し、[ライセンスを購入](../licenses/buy-licenses.md)します。</span><span class="sxs-lookup"><span data-stu-id="6df95-137">Go to the **Products & services** page and [buy more licenses](../licenses/buy-licenses.md).</span></span>

> <span data-ttu-id="6df95-138">[古いライセンスの処理](#what-about-the-old-licenses)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6df95-138">[What about the old licenses?](#what-about-the-old-licenses)</span></span>

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a><span data-ttu-id="6df95-139">新しいサブスクリプションが一覧に表示されない、またはアクティブではない</span><span class="sxs-lookup"><span data-stu-id="6df95-139">The new subscription isn't listed, or isn't active</span></span>

- <span data-ttu-id="6df95-140">**2 つのサブスクリプションを購入し、両方とも一覧に表示されない場合** 、異なる組織 (異なるドメイン) 用に購入した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6df95-140">**If you purchased two subscriptions and they are not both listed here**, they may have been purchased for different organizations (for different domains).</span></span> <span data-ttu-id="6df95-141">サブスクリプションは組織の境界を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="6df95-141">Subscriptions can't cross organization boundaries.</span></span>

- <span data-ttu-id="6df95-142">**追加のサブスクリプションがあることがわかっ**ており、ここにリストされていない場合、またはアクティブでない場合は、 [Microsoft サポートにお問い合わせ](../../admin/contact-support-for-business-products.md)ください。</span><span class="sxs-lookup"><span data-stu-id="6df95-142">**If you know you have an additional subscription**, and it's not listed here, or is not active, [call Microsoft support](../../admin/contact-support-for-business-products.md).</span></span>

### <a name="what-about-the-old-licenses"></a><span data-ttu-id="6df95-143">古いライセンスの処理</span><span class="sxs-lookup"><span data-stu-id="6df95-143">What about the old licenses?</span></span>

<span data-ttu-id="6df95-144">現在のサブスクリプションのライセンスは後で削除されるので、それ以降は新しいユーザー ライセンスの料金のみを支払うことになります。</span><span class="sxs-lookup"><span data-stu-id="6df95-144">The licenses for the current subscription will be removed later; you'll only pay for the new user licenses from then on.</span></span>

## <a name="step-4-reassign-licenses"></a><span data-ttu-id="6df95-145">手順 4: ライセンスを再割り当てする</span><span class="sxs-lookup"><span data-stu-id="6df95-145">Step 4: Reassign licenses</span></span>

### <a name="reassign-a-license-for-one-user"></a><span data-ttu-id="6df95-146">1 人のユーザーのライセンスを再割り当てする</span><span class="sxs-lookup"><span data-stu-id="6df95-146">Reassign a license for one user</span></span>

1. <span data-ttu-id="6df95-147">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="6df95-147">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="6df95-148">[**アクティブなユーザー** ] ページで、ライセンスを割り当てるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6df95-148">On the **Active users** page, select the user to whom you want to assign a license.</span></span>

3. <span data-ttu-id="6df95-149">[**ライセンスとアプリ**] タブで、[**ライセンス**] を展開し、割り当てるライセンスのボックスを選択して、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6df95-149">On te **Licenses and Apps** tab, expand **Licenses**, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

### <a name="reassign-licenses-for-multiple-users-at-once"></a><span data-ttu-id="6df95-150">複数のユーザーのライセンスを一度に再割り当てする</span><span class="sxs-lookup"><span data-stu-id="6df95-150">Reassign licenses for multiple users at once</span></span>

1. <span data-ttu-id="6df95-151">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="6df95-151">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="6df95-152">既存のライセンスを置換するユーザーの名前の横にある円を選択します。</span><span class="sxs-lookup"><span data-stu-id="6df95-152">Select the circles next to the names of the users for whom you want to replace existing licenses.</span></span>

3. <span data-ttu-id="6df95-153">上部で、[**その他のオプション**(**...**)] を選択し、[**製品ライセンスの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6df95-153">At the top, select **More options** (**...**), and then choose **Manage product licenses**.</span></span>

4. <span data-ttu-id="6df95-154">Select **Replace existing product license assignments** \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="6df95-154">Select **Replace existing product license assignments** \> **Next**.</span></span>

5. <span data-ttu-id="6df95-155">これらのユーザーに割り当てる製品を [ **オン**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="6df95-155">Switch the toggle to the **On** position for the products you want to assign to these users.</span></span>

    > [!TIP]
    > - <span data-ttu-id="6df95-156">ユーザーが使用できるサービスを制限するには、そのユーザーで削除するサービスを [ **オフ**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="6df95-156">To limit which services are available to the user, switch to toggles to the **Off** position for the services that you want to remove for that user.</span></span> <span data-ttu-id="6df95-157">たとえば、Skype for Business Online 以外のすべてのサービスにユーザーがアクセスできるようにするには、Skype for Business Online サービスを [ **オフ**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="6df95-157">For example, if you want the user to have access to all available services except Skype for Business Online, you can switch the toggle for the Skype for Business Online service to the **Off** position.</span></span>
    > - <span data-ttu-id="6df95-158">選択したユーザーで以前に割り当てられたライセンスは削除されます。</span><span class="sxs-lookup"><span data-stu-id="6df95-158">Any previous license assignments for the selected users will be removed.</span></span>

6. <span data-ttu-id="6df95-159">[**既存の製品を置き換える**] ウィンドウの下部で、[**置換**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="6df95-159">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close**.</span></span>

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a><span data-ttu-id="6df95-160">手順 5: サブスクリプションをキャンセルするか、不要になったライセンスを削除する (オプション)</span><span class="sxs-lookup"><span data-stu-id="6df95-160">Step 5: Cancel subscriptions or remove licenses that you no longer need (Optional)</span></span>

<span data-ttu-id="6df95-161">1 つのサブスクリプションから別のサブスクリプションにすべてのユーザーを移動し、元のサブスクリプションが不要になった場合、[サブスクリプションをキャンセルする](cancel-your-subscription.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="6df95-161">If you moved all users from one subscription to another, and you no longer need the original subscription, you can [cancel the subscription](cancel-your-subscription.md).</span></span>

<span data-ttu-id="6df95-162">一部のユーザーのみを別のサブスクリプションに移動した場合は、不要になった[ライセンスを削除](../licenses/remove-licenses-from-subscription.md)します。</span><span class="sxs-lookup"><span data-stu-id="6df95-162">If you moved only some users to a different subscription, [remove licenses](../licenses/remove-licenses-from-subscription.md) that you no longer need.</span></span>

## <a name="call-support-to-help-you-change-plans"></a><span data-ttu-id="6df95-163">プランを変更するためのサポートへのお問い合わせ</span><span class="sxs-lookup"><span data-stu-id="6df95-163">Call support to help you change plans</span></span>
[<span data-ttu-id="6df95-164">Microsoft サポートに連絡する</span><span class="sxs-lookup"><span data-stu-id="6df95-164">Call Microsoft support</span></span>](../../admin/contact-support-for-business-products.md)