---
title: サブスクリプション ライセンスを管理する
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 36081d8d-b3fa-4948-8c34-e217bba825e1
description: Microsoft 365 for business のサブスクリプションでライセンスの追加と削除を行う方法を説明します。
ms.openlocfilehash: c4b2b30c9d444aad11ea4cd2faf8b2546e33c39c
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44404024"
---
# <a name="manage-subscription-licenses"></a><span data-ttu-id="4e4a0-103">サブスクリプション ライセンスを管理する</span><span class="sxs-lookup"><span data-stu-id="4e4a0-103">Manage subscription licenses</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="4e4a0-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-104">The admin center is changing.</span></span> <span data-ttu-id="4e4a0-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="4e4a0-106">以下の手順を使用すると、サブスクリプションのライセンスを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-106">You can add or remove licenses from your subscriptions using these steps.</span></span>

<span data-ttu-id="4e4a0-107">ユーザーに割り当てられているライセンスは、サブスクリプションから削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-107">You can't remove a license from a subscription if it's assigned to a user.</span></span> <span data-ttu-id="4e4a0-108">現在誰かに割り当てられているライセンスを削除する場合、先に[ユーザーからライセンスを削除](../../admin/manage/remove-licenses-from-users.md)しないと、サブスクリプションからそのライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-108">If you want to remove a license that is currently assigned to someone, you'll need to [remove licenses from users](../../admin/manage/remove-licenses-from-users.md) before you can remove the license from the subscription.</span></span>

## <a name="add-or-remove-licenses-for-your-business-subscription"></a><span data-ttu-id="4e4a0-109">一般法人向けスクリプションのライセンスを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="4e4a0-109">Add or remove licenses for your business subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4e4a0-110">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">お使いの製品</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-110">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="4e4a0-111">[**お使いの製品**] ページで、ライセンスを追加または削除するサブスクリプションを見つけ、[**ライセンスの追加/削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-111">On the **Your products** page, find the subscription to which you want to add or remove licenses, and then select **Add/Remove licenses**.</span></span>

    <span data-ttu-id="4e4a0-112">[[ライセンスの追加/削除] のリンクが表示されない場合](#what-if-i-dont-see-the-addremove-licenses-link)</span><span class="sxs-lookup"><span data-stu-id="4e4a0-112">[What if I don't see the Add/Remove licenses link?](#what-if-i-dont-see-the-addremove-licenses-link)</span></span>

3. <span data-ttu-id="4e4a0-113">[**ライセンスの総数**] ボックスにこのサブスクリプション用に必要なライセンスの総数を入力し、[**変更の送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-113">In the **Total licenses** box, enter the total number of licenses that you need for this subscription, and then select **Submit change**.</span></span> <span data-ttu-id="4e4a0-114">たとえば、100 のライセンスがあり、さらに 5 つ追加する必要がある場合は、105 と入力します。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-114">For example, if you have 100 licenses and you need to add 5 more, enter 105.</span></span> <span data-ttu-id="4e4a0-115">ライセンスを 5 つ削除する場合は、95 と入力します。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-115">If you want to remove 5 of them, enter 95.</span></span>

<span data-ttu-id="4e4a0-116">新しいライセンスを購入したら、購入した[ライセンス必ずユーザーに割り当てる](../../admin/manage/assign-licenses-to-users.md)ようにします。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-116">After you purchase new licenses, be sure to [assign the licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4e4a0-117">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-117">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="4e4a0-118">[**サブスクリプション**] ページで、ライセンスを追加または削除するサブスクリプションを選択し、[**ライセンスの追加/削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-118">On the **Subscriptions** page, select the subscription to which you want to add or remove licenses, and then select **Add/Remove licenses**.</span></span>

    <span data-ttu-id="4e4a0-119">[[ライセンスの追加/削除] のリンクが表示されない場合](#what-if-i-dont-see-the-addremove-licenses-link)</span><span class="sxs-lookup"><span data-stu-id="4e4a0-119">[What if I don't see the Add/Remove licenses link?](#what-if-i-dont-see-the-addremove-licenses-link)</span></span>

3. <span data-ttu-id="4e4a0-120">[**ライセンスの総数**] ボックスにこのサブスクリプション用に必要なライセンスの総数を入力し、[**送信**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-120">In the **Total licenses** box, enter the total number of licenses that you need for this subscription, and then select **Submit** \> **Close**.</span></span> <span data-ttu-id="4e4a0-121">たとえば、100 のライセンスがあり、さらに 5 つ追加する必要がある場合は、105 と入力します。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-121">For example, if you have 100 licenses and you need to add 5 more, enter 105.</span></span> <span data-ttu-id="4e4a0-122">ライセンスを 5 つ削除する場合は、95 と入力します。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-122">If you want to remove 5 of them, enter 95.</span></span>

<span data-ttu-id="4e4a0-123">新しいライセンスを購入したら、購入した[ライセンス必ずユーザーに割り当てる](../../admin/manage/assign-licenses-to-users.md)ようにします。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-123">After you purchase new licenses, be sure to [assign the licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4e4a0-124">管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-124">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="4e4a0-125">[**サブスクリプション**] ページで、ライセンスを追加または削除するサブスクリプションを選択し、[**ライセンスの追加/削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-125">On the **Subscriptions** page, select the subscription to which you want to add or remove licenses, and then select **Add/Remove licenses**.</span></span>

    <span data-ttu-id="4e4a0-126">[[ライセンスの追加/削除] のリンクが表示されない場合](#what-if-i-dont-see-the-addremove-licenses-link)</span><span class="sxs-lookup"><span data-stu-id="4e4a0-126">[What if I don't see the Add/Remove licenses link?](#what-if-i-dont-see-the-addremove-licenses-link)</span></span>

3. <span data-ttu-id="4e4a0-127">[**ライセンスの総数**] ボックスにこのサブスクリプション用に必要なライセンスの総数を入力し、[**送信**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-127">In the **Total licenses** box, enter the total number of licenses that you need for this subscription, and then select **Submit** \> **Close**.</span></span> <span data-ttu-id="4e4a0-128">たとえば、100 のライセンスがあり、さらに 5 つ追加する必要がある場合は、105 と入力します。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-128">For example, if you have 100 licenses and you need to add 5 more, enter 105.</span></span> <span data-ttu-id="4e4a0-129">ライセンスを 5 つ削除する場合は、95 と入力します。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-129">If you want to remove 5 of them, enter 95.</span></span>

<span data-ttu-id="4e4a0-130">新しいライセンスを購入したら、購入した[ライセンス必ずユーザーに割り当てる](../../admin/manage/assign-licenses-to-users.md)ようにします。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-130">After you purchase new licenses, be sure to [assign the licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>

::: moniker-end

## <a name="what-if-i-dont-see-the-addremove-licenses-link"></a><span data-ttu-id="4e4a0-131">[ライセンスの追加/削除] のリンクが表示されない場合</span><span class="sxs-lookup"><span data-stu-id="4e4a0-131">What if I don't see the Add/Remove licenses link?</span></span>

<span data-ttu-id="4e4a0-132">この表では、[**ライセンスの追加/削除**] のリンクが表示されない場合の理由と対処方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-132">This table describes the reasons why the **Add/Remove licenses** link might not be available, and what you can do about it.</span></span> 

|<span data-ttu-id="4e4a0-133">理由</span><span class="sxs-lookup"><span data-stu-id="4e4a0-133">Reason</span></span>  |<span data-ttu-id="4e4a0-134">説明</span><span class="sxs-lookup"><span data-stu-id="4e4a0-134">Description</span></span>  |<span data-ttu-id="4e4a0-135">解決方法</span><span class="sxs-lookup"><span data-stu-id="4e4a0-135">Solution</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="4e4a0-136">与信審査が保留中。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-136">A credit check is pending.</span></span> |<span data-ttu-id="4e4a0-137">与信審査が保留中の場合、"与信審査待ち" のメッセージが表示され、その与信審査が完了するまで、ライセンスの購入ができません。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-137">If a credit check is pending, you'll see a "Pending credit check" message, and you won't be able to buy licenses until the credit check is completed.</span></span>  | <span data-ttu-id="4e4a0-138">与信審査が完了しているかどうかをしばらく待ってから確認してください。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-138">Check back later to see if the credit check has completed.</span></span> <span data-ttu-id="4e4a0-139">通常、与信審査が完了するまで 2 営業日かかります。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-139">Credit checks typically take up to two working days to complete.</span></span><br><span data-ttu-id="4e4a0-140">与信審査が完了すると、[**ユーザー**] セクションに [**追加/削除**] のリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-140">After the credit check is complete, you should see the **Add/Remove licenses** link in the **Users** section.</span></span> <span data-ttu-id="4e4a0-141">表示されている場合、「[サブスクリプション ライセンスを管理する](#manage-subscription-licenses)」に移動します。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-141">If so, go to [Manage subscription licenses](#manage-subscription-licenses).</span></span> |
|<span data-ttu-id="4e4a0-142">プロダクト キーを使用してサブスクリプションをアクティベートした。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-142">You activated the subscription using a product key.</span></span>| <span data-ttu-id="4e4a0-143">25 桁のプロダクト キーを使用してサブスクリプションの購入とライセンス認証を行った場合、"前払" という文字が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-143">If the subscription was purchased and activated using a 25-character product key product key, you'll see the text "Prepaid".</span></span>  |<span data-ttu-id="4e4a0-144">「[プロダクト キーを使って支払われたサブスクリプションにライセンスを追加する](add-licenses-using-product-key.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-144">See [Add licenses to a subscription paid for using a product key](add-licenses-using-product-key.md).</span></span> |
|<span data-ttu-id="4e4a0-145">パートナーを通じてサブスクリプションを購入したため。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-145">You bought your subscription through a partner.</span></span> | <span data-ttu-id="4e4a0-146">パートナー経由でサブスクリプションを購入した場合、[ボリュームライセンスサービスセンター (VLSC)] リンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-146">If the subscription was purchased via a partner, you'll see the Volume Licensing Service Center (VLSC) link.</span></span> | <span data-ttu-id="4e4a0-147">「[ボリューム ライセンス サービス センター (VLSC) 経由で購入したサブスクリプションにライセンスを追加する](add-licenses-bought-through-vlsc.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-147">See [Add licenses to a subscription purchased through the Volume Licensing Service Center](add-licenses-bought-through-vlsc.md).</span></span> |
|<span data-ttu-id="4e4a0-148">再販業者を通じてサブスクリプションを購入した。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-148">You bought your subscription through a reseller.</span></span>|| <span data-ttu-id="4e4a0-149">クラウド ソリューション プロバイダー (CSP) パートナーを介してサブスクリプションを購入した場合、ライセンスを追加購入するには、その CSP パートナーに連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-149">If the subscription was purchased via a Cloud Solution Provider (CSP) partner, you must contact your CSP partner to buy more licenses.</span></span>        |
|<span data-ttu-id="4e4a0-150">試用版サブスクリプションを使用している。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-150">You have a trial subscription.</span></span> |<span data-ttu-id="4e4a0-151">Microsoft 365 の試用版には "使用版" という文字が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-151">A trial version of Microsoft 365 will display the text "Trial".</span></span> | <span data-ttu-id="4e4a0-152">まず、試用版サブスクリプションを買い上げる必要があります。その後、ライセンスを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-152">You must first buy your trial subscription, then you can add more licenses.</span></span> <span data-ttu-id="4e4a0-153">「[無料試用版から Microsoft 365 for business のサブスクリプションを購入する](../buy-a-subscription-from-your-free-trial.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-153">See [Buy a subscription to Microsoft 365 for business from your free trial](../buy-a-subscription-from-your-free-trial.md).</span></span>|

## <a name="what-you-need-to-know-about-buying-licenses-for-your-business-subscription"></a><span data-ttu-id="4e4a0-154">一般法人向けサブスクリプションのライセンスを購入する際に知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="4e4a0-154">What you need to know about buying licenses for your business subscription</span></span>

### <a name="buying-licenses"></a><span data-ttu-id="4e4a0-155">ライセンスの購入</span><span class="sxs-lookup"><span data-stu-id="4e4a0-155">Buying licenses</span></span>

- <span data-ttu-id="4e4a0-156">ライセンスを購入するには、グローバル管理者または課金管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-156">You need to be either a Global admin or a Billing admin to buy licenses.</span></span> <span data-ttu-id="4e4a0-157">詳細については、「[管理者ロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-157">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="4e4a0-158">ライセンスを購入し、同時にサブスクリプションに新しいユーザーを追加するには、「[Microsoft 365 にユーザーを個別に、またはまとめて追加する - 管理者向けヘルプ](../../admin/add-users/add-users.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-158">To buy a license and add a new user to your subscription at the same time, see [Add users individually or in bulk Microsoft 365 - Admin Help](../../admin/add-users/add-users.md).</span></span>

### <a name="license-availability"></a><span data-ttu-id="4e4a0-159">ライセンスを購入するための条件</span><span class="sxs-lookup"><span data-stu-id="4e4a0-159">License availability</span></span>

- <span data-ttu-id="4e4a0-p110">サブスクリプションの支払いにクレジット カードまたは銀行口座を使用している場合、購入した新しいライセンスは注文確認の受け取り直後に使用可能になります。請求書支払いの場合は、与信審査を待機する必要があり、その後で新しいライセンスが使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-p110">If you pay for your subscription by credit card or bank account, any new licenses that you buy are available immediately after you receive an order confirmation. If you pay by invoice, you might have to wait for a credit check before your new licenses are available to use.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4e4a0-162">一部の国または地域では、銀行口座引き落としによる支払いを利用できません。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-162">Paying by bank account is not available in some countries or regions.</span></span>

- <span data-ttu-id="4e4a0-163">プロダクト キーを使ってサブスクリプションを前払いしている場合は、クレジット カードまたは銀行口座を追加して新しいライセンスの追加料金を払うことで、ライセンスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-163">If you prepaid for your subscription with a product key, you can add more licenses by adding a credit card or bank account to cover the additional cost of the new licenses.</span></span> <span data-ttu-id="4e4a0-164">新しいライセンスを購入すると、追加した新しいライセンスの数を含む 2 つ目のサブスクリプションが追加されます。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-164">After you have purchased the new licenses, we add a second subscription with the number of new licenses that you just added.</span></span> <span data-ttu-id="4e4a0-165">たとえば、5 ライセンスのサブスクリプションを前払いしていて、その後さらに 10 ライセンスを購入した場合は、5 個の前払いライセンスを含むサブスクリプションと、10 個の新しいライセンスを含むサブスクリプションの 2 個のサブスクリプションを所有することになります。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-165">For example, if you have a prepaid subscription with 5 licenses, and then bought 10 more licenses, you will see two subscriptions listed: one with the five prepaid licenses, and one with the 10 new licenses.</span></span>

### <a name="billing-statements"></a><span data-ttu-id="4e4a0-166">請求明細書</span><span class="sxs-lookup"><span data-stu-id="4e4a0-166">Billing statements</span></span>

- <span data-ttu-id="4e4a0-167">クレジット カードまたは銀行口座で支払う場合、新しいライセンスの購入に対する請求は 2 日後にクレジット カードの明細に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-167">If you pay by credit card or bank account, the charge for buying new licenses will appear on your payment method in two days.</span></span>
- <span data-ttu-id="4e4a0-168">請求書で支払い場合、新しいライセンスの購入に対する請求は次の請求明細に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-168">If you pay by invoice, the charge for buying new licenses will appear on your next billing statement.</span></span>
- <span data-ttu-id="4e4a0-p112">請求期間の途中で新しいライセンスを購入した場合、最初の請求明細で一部だけ請求されることがあります。残りの金額は次の請求明細に含まれます。</span><span class="sxs-lookup"><span data-stu-id="4e4a0-p112">If you buy new licenses in the middle of your billing period, your first billing statement might have a partial charge. The remaining amount will be included on your next billing statement.</span></span>

## <a name="related-articles"></a><span data-ttu-id="4e4a0-171">関連記事</span><span class="sxs-lookup"><span data-stu-id="4e4a0-171">Related articles</span></span>

[<span data-ttu-id="4e4a0-172">サブスクリプションとライセンスを理解する</span><span class="sxs-lookup"><span data-stu-id="4e4a0-172">Understand subscriptions and licenses</span></span>](subscriptions-and-licenses.md)

[<span data-ttu-id="4e4a0-173">サブスクリプションのライセンスを購入する</span><span class="sxs-lookup"><span data-stu-id="4e4a0-173">Buy licenses for your subscription</span></span>](buy-licenses.md)

[<span data-ttu-id="4e4a0-174">別のサブスクリプションを購入する</span><span class="sxs-lookup"><span data-stu-id="4e4a0-174">Buy another subscription</span></span>](../buy-another-subscription.md)

[<span data-ttu-id="4e4a0-175">ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4e4a0-175">Assign licenses to users</span></span>](../../admin/manage/assign-licenses-to-users.md)

[<span data-ttu-id="4e4a0-176">Yammer ユーザー ライセンスを管理する</span><span class="sxs-lookup"><span data-stu-id="4e4a0-176">Manage Yammer user licenses</span></span>](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)
