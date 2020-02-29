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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: Microsoft 365 管理センターで支払い方法を管理する方法について説明します。
ms.openlocfilehash: 61c6d0b4fb21762eaeee96d8923eda7702fc70bb
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341597"
---
# <a name="manage-payment-methods"></a><span data-ttu-id="cdf54-103">支払方法を管理する</span><span class="sxs-lookup"><span data-stu-id="cdf54-103">Manage payment methods</span></span>

<span data-ttu-id="cdf54-104">Microsoft からビジネス製品またはサービスを購入する場合は、既存の支払い方法を使用するか、または新しいサービスを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="cdf54-104">When you buy business products or services from Microsoft, you can use an existing payment method, or add a new one.</span></span> <span data-ttu-id="cdf54-105">クレジットカードまたはデビットカードまたは銀行口座を使用して、購入された事柄に対して支払いを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cdf54-105">You can use a credit or debit card, or bank account to pay for the things you buy.</span></span> <span data-ttu-id="cdf54-106">ただし、追加する支払い方法のみを管理できます。</span><span class="sxs-lookup"><span data-stu-id="cdf54-106">But you can only manage payment methods that you add.</span></span>

> [!NOTE]
> <span data-ttu-id="cdf54-107">銀行口座で支払うオプションは、一部の国や地域では使用できません。</span><span class="sxs-lookup"><span data-stu-id="cdf54-107">The option to pay with a bank account is not available in some countries or regions.</span></span>
>
> <span data-ttu-id="cdf54-108">テナントと同じ国から発行された支払い方法を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdf54-108">You must use a payment method issued from the same country as your tenant.</span></span>

## <a name="update-payment-method-details"></a><span data-ttu-id="cdf54-109">支払い方法の詳細を更新する</span><span class="sxs-lookup"><span data-stu-id="cdf54-109">Update payment method details</span></span>

<span data-ttu-id="cdf54-110">既存の支払い方法のクレジットカードまたはデビットカードの名前、請求先の住所、または有効期限を変更できます。</span><span class="sxs-lookup"><span data-stu-id="cdf54-110">You can change the name on the credit or debit card, billing address, or expiration date for an existing payment method.</span></span> <span data-ttu-id="cdf54-111">ただし、カードまたは口座番号を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="cdf54-111">However, you can't change the card or account number.</span></span> <span data-ttu-id="cdf54-112">アカウント番号が変更されている場合は、[別の支払い方法に置き換え](#replace-a-payment-method)てから、[古いものを削除](#delete-a-payment-method)します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-112">If the account number has changed, [replace it with a different payment method](#replace-a-payment-method), and then [delete the old one](#delete-a-payment-method).</span></span>

1. <span data-ttu-id="cdf54-113">管理センターで、[**課金請求書** > **&** > 支払い<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-113">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="cdf54-114">更新する支払い方法の行を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-114">Select the row of the payment method to update.</span></span> <span data-ttu-id="cdf54-115">右側のウィンドウで、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-115">In the right pane, select **Edit**.</span></span>
3. <span data-ttu-id="cdf54-116">支払い方法の情報 (クレジットカードまたはデビットカードの名前、請求先の住所、または有効期限の日付) を更新し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-116">Update your payment method information (name on the credit or debit card, billing address, or expiration date), then select **Save**.</span></span>

## <a name="replace-a-payment-method"></a><span data-ttu-id="cdf54-117">支払い方法を置換する</span><span class="sxs-lookup"><span data-stu-id="cdf54-117">Replace a payment method</span></span>

<span data-ttu-id="cdf54-118">支払い方法を置き換える場合、同じ支払い方法を使用しているすべてのサブスクリプションと請求書のプロファイルに対して、支払方法を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="cdf54-118">When you replace a payment method, you replace it for all subscriptions and billing profiles that use the same payment method.</span></span> <span data-ttu-id="cdf54-119">支払い方法を置き換えても、既存の支払い方法が削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="cdf54-119">Replacing a payment method doesn’t delete the existing payment method.</span></span> <span data-ttu-id="cdf54-120">その他のサブスクリプションと請求プロファイルのために、選択して使用することができます。</span><span class="sxs-lookup"><span data-stu-id="cdf54-120">It’s still available for you to select and use for other subscriptions and billing profiles.</span></span>

<span data-ttu-id="cdf54-121">単一のサブスクリプションの支払い方法を変更するには、「 [1 つのサブスクリプションの支払い方法を変更](#change-a-payment-method-for-a-single-subscription)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdf54-121">To change the payment method for a single subscription, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span>

1. <span data-ttu-id="cdf54-122">管理センターで、[**課金請求書** > **&** > 支払い<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-122">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="cdf54-123">置換する支払い方法の行を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-123">Select the row of the payment method to replace.</span></span> <span data-ttu-id="cdf54-124">右ウィンドウには、選択した支払い方法を使用するすべての課金プロファイルと個々のサブスクリプションが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="cdf54-124">The right pane lists all billing profiles and individual subscriptions that use the selected payment method.</span></span>
3. <span data-ttu-id="cdf54-125">右側のウィンドウで、[**すべてのアイテムに対して支払い方法を置換する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-125">In the right pane, select **Replace payment method for all items**.</span></span>
4. <span data-ttu-id="cdf54-126">既存の支払い方法を使用するには、ドロップダウンリストから1つを選択し、[**置換**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-126">To use an existing payment method, choose one from the drop-down list, then select **Replace**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="cdf54-127">課金プロファイルに関連付けられているサブスクリプションがある場合は、クレジットカードまたはデビットカードのみを使用して料金を支払うことができます。</span><span class="sxs-lookup"><span data-stu-id="cdf54-127">If you have subscriptions associated with a billing profile, you can only use a credit or debit card to pay for them.</span></span> <span data-ttu-id="cdf54-128">[**支払方法**] ページに銀行口座が表示されている場合は、ドロップダウンリストで選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="cdf54-128">If you have bank accounts listed on the **Payment methods** page, they aren’t available to select in the drop-down list.</span></span>
5. <span data-ttu-id="cdf54-129">新しい支払い方法を追加するには、[**支払い方法の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-129">To add a new payment method, select **Add payment method**.</span></span>
6. <span data-ttu-id="cdf54-130">[**支払い方法の追加**] ウィンドウで、アカウント情報を入力し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-130">In the **Add a payment method** pane, enter the account information, then select **Save**.</span></span> <span data-ttu-id="cdf54-131">テナントと同じ国の支払い方法を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdf54-131">You must use a payment method from the same country as your tenant.</span></span>
7. <span data-ttu-id="cdf54-132">新しい支払い方法は、ドロップダウンリストで既に選択されています。</span><span class="sxs-lookup"><span data-stu-id="cdf54-132">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="cdf54-133">**[置換]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-133">Select **Replace**.</span></span>

## <a name="change-a-payment-method-for-a-single-subscription"></a><span data-ttu-id="cdf54-134">1つのサブスクリプションの支払い方法を変更する</span><span class="sxs-lookup"><span data-stu-id="cdf54-134">Change a payment method for a single subscription</span></span>

<span data-ttu-id="cdf54-135">1つのサブスクリプションの支払いに使用する支払い方法を変更できます。</span><span class="sxs-lookup"><span data-stu-id="cdf54-135">You can change the payment method used to pay for a single subscription.</span></span>

1. <span data-ttu-id="cdf54-136">管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">製品とサービス</a>] のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-136">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>
2. <span data-ttu-id="cdf54-137">[**サブスクリプション**] タブで、別の支払い方法で支払う対象のサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-137">On the **Subscriptions** tab, select the subscription that you want to pay for with the alternate payment method.</span></span> 
3. <span data-ttu-id="cdf54-138">[**請求**] の下で支払い方法の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-138">Under **Billing**, next to the payment method, select **Edit**.</span></span>
4. <span data-ttu-id="cdf54-139">既存の支払い方法の横にある [**変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-139">Next to your existing payment method, select **Change**.</span></span>
5. <span data-ttu-id="cdf54-140">ドロップダウンリストから別の支払い方法を選択するか、支払い方法を追加します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-140">From the drop-down list, choose an alternate payment method, or choose to add a payment method.</span></span>
6. <span data-ttu-id="cdf54-141">支払い方法を追加する場合は、カードまたは口座の詳細を入力し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-141">If you add a payment method, enter the card or account details, then select **Save**.</span></span>
7. <span data-ttu-id="cdf54-142">選択した支払い方法が正しいことを確認し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-142">Verify that the selected payment method is correct, then select **Save**.</span></span>

## <a name="delete-a-payment-method"></a><span data-ttu-id="cdf54-143">支払い方法を削除する</span><span class="sxs-lookup"><span data-stu-id="cdf54-143">Delete a payment method</span></span>

<span data-ttu-id="cdf54-144">削除できるのは、サブスクリプションまたは課金プロファイルに関連付けられていない支払い方法のみです。</span><span class="sxs-lookup"><span data-stu-id="cdf54-144">You can only delete a payment method that isn’t attached to a subscription or billing profile.</span></span> <span data-ttu-id="cdf54-145">これは、その状態にかかわらずすべてのサブスクリプションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="cdf54-145">This applies to all subscriptions, whatever their status.</span></span>

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="cdf54-146">サブスクリプションまたは課金プロファイルが添付されていない支払い方法を削除する</span><span class="sxs-lookup"><span data-stu-id="cdf54-146">Delete a payment method with no subscriptions or billing profiles attached</span></span>

<span data-ttu-id="cdf54-147">支払い方法がサブスクリプションまたは請求プロファイルに関連付けられていない場合は、すぐに削除できます。</span><span class="sxs-lookup"><span data-stu-id="cdf54-147">If a payment method isn't associated with any subscriptions or billing profiles, you can immediately delete it.</span></span>

1. <span data-ttu-id="cdf54-148">管理センターで、[**課金請求書** > **&** > 支払い<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-148">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="cdf54-149">削除する支払い方法を検索し、3つのドットを選択して、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-149">Find the payment method to delete, select the three dots, then select **Delete**.</span></span>
3. <span data-ttu-id="cdf54-150">右側のウィンドウの下部にある [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-150">At the bottom of the right pane, select **Delete**.</span></span>

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="cdf54-151">サブスクリプションまたは課金プロファイルが添付されている支払い方法を削除する</span><span class="sxs-lookup"><span data-stu-id="cdf54-151">Delete a payment method with subscriptions or billing profiles attached</span></span>

<span data-ttu-id="cdf54-152">支払い方法がサブスクリプションまたは請求プロファイルに関連付けられている場合は、最初に既存の支払い方法で置き換えるか、新しい支払い方法を追加して、古い支払い方法を削除します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-152">If a payment method is attached to any subscriptions or billing profiles, first replace it with an existing payment method, or add a new one, then delete the old payment method.</span></span>

1. <span data-ttu-id="cdf54-153">管理センターで、[**課金請求書** > **&** > 支払い<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-153">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="cdf54-154">削除する支払い方法の行を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-154">Select the row for the payment method to delete.</span></span> <span data-ttu-id="cdf54-155">右側のウィンドウには、その支払い方法を使用する既存のサブスクリプションが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="cdf54-155">The right pane lists existing subscriptions that use that payment method.</span></span>
3. <span data-ttu-id="cdf54-156">右側のウィンドウで、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-156">In the right pane, select **Delete**.</span></span>
4. <span data-ttu-id="cdf54-157">既存の支払い方法を使用するには、ドロップダウンリストから1つを選択し、[**次へ**] を選択して、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-157">To use an existing payment method, choose one from the drop-down list, select **Next**, and then select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="cdf54-158">課金プロファイルに関連付けられているサブスクリプションがある場合は、クレジットカードのみを使用して料金を支払うことができます。</span><span class="sxs-lookup"><span data-stu-id="cdf54-158">If you have subscriptions associated with a billing profile, you can only use a credit card to pay for them.</span></span> <span data-ttu-id="cdf54-159">[**支払方法**] ページに銀行口座が表示されている場合は、ドロップダウンリストで選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="cdf54-159">If you have bank accounts listed on the **Payment methods** page, they aren’t available to choose in the drop-down list.</span></span>
5. <span data-ttu-id="cdf54-160">新しい支払い方法を追加するには、[**支払い方法の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-160">To add a new payment method, select **Add payment method**.</span></span>
6. <span data-ttu-id="cdf54-161">追加する支払い方法の種類を選択し、アカウント情報を入力してから [**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-161">Choose the type of payment method that you want to add, enter the account information, and then select **Save**.</span></span>
7. <span data-ttu-id="cdf54-162">新しい支払い方法は、ドロップダウンリストで既に選択されています。</span><span class="sxs-lookup"><span data-stu-id="cdf54-162">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="cdf54-163">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-163">Select **Next**.</span></span>
8. <span data-ttu-id="cdf54-164">**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-164">Select **Delete**.</span></span>

## <a name="troubleshoot-payment-methods"></a><span data-ttu-id="cdf54-165">支払い方法のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="cdf54-165">Troubleshoot payment methods</span></span>

|<span data-ttu-id="cdf54-166">**問題**</span><span class="sxs-lookup"><span data-stu-id="cdf54-166">**Issue**</span></span>|<span data-ttu-id="cdf54-167">**トラブルシューティングの手順**</span><span class="sxs-lookup"><span data-stu-id="cdf54-167">**Troubleshooting steps**</span></span>|
|:----------|:-----|
|<span data-ttu-id="cdf54-168">**"ブラウザーは現在、cookie をブロックするように設定されています" というエラーメッセージが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="cdf54-168">**I get an error message that says, "The browser is currently set to block cookies."**</span></span> |<span data-ttu-id="cdf54-169">サード パーティの Cookie を許可するようにブラウザーを設定し、もう一度試してください。</span><span class="sxs-lookup"><span data-stu-id="cdf54-169">Set your browser to allow third-party cookies and try again.</span></span> |
|<span data-ttu-id="cdf54-170">**クレジットカードまたはデビットカードが拒否されました。**</span><span class="sxs-lookup"><span data-stu-id="cdf54-170">**My credit or debit card was declined.**</span></span> |<span data-ttu-id="cdf54-171">クレジットカードまたはデビットカードで支払い、カードが拒否された場合、Microsoft が支払いを処理できなかったという電子メールが届きます。</span><span class="sxs-lookup"><span data-stu-id="cdf54-171">If you pay by credit or debit card, and your card is declined, you receive an email that says Microsoft was unable to process the payment.</span></span> <span data-ttu-id="cdf54-172">カードの詳細&mdash;カード番号、有効期限、カードの名前、および住所 (市区町村、都道府県、郵便番号を含む) がカードと明細書の内容とまったく同じように表示されることを、もう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="cdf54-172">Double-check that the card details &mdash; card number, expiration date, name on the card, and address, including city, state, and ZIP code — appear exactly as they do on the card and your statement.</span></span> <span data-ttu-id="cdf54-173">[サブスクリプションの詳細] ページの [**課金**] セクションの [**決済バランス**] リンクを使用して、カード情報を更新し、すぐに支払いを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="cdf54-173">You can update your card information and immediately submit the payment by using the **Settle balance** link in the **Billing** section of the subscription details page.</span></span> <span data-ttu-id="cdf54-174">詳細については、「[クレジット カードが拒否され、支払い期日を過ぎてしまった場合はどうなりますか?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdf54-174">For more information, see [What if my credit card was declined and my payment is past due?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)</span></span>  <br/><br/>  <span data-ttu-id="cdf54-175">引き続き "辞退" メッセージが表示される場合は、銀行にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="cdf54-175">If you continue to see the "declined" message, contact your bank.</span></span> <span data-ttu-id="cdf54-176">カードがアクティブではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cdf54-176">It's possible that your card isn't active.</span></span> <span data-ttu-id="cdf54-177">メールで、更新された有効期限の日付を最近受信した場合は、そのカードが有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cdf54-177">If you recently received the card in the mail with an updated expiration date, make sure it's activated.</span></span> <span data-ttu-id="cdf54-178">また、銀行は、オンライン、国際、または定期的な取引でカードが承認されていないかどうかを知らせることもできます。</span><span class="sxs-lookup"><span data-stu-id="cdf54-178">Your bank can also tell you whether your card isn't approved for online, international, or recurring transactions.</span></span> |
|<span data-ttu-id="cdf54-179">**カードまたは銀行口座番号を更新する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="cdf54-179">**I want to update a card or bank account number.**</span></span> |<span data-ttu-id="cdf54-180">既存の支払い方法でカードまたは口座番号を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="cdf54-180">You can't change the card or account number on an existing payment method.</span></span> <span data-ttu-id="cdf54-181">カードまたは口座番号が変更されている場合は、[別の支払い方法に置き換え](#replace-a-payment-method)ます。これは、支払い方法から新しい支払い方法にすべてのアクティブなサブスクリプションを移動して、[古い支払い方法を削除](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached)します。</span><span class="sxs-lookup"><span data-stu-id="cdf54-181">If your card or account number has changed, [replace it with a different payment method](#replace-a-payment-method), which moves all active subscriptions from the payment method to the new one, then [delete the old payment method](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span></span> |
|<span data-ttu-id="cdf54-182">**自分のアカウントに1つのカードまたは銀行口座しかない場合、そのアカウントを削除します。**</span><span class="sxs-lookup"><span data-stu-id="cdf54-182">**I only have one card or bank account on my account and I want to remove it.**</span></span> |<span data-ttu-id="cdf54-183">支払い方法が1つだけの場合は、それを削除する前に、[新しい支払い方法に置き換える](#replace-a-payment-method)必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdf54-183">If you only have one payment method, you must [replace it with a new payment method](#replace-a-payment-method) before you can delete it.</span></span> |
|<span data-ttu-id="cdf54-184">**自分のカードまたは銀行口座を追加できません。**</span><span class="sxs-lookup"><span data-stu-id="cdf54-184">**I can't add my card or bank account.**</span></span>  |<span data-ttu-id="cdf54-185">テナントと同じ国から発行された支払い方法を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdf54-185">You must use a payment method issued from the same country as your tenant.</span></span> <span data-ttu-id="cdf54-186">カードまたは銀行口座情報を入力するときに問題が発生した場合は、[サポートにお問い合わせ](../../admin/contact-support-for-business-products.md)ください。</span><span class="sxs-lookup"><span data-stu-id="cdf54-186">If you have trouble entering your card or bank account information, you can [contact support](../../admin/contact-support-for-business-products.md).</span></span> |

## <a name="related-articles"></a><span data-ttu-id="cdf54-187">関連記事</span><span class="sxs-lookup"><span data-stu-id="cdf54-187">Related articles</span></span>

[<span data-ttu-id="cdf54-188">法人向けサブスクリプションの支払い</span><span class="sxs-lookup"><span data-stu-id="cdf54-188">Pay for your business subscription</span></span>](pay-for-your-subscription.md)

[<span data-ttu-id="cdf54-189">課金プロフィールを管理する</span><span class="sxs-lookup"><span data-stu-id="cdf54-189">Manage billing profiles</span></span>](manage-billing-profiles.md)

[<span data-ttu-id="cdf54-190">支払い頻度を変更する</span><span class="sxs-lookup"><span data-stu-id="cdf54-190">Change your payment frequency</span></span>](change-payment-frequency.md)