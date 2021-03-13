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
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: Microsoft 365 管理センターで支払方法を管理する方法を説明します。
ms.date: ''
ms.openlocfilehash: a6866a9691e42928a5712c3069704f11fac0546f
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741391"
---
# <a name="manage-payment-methods"></a><span data-ttu-id="bd6c4-103">支払方法を管理する</span><span class="sxs-lookup"><span data-stu-id="bd6c4-103">Manage payment methods</span></span>

::: moniker range="o365-21vianet"
> [!NOTE]
> <span data-ttu-id="bd6c4-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-104">The admin center is changing.</span></span> <span data-ttu-id="bd6c4-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>
::: moniker-end

<span data-ttu-id="bd6c4-106">Microsoft からビジネス製品またはサービスを購入する場合、既存の支払方法を使用することも、新しい支払方法を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-106">When you buy business products or services from Microsoft, you can use an existing payment method, or add a new one.</span></span> <span data-ttu-id="bd6c4-107">クレジット カード、デビット カード、または銀行口座を使用して、購入したものの支払いを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-107">You can use a credit or debit card, or bank account to pay for the things you buy.</span></span>

<span data-ttu-id="bd6c4-108">ビジネス アカウントに課金プロファイルがあり、課金プロファイルの所有者または課金プロファイルの共同作成者である場合は、クレジット カードまたは請求書の支払いに裏付けられた課金プロファイルを使用して、購入または請求を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-108">If your business account has a billing profile, and you are a billing profile owner or billing profile contributor, you can use the billing profile that's backed by a credit card or invoice payment to make purchases or pay bills.</span></span> <span data-ttu-id="bd6c4-109">請求書マネージャーの場合、請求書の支払いには課金プロファイルのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-109">If you're a billing invoice manager, you can only use a billing profile to pay bills.</span></span> <span data-ttu-id="bd6c4-110">課金プロファイルと役割の詳細については、「[課金プロファイルの管理](manage-billing-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-110">To learn more about billing profiles and roles, see [Manage billing profiles](manage-billing-profiles.md).</span></span>

<span data-ttu-id="bd6c4-111">ビジネス アカウントに課金プロファイルがない場合、グローバル管理者または課金管理者は、ビジネス アカウントに追加された銀行口座を管理および使用できます。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-111">If your business account doesn't have a billing profile, any Global or Billing admin can manage and use any bank account that is added to the business account.</span></span> <span data-ttu-id="bd6c4-112">ただし、管理または使用できるのは、追加したクレジット カードのみです。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-112">However, you can only manage or use credit cards that you add.</span></span>

> [!NOTE]
> <span data-ttu-id="bd6c4-113">一部の国または地域では、銀行口座引き落としによる支払いを利用できません。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-113">The option to pay with a bank account is not available in some countries or regions.</span></span>
>
> <span data-ttu-id="bd6c4-114">テナントと同じ国から発行された支払方法を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-114">You must use a payment method issued from the same country as your tenant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="bd6c4-115">開始する前に</span><span class="sxs-lookup"><span data-stu-id="bd6c4-115">Before you begin</span></span>

<span data-ttu-id="bd6c4-116">この記事で説明されている手順を実行するには、全体管理者または課金管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-116">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="bd6c4-117">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="add-a-payment-method"></a><span data-ttu-id="bd6c4-118">支払方法を追加する</span><span class="sxs-lookup"><span data-stu-id="bd6c4-118">Add a payment method</span></span>

<span data-ttu-id="bd6c4-119">支払方法を追加しても、サブスクリプションは関連付けられません。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-119">Adding a payment method doesn't associate any subscriptions with it.</span></span> <span data-ttu-id="bd6c4-120">1 つのサブスクリプションを支払方法に割り当てるには、「[1 つのサブスクリプションの支払方法を変更する](#change-a-payment-method-for-a-single-subscription)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-120">To assign a single subscription to the payment method, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span> <span data-ttu-id="bd6c4-121">別の支払方法を使用するすべてのサブスクリプションを新しいものに置き換えるには、「[支払方法の置き換え](#replace-a-payment-method)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-121">To replace all subscriptions that use another payment method with the new one, see [Replace a payment method](#replace-a-payment-method).</span></span>

1. <span data-ttu-id="bd6c4-122">管理センターで、**[課金]** > **[請求と支払い]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">[支払方法]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-122">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="bd6c4-123">[**お支払方法の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-123">Select **Add a payment method**.</span></span>
3. <span data-ttu-id="bd6c4-124">[**支払い方法**] ページで、ドロップダウン メニューから支払い方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-124">On the **Payment methods** page, pick a payment method from the drop-down menu.</span></span>
4. <span data-ttu-id="bd6c4-125">新しいカードまたは銀行口座に関する情報を入力して、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-125">Enter the information for the new card or bank account, then select **Add**.</span></span>

## <a name="update-payment-method-details"></a><span data-ttu-id="bd6c4-126">支払方法の詳細の更新</span><span class="sxs-lookup"><span data-stu-id="bd6c4-126">Update payment method details</span></span>

<span data-ttu-id="bd6c4-127">クレジット カードまたはデビット カードの名前、請求先住所、または既存の支払方法の有効期限を変更できます。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-127">You can change the name on the credit or debit card, billing address, or expiration date for an existing payment method.</span></span> <span data-ttu-id="bd6c4-128">ただし、カード番号や口座番号は変更できません。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-128">However, you can't change the card or account number.</span></span> <span data-ttu-id="bd6c4-129">アカウント番号が変更された場合は、[別の支払方法に置き換えて](#replace-a-payment-method)から、[古いアカウント番号を削除](#delete-a-payment-method)します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-129">If the account number has changed, [replace it with a different payment method](#replace-a-payment-method), and then [delete the old one](#delete-a-payment-method).</span></span>

1. <span data-ttu-id="bd6c4-130">管理センターで、**[課金]** > **[請求と支払い]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">[支払方法]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-130">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="bd6c4-131">更新する支払い方法の行を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-131">Select the row of the payment method to update.</span></span> <span data-ttu-id="bd6c4-132">右側のウィンドウで、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-132">In the right pane, select **Edit**.</span></span>
3. <span data-ttu-id="bd6c4-133">クレジット カードまたはデビット カードの名前、請求先住所、有効期限などのお支払い方法の情報を更新し、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-133">Update your payment method information, including the name on the credit or debit card, billing address, or expiration date, and then select **Save**.</span></span>

## <a name="replace-a-payment-method"></a><span data-ttu-id="bd6c4-134">支払方法を置き換える</span><span class="sxs-lookup"><span data-stu-id="bd6c4-134">Replace a payment method</span></span>

<span data-ttu-id="bd6c4-135">支払方法を置き換えると、同じ支払方法を使用するすべてのサブスクリプションと課金プロファイルで置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-135">When you replace a payment method, you replace it for all subscriptions and billing profiles that use the same payment method.</span></span> <span data-ttu-id="bd6c4-136">支払方法を置き換えても、既存の支払方法は削除されません。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-136">Replacing a payment method doesn't delete the existing payment method.</span></span> <span data-ttu-id="bd6c4-137">他のサブスクリプションや課金プロファイルを選択して使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-137">It's still available for you to select and use for other subscriptions and billing profiles.</span></span>

<span data-ttu-id="bd6c4-138">1 つのサブスクリプションの支払方法を変更するには、「[1 つのサブスクリプションの支払方法を変更する](#change-a-payment-method-for-a-single-subscription)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-138">To change the payment method for a single subscription, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span>

1. <span data-ttu-id="bd6c4-139">管理センターで、**[課金]** > **[請求と支払い]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">[支払方法]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-139">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="bd6c4-140">変更する支払い方法の行を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-140">Select the row of the payment method to replace.</span></span> <span data-ttu-id="bd6c4-141">右側のウィンドウには、選択した支払方法を使用する請求プロファイルと個々のサブスクリプションがすべて一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-141">The right pane lists all billing profiles and individual subscriptions that use the selected payment method.</span></span>
3. <span data-ttu-id="bd6c4-142">右側のウィンドウで、**[すべてのアイテムの支払方法を置き換える]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-142">In the right pane, select **Replace payment method for all items**.</span></span>
4. <span data-ttu-id="bd6c4-143">既存の支払い方法を使用する場合は、ドロップダウン リストからいずれかのオプションを選択して、**[置換]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-143">To use an existing payment method, choose one from the drop-down list, then select **Replace**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="bd6c4-144">請求プロファイルに関連付けられているサブスクリプションがある場合は、クレジット カードまたはデビット カードのみ支払いに使用できます。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-144">If you have subscriptions associated with a billing profile, you can only use a credit or debit card to pay for them.</span></span> <span data-ttu-id="bd6c4-145">**[支払方法]** ページに銀行口座が表示されている場合は、ドロップダウン リストで選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-145">If you have bank accounts listed on the **Payment methods** page, they aren't available to select in the drop-down list.</span></span>
5. <span data-ttu-id="bd6c4-146">新しい支払方法を追加するには、**[支払方法の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-146">To add a new payment method, select **Add payment method**.</span></span>
6. <span data-ttu-id="bd6c4-147">**[支払方法の追加]** ウィンドウで、アカウント情報を入力し、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-147">In the **Add a payment method** pane, enter the account information, then select **Save**.</span></span> <span data-ttu-id="bd6c4-148">テナントと同じ国の支払い方法を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-148">You must use a payment method from the same country as your tenant.</span></span>
7. <span data-ttu-id="bd6c4-149">新しい支払い方法は、ドロップダウン リストで既に選択されています。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-149">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="bd6c4-150">**[置換]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-150">Select **Replace**.</span></span>

## <a name="change-a-payment-method-for-a-single-subscription"></a><span data-ttu-id="bd6c4-151">1 つのサブスクリプションの支払方法を変更する</span><span class="sxs-lookup"><span data-stu-id="bd6c4-151">Change a payment method for a single subscription</span></span>

<span data-ttu-id="bd6c4-152">1 つのサブスクリプションの支払いに使用される支払方法を変更できます。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-152">You can change the payment method used to pay for a single subscription.</span></span>

1. <span data-ttu-id="bd6c4-153">管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-153">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="bd6c4-154">**[製品]** タブで、別の支払い方法で支払いたいサブスクリプションを見つけます。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-154">On the **Products** tab, find the subscription that you want to pay for with the alternate payment method.</span></span>
3. <span data-ttu-id="bd6c4-155">**[その他の操作]** (3 つのドット) を選択してから、**[お支払い方法を置換]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-155">Select **More actions** (three dots), then select **Replace payment method**.</span></span>
4. <span data-ttu-id="bd6c4-156">**お支払い方法を置換** ウィンドウのドロップダウン リストから、別の支払方法を選択するか、支払方法の追加を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-156">In the **Replace payment method** pane, from the drop-down list, choose an alternate payment method, or choose to add a payment method.</span></span>
5. <span data-ttu-id="bd6c4-157">支払方法を追加する場合は、カードまたは口座の詳細を入力し、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-157">If you add a payment method, enter the card or account details, then select **Save**.</span></span>
6. <span data-ttu-id="bd6c4-158">選択した支払方法が正しいことを確認し、**[置換]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-158">Verify that the selected payment method is correct, then select **Replace**.</span></span>

## <a name="delete-a-payment-method"></a><span data-ttu-id="bd6c4-159">支払方法を削除する</span><span class="sxs-lookup"><span data-stu-id="bd6c4-159">Delete a payment method</span></span>

<span data-ttu-id="bd6c4-160">サブスクリプションまたは課金プロファイルに関連付けられていない支払方法のみを削除できます。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-160">You can only delete a payment method that isn't attached to a subscription or billing profile.</span></span> <span data-ttu-id="bd6c4-161">これは、状態に関係なく、すべてのサブスクリプションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-161">This applies to all subscriptions, whatever their status.</span></span>

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="bd6c4-162">サブスクリプションまたは課金プロファイルが関連付けられていない支払方法を削除する</span><span class="sxs-lookup"><span data-stu-id="bd6c4-162">Delete a payment method with no subscriptions or billing profiles attached</span></span>

<span data-ttu-id="bd6c4-163">支払方法がサブスクリプションまたは課金プロファイルに関連付けられていない場合は、すぐに削除できます。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-163">If a payment method isn't associated with any subscriptions or billing profiles, you can immediately delete it.</span></span>

1. <span data-ttu-id="bd6c4-164">管理センターで、**[課金]** > **[請求と支払い]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">[支払方法]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-164">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="bd6c4-165">削除するお支払方法を見つけ、3 つのドットを選択してから、**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-165">Find the payment method to delete, select the three dots, then select **Delete**.</span></span>
3. <span data-ttu-id="bd6c4-166">右側のウィンドウの一番下にある **[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-166">At the bottom of the right pane, select **Delete**.</span></span>

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="bd6c4-167">サブスクリプションまたは課金プロファイルが関連付けられている支払方法を削除する</span><span class="sxs-lookup"><span data-stu-id="bd6c4-167">Delete a payment method with subscriptions or billing profiles attached</span></span>

<span data-ttu-id="bd6c4-168">支払方法がサブスクリプションまたは課金プロファイルに関連付けられている場合は、既存の支払方法に置き換えるか、新しい支払方法を追加してから、古い支払方法を削除します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-168">If a payment method is attached to any subscriptions or billing profiles, first replace it with an existing payment method, or add a new one, then delete the old payment method.</span></span>

1. <span data-ttu-id="bd6c4-169">管理センターで、**[課金]** > **[請求と支払い]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">[支払方法]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-169">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="bd6c4-170">削除する支払方法の行を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-170">Select the row for the payment method to delete.</span></span> <span data-ttu-id="bd6c4-171">右側のウィンドウには、その支払方法を使用する既存のサブスクリプションが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-171">The right pane lists existing subscriptions that use that payment method.</span></span>
3. <span data-ttu-id="bd6c4-172">右側のウィンドウで、**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-172">In the right pane, select **Delete**.</span></span>
4. <span data-ttu-id="bd6c4-173">既存の支払方法を使用する場合は、ドロップダウン リストからいずれかのオプションを選択して、**[次へ]** を選択してから **[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-173">To use an existing payment method, choose one from the drop-down list, select **Next**, and then select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="bd6c4-174">課金プロファイルに関連付けられているサブスクリプションがある場合は、クレジット カードのみ支払いに使用できます。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-174">If you have subscriptions associated with a billing profile, you can only use a credit card to pay for them.</span></span> <span data-ttu-id="bd6c4-175">**[支払方法]** ページに銀行口座が表示されている場合は、ドロップダウン リストで選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-175">If you have bank accounts listed on the **Payment methods** page, they aren't available to choose in the drop-down list.</span></span>
5. <span data-ttu-id="bd6c4-176">新しい支払方法を追加するには、**[支払方法の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-176">To add a new payment method, select **Add payment method**.</span></span>
6. <span data-ttu-id="bd6c4-177">追加するお支払方法の種類を選択し、アカウント情報を入力して、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-177">Choose the type of payment method that you want to add, enter the account information, and then select **Save**.</span></span>
7. <span data-ttu-id="bd6c4-178">新しい支払方法は、ドロップダウン リストで既に選択されています。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-178">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="bd6c4-179">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-179">Select **Next**.</span></span>
8. <span data-ttu-id="bd6c4-180">**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-180">Select **Delete**.</span></span>

## <a name="troubleshoot-payment-methods"></a><span data-ttu-id="bd6c4-181">支払方法のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bd6c4-181">Troubleshoot payment methods</span></span>

| <span data-ttu-id="bd6c4-182">問題</span><span class="sxs-lookup"><span data-stu-id="bd6c4-182">Issue</span></span> | <span data-ttu-id="bd6c4-183">トラブルシューティングの手順</span><span class="sxs-lookup"><span data-stu-id="bd6c4-183">Troubleshooting steps</span></span> |
|:----------|:-----|
|<span data-ttu-id="bd6c4-184">**「ブラウザーが Cookie をブロックする設定になっています。」というエラー メッセージが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="bd6c4-184">**I get an error message that says, "The browser is currently set to block cookies."**</span></span> |<span data-ttu-id="bd6c4-185">サードパーティの Cookie を許可するようにブラウザーを設定し、もう一度試してください。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-185">Set your browser to allow third-party cookies and try again.</span></span> |
|<span data-ttu-id="bd6c4-186">**自分のクレジット カードまたはデビット カードが拒否されました。**</span><span class="sxs-lookup"><span data-stu-id="bd6c4-186">**My credit or debit card was declined.**</span></span> |<span data-ttu-id="bd6c4-187">クレジット カードまたはデビット カードで支払い、カードが拒否された場合、Microsoft が支払いを処理できなかったことを通知するメールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-187">If you pay by credit or debit card, and your card is declined, you receive an email that says Microsoft was unable to process the payment.</span></span> <span data-ttu-id="bd6c4-188">&mdash;カード番号、有効期限、名義人の氏名、住所 (市町村、都道府県、郵便番号を含む)&mdash; などのカードの詳細がカードに刻印された情報やご利用明細書に記載された内容と同じであることを再確認してください。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-188">Double-check that the card details&mdash;card number, expiration date, name on the card, and address, including city, state, and ZIP code&mdash;appear exactly as they do on the card and your statement.</span></span> <span data-ttu-id="bd6c4-189">サブスクリプションの詳細ページの **[課金]** セクションにある **[残高の決済]** リンクを使用すると、カード情報を更新してすぐに支払いを申し込むことができます。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-189">You can update your card information and immediately submit the payment by using the **Settle balance** link in the **Billing** section of the subscription details page.</span></span> <span data-ttu-id="bd6c4-190">詳細については、「[未払額ある場合、どうなりますか?](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-190">For more information, see [What if I have an outstanding balance?](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)</span></span>  <br/><br/>  <span data-ttu-id="bd6c4-191">それでも、ご利用いただけないというメッセージが表示される場合は、ご契約先の金融機関にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-191">If you continue to see the "declined" message, contact your bank.</span></span> <span data-ttu-id="bd6c4-192">カードがアクティブでない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-192">It's possible that your card isn't active.</span></span> <span data-ttu-id="bd6c4-193">有効期限が更新されたカードを最近メールで受け取った場合は、有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-193">If you recently received the card in the mail with an updated expiration date, make sure it's activated.</span></span> <span data-ttu-id="bd6c4-194">また、カードでのオンライン取引、国際取引、または定期的な取引が承認されていないかどうかも、ご契約先の金融機関に確認できます。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-194">Your bank can also tell you whether your card isn't approved for online, international, or recurring transactions.</span></span> |
|<span data-ttu-id="bd6c4-195">**カード番号または銀行口座番号を更新したいです。**</span><span class="sxs-lookup"><span data-stu-id="bd6c4-195">**I want to update a card or bank account number.**</span></span> |<span data-ttu-id="bd6c4-196">既存の支払方法ではカード番号や口座番号の変更はできません。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-196">You can't change the card or account number on an existing payment method.</span></span> <span data-ttu-id="bd6c4-197">カード番号または口座番号が変更された場合は、[別の支払方法に置き換えて](#replace-a-payment-method)、アクティブなすべてのサブスクリプションの支払方法を新しい支払方法に置き換えてから、[古い支払方法を削除します](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached)。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-197">If your card or account number has changed, [replace it with a different payment method](#replace-a-payment-method), which moves all active subscriptions from the payment method to the new one, then [delete the old payment method](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span></span> |
|<span data-ttu-id="bd6c4-198">**アカウントにカードまたは口座を 1 つだけ登録していますが、そのカードまたは口座を削除したいです。**</span><span class="sxs-lookup"><span data-stu-id="bd6c4-198">**I only have one card or bank account on my account and I want to remove it.**</span></span> |<span data-ttu-id="bd6c4-199">支払方法が 1 つのみである場合は、削除する前に、[新しい支払方法に置き換える](#replace-a-payment-method)必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-199">If you only have one payment method, you must [replace it with a new payment method](#replace-a-payment-method) before you can delete it.</span></span> |
|<span data-ttu-id="bd6c4-200">**カードや銀行口座を追加できません。**</span><span class="sxs-lookup"><span data-stu-id="bd6c4-200">**I can't add my card or bank account.**</span></span>  |<span data-ttu-id="bd6c4-201">テナントと同じ国から発行された支払方法を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-201">You must use a payment method issued from the same country as your tenant.</span></span> <span data-ttu-id="bd6c4-202">カード情報や銀行口座情報の入力に関する問題が発生している場合は、[サポートにお問い合わせください](../../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="bd6c4-202">If you have trouble entering your card or bank account information, you can [contact support](../../admin/contact-support-for-business-products.md).</span></span> |

## <a name="related-content"></a><span data-ttu-id="bd6c4-203">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="bd6c4-203">Related content</span></span>

<span data-ttu-id="bd6c4-204">[一般法人向けサブスクリプションを支払う](pay-for-your-subscription.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="bd6c4-204">[Pay for your business subscription](pay-for-your-subscription.md) (article)</span></span>\
<span data-ttu-id="bd6c4-205">[課金プロフィールを管理する](manage-billing-profiles.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="bd6c4-205">[Manage billing profiles](manage-billing-profiles.md) (article)</span></span>\
<span data-ttu-id="bd6c4-206">[請求頻度を変更する](change-payment-frequency.md) (記事)\</span><span class="sxs-lookup"><span data-stu-id="bd6c4-206">[Change your billing frequency](change-payment-frequency.md) (article)</span></span>
