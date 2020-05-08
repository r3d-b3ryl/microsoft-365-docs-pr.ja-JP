---
title: 組織のサービスとしてのソフトウェアアプリを管理する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: Normal
ms.collection:
- commerce
search.appverid: MET150
description: Microsoft 365 管理センターでサードパーティ製アプリをアクティブ化および管理する方法について説明します。
ms.openlocfilehash: eb2826a4b0c69d61eb35a9dfff37e9dc2dd6ad71
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141190"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="52bf1-103">組織のサードパーティ製アプリのサブスクリプションを管理する</span><span class="sxs-lookup"><span data-stu-id="52bf1-103">Manage third-party app subscriptions for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="52bf1-104">管理センターが変更されています。</span><span class="sxs-lookup"><span data-stu-id="52bf1-104">The admin center is changing.</span></span> <span data-ttu-id="52bf1-105">ここに示されている詳細情報とは異なる場合は、「[新しい Microsoft 365 管理センターについ](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52bf1-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="52bf1-106">プレビューモードがオンになっている Microsoft 365 管理センターで、サードパーティ製アプリのライセンスと請求を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="52bf1-106">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="52bf1-107">更新された機能には、サブスクリプション管理の強化、請求情報へのアクセスの向上、請求書管理の柔軟性の向上などがあります。</span><span class="sxs-lookup"><span data-stu-id="52bf1-107">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="52bf1-108">サブスクリプション管理は、Microsoft の更新された commerce プラットフォームに基づいています。</span><span class="sxs-lookup"><span data-stu-id="52bf1-108">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="52bf1-109">これは、顧客が直接購入した、またはサードパーティプロバイダーからの、サービスとしてのソフトウェアアプリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="52bf1-109">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>

## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="52bf1-110">サービスとしてのソフトウェアアプリを入手する方法</span><span class="sxs-lookup"><span data-stu-id="52bf1-110">How to get software-as-a-service apps</span></span>

<span data-ttu-id="52bf1-111">サードパーティ製アプリを購入するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="52bf1-111">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="52bf1-112">**直接購入**–お客様は、 [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/)または[appsource](https://www.appsource.com/)からサブスクリプションを直接購入できます。</span><span class="sxs-lookup"><span data-stu-id="52bf1-112">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span>
- <span data-ttu-id="52bf1-113">**パートナー購入**–パートナーと協力してサブスクリプションを購入します。</span><span class="sxs-lookup"><span data-stu-id="52bf1-113">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="52bf1-114">**Microsoft 提案**: サードパーティ製のアプリを含む microsoft Sales からの提案に対応します。</span><span class="sxs-lookup"><span data-stu-id="52bf1-114">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="52bf1-115">お客様は、お客様がアプリを購入し、microsoft のカスタマーアグリーメントに同意すると、Microsoft 365 管理センターまたは Microsoft Store for Business でそれらを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="52bf1-115">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="52bf1-116">アプリプロバイダーは、フラットなレートで、またはユーザーのライセンスを購入することで、アプリを販売します。</span><span class="sxs-lookup"><span data-stu-id="52bf1-116">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="52bf1-117">**一律レート**–サイトベースの価格とも呼ばれ、アプリの価格は月または年間の価格になります。</span><span class="sxs-lookup"><span data-stu-id="52bf1-117">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="52bf1-118">[アプリ] ページで、ライセンスの数量が無制限に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="52bf1-118">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="52bf1-119">**ライセンス**–アプリの価格はライセンスによるものです。</span><span class="sxs-lookup"><span data-stu-id="52bf1-119">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="52bf1-120">顧客が組織内の各ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="52bf1-120">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="52bf1-121">サポートされる地域</span><span class="sxs-lookup"><span data-stu-id="52bf1-121">Supported regions</span></span>

<span data-ttu-id="52bf1-122">サードパーティ製アプリのサポートは、次の地域で利用できます。</span><span class="sxs-lookup"><span data-stu-id="52bf1-122">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="52bf1-123">アルゼンチン</span><span class="sxs-lookup"><span data-stu-id="52bf1-123">Argentina</span></span>
- <span data-ttu-id="52bf1-124">オーストラリア</span><span class="sxs-lookup"><span data-stu-id="52bf1-124">Australia</span></span>
- <span data-ttu-id="52bf1-125">カナダ</span><span class="sxs-lookup"><span data-stu-id="52bf1-125">Canada</span></span>
- <span data-ttu-id="52bf1-126">チリ</span><span class="sxs-lookup"><span data-stu-id="52bf1-126">Chile</span></span>
- <span data-ttu-id="52bf1-127">フランス</span><span class="sxs-lookup"><span data-stu-id="52bf1-127">France</span></span>
- <span data-ttu-id="52bf1-128">ドイツ</span><span class="sxs-lookup"><span data-stu-id="52bf1-128">Germany</span></span>
- <span data-ttu-id="52bf1-129">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="52bf1-129">Greece</span></span>
- <span data-ttu-id="52bf1-130">プエルトリコ</span><span class="sxs-lookup"><span data-stu-id="52bf1-130">Puerto Rico</span></span>
- <span data-ttu-id="52bf1-131">南アフリカ</span><span class="sxs-lookup"><span data-stu-id="52bf1-131">South Africa</span></span>
- <span data-ttu-id="52bf1-132">英国</span><span class="sxs-lookup"><span data-stu-id="52bf1-132">United Kingdom</span></span>
- <span data-ttu-id="52bf1-133">米国</span><span class="sxs-lookup"><span data-stu-id="52bf1-133">United States</span></span>
- <span data-ttu-id="52bf1-134">西ヨーロッパ</span><span class="sxs-lookup"><span data-stu-id="52bf1-134">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="52bf1-135">サードパーティ製アプリをアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="52bf1-135">Activate third-party apps</span></span>

<span data-ttu-id="52bf1-136">管理者は、ユーザーに割り当てる前にサードパーティ製アプリをアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52bf1-136">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="52bf1-137">これらのアプリは、サードパーティの発行元のポータルでアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="52bf1-137">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="52bf1-138">管理センターで、[**製品** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">アプリ</a>の**課金** > ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="52bf1-138">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="52bf1-139">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="52bf1-139">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="52bf1-140">[**設定 & アクション**] で、[**パブリッシャーのポータルで管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="52bf1-140">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="52bf1-141">アプリをアクティブ化できるアプリの発行元のサイトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="52bf1-141">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="52bf1-142">サードパーティ製のアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="52bf1-142">Manage third-party apps</span></span>

<span data-ttu-id="52bf1-143">管理者は、サードパーティ製アプリを2か所で管理します。 Microsoft 365 管理センター、およびサードパーティのアプリプロバイダーのポータル。</span><span class="sxs-lookup"><span data-stu-id="52bf1-143">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="52bf1-144">各ポータルで実行できる操作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="52bf1-144">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="52bf1-145">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="52bf1-145">Microsoft 365 admin center</span></span> | <span data-ttu-id="52bf1-146">アプリ発行元ポータル</span><span class="sxs-lookup"><span data-stu-id="52bf1-146">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="52bf1-147">ライセンス数を変更する</span><span class="sxs-lookup"><span data-stu-id="52bf1-147">Change license quantity</span></span> <br> <span data-ttu-id="52bf1-148">支払い方法を管理する</span><span class="sxs-lookup"><span data-stu-id="52bf1-148">Manage how you pay your bill</span></span> <br> <span data-ttu-id="52bf1-149">支払い方法を管理する</span><span class="sxs-lookup"><span data-stu-id="52bf1-149">Manage how you pay your bill</span></span> <br> <span data-ttu-id="52bf1-150">支払い方法の変更 (クレジットカード)</span><span class="sxs-lookup"><span data-stu-id="52bf1-150">Change payment method (credit card)</span></span> <br> <span data-ttu-id="52bf1-151">請求書の表示</span><span class="sxs-lookup"><span data-stu-id="52bf1-151">View invoice</span></span> <br> <span data-ttu-id="52bf1-152">アプリのサブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="52bf1-152">Cancel app subscription</span></span> | <span data-ttu-id="52bf1-153">アプリをセットアップする (アプリごとに1回)</span><span class="sxs-lookup"><span data-stu-id="52bf1-153">Set up app (once for each app)</span></span> <br> <span data-ttu-id="52bf1-154">ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="52bf1-154">Assign licenses to users</span></span> <br> <span data-ttu-id="52bf1-155">テクニカル サポート</span><span class="sxs-lookup"><span data-stu-id="52bf1-155">Technical support</span></span> |

<span data-ttu-id="52bf1-156">アプリがアクティブ化されると、そのアプリはキャンセルされるか、期限切れになるか、または支払いが最新の状態に保たれない限り、アクティブのままになります。</span><span class="sxs-lookup"><span data-stu-id="52bf1-156">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="52bf1-157">これらのイベントは、アプリの状態を無効に変更します。</span><span class="sxs-lookup"><span data-stu-id="52bf1-157">These events change the app status to disabled.</span></span> <span data-ttu-id="52bf1-158">アプリを無効にすると、再度アクティブにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="52bf1-158">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="52bf1-159">アプリを引き続き使用するには、別のコピーを購入してください。</span><span class="sxs-lookup"><span data-stu-id="52bf1-159">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="52bf1-160">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="52bf1-160">Assign licenses</span></span>

<span data-ttu-id="52bf1-161">管理者は、ユーザーに割り当てる前に、サードパーティ製のアプリをアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52bf1-161">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="52bf1-162">これらは、サードパーティの発行元のポータルでアクティブ化されています。</span><span class="sxs-lookup"><span data-stu-id="52bf1-162">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="52bf1-163">[アプリ] ページの [**設定 & アクション**] で、ライセンスを割り当てるリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="52bf1-163">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="52bf1-164">管理センターで、[**製品** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">アプリ</a>の**課金** > ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="52bf1-164">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="52bf1-165">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="52bf1-165">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="52bf1-166">**[設定とアクション]** で、**[発行元のポータルで管理する]** へのリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="52bf1-166">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="52bf1-167">ライセンス数を変更する</span><span class="sxs-lookup"><span data-stu-id="52bf1-167">Change license quantity</span></span>

<span data-ttu-id="52bf1-168">管理者は、組織によって所有されているライセンスの数を変更できます。</span><span class="sxs-lookup"><span data-stu-id="52bf1-168">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="52bf1-169">これは、座席ベースの価格設定を使用して購入したアプリにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="52bf1-169">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="52bf1-170">管理センターで、[**製品** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">アプリ</a>の**課金** > ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="52bf1-170">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="52bf1-171">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="52bf1-171">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="52bf1-172">[**ライセンス数量の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="52bf1-172">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="52bf1-173">支払方法を管理する</span><span class="sxs-lookup"><span data-stu-id="52bf1-173">Manage payment methods</span></span>

<span data-ttu-id="52bf1-174">サービスとしてのソフトウェアアプリにはそれぞれ、請求プロファイルが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="52bf1-174">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="52bf1-175">請求プロファイルを使用すると、請求書に含める製品をカスタマイズしたり、請求書に支払いを行ったりすることができます。</span><span class="sxs-lookup"><span data-stu-id="52bf1-175">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="52bf1-176">これには以下の関係者が含まれます。</span><span class="sxs-lookup"><span data-stu-id="52bf1-176">They include:</span></span>

- <span data-ttu-id="52bf1-177">**支払い方法**–クレジットカードまたは小切手/ワイヤ転送</span><span class="sxs-lookup"><span data-stu-id="52bf1-177">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="52bf1-178">**連絡先情報**-請求先住所と連絡先の名前</span><span class="sxs-lookup"><span data-stu-id="52bf1-178">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="52bf1-179">**役割**–請求プロファイルを変更したり、支払いを行ったり、購入するために請求書プロファイルの支払い方法を使用したりできるようにする役割。</span><span class="sxs-lookup"><span data-stu-id="52bf1-179">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="52bf1-180">請求プロファイルの詳細については、「[課金プロファイル](https://docs.microsoft.com/microsoft-store/billing-profile)について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52bf1-180">For more information on billing profiles, see [Understand billing profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="52bf1-181">サービスとしてのソフトウェアアプリサブスクリプションの課金プロファイルを変更する</span><span class="sxs-lookup"><span data-stu-id="52bf1-181">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="52bf1-182">管理センターで、[**製品** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">アプリ</a>の**課金** > ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="52bf1-182">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="52bf1-183">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="52bf1-183">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="52bf1-184">[**課金プロファイル**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="52bf1-184">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="52bf1-185">請求書の詳細については、「[請求書を理解する](billing-and-payments/understand-your-invoice.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52bf1-185">For more information on invoices, see [Understand your invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="52bf1-186">サービスとしてのソフトウェアアプリのサブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="52bf1-186">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="52bf1-187">アプリページから、サービスとしてのソフトウェアアプリを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="52bf1-187">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="52bf1-188">管理センターで、[**製品** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">アプリ</a>の**課金** > ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="52bf1-188">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="52bf1-189">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="52bf1-189">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="52bf1-190">[**設定とアクション**] の下で、[**サブスクリプションのキャンセル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="52bf1-190">Under **Settings & actions**, select **Cancel subscription**.</span></span>
