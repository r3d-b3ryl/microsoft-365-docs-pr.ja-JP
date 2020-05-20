---
title: 支払方法を管理する
f1.keywords:
- CSH
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
- TopSMBIssues
- okr_SMB
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: Microsoft 365 管理センターで支払い方法を管理する方法について説明します。
ms.openlocfilehash: d31da19c10eb61719ba813d271dbdcf573a5aff3
ms.sourcegitcommit: 5c43e89ed94ad9fd1db049446383c65e548189b7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "44322161"
---
# <a name="manage-payment-methods"></a><span data-ttu-id="7bb44-103">支払方法を管理する</span><span class="sxs-lookup"><span data-stu-id="7bb44-103">Manage payment methods</span></span>

::: moniker range="o365-21vianet"
> [!NOTE]
> <span data-ttu-id="7bb44-104">管理センターが変更されています。</span><span class="sxs-lookup"><span data-stu-id="7bb44-104">The admin center is changing.</span></span> <span data-ttu-id="7bb44-105">ここに示されている詳細情報とは異なる場合は、「[新しい Microsoft 365 管理センターについ](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bb44-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>
::: moniker-end

<span data-ttu-id="7bb44-106">Microsoft からビジネス製品またはサービスを購入する場合は、既存の支払い方法を使用するか、または新しいサービスを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="7bb44-106">When you buy business products or services from Microsoft, you can use an existing payment method, or add a new one.</span></span> <span data-ttu-id="7bb44-107">クレジットカードまたはデビットカードまたは銀行口座を使用して、購入された事柄に対して支払いを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7bb44-107">You can use a credit or debit card, or bank account to pay for the things you buy.</span></span>

<span data-ttu-id="7bb44-108">ビジネスアカウントに請求書プロファイルがあり、請求プロファイル所有者または請求プロファイル投稿者である場合は、クレジットカードまたは請求書の支払いによってサポートされている課金プロファイルを使用して、請求書を購入または支払いすることができます。</span><span class="sxs-lookup"><span data-stu-id="7bb44-108">If your business account has a billing profile, and you are a billing profile owner or billing profile contributor, you can use the billing profile that's backed by a credit card or invoice payment to make purchases or pay bills.</span></span> <span data-ttu-id="7bb44-109">請求書管理者である場合は、請求書の支払にのみ課金プロファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7bb44-109">If you're a billing invoice manager, you can only use a billing profile to pay bills.</span></span> <span data-ttu-id="7bb44-110">請求プロファイルとロールの詳細については、「[課金プロファイルを管理](manage-billing-profiles.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bb44-110">To learn more about billing profiles and roles, see [Manage billing profiles](manage-billing-profiles.md).</span></span>

<span data-ttu-id="7bb44-111">ビジネスアカウントに請求書プロファイルがない場合は、すべてのグローバルまたは課金管理者が、ビジネスアカウントに追加された銀行口座を管理し、使用することができます。</span><span class="sxs-lookup"><span data-stu-id="7bb44-111">If your business account doesn't have a billing profile, any Global or Billing admin can manage and use any bank account that is added to the business account.</span></span> <span data-ttu-id="7bb44-112">ただし、追加するクレジットカードの管理または使用のみが可能です。</span><span class="sxs-lookup"><span data-stu-id="7bb44-112">However, you can only manage or use credit cards that you add.</span></span>

> [!NOTE]
> <span data-ttu-id="7bb44-113">銀行口座で支払うオプションは、一部の国や地域では使用できません。</span><span class="sxs-lookup"><span data-stu-id="7bb44-113">The option to pay with a bank account is not available in some countries or regions.</span></span>
>
> <span data-ttu-id="7bb44-114">テナントと同じ国から発行された支払い方法を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bb44-114">You must use a payment method issued from the same country as your tenant.</span></span>

## <a name="add-a-payment-method"></a><span data-ttu-id="7bb44-115">支払い方法を追加する</span><span class="sxs-lookup"><span data-stu-id="7bb44-115">Add a payment method</span></span>

<span data-ttu-id="7bb44-116">支払い方法を追加しても、サブスクリプションがそれに関連付けられることはありません。</span><span class="sxs-lookup"><span data-stu-id="7bb44-116">Adding a payment method doesn't associate any subscriptions with it.</span></span> <span data-ttu-id="7bb44-117">支払い方法に1つのサブスクリプションを割り当てるには、「 [1 つのサブスクリプションの支払い方法を変更](#change-a-payment-method-for-a-single-subscription)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bb44-117">To assign a single subscription to the payment method, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span> <span data-ttu-id="7bb44-118">別の支払い方法を使用しているすべてのサブスクリプションを新しい支払い方法で置き換える場合は、「[支払い方法を置き換える](#replace-a-payment-method)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bb44-118">To replace all subscriptions that use another payment method with the new one, see [Replace a payment method](#replace-a-payment-method).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="7bb44-119">管理センターで、[**課金請求書** > **&** 支払い > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-119">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="7bb44-120">管理センターで、[**課金請求書** > **&** 支払い > **方法**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-120">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="7bb44-121">管理センターで、[**課金請求書** > **&** 支払い > **方法**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-121">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="7bb44-122">[**お支払方法の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-122">Select **Add a payment method**.</span></span>

3. <span data-ttu-id="7bb44-123">[**支払い方法**] ページで、ドロップダウン メニューから支払い方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-123">On the **Payment methods** page, pick a payment method from the drop-down menu.</span></span>

4. <span data-ttu-id="7bb44-124">新しいカードまたは銀行口座の情報を入力し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-124">Enter the information for the new card or bank account, then select **Add**.</span></span>

## <a name="update-payment-method-details"></a><span data-ttu-id="7bb44-125">支払い方法の詳細の更新</span><span class="sxs-lookup"><span data-stu-id="7bb44-125">Update payment method details</span></span>

<span data-ttu-id="7bb44-126">既存の支払い方法のクレジットカードまたはデビットカードの名前、請求先の住所、または有効期限を変更できます。</span><span class="sxs-lookup"><span data-stu-id="7bb44-126">You can change the name on the credit or debit card, billing address, or expiration date for an existing payment method.</span></span> <span data-ttu-id="7bb44-127">ただし、カードまたは口座番号を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="7bb44-127">However, you can't change the card or account number.</span></span> <span data-ttu-id="7bb44-128">アカウント番号が変更されている場合は、[別の支払い方法に置き換え](#replace-a-payment-method)てから、[古いものを削除](#delete-a-payment-method)します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-128">If the account number has changed, [replace it with a different payment method](#replace-a-payment-method), and then [delete the old one](#delete-a-payment-method).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="7bb44-129">管理センターで、[**課金請求書** > **&** 支払い > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-129">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="7bb44-130">管理センターで、[**課金請求書** > **&** 支払い > **方法**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-130">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="7bb44-131">管理センターで、[**課金請求書** > **&** 支払い > **方法**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-131">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="7bb44-132">更新する支払い方法の行を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-132">Select the row of the payment method to update.</span></span> <span data-ttu-id="7bb44-133">右側のウィンドウで、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-133">In the right pane, select **Edit**.</span></span>

3. <span data-ttu-id="7bb44-134">クレジット カードまたはデビット カードの名前、請求先住所、有効期限などのお支払い方法の情報を更新し、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-134">Update your payment method information, including the name on the credit or debit card, billing address, or expiration date, and then select **Save**.</span></span>

## <a name="replace-a-payment-method"></a><span data-ttu-id="7bb44-135">支払い方法を置換する</span><span class="sxs-lookup"><span data-stu-id="7bb44-135">Replace a payment method</span></span>

<span data-ttu-id="7bb44-136">支払い方法を置き換える場合、同じ支払い方法を使用しているすべてのサブスクリプションと請求書のプロファイルに対して、支払方法を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="7bb44-136">When you replace a payment method, you replace it for all subscriptions and billing profiles that use the same payment method.</span></span> <span data-ttu-id="7bb44-137">支払い方法を置き換えても、既存の支払い方法が削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="7bb44-137">Replacing a payment method doesn't delete the existing payment method.</span></span> <span data-ttu-id="7bb44-138">その他のサブスクリプションと請求プロファイルのために、選択して使用することができます。</span><span class="sxs-lookup"><span data-stu-id="7bb44-138">It's still available for you to select and use for other subscriptions and billing profiles.</span></span>

<span data-ttu-id="7bb44-139">単一のサブスクリプションの支払い方法を変更するには、「 [1 つのサブスクリプションの支払い方法を変更](#change-a-payment-method-for-a-single-subscription)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bb44-139">To change the payment method for a single subscription, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="7bb44-140">管理センターで、[**課金請求書** > **&** 支払い > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-140">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="7bb44-141">管理センターで、[**課金請求書** > **&** 支払い > **方法**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-141">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="7bb44-142">管理センターで、[**課金請求書** > **&** 支払い > **方法**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-142">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="7bb44-143">変更する支払い方法の行を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-143">Select the row of the payment method to replace.</span></span> <span data-ttu-id="7bb44-144">右側のウィンドウには、選択した支払方法を使用する請求プロファイルと個々のサブスクリプションがすべて一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="7bb44-144">The right pane lists all billing profiles and individual subscriptions that use the selected payment method.</span></span>

3. <span data-ttu-id="7bb44-145">右側のウィンドウで、**[すべてのアイテムの支払方法を置き換える]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-145">In the right pane, select **Replace payment method for all items**.</span></span>

4. <span data-ttu-id="7bb44-146">既存の支払い方法を使用する場合は、ドロップダウン リストからいずれかのオプションを選択して、**[置換]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-146">To use an existing payment method, choose one from the drop-down list, then select **Replace**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="7bb44-147">請求プロファイルに関連付けられているサブスクリプションがある場合は、クレジット カードまたはデビット カードのみ支払いに使用できます。</span><span class="sxs-lookup"><span data-stu-id="7bb44-147">If you have subscriptions associated with a billing profile, you can only use a credit or debit card to pay for them.</span></span> <span data-ttu-id="7bb44-148">**[支払方法]** ページに銀行口座が表示されている場合は、ドロップダウン リストで選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="7bb44-148">If you have bank accounts listed on the **Payment methods** page, they aren't available to select in the drop-down list.</span></span>

5. <span data-ttu-id="7bb44-149">新しい支払方法を追加するには、**[支払方法の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-149">To add a new payment method, select **Add payment method**.</span></span>

6. <span data-ttu-id="7bb44-150">**[支払方法の追加]** ウィンドウで、アカウント情報を入力し、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-150">In the **Add a payment method** pane, enter the account information, then select **Save**.</span></span> <span data-ttu-id="7bb44-151">テナントと同じ国の支払い方法を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bb44-151">You must use a payment method from the same country as your tenant.</span></span>

7. <span data-ttu-id="7bb44-152">新しい支払い方法は、ドロップダウン リストで既に選択されています。</span><span class="sxs-lookup"><span data-stu-id="7bb44-152">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="7bb44-153">**[置換]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-153">Select **Replace**.</span></span>

## <a name="change-a-payment-method-for-a-single-subscription"></a><span data-ttu-id="7bb44-154">1つのサブスクリプションの支払い方法を変更する</span><span class="sxs-lookup"><span data-stu-id="7bb44-154">Change a payment method for a single subscription</span></span>

<span data-ttu-id="7bb44-155">1つのサブスクリプションの支払いに使用する支払い方法を変更できます。</span><span class="sxs-lookup"><span data-stu-id="7bb44-155">You can change the payment method used to pay for a single subscription.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="7bb44-156">管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-156">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="7bb44-157">管理センターで、**[課金]** > **[製品]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-157">In the admin center, go to the **Billing** > **Your products** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="7bb44-158">管理センターで、**[課金]** > **[製品]** ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-158">In the admin center, go to the **Billing** > **Your products** page.</span></span>
::: moniker-end

2. <span data-ttu-id="7bb44-159">[**サブスクリプション**] タブで、別の支払い方法で支払う対象のサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-159">On the **Subscriptions** tab, select the subscription that you want to pay for with the alternate payment method.</span></span>

3. <span data-ttu-id="7bb44-160">[**請求**] の下で支払い方法の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-160">Under **Billing**, next to the payment method, select **Edit**.</span></span>

4. <span data-ttu-id="7bb44-161">既存の支払い方法の横にある [**変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-161">Next to your existing payment method, select **Change**.</span></span>

5. <span data-ttu-id="7bb44-162">ドロップダウンリストから別の支払い方法を選択するか、支払い方法を追加します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-162">From the drop-down list, choose an alternate payment method, or choose to add a payment method.</span></span>

6. <span data-ttu-id="7bb44-163">支払い方法を追加する場合は、カードまたは口座の詳細を入力し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-163">If you add a payment method, enter the card or account details, then select **Save**.</span></span>

7. <span data-ttu-id="7bb44-164">選択した支払い方法が正しいことを確認し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-164">Verify that the selected payment method is correct, then select **Save**.</span></span>

## <a name="delete-a-payment-method"></a><span data-ttu-id="7bb44-165">支払い方法を削除する</span><span class="sxs-lookup"><span data-stu-id="7bb44-165">Delete a payment method</span></span>

<span data-ttu-id="7bb44-166">削除できるのは、サブスクリプションまたは課金プロファイルに関連付けられていない支払い方法のみです。</span><span class="sxs-lookup"><span data-stu-id="7bb44-166">You can only delete a payment method that isn't attached to a subscription or billing profile.</span></span> <span data-ttu-id="7bb44-167">これは、その状態にかかわらずすべてのサブスクリプションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="7bb44-167">This applies to all subscriptions, whatever their status.</span></span>

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="7bb44-168">サブスクリプションまたは課金プロファイルが添付されていない支払い方法を削除する</span><span class="sxs-lookup"><span data-stu-id="7bb44-168">Delete a payment method with no subscriptions or billing profiles attached</span></span>

<span data-ttu-id="7bb44-169">支払い方法がサブスクリプションまたは請求プロファイルに関連付けられていない場合は、すぐに削除できます。</span><span class="sxs-lookup"><span data-stu-id="7bb44-169">If a payment method isn't associated with any subscriptions or billing profiles, you can immediately delete it.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="7bb44-170">管理センターで、[**課金請求書** > **&** 支払い > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-170">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="7bb44-171">管理センターで、[**課金請求書** > **&** 支払い > **方法**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-171">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="7bb44-172">管理センターで、[**課金請求書** > **&** 支払い > **方法**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-172">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="7bb44-173">削除する支払い方法を検索し、3つのドットを選択して、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-173">Find the payment method to delete, select the three dots, then select **Delete**.</span></span>

3. <span data-ttu-id="7bb44-174">右側のウィンドウの下部にある [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-174">At the bottom of the right pane, select **Delete**.</span></span>

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="7bb44-175">サブスクリプションまたは課金プロファイルが添付されている支払い方法を削除する</span><span class="sxs-lookup"><span data-stu-id="7bb44-175">Delete a payment method with subscriptions or billing profiles attached</span></span>

<span data-ttu-id="7bb44-176">支払い方法がサブスクリプションまたは請求プロファイルに関連付けられている場合は、最初に既存の支払い方法で置き換えるか、新しい支払い方法を追加して、古い支払い方法を削除します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-176">If a payment method is attached to any subscriptions or billing profiles, first replace it with an existing payment method, or add a new one, then delete the old payment method.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="7bb44-177">管理センターで、[**課金請求書** > **&** 支払い > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-177">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="7bb44-178">管理センターで、[**課金請求書** > **&** 支払い > **方法**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-178">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="7bb44-179">管理センターで、[**課金請求書** > **&** 支払い > **方法**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-179">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="7bb44-180">削除する支払い方法の行を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-180">Select the row for the payment method to delete.</span></span> <span data-ttu-id="7bb44-181">右側のウィンドウには、その支払い方法を使用する既存のサブスクリプションが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="7bb44-181">The right pane lists existing subscriptions that use that payment method.</span></span>

3. <span data-ttu-id="7bb44-182">右側のウィンドウで、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-182">In the right pane, select **Delete**.</span></span>

4. <span data-ttu-id="7bb44-183">既存の支払い方法を使用するには、ドロップダウンリストから1つを選択し、[**次へ**] を選択して、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-183">To use an existing payment method, choose one from the drop-down list, select **Next**, and then select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="7bb44-184">課金プロファイルに関連付けられているサブスクリプションがある場合は、クレジットカードのみを使用して料金を支払うことができます。</span><span class="sxs-lookup"><span data-stu-id="7bb44-184">If you have subscriptions associated with a billing profile, you can only use a credit card to pay for them.</span></span> <span data-ttu-id="7bb44-185">[**支払方法**] ページに銀行口座が表示されている場合は、ドロップダウンリストで選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="7bb44-185">If you have bank accounts listed on the **Payment methods** page, they aren't available to choose in the drop-down list.</span></span>

5. <span data-ttu-id="7bb44-186">新しい支払方法を追加するには、**[支払方法の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-186">To add a new payment method, select **Add payment method**.</span></span>

6. <span data-ttu-id="7bb44-187">追加する支払い方法の種類を選択し、アカウント情報を入力してから [**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-187">Choose the type of payment method that you want to add, enter the account information, and then select **Save**.</span></span>

7. <span data-ttu-id="7bb44-188">新しい支払い方法は、ドロップダウン リストで既に選択されています。</span><span class="sxs-lookup"><span data-stu-id="7bb44-188">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="7bb44-189">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-189">Select **Next**.</span></span>

8. <span data-ttu-id="7bb44-190">**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-190">Select **Delete**.</span></span>

## <a name="troubleshoot-payment-methods"></a><span data-ttu-id="7bb44-191">支払い方法のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7bb44-191">Troubleshoot payment methods</span></span>

|<span data-ttu-id="7bb44-192">**問題**</span><span class="sxs-lookup"><span data-stu-id="7bb44-192">**Issue**</span></span>|<span data-ttu-id="7bb44-193">**トラブルシューティングの手順**</span><span class="sxs-lookup"><span data-stu-id="7bb44-193">**Troubleshooting steps**</span></span>|
|:----------|:-----|
|<span data-ttu-id="7bb44-194">**"ブラウザーは現在、cookie をブロックするように設定されています" というエラーメッセージが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="7bb44-194">**I get an error message that says, "The browser is currently set to block cookies."**</span></span> |<span data-ttu-id="7bb44-195">サード パーティの Cookie を許可するようにブラウザーを設定し、もう一度試してください。</span><span class="sxs-lookup"><span data-stu-id="7bb44-195">Set your browser to allow third-party cookies and try again.</span></span> |
|<span data-ttu-id="7bb44-196">**クレジットカードまたはデビットカードが拒否されました。**</span><span class="sxs-lookup"><span data-stu-id="7bb44-196">**My credit or debit card was declined.**</span></span> |<span data-ttu-id="7bb44-197">クレジットカードまたはデビットカードで支払い、カードが拒否された場合、Microsoft が支払いを処理できなかったという電子メールが届きます。</span><span class="sxs-lookup"><span data-stu-id="7bb44-197">If you pay by credit or debit card, and your card is declined, you receive an email that says Microsoft was unable to process the payment.</span></span> <span data-ttu-id="7bb44-198">カードの詳細、カード番号、 &mdash; 有効期限、カードの名前、住所 (市区町村、都道府県、および郵便番号を含む) がカードとステートメントの内容と正確に一致しているかどうかを確認し &mdash; ます。</span><span class="sxs-lookup"><span data-stu-id="7bb44-198">Double-check that the card details&mdash;card number, expiration date, name on the card, and address, including city, state, and ZIP code&mdash;appear exactly as they do on the card and your statement.</span></span> <span data-ttu-id="7bb44-199">[サブスクリプションの詳細] ページの [**課金**] セクションの [**決済バランス**] リンクを使用して、カード情報を更新し、すぐに支払いを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="7bb44-199">You can update your card information and immediately submit the payment by using the **Settle balance** link in the **Billing** section of the subscription details page.</span></span> <span data-ttu-id="7bb44-200">詳細については、「[クレジット カードが拒否され、支払い期日を過ぎてしまった場合はどうなりますか?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bb44-200">For more information, see [What if my credit card was declined and my payment is past due?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)</span></span>  <br/><br/>  <span data-ttu-id="7bb44-201">引き続き "辞退" メッセージが表示される場合は、銀行にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="7bb44-201">If you continue to see the "declined" message, contact your bank.</span></span> <span data-ttu-id="7bb44-202">カードがアクティブではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7bb44-202">It's possible that your card isn't active.</span></span> <span data-ttu-id="7bb44-203">メールで、更新された有効期限の日付を最近受信した場合は、そのカードが有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7bb44-203">If you recently received the card in the mail with an updated expiration date, make sure it's activated.</span></span> <span data-ttu-id="7bb44-204">また、銀行は、オンライン、国際、または定期的な取引でカードが承認されていないかどうかを知らせることもできます。</span><span class="sxs-lookup"><span data-stu-id="7bb44-204">Your bank can also tell you whether your card isn't approved for online, international, or recurring transactions.</span></span> |
|<span data-ttu-id="7bb44-205">**カードまたは銀行口座番号を更新する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="7bb44-205">**I want to update a card or bank account number.**</span></span> |<span data-ttu-id="7bb44-206">既存の支払い方法でカードまたは口座番号を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="7bb44-206">You can't change the card or account number on an existing payment method.</span></span> <span data-ttu-id="7bb44-207">カードまたは口座番号が変更されている場合は、[別の支払い方法に置き換え](#replace-a-payment-method)ます。これは、支払い方法から新しい支払い方法にすべてのアクティブなサブスクリプションを移動して、[古い支払い方法を削除](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached)します。</span><span class="sxs-lookup"><span data-stu-id="7bb44-207">If your card or account number has changed, [replace it with a different payment method](#replace-a-payment-method), which moves all active subscriptions from the payment method to the new one, then [delete the old payment method](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span></span> |
|<span data-ttu-id="7bb44-208">**自分のアカウントに1つのカードまたは銀行口座しかない場合、そのアカウントを削除します。**</span><span class="sxs-lookup"><span data-stu-id="7bb44-208">**I only have one card or bank account on my account and I want to remove it.**</span></span> |<span data-ttu-id="7bb44-209">支払い方法が1つだけの場合は、それを削除する前に、[新しい支払い方法に置き換える](#replace-a-payment-method)必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bb44-209">If you only have one payment method, you must [replace it with a new payment method](#replace-a-payment-method) before you can delete it.</span></span> |
|<span data-ttu-id="7bb44-210">**自分のカードまたは銀行口座を追加できません。**</span><span class="sxs-lookup"><span data-stu-id="7bb44-210">**I can't add my card or bank account.**</span></span>  |<span data-ttu-id="7bb44-211">テナントと同じ国から発行された支払い方法を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bb44-211">You must use a payment method issued from the same country as your tenant.</span></span> <span data-ttu-id="7bb44-212">カードまたは銀行口座情報を入力するときに問題が発生した場合は、[サポートにお問い合わせ](../../admin/contact-support-for-business-products.md)ください。</span><span class="sxs-lookup"><span data-stu-id="7bb44-212">If you have trouble entering your card or bank account information, you can [contact support](../../admin/contact-support-for-business-products.md).</span></span> |

## <a name="related-articles"></a><span data-ttu-id="7bb44-213">関連記事</span><span class="sxs-lookup"><span data-stu-id="7bb44-213">Related articles</span></span>

[<span data-ttu-id="7bb44-214">法人向けサブスクリプションの支払い</span><span class="sxs-lookup"><span data-stu-id="7bb44-214">Pay for your business subscription</span></span>](pay-for-your-subscription.md)

[<span data-ttu-id="7bb44-215">課金プロフィールを管理する</span><span class="sxs-lookup"><span data-stu-id="7bb44-215">Manage billing profiles</span></span>](manage-billing-profiles.md)

[<span data-ttu-id="7bb44-216">支払い頻度を変更する</span><span class="sxs-lookup"><span data-stu-id="7bb44-216">Change your payment frequency</span></span>](change-payment-frequency.md)