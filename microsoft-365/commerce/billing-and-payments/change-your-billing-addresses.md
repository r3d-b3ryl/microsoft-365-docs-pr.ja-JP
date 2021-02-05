---
title: 請求先住所を変更する
f1.keywords:
- NOCSH
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
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: a25c10d6-c1e9-4299-9185-25178df9eba6
description: ビジネス向け Microsoft 365 の請求先住所を更新する方法について説明します。請求通知の受信に使用するメール アドレスを更新することもできます。
ms.openlocfilehash: a6019a72bff1e5f4a3d0e6fdc6bb8cf7b8344d26
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114873"
---
# <a name="change-your-billing-addresses"></a><span data-ttu-id="4e99e-104">請求先住所を変更する</span><span class="sxs-lookup"><span data-stu-id="4e99e-104">Change your billing addresses</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="4e99e-105">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="4e99e-105">The admin center is changing.</span></span> <span data-ttu-id="4e99e-106">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e99e-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="4e99e-107">課金内容や請求書には次の 3 つの住所が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4e99e-107">Your bill or invoice contains three addresses:</span></span>
  
- <span data-ttu-id="4e99e-108">**販売先住所** 組織のプロファイルに表示されている会社の名前と住所です。</span><span class="sxs-lookup"><span data-stu-id="4e99e-108">**Sold-To Address** Your company name and address, as shown in your organization profile.</span></span>

- <span data-ttu-id="4e99e-109">**請求先住所** これは請求部門の住所で、通常は **販売先** の住所と同じです。</span><span class="sxs-lookup"><span data-stu-id="4e99e-109">**Bill-To address** The address of your billing department, usually the same as the **Sold-To** address.</span></span>

- <span data-ttu-id="4e99e-p103">**サービスの利用先住所** サービスが使用される住所です。通常、これは **販売先** 住所と同じです。組織にリモート ユーザーまたは複数のオフィスが存在する場合は、ユーザーの大多数が存在する住所を使用します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-p103">**Service Usage Address** The address where the service is being used, usually the same as the **Sold-To** address. If your organization has remote users or multiple offices, use the address where the majority of your users are located.</span></span>

<span data-ttu-id="4e99e-112">ほとんどの場合、これらの住所は同じです。</span><span class="sxs-lookup"><span data-stu-id="4e99e-112">In most cases, these addresses are the same.</span></span> <span data-ttu-id="4e99e-113">必要があれば、これらの住所のうち 1 つ以上を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="4e99e-113">If you need to change one or more of the addresses, you can do that.</span></span> <span data-ttu-id="4e99e-114">また、請求通知を受信する連絡用メール アドレスを指定し、他の管理者の連絡用メール アドレスを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="4e99e-114">You can also provide an alternate email address to receive billing notifications and change the alternate email address for other admins.</span></span>
  
::: moniker range="o365-worldwide"

<span data-ttu-id="4e99e-115">請求書または請求書の詳細については、「請求書または請求書[](view-your-bill-or-invoice.md)を表示する」および「請求書または請求書について[」を参照してください](understand-your-invoice2.md)。</span><span class="sxs-lookup"><span data-stu-id="4e99e-115">To learn more about your bill or invoice, see [View your bill or invoice](view-your-bill-or-invoice.md) and [Understand your bill or invoice](understand-your-invoice2.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="4e99e-116">請求書または請求書の詳細については、「請求書または請求書[](view-your-bill-or-invoice.md)を表示する」および「請求書または請求書について[」を参照してください](understand-your-invoice2.md)。</span><span class="sxs-lookup"><span data-stu-id="4e99e-116">To learn more about your bill or invoice, see [View your bill or invoice](view-your-bill-or-invoice.md) and [Understand your bill or invoice](understand-your-invoice2.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="4e99e-117">中国の 21Vianet が運営する Office 365 を使用している場合は、「[21Vianet で運用されている Office 365 での請求書の表示または Fapiaos の取得](../../admin/services-in-china/view-your-bill-or-get-a-fapiao.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e99e-117">If you're using Office 365 operated by 21Vianet in China, see [View your bill or get Fapiaos for Office 365 operated by 21Vianet](../../admin/services-in-china/view-your-bill-or-get-a-fapiao.md).</span></span>

::: moniker-end

## <a name="change-your-sold-to-address"></a><span data-ttu-id="4e99e-118">販売先住所を変更する</span><span class="sxs-lookup"><span data-stu-id="4e99e-118">Change your Sold-To address</span></span>

1. <span data-ttu-id="4e99e-119">管理センターで、**[課金情報]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">[請求対象アカウント]</a> ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-119">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Billing accounts</a> page.</span></span>

2. <span data-ttu-id="4e99e-120">[**請求先アカウントの情報を編集する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-120">select **Edit billing account information**.</span></span>

3. <span data-ttu-id="4e99e-121">組織の情報を更新し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-121">Update your organization information, then select **Save**.</span></span>
  
## <a name="change-your-bill-to-address"></a><span data-ttu-id="4e99e-122">請求先住所を変更する</span><span class="sxs-lookup"><span data-stu-id="4e99e-122">Change your Bill-To address</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4e99e-123">管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">支払い方法</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-123">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>

2. <span data-ttu-id="4e99e-124">変更するクレジット カードまたは銀行口座を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-124">Select the credit card or bank account that you want to change.</span></span>

3. <span data-ttu-id="4e99e-125">[**支払方法の詳細**] ページで、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-125">On the **Payment method details** page, select **Edit**.</span></span>

4. <span data-ttu-id="4e99e-126">請求先住所を更新し、[**保存**] \> [**完了**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-126">Update your billing address, then select **Save** \> **Done**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4e99e-127">管理センターの [**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-127">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="4e99e-128">変更するサブスクリプションを選択し、[**支払いの詳細の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-128">Select the subscription you want to change, then select **Change payment details**.</span></span>

    ![クレジット カードを使用して支払われているサブスクリプションのサブスクリプション カードの [支払い方法] セクション。](../../media/6c9d9cae-6086-4687-a979-bb971f35f1b4.png)
  
3. <span data-ttu-id="4e99e-130">*クレジット カードおよび銀行口座のお客様:* [**支払いの詳細の変更**] ページで、更新するクレジット カードまたは銀行口座を選択し、[**詳細の編集**] を選択し、請求先住所を更新して [**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-130">*Credit card and bank account customers:*  On the **Change payment details** page, select the credit card or bank account that you want to update, select **Edit details**, update your billing address, then select **Submit**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="4e99e-131">一部の国または地域では、銀行口座引き落としによる支払いを利用できません。</span><span class="sxs-lookup"><span data-stu-id="4e99e-131">The ability to pay by bank account isn't available in some countries or regions.</span></span>

     <span data-ttu-id="4e99e-132">*請求書のお客様:* [**支払いの詳細の変更**] ページで請求先住所を更新し、[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-132">*Invoice customers:*  On the **Change payment details** page, update your billing address, then select **Submit**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="4e99e-133">一部の国または地域では、小切手による請求書の支払いを利用できません。</span><span class="sxs-lookup"><span data-stu-id="4e99e-133">The ability to pay an invoice by check isn't available in some countries or regions.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4e99e-134">管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">製品とサービス</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-134">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="4e99e-135">変更するサブスクリプションを選択し、[**支払いの詳細の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-135">Select the subscription you want to change, then select **Change payment details**.</span></span>

    ![請求書を使用して支払われているサブスクリプションのサブスクリプション カードの [支払い方法] セクション。](../../media/51ab38aa-6e15-4e51-9f27-261c38c98fed.png)
  
3. <span data-ttu-id="4e99e-137">[**支払いの詳細の変更**] ページで請求先住所を更新し、[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-137">On the **Change payment details** page, update your billing address, and then select **Submit**.</span></span>

    <span data-ttu-id="4e99e-138">21Vianet が運用している Office 365 の支払い方法は、Alipay または China UnionPay を使用して請求書からオンライン支払いに変更するか、またはその逆を使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="4e99e-138">You can change your payment method for Office 365 operated by 21Vianet from Invoice to Online payment using Alipay or China UnionPay, or vice versa.</span></span>

::: moniker-end

## <a name="change-your-service-usage-address"></a><span data-ttu-id="4e99e-139">サービスの利用先住所を変更する</span><span class="sxs-lookup"><span data-stu-id="4e99e-139">Change your service usage address</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4e99e-140">管理センターで、**[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[お使いの製品]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-140">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="4e99e-141">**[製品]** タブで、変更するサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-141">On the **Products** tab, select the subscription that you want to change.</span></span>
3. <span data-ttu-id="4e99e-142">サブスクリプションの詳細ページの [サービスの利用先アドレス **]** セクションで、[サービスの利用先住所の編集 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4e99e-142">On the subscription details page, in the **Service usage address** section, select **Edit service usage address**.</span></span>
4. <span data-ttu-id="4e99e-143">[サービスの **利用先住所の編集** ] ウィンドウで、アドレスを更新し、[保存] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="4e99e-143">In the **Edit service usage address** pane, update your address, then select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4e99e-144">管理センターの **[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">[サブスクリプション]</a> ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-144">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="4e99e-145">変更するサブスクリプションを選択し、[**その他の操作**] を選択し、[**サービスの利用先住所の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-145">Select the subscription you want to change, select **More actions**, then choose **Edit service usage address**.</span></span>

    ![[その他の操作] メニューのクローズアップ。](../../media/befa74b7-62c1-42a3-a38e-db76a1c97dba.png)
  
3. <span data-ttu-id="4e99e-147">[**サービスの利用先住所の編集**] ウィンドウで住所を更新し、[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-147">In the **Edit your service usage address** pane, update your address, then select **Submit**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4e99e-148">管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">製品とサービス</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-148">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="4e99e-149">変更するサブスクリプションを選択し、[**その他の操作**] を選択し、[**サービスの利用先住所の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-149">Select the subscription you want to change, select **More actions**, then choose **Edit service usage address**.</span></span>

    ![[その他の操作] メニューのクローズアップ。](../../media/befa74b7-62c1-42a3-a38e-db76a1c97dba.png)
  
3. <span data-ttu-id="4e99e-151">[**サービスの利用先住所の編集**] ウィンドウで住所を更新し、[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-151">In the **Edit your service usage address** pane, update your address, then select **Submit**.</span></span>

::: moniker-end

## <a name="change-the-alternate-email-address-your-billing-notifications-are-sent-to"></a><span data-ttu-id="4e99e-152">請求通知の送り先である連絡用電子メール アドレスを変更する</span><span class="sxs-lookup"><span data-stu-id="4e99e-152">Change the alternate email address your billing notifications are sent to</span></span>

<span data-ttu-id="4e99e-153">既定では、組織の請求通知は、組織内のすべてのグローバル管理者および課金管理者の Microsoft 電子メール アドレスと連絡用メール アドレスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="4e99e-153">By default, your organization's billing notifications are sent to the Microsoft email address and the alternate email address of every global and billing admin in your organization.</span></span> <span data-ttu-id="4e99e-154">各管理者は、自身のプロファイル情報を更新することによって、連絡用メール アドレスを変更できます。</span><span class="sxs-lookup"><span data-stu-id="4e99e-154">Each admin can change their alternate email address by updating their profile information.</span></span>
  
1. <span data-ttu-id="4e99e-155">グローバル管理者として、自分の仕事用または学校アカウントで Microsoft 365 にサインインします。サインインする [方法について説明します](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="4e99e-155">Sign in to Microsoft 365 with your work or school account as a global admin. [Learn how to sign in](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="4e99e-156">[**ユーザー アイコン**] を選択し、[**マイ アカウント**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-156">Select the **User icon**, then select **My account**.</span></span>
  
3. <span data-ttu-id="4e99e-157">[**個人情報**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-157">Select **Personal info**.</span></span>
  
4. <span data-ttu-id="4e99e-158">[**連絡先の詳細**] ボックスで [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-158">In the **Contact details** box, select **Edit**.</span></span>

5. <span data-ttu-id="4e99e-159">[**連絡用メール アドレス**] ボックスに使用する連絡用メール アドレスを入力し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-159">In the **Alternate email** box, type the alternate email address you want to use, then select **Save**.</span></span>
  
## <a name="change-the-alternate-email-address-for-another-admin"></a><span data-ttu-id="4e99e-160">別の管理者の連絡用メール アドレスを変更する</span><span class="sxs-lookup"><span data-stu-id="4e99e-160">Change the alternate email address for another admin</span></span>

<span data-ttu-id="4e99e-161">組織内の他のグローバル カタログや課金管理者の連絡用メール アドレスを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="4e99e-161">You can also change the alternate email address of other global and billing admins in your organization.</span></span>

::: moniker range="o365-worldwide"
  
1. <span data-ttu-id="4e99e-162">管理センターで、**[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">[課金に関する通知]</a> ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-162">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4e99e-163">管理センターで、**[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=853213" target="_blank">[課金に関する通知]</a> ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-163">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=853213" target="_blank">Billing notifications</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4e99e-164">管理センターで、[課金情報の通知] \> <a href="https://go.microsoft.com/fwlink/p/?linkid=853215" target="_blank">ページに移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-164">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=853215" target="_blank">Billing Notifications</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="4e99e-165">[**課金に関する通知**] ページで、変更する管理者を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-165">On the **Billing notifications** page, select the admin you want to change.</span></span>

3. <span data-ttu-id="4e99e-166">[**ユーザーの役割の編集**] ウィンドウで使用する連絡用メール アドレスを入力し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e99e-166">In the **Edit user roles** pane, type the alternate email address you want to use, then select **Save**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="4e99e-167">関連記事</span><span class="sxs-lookup"><span data-stu-id="4e99e-167">Related articles</span></span>

[<span data-ttu-id="4e99e-168">課金内容または請求書を表示する</span><span class="sxs-lookup"><span data-stu-id="4e99e-168">View your bill or invoice</span></span>](view-your-bill-or-invoice.md)

[<span data-ttu-id="4e99e-169">課金内容または請求書の内容を理解する</span><span class="sxs-lookup"><span data-stu-id="4e99e-169">Understand your bill or invoice</span></span>](understand-your-invoice2.md)

[<span data-ttu-id="4e99e-170">サブスクリプションの代金を支払う</span><span class="sxs-lookup"><span data-stu-id="4e99e-170">Pay for your subscription</span></span>](pay-for-your-subscription.md)

[<span data-ttu-id="4e99e-171">サブスクリプションと課金 - 管理者向けヘルプ</span><span class="sxs-lookup"><span data-stu-id="4e99e-171">Subscriptions and billing - Admin Help</span></span>](../index.yml)
