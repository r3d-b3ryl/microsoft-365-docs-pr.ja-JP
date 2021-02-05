---
title: 支払方法を管理する
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: Microsoft 365 管理センターで支払い方法を管理する方法について説明します。
ms.date: ''
ms.openlocfilehash: 6cba5e33ba99212cb6e67a90d1535120ccac3c38
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114851"
---
# <a name="manage-payment-methods"></a><span data-ttu-id="656f5-103">支払方法を管理する</span><span class="sxs-lookup"><span data-stu-id="656f5-103">Manage payment methods</span></span>

::: moniker range="o365-21vianet"
> [!NOTE]
> <span data-ttu-id="656f5-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="656f5-104">The admin center is changing.</span></span> <span data-ttu-id="656f5-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="656f5-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>
::: moniker-end

<span data-ttu-id="656f5-106">Microsoft からビジネス製品やサービスを購入する場合は、既存の支払い方法を使用するか、新しい支払い方法を追加できます。</span><span class="sxs-lookup"><span data-stu-id="656f5-106">When you buy business products or services from Microsoft, you can use an existing payment method, or add a new one.</span></span> <span data-ttu-id="656f5-107">購入した支払いには、クレジット カードやデビット カード、または銀行口座を使います。</span><span class="sxs-lookup"><span data-stu-id="656f5-107">You can use a credit or debit card, or bank account to pay for the things you buy.</span></span>

<span data-ttu-id="656f5-108">ビジネス アカウントに請求プロファイルが設定され、課金プロファイルの所有者または課金プロファイル投稿者である場合は、クレジット カードまたは請求書の支払いによって裏付けられている請求プロファイルを使用して、購入や請求書の支払いを行います。</span><span class="sxs-lookup"><span data-stu-id="656f5-108">If your business account has a billing profile, and you are a billing profile owner or billing profile contributor, you can use the billing profile that's backed by a credit card or invoice payment to make purchases or pay bills.</span></span> <span data-ttu-id="656f5-109">請求書マネージャーの場合は、課金プロファイルを使用して請求書を支払う必要があります。</span><span class="sxs-lookup"><span data-stu-id="656f5-109">If you're a billing invoice manager, you can only use a billing profile to pay bills.</span></span> <span data-ttu-id="656f5-110">請求プロファイルとロールの詳細については、「請求プロファイルの [管理」を参照してください](manage-billing-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="656f5-110">To learn more about billing profiles and roles, see [Manage billing profiles](manage-billing-profiles.md).</span></span>

<span data-ttu-id="656f5-111">ビジネス アカウントに請求プロファイルが設定されていない場合、グローバル管理者または課金管理者は、ビジネス アカウントに追加された銀行口座を管理して使用できます。</span><span class="sxs-lookup"><span data-stu-id="656f5-111">If your business account doesn't have a billing profile, any Global or Billing admin can manage and use any bank account that is added to the business account.</span></span> <span data-ttu-id="656f5-112">ただし、追加したクレジット カードのみを管理または使用できます。</span><span class="sxs-lookup"><span data-stu-id="656f5-112">However, you can only manage or use credit cards that you add.</span></span>

> [!NOTE]
> <span data-ttu-id="656f5-113">銀行口座を使って支払うオプションは、一部の国や地域では利用できません。</span><span class="sxs-lookup"><span data-stu-id="656f5-113">The option to pay with a bank account is not available in some countries or regions.</span></span>
>
> <span data-ttu-id="656f5-114">テナントと同じ国から発行された支払い方法を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="656f5-114">You must use a payment method issued from the same country as your tenant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="656f5-115">開始する前に</span><span class="sxs-lookup"><span data-stu-id="656f5-115">Before you begin</span></span>

<span data-ttu-id="656f5-116">この記事で説明されている手順を実行するには、全体管理者または課金管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="656f5-116">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="656f5-117">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="656f5-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="add-a-payment-method"></a><span data-ttu-id="656f5-118">支払い方法を追加する</span><span class="sxs-lookup"><span data-stu-id="656f5-118">Add a payment method</span></span>

<span data-ttu-id="656f5-119">支払い方法を追加しても、サブスクリプションは関連付けらなんか行わない。</span><span class="sxs-lookup"><span data-stu-id="656f5-119">Adding a payment method doesn't associate any subscriptions with it.</span></span> <span data-ttu-id="656f5-120">支払い方法に 1 つのサブスクリプションを割り当てるには、「1 つのサブスクリプションの支払い方法を [変更する」を参照してください](#change-a-payment-method-for-a-single-subscription)。</span><span class="sxs-lookup"><span data-stu-id="656f5-120">To assign a single subscription to the payment method, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span> <span data-ttu-id="656f5-121">別の支払い方法を使用しているすべてのサブスクリプションを新しい支払い方法に置き換える場合は、「支払い方法を置換 [する」を参照してください](#replace-a-payment-method)。</span><span class="sxs-lookup"><span data-stu-id="656f5-121">To replace all subscriptions that use another payment method with the new one, see [Replace a payment method](#replace-a-payment-method).</span></span>

1. <span data-ttu-id="656f5-122">管理センターで、[**課金情報**] > [**請求と支払い**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">支払方法</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="656f5-122">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="656f5-123">[**お支払方法の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="656f5-123">Select **Add a payment method**.</span></span>
3. <span data-ttu-id="656f5-124">[**支払い方法**] ページで、ドロップダウン メニューから支払い方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="656f5-124">On the **Payment methods** page, pick a payment method from the drop-down menu.</span></span>
4. <span data-ttu-id="656f5-125">新しいカードまたは銀行口座の情報を入力し、[追加] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="656f5-125">Enter the information for the new card or bank account, then select **Add**.</span></span>

## <a name="update-payment-method-details"></a><span data-ttu-id="656f5-126">支払い方法の詳細の更新</span><span class="sxs-lookup"><span data-stu-id="656f5-126">Update payment method details</span></span>

<span data-ttu-id="656f5-127">既存の支払い方法のクレジット カードまたはデビット カード、請求先住所、または有効期限日の名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="656f5-127">You can change the name on the credit or debit card, billing address, or expiration date for an existing payment method.</span></span> <span data-ttu-id="656f5-128">ただし、カードまたはアカウント番号は変更できません。</span><span class="sxs-lookup"><span data-stu-id="656f5-128">However, you can't change the card or account number.</span></span> <span data-ttu-id="656f5-129">アカウント番号が変更されている [場合は、](#replace-a-payment-method)別の支払い方法に置き換え、古い支払い方法 [を削除します](#delete-a-payment-method)。</span><span class="sxs-lookup"><span data-stu-id="656f5-129">If the account number has changed, [replace it with a different payment method](#replace-a-payment-method), and then [delete the old one](#delete-a-payment-method).</span></span>

1. <span data-ttu-id="656f5-130">管理センターで、[**課金情報**] > [**請求と支払い**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">支払方法</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="656f5-130">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="656f5-131">更新する支払い方法の行を選択します。</span><span class="sxs-lookup"><span data-stu-id="656f5-131">Select the row of the payment method to update.</span></span> <span data-ttu-id="656f5-132">右側のウィンドウで、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="656f5-132">In the right pane, select **Edit**.</span></span>
3. <span data-ttu-id="656f5-133">クレジット カードまたはデビット カードの名前、請求先住所、有効期限などのお支払い方法の情報を更新し、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="656f5-133">Update your payment method information, including the name on the credit or debit card, billing address, or expiration date, and then select **Save**.</span></span>

## <a name="replace-a-payment-method"></a><span data-ttu-id="656f5-134">支払い方法を置き換える</span><span class="sxs-lookup"><span data-stu-id="656f5-134">Replace a payment method</span></span>

<span data-ttu-id="656f5-135">支払い方法を置き換える場合は、同じ支払い方法を使用しているすべてのサブスクリプションと請求プロファイルで支払い方法を置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="656f5-135">When you replace a payment method, you replace it for all subscriptions and billing profiles that use the same payment method.</span></span> <span data-ttu-id="656f5-136">支払い方法を置換しても、既存の支払い方法は削除されます。</span><span class="sxs-lookup"><span data-stu-id="656f5-136">Replacing a payment method doesn't delete the existing payment method.</span></span> <span data-ttu-id="656f5-137">他のサブスクリプションや請求プロファイルを選択して使用できます。</span><span class="sxs-lookup"><span data-stu-id="656f5-137">It's still available for you to select and use for other subscriptions and billing profiles.</span></span>

<span data-ttu-id="656f5-138">1 つのサブスクリプションの支払い方法を変更するには、「1 つのサブスクリプションの支払い方法を [変更する」を参照してください](#change-a-payment-method-for-a-single-subscription)。</span><span class="sxs-lookup"><span data-stu-id="656f5-138">To change the payment method for a single subscription, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span>

1. <span data-ttu-id="656f5-139">管理センターで、**[課金]** > **[請求と支払い]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">[支払方法]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="656f5-139">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="656f5-140">変更する支払い方法の行を選択します。</span><span class="sxs-lookup"><span data-stu-id="656f5-140">Select the row of the payment method to replace.</span></span> <span data-ttu-id="656f5-141">右側のウィンドウには、選択した支払方法を使用する請求プロファイルと個々のサブスクリプションがすべて一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="656f5-141">The right pane lists all billing profiles and individual subscriptions that use the selected payment method.</span></span>
3. <span data-ttu-id="656f5-142">右側のウィンドウで、**[すべてのアイテムの支払方法を置き換える]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="656f5-142">In the right pane, select **Replace payment method for all items**.</span></span>
4. <span data-ttu-id="656f5-143">既存の支払い方法を使用する場合は、ドロップダウン リストからいずれかのオプションを選択して、**[置換]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="656f5-143">To use an existing payment method, choose one from the drop-down list, then select **Replace**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="656f5-144">請求プロファイルに関連付けられているサブスクリプションがある場合は、クレジット カードまたはデビット カードのみ支払いに使用できます。</span><span class="sxs-lookup"><span data-stu-id="656f5-144">If you have subscriptions associated with a billing profile, you can only use a credit or debit card to pay for them.</span></span> <span data-ttu-id="656f5-145">**[支払方法]** ページに銀行口座が表示されている場合は、ドロップダウン リストで選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="656f5-145">If you have bank accounts listed on the **Payment methods** page, they aren't available to select in the drop-down list.</span></span>
5. <span data-ttu-id="656f5-146">新しい支払方法を追加するには、**[支払方法の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="656f5-146">To add a new payment method, select **Add payment method**.</span></span>
6. <span data-ttu-id="656f5-147">**[支払方法の追加]** ウィンドウで、アカウント情報を入力し、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="656f5-147">In the **Add a payment method** pane, enter the account information, then select **Save**.</span></span> <span data-ttu-id="656f5-148">テナントと同じ国の支払い方法を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="656f5-148">You must use a payment method from the same country as your tenant.</span></span>
7. <span data-ttu-id="656f5-149">新しい支払い方法は、ドロップダウン リストで既に選択されています。</span><span class="sxs-lookup"><span data-stu-id="656f5-149">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="656f5-150">**[置換]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="656f5-150">Select **Replace**.</span></span>

## <a name="change-a-payment-method-for-a-single-subscription"></a><span data-ttu-id="656f5-151">1 つのサブスクリプションの支払い方法を変更する</span><span class="sxs-lookup"><span data-stu-id="656f5-151">Change a payment method for a single subscription</span></span>

<span data-ttu-id="656f5-152">1 つのサブスクリプションの支払い方法を変更できます。</span><span class="sxs-lookup"><span data-stu-id="656f5-152">You can change the payment method used to pay for a single subscription.</span></span>

1. <span data-ttu-id="656f5-153">管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="656f5-153">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="656f5-154">[製品 **] タブ** で、別の支払い方法で支払うサブスクリプションを探します。</span><span class="sxs-lookup"><span data-stu-id="656f5-154">On the **Products** tab, find the subscription that you want to pay for with the alternate payment method.</span></span>
3. <span data-ttu-id="656f5-155">その他 **のアクション (3** つのドット) を選択し、[支払い方法の置換 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="656f5-155">Select **More actions** (three dots), then select **Replace payment method**.</span></span>
4. <span data-ttu-id="656f5-156">[支払 **い方法の** 置換] ウィンドウのドロップダウン リストで、別の支払い方法を選択するか、支払い方法を追加します。</span><span class="sxs-lookup"><span data-stu-id="656f5-156">In the **Replace payment method** pane, from the drop-down list, choose an alternate payment method, or choose to add a payment method.</span></span>
5. <span data-ttu-id="656f5-157">支払い方法を追加する場合は、カードまたは口座の詳細を入力し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="656f5-157">If you add a payment method, enter the card or account details, then select **Save**.</span></span>
6. <span data-ttu-id="656f5-158">選択した支払い方法が正しいか確認し、[置換] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="656f5-158">Verify that the selected payment method is correct, then select **Replace**.</span></span>

## <a name="delete-a-payment-method"></a><span data-ttu-id="656f5-159">支払い方法を削除する</span><span class="sxs-lookup"><span data-stu-id="656f5-159">Delete a payment method</span></span>

<span data-ttu-id="656f5-160">削除できるのは、サブスクリプションまたは請求プロファイルに添付されていない支払い方法のみです。</span><span class="sxs-lookup"><span data-stu-id="656f5-160">You can only delete a payment method that isn't attached to a subscription or billing profile.</span></span> <span data-ttu-id="656f5-161">これは、状態に関して、すべてのサブスクリプションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="656f5-161">This applies to all subscriptions, whatever their status.</span></span>

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="656f5-162">サブスクリプションまたは請求プロファイルが添付されている支払い方法を削除する</span><span class="sxs-lookup"><span data-stu-id="656f5-162">Delete a payment method with no subscriptions or billing profiles attached</span></span>

<span data-ttu-id="656f5-163">支払い方法がサブスクリプションや請求プロファイルに関連付けされていない場合は、すぐに削除できます。</span><span class="sxs-lookup"><span data-stu-id="656f5-163">If a payment method isn't associated with any subscriptions or billing profiles, you can immediately delete it.</span></span>

1. <span data-ttu-id="656f5-164">管理センターで、[**課金情報**] > [**請求と支払い**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">支払方法</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="656f5-164">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="656f5-165">削除する支払い方法を見つけ、3 つのドットを選択し、[削除] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="656f5-165">Find the payment method to delete, select the three dots, then select **Delete**.</span></span>
3. <span data-ttu-id="656f5-166">右側のウィンドウの下部で、[削除] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="656f5-166">At the bottom of the right pane, select **Delete**.</span></span>

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="656f5-167">サブスクリプションまたは請求プロファイルが添付された支払い方法を削除する</span><span class="sxs-lookup"><span data-stu-id="656f5-167">Delete a payment method with subscriptions or billing profiles attached</span></span>

<span data-ttu-id="656f5-168">支払い方法がサブスクリプションまたは請求プロファイルに添付されている場合は、最初に既存の支払い方法に置き換えるか、新しい支払い方法を追加してから、古い支払い方法を削除します。</span><span class="sxs-lookup"><span data-stu-id="656f5-168">If a payment method is attached to any subscriptions or billing profiles, first replace it with an existing payment method, or add a new one, then delete the old payment method.</span></span>

1. <span data-ttu-id="656f5-169">管理センターで、[**課金情報**] > [**請求と支払い**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">支払方法</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="656f5-169">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="656f5-170">削除する支払い方法の行を選択します。</span><span class="sxs-lookup"><span data-stu-id="656f5-170">Select the row for the payment method to delete.</span></span> <span data-ttu-id="656f5-171">右側のウィンドウには、その支払い方法を使用する既存のサブスクリプションが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="656f5-171">The right pane lists existing subscriptions that use that payment method.</span></span>
3. <span data-ttu-id="656f5-172">右側のウィンドウで、[削除] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="656f5-172">In the right pane, select **Delete**.</span></span>
4. <span data-ttu-id="656f5-173">既存の支払い方法を使用するには、ドロップダウン リストから支払い方法を選択し、[次へ] を選択して、[削除] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="656f5-173">To use an existing payment method, choose one from the drop-down list, select **Next**, and then select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="656f5-174">請求プロファイルに関連付けられているサブスクリプションがある場合、支払いにはクレジット カードのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="656f5-174">If you have subscriptions associated with a billing profile, you can only use a credit card to pay for them.</span></span> <span data-ttu-id="656f5-175">[支払い方法] ページに銀行口座が表示されている場合、その銀行口座はドロップダウン リストで選択できません。</span><span class="sxs-lookup"><span data-stu-id="656f5-175">If you have bank accounts listed on the **Payment methods** page, they aren't available to choose in the drop-down list.</span></span>
5. <span data-ttu-id="656f5-176">新しい支払方法を追加するには、**[支払方法の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="656f5-176">To add a new payment method, select **Add payment method**.</span></span>
6. <span data-ttu-id="656f5-177">追加する支払い方法の種類を選択し、アカウント情報を入力して、[保存] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="656f5-177">Choose the type of payment method that you want to add, enter the account information, and then select **Save**.</span></span>
7. <span data-ttu-id="656f5-178">新しい支払い方法は、ドロップダウン リストで既に選択されています。</span><span class="sxs-lookup"><span data-stu-id="656f5-178">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="656f5-179">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="656f5-179">Select **Next**.</span></span>
8. <span data-ttu-id="656f5-180">**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="656f5-180">Select **Delete**.</span></span>

## <a name="troubleshoot-payment-methods"></a><span data-ttu-id="656f5-181">支払い方法のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="656f5-181">Troubleshoot payment methods</span></span>

| <span data-ttu-id="656f5-182">問題</span><span class="sxs-lookup"><span data-stu-id="656f5-182">Issue</span></span> | <span data-ttu-id="656f5-183">トラブルシューティングの手順</span><span class="sxs-lookup"><span data-stu-id="656f5-183">Troubleshooting steps</span></span> |
|:----------|:-----|
|<span data-ttu-id="656f5-184">**「ブラウザーは現在 Cookie をブロックするために設定されています」というエラー メッセージが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="656f5-184">**I get an error message that says, "The browser is currently set to block cookies."**</span></span> |<span data-ttu-id="656f5-185">サード パーティの Cookie を許可するようにブラウザーを設定し、もう一度試してください。</span><span class="sxs-lookup"><span data-stu-id="656f5-185">Set your browser to allow third-party cookies and try again.</span></span> |
|<span data-ttu-id="656f5-186">**クレジット カードまたはデビット カードが拒否されました。**</span><span class="sxs-lookup"><span data-stu-id="656f5-186">**My credit or debit card was declined.**</span></span> |<span data-ttu-id="656f5-187">クレジット カードまたはデビット カードで支払いを行い、カードが拒否された場合は、Microsoft が支払いを処理できなかったというメールを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="656f5-187">If you pay by credit or debit card, and your card is declined, you receive an email that says Microsoft was unable to process the payment.</span></span> <span data-ttu-id="656f5-188">カードの詳細カード番号、有効期限、カードの名前、住所 (市区町会、州、郵便番号など) が、カードとステートメントの場合とまったく同じに表示されるのを確認します。 &mdash; &mdash;</span><span class="sxs-lookup"><span data-stu-id="656f5-188">Double-check that the card details&mdash;card number, expiration date, name on the card, and address, including city, state, and ZIP code&mdash;appear exactly as they do on the card and your statement.</span></span> <span data-ttu-id="656f5-189">サブスクリプションの詳細ページの [請求] セクションにある [残高の決済]リンクを使用して、カード情報を更新し、すぐに支払いを送信できます。</span><span class="sxs-lookup"><span data-stu-id="656f5-189">You can update your card information and immediately submit the payment by using the **Settle balance** link in the **Billing** section of the subscription details page.</span></span> <span data-ttu-id="656f5-190">詳細については、「未払い残高 [がある場合の確認方法」を参照してください。](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)</span><span class="sxs-lookup"><span data-stu-id="656f5-190">For more information, see [What if I have an outstanding balance?](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)</span></span>  <br/><br/>  <span data-ttu-id="656f5-191">引き続き 「辞退」メッセージが表示される場合は、銀行にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="656f5-191">If you continue to see the "declined" message, contact your bank.</span></span> <span data-ttu-id="656f5-192">カードがアクティブではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="656f5-192">It's possible that your card isn't active.</span></span> <span data-ttu-id="656f5-193">有効期限が更新されたカードをメールで最近受信した場合は、カードがアクティブ化されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="656f5-193">If you recently received the card in the mail with an updated expiration date, make sure it's activated.</span></span> <span data-ttu-id="656f5-194">銀行は、カードがオンライン、国際取引、または定期的な取引に対して承認されていないかどうかも確認できます。</span><span class="sxs-lookup"><span data-stu-id="656f5-194">Your bank can also tell you whether your card isn't approved for online, international, or recurring transactions.</span></span> |
|<span data-ttu-id="656f5-195">**カード番号または銀行口座番号を更新する。**</span><span class="sxs-lookup"><span data-stu-id="656f5-195">**I want to update a card or bank account number.**</span></span> |<span data-ttu-id="656f5-196">既存の支払い方法でカードまたはアカウント番号を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="656f5-196">You can't change the card or account number on an existing payment method.</span></span> <span data-ttu-id="656f5-197">If your card or account number has changed, [replace it with a different payment method,](#replace-a-payment-method)which moves all active subscriptions from the payment method to the new one, then delete the old payment [method](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span><span class="sxs-lookup"><span data-stu-id="656f5-197">If your card or account number has changed, [replace it with a different payment method](#replace-a-payment-method), which moves all active subscriptions from the payment method to the new one, then [delete the old payment method](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span></span> |
|<span data-ttu-id="656f5-198">**アカウントにカードまたは銀行口座を 1 つしか持たず、削除します。**</span><span class="sxs-lookup"><span data-stu-id="656f5-198">**I only have one card or bank account on my account and I want to remove it.**</span></span> |<span data-ttu-id="656f5-199">支払い方法が 1 つしか[](#replace-a-payment-method)ない場合は、削除する前に新しい支払い方法に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="656f5-199">If you only have one payment method, you must [replace it with a new payment method](#replace-a-payment-method) before you can delete it.</span></span> |
|<span data-ttu-id="656f5-200">**カードまたは銀行口座を追加できません。**</span><span class="sxs-lookup"><span data-stu-id="656f5-200">**I can't add my card or bank account.**</span></span>  |<span data-ttu-id="656f5-201">テナントと同じ国から発行された支払い方法を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="656f5-201">You must use a payment method issued from the same country as your tenant.</span></span> <span data-ttu-id="656f5-202">If you have trouble entering your card or bank account information, you can [contact support](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="656f5-202">If you have trouble entering your card or bank account information, you can [contact support](../../admin/contact-support-for-business-products.md).</span></span> |

## <a name="related-content"></a><span data-ttu-id="656f5-203">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="656f5-203">Related content</span></span>

<span data-ttu-id="656f5-204">[ビジネス サブスクリプションの支払い](pay-for-your-subscription.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="656f5-204">[Pay for your business subscription](pay-for-your-subscription.md) (article)</span></span>\
<span data-ttu-id="656f5-205">[請求プロファイルを管理する](manage-billing-profiles.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="656f5-205">[Manage billing profiles](manage-billing-profiles.md) (article)</span></span>\
<span data-ttu-id="656f5-206">[請求頻度を変更する](change-payment-frequency.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="656f5-206">[Change your billing frequency](change-payment-frequency.md) (article)</span></span>
