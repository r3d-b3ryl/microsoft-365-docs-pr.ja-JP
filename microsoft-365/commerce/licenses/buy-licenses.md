---
title: サブスクリプションのライセンスを管理する
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
- Adm_TOC
- commerce
ms.custom:
- SaRA
- okr_SMB
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 36081d8d-b3fa-4948-8c34-e217bba825e1
description: Office 365 for business サブスクリプションのライセンスを追加および削除する方法について説明します。
ms.openlocfilehash: 2f9c6b58a478b18fa1844c33689a8a4974a5917a
ms.sourcegitcommit: 0d7d18b045c9a14c943bc382b16715e67c86259a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2020
ms.locfileid: "42410044"
---
# <a name="manage-subscription-licenses"></a><span data-ttu-id="80511-103">サブスクリプションのライセンスを管理する</span><span class="sxs-lookup"><span data-stu-id="80511-103">Manage subscription licenses</span></span>

<span data-ttu-id="80511-104">次の手順を使用して、サブスクリプションのライセンスを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="80511-104">You can add or remove licenses from your subscriptions using these steps.</span></span>

<span data-ttu-id="80511-105">ユーザーに割り当てられているライセンスは、サブスクリプションから削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="80511-105">You can't remove a license from a subscription if it's assigned to a user.</span></span> <span data-ttu-id="80511-106">現在他のユーザーに割り当てられているライセンスを削除する場合は、サブスクリプションからライセンスを削除する前に、[ユーザーからライセンスを削除](../../admin/manage/remove-licenses-from-users.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80511-106">If you want to remove a license that is currently assigned to someone, you'll need to [remove licenses from users](../../admin/manage/remove-licenses-from-users.md) before you can remove the license from the subscription.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="80511-107">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="80511-107">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

## <a name="what-you-need-to-know-about-buying-licenses-for-your-business-subscription"></a><span data-ttu-id="80511-108">お客様のビジネス向けサブスクリプションのためのライセンス購入について知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="80511-108">What you need to know about buying licenses for your business subscription</span></span>

1. <span data-ttu-id="80511-109">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">製品とサービス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="80511-109">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="80511-110">[ **Products & services** ] ページで、ライセンスを追加または削除するサブスクリプションを検索し、[ライセンスの**追加/削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="80511-110">On the **Products & services** page, find the subscription to which you want to add or remove licenses, and then select **Add/Remove licenses**.</span></span>

    <span data-ttu-id="80511-111">[[ライセンスの追加/削除] のリンクが表示されない場合](#what-if-i-dont-see-the-addremove-licenses-link)</span><span class="sxs-lookup"><span data-stu-id="80511-111">[What if I don't see the Add/Remove licenses link?](#what-if-i-dont-see-the-addremove-licenses-link)</span></span>

3. <span data-ttu-id="80511-112">[**ライセンスの総数**] ボックスにこのサブスクリプション用に必要なライセンスの総数を入力し、[**変更の送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="80511-112">In the **Total licenses** box, enter the total number of licenses that you need for this subscription, and then select **Submit change**.</span></span> <span data-ttu-id="80511-113">たとえば、100 のライセンスがあり、さらに 5 つ追加する必要がある場合は、105 と入力します。</span><span class="sxs-lookup"><span data-stu-id="80511-113">For example, if you have 100 licenses and you need to add 5 more, enter 105.</span></span> <span data-ttu-id="80511-114">5個を削除する場合は、95と入力します。</span><span class="sxs-lookup"><span data-stu-id="80511-114">If you want to remove 5 of them, enter 95.</span></span>

<span data-ttu-id="80511-115">新しいライセンスを購入したら、必ず[ユーザーにライセンスを割り当て](../../admin/manage/assign-licenses-to-users.md)てください。</span><span class="sxs-lookup"><span data-stu-id="80511-115">After you purchase new licenses, be sure to [assign the licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="80511-116">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="80511-116">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="80511-117">[**サブスクリプション**] ページで、ライセンスを追加または削除するサブスクリプションを選択し、[ライセンスの**追加/削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="80511-117">On the **Subscriptions** page, select the subscription to which you want to add or remove licenses, and then select **Add/Remove licenses**.</span></span>

    <span data-ttu-id="80511-118">[[ライセンスの追加/削除] のリンクが表示されない場合](#what-if-i-dont-see-the-addremove-licenses-link)</span><span class="sxs-lookup"><span data-stu-id="80511-118">[What if I don't see the Add/Remove licenses link?](#what-if-i-dont-see-the-addremove-licenses-link)</span></span>

3. <span data-ttu-id="80511-119">[**ライセンスの総数**] ボックスに、このサブスクリプションに必要なライセンスの合計数を入力し、[ \*\*\*\* \> **閉じる**の送信] を選択します。</span><span class="sxs-lookup"><span data-stu-id="80511-119">In the **Total licenses** box, enter the total number of licenses that you need for this subscription, and then select **Submit** \> **Close**.</span></span> <span data-ttu-id="80511-120">たとえば、100 のライセンスがあり、さらに 5 つ追加する必要がある場合は、105 と入力します。</span><span class="sxs-lookup"><span data-stu-id="80511-120">For example, if you have 100 licenses and you need to add 5 more, enter 105.</span></span> <span data-ttu-id="80511-121">5個を削除する場合は、95と入力します。</span><span class="sxs-lookup"><span data-stu-id="80511-121">If you want to remove 5 of them, enter 95.</span></span>

<span data-ttu-id="80511-122">新しいライセンスを購入したら、必ず[ユーザーにライセンスを割り当て](../../admin/manage/assign-licenses-to-users.md)てください。</span><span class="sxs-lookup"><span data-stu-id="80511-122">After you purchase new licenses, be sure to [assign the licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="80511-123">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="80511-123">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="80511-124">[**サブスクリプション**] ページで、ライセンスを追加または削除するサブスクリプションを選択し、[ライセンスの**追加/削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="80511-124">On the **Subscriptions** page, select the subscription to which you want to add or remove licenses, and then select **Add/Remove licenses**.</span></span>

    <span data-ttu-id="80511-125">[[ライセンスの追加/削除] のリンクが表示されない場合](#what-if-i-dont-see-the-addremove-licenses-link)</span><span class="sxs-lookup"><span data-stu-id="80511-125">[What if I don't see the Add/Remove licenses link?](#what-if-i-dont-see-the-addremove-licenses-link)</span></span>

3. <span data-ttu-id="80511-126">[**ライセンスの総数**] ボックスに、このサブスクリプションに必要なライセンスの合計数を入力し、[ \*\*\*\* \> **閉じる**の送信] を選択します。</span><span class="sxs-lookup"><span data-stu-id="80511-126">In the **Total licenses** box, enter the total number of licenses that you need for this subscription, and then select **Submit** \> **Close**.</span></span> <span data-ttu-id="80511-127">たとえば、100 のライセンスがあり、さらに 5 つ追加する必要がある場合は、105 と入力します。</span><span class="sxs-lookup"><span data-stu-id="80511-127">For example, if you have 100 licenses and you need to add 5 more, enter 105.</span></span> <span data-ttu-id="80511-128">5個を削除する場合は、95と入力します。</span><span class="sxs-lookup"><span data-stu-id="80511-128">If you want to remove 5 of them, enter 95.</span></span>

<span data-ttu-id="80511-129">新しいライセンスを購入したら、必ず[ユーザーにライセンスを割り当て](../../admin/manage/assign-licenses-to-users.md)てください。</span><span class="sxs-lookup"><span data-stu-id="80511-129">After you purchase new licenses, be sure to [assign the licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>

::: moniker-end

## <a name="what-if-i-dont-see-the-addremove-licenses-link"></a><span data-ttu-id="80511-130">[ライセンスの追加/削除] のリンクが表示されない場合</span><span class="sxs-lookup"><span data-stu-id="80511-130">What if I don't see the Add/Remove licenses link?</span></span>

<span data-ttu-id="80511-131">次の表に、[**ライセンスの追加/削除**] リンクが使用できない可能性がある理由と、その方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="80511-131">This table describes the reasons why the **Add/Remove licenses** link might not be available, and what you can do about it.</span></span> 

|<span data-ttu-id="80511-132">理由</span><span class="sxs-lookup"><span data-stu-id="80511-132">Reason</span></span>  |<span data-ttu-id="80511-133">説明</span><span class="sxs-lookup"><span data-stu-id="80511-133">Description</span></span>  |<span data-ttu-id="80511-134">解決方法</span><span class="sxs-lookup"><span data-stu-id="80511-134">Solution</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="80511-135">信用度チェックが保留中です。</span><span class="sxs-lookup"><span data-stu-id="80511-135">A credit check is pending.</span></span> |<span data-ttu-id="80511-136">与信審査が保留中の場合、"与信審査待ち" のメッセージが表示され、その与信審査が完了するまで、ライセンスの購入ができません。</span><span class="sxs-lookup"><span data-stu-id="80511-136">If a credit check is pending, you'll see a "Pending credit check" message, and you won't be able to buy licenses until the credit check is completed.</span></span>  | <span data-ttu-id="80511-137">後で、与信審査が完了しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="80511-137">Check back later to see if the credit check has completed.</span></span> <span data-ttu-id="80511-138">通常、与信審査が完了するまで 2 営業日かかります。</span><span class="sxs-lookup"><span data-stu-id="80511-138">Credit checks typically take up to two working days to complete.</span></span><br><span data-ttu-id="80511-139">与信審査が完了したら、[ **ユーザー**] セクションに [ **ライセンスの追加/削除**] のリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="80511-139">After the credit check is complete, you should see the **Add/Remove licenses** link in the **Users** section.</span></span> <span data-ttu-id="80511-140">その場合は、「[サブスクリプションライセンスの管理](#manage-subscription-licenses)」にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="80511-140">If so, go to [Manage subscription licenses](#manage-subscription-licenses).</span></span> |
|<span data-ttu-id="80511-141">プロダクトキーを使用してサブスクリプションをアクティブ化しました。</span><span class="sxs-lookup"><span data-stu-id="80511-141">You activated the subscription using a product key.</span></span>| <span data-ttu-id="80511-142">サブスクリプションを購入し、25 桁のプロダクト キーでライセンス認証を行っていると、"プリペイド" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="80511-142">If the subscription was purchased and activated using a 25-character product key product key, you'll see the text "Prepaid".</span></span>  |<span data-ttu-id="80511-143">[プロダクトキーを使用して有料のサブスクリプションにライセンスを追加する](add-licenses-using-product-key.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80511-143">See [Add licenses to a subscription paid for using a product key](add-licenses-using-product-key.md).</span></span> |
|<span data-ttu-id="80511-144">パートナーを通じてサブスクリプションを購入した場合。</span><span class="sxs-lookup"><span data-stu-id="80511-144">You bought your subscription through a partner.</span></span> | <span data-ttu-id="80511-145">サブスクリプションがパートナー経由で購入されている場合、ボリューム ライセンス サービス センター (VLSC) のリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="80511-145">If the subscription was purchased via a partner, you'll see the Volume Licensing Service Center (VLSC) link.</span></span> | <span data-ttu-id="80511-146">[ボリュームライセンスサービスセンター経由で購入したサブスクリプションにライセンスを追加するを](add-licenses-bought-through-vlsc.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="80511-146">See [Add licenses to a subscription purchased through the Volume Licensing Service Center](add-licenses-bought-through-vlsc.md).</span></span> |
|<span data-ttu-id="80511-147">販売店からサブスクリプションを購入した場合。</span><span class="sxs-lookup"><span data-stu-id="80511-147">You bought your subscription through a reseller.</span></span>|| <span data-ttu-id="80511-148">クラウド ソリューション プロバイダー (CSP) パートナーを介してサブスクリプションを購入した場合、ライセンスを追加購入するには、その CSP パートナーに連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80511-148">If the subscription was purchased via a Cloud Solution Provider (CSP) partner, you must contact your CSP partner to buy more licenses.</span></span>        |
|<span data-ttu-id="80511-149">試用版サブスクリプションがあります。</span><span class="sxs-lookup"><span data-stu-id="80511-149">You have a trial subscription.</span></span> |<span data-ttu-id="80511-150">Office 365 の試用版では、"試用版" というテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="80511-150">A trial version of Office 365 will display the text "Trial".</span></span> | <span data-ttu-id="80511-151">最初に試用版サブスクリプションを購入する必要があります。その後、ライセンスを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="80511-151">You must first buy your trial subscription, then you can add more licenses.</span></span> <span data-ttu-id="80511-152">[無料の試用版から、「Office 365 for business のサブスクリプションを購入する](../buy-a-subscription-from-your-free-trial.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80511-152">See [Buy a subscription to Office 365 for business from your free trial](../buy-a-subscription-from-your-free-trial.md).</span></span>|

## <a name="what-you-need-to-know-about-buying-licenses-for-your-business-subscription"></a><span data-ttu-id="80511-153">お客様のビジネス向けサブスクリプションのためのライセンス購入について知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="80511-153">What you need to know about buying licenses for your business subscription</span></span>

### <a name="buying-licenses"></a><span data-ttu-id="80511-154">ライセンスを購入する</span><span class="sxs-lookup"><span data-stu-id="80511-154">Buying licenses</span></span>

- <span data-ttu-id="80511-155">ライセンスを購入するには、グローバル管理者または課金管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="80511-155">You need to be either a Global admin or a Billing admin to buy licenses.</span></span> <span data-ttu-id="80511-156">詳細については、「[管理者の役割につい](../../admin/add-users/about-admin-roles.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80511-156">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="80511-157">ライセンスを購入し、同時にサブスクリプションに新しいユーザーを追加するには、「[Office 365 にユーザーを個別に、またはまとめて追加する - 管理者向けヘルプ](../../admin/add-users/add-users.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80511-157">To buy a license and add a new user to your subscription at the same time, see [Add users individually or in bulk to Office 365 - Admin Help](../../admin/add-users/add-users.md).</span></span>

### <a name="license-availability"></a><span data-ttu-id="80511-158">ライセンスの可用性</span><span class="sxs-lookup"><span data-stu-id="80511-158">License availability</span></span>

- <span data-ttu-id="80511-p109">サブスクリプションの支払いにクレジット カードまたは銀行口座を使用している場合、購入した新しいライセンスは注文確認の受け取り直後に使用可能になります。請求書支払いの場合は、与信審査を待機する必要があり、その後で新しいライセンスが使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="80511-p109">If you pay for your subscription by credit card or bank account, any new licenses that you buy are available immediately after you receive an order confirmation. If you pay by invoice, you might have to wait for a credit check before your new licenses are available to use.</span></span>

  > [!NOTE]
  > <span data-ttu-id="80511-161">銀行口座による支払いは、一部の国や地域では使用できません。</span><span class="sxs-lookup"><span data-stu-id="80511-161">Paying by bank account is not available in some countries or regions.</span></span>

- <span data-ttu-id="80511-162">プロダクトキーを使用してサブスクリプションを前払いした場合は、新しいライセンスの追加コストをカバーするクレジットカードまたは銀行口座を追加することによって、ライセンスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="80511-162">If you prepaid for your subscription with a product key, you can add more licenses by adding a credit card or bank account to cover the additional cost of the new licenses.</span></span> <span data-ttu-id="80511-163">新しいライセンスを購入すると、追加した新しいライセンスの数を含む 2 つ目のサブスクリプションが追加されます。</span><span class="sxs-lookup"><span data-stu-id="80511-163">After you have purchased the new licenses, we add a second subscription with the number of new licenses that you just added.</span></span> <span data-ttu-id="80511-164">たとえば、5 ライセンスのサブスクリプションを前払いしていて、その後さらに 10 ライセンスを購入した場合は、5 個の前払いライセンスを含むサブスクリプションと、10 個の新しいライセンスを含むサブスクリプションの 2 個のサブスクリプションを所有することになります。</span><span class="sxs-lookup"><span data-stu-id="80511-164">For example, if you have a prepaid subscription with 5 licenses, and then bought 10 more licenses, you will see two subscriptions listed: one with the five prepaid licenses, and one with the 10 new licenses.</span></span>

### <a name="billing-statements"></a><span data-ttu-id="80511-165">請求明細書</span><span class="sxs-lookup"><span data-stu-id="80511-165">Billing statements</span></span>

- <span data-ttu-id="80511-166">クレジット カードまたは銀行口座で支払う場合、新しいライセンスの購入に対する請求は 2 日後にクレジット カードの明細に表示されます。</span><span class="sxs-lookup"><span data-stu-id="80511-166">If you pay by credit card or bank account, the charge for buying new licenses will appear on your payment method in two days.</span></span>
- <span data-ttu-id="80511-167">請求書で支払い場合、新しいライセンスの購入に対する請求は次の請求明細に表示されます。</span><span class="sxs-lookup"><span data-stu-id="80511-167">If you pay by invoice, the charge for buying new licenses will appear on your next billing statement.</span></span>
- <span data-ttu-id="80511-p111">請求期間の途中で新しいライセンスを購入した場合、最初の請求明細で一部だけ請求されることがあります。残りの金額は次の請求明細に含まれます。</span><span class="sxs-lookup"><span data-stu-id="80511-p111">If you buy new licenses in the middle of your billing period, your first billing statement might have a partial charge. The remaining amount will be included on your next billing statement.</span></span>

## <a name="related-articles"></a><span data-ttu-id="80511-170">関連記事</span><span class="sxs-lookup"><span data-stu-id="80511-170">Related articles</span></span>

[<span data-ttu-id="80511-171">サブスクリプションとライセンスを理解する</span><span class="sxs-lookup"><span data-stu-id="80511-171">Understand subscriptions and licenses</span></span>](subscriptions-and-licenses.md)

[<span data-ttu-id="80511-172">サブスクリプションのライセンスを購入する</span><span class="sxs-lookup"><span data-stu-id="80511-172">Buy licenses for your subscription</span></span>](buy-licenses.md)

[<span data-ttu-id="80511-173">別のサブスクリプションを購入する</span><span class="sxs-lookup"><span data-stu-id="80511-173">Buy another subscription</span></span>](../buy-another-subscription.md)

[<span data-ttu-id="80511-174">ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="80511-174">Assign licenses to users</span></span>](../../admin/manage/assign-licenses-to-users.md)

[<span data-ttu-id="80511-175">Yammer ユーザー ライセンスを管理する</span><span class="sxs-lookup"><span data-stu-id="80511-175">Manage Yammer user licenses</span></span>](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)
