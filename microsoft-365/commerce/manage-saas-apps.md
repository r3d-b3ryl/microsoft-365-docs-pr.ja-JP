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
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Microsoft 365 管理センターでサードパーティ製アプリをアクティブ化および管理する方法について説明します。
ms.openlocfilehash: ed1a88345ae5cc135a43f4297ce518b444eaabe7
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402584"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="52c12-103">組織のサードパーティ製アプリのサブスクリプションを管理する</span><span class="sxs-lookup"><span data-stu-id="52c12-103">Manage third-party app subscriptions for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="52c12-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="52c12-104">The admin center is changing.</span></span> <span data-ttu-id="52c12-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52c12-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="52c12-106">プレビューモードがオンになっている Microsoft 365 管理センターで、サードパーティ製アプリのライセンスと請求を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="52c12-106">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="52c12-107">更新された機能には、サブスクリプション管理の強化、請求情報へのアクセスの向上、請求書管理の柔軟性の向上などがあります。</span><span class="sxs-lookup"><span data-stu-id="52c12-107">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="52c12-108">サブスクリプション管理は、Microsoft の更新された commerce プラットフォームに基づいています。</span><span class="sxs-lookup"><span data-stu-id="52c12-108">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="52c12-109">これは、顧客が直接購入した、またはサードパーティプロバイダーからの、サービスとしてのソフトウェアアプリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="52c12-109">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>

## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="52c12-110">サービスとしてのソフトウェアアプリを入手する方法</span><span class="sxs-lookup"><span data-stu-id="52c12-110">How to get software-as-a-service apps</span></span>

<span data-ttu-id="52c12-111">サードパーティ製アプリを購入するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="52c12-111">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="52c12-112">**直接購入**–お客様は、 [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/)または[appsource](https://www.appsource.com/)からサブスクリプションを直接購入できます。</span><span class="sxs-lookup"><span data-stu-id="52c12-112">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span>
- <span data-ttu-id="52c12-113">**パートナー購入**–パートナーと協力してサブスクリプションを購入します。</span><span class="sxs-lookup"><span data-stu-id="52c12-113">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="52c12-114">**Microsoft 提案**: サードパーティ製のアプリを含む microsoft Sales からの提案に対応します。</span><span class="sxs-lookup"><span data-stu-id="52c12-114">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="52c12-115">お客様は、お客様がアプリを購入し、microsoft のカスタマーアグリーメントに同意すると、Microsoft 365 管理センターまたは Microsoft Store for Business でそれらを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="52c12-115">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="52c12-116">アプリプロバイダーは、フラットなレートで、またはユーザーのライセンスを購入することで、アプリを販売します。</span><span class="sxs-lookup"><span data-stu-id="52c12-116">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="52c12-117">**一律レート**–サイトベースの価格とも呼ばれ、アプリの価格は月または年間の価格になります。</span><span class="sxs-lookup"><span data-stu-id="52c12-117">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="52c12-118">[アプリ] ページで、ライセンスの数量が無制限に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="52c12-118">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="52c12-119">**ライセンス**–アプリの価格はライセンスによるものです。</span><span class="sxs-lookup"><span data-stu-id="52c12-119">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="52c12-120">顧客が組織内の各ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="52c12-120">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="52c12-121">サポートされる地域</span><span class="sxs-lookup"><span data-stu-id="52c12-121">Supported regions</span></span>

<span data-ttu-id="52c12-122">サードパーティ製アプリのサポートは、次の地域で利用できます。</span><span class="sxs-lookup"><span data-stu-id="52c12-122">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="52c12-123">アルゼンチン</span><span class="sxs-lookup"><span data-stu-id="52c12-123">Argentina</span></span>
- <span data-ttu-id="52c12-124">オーストラリア</span><span class="sxs-lookup"><span data-stu-id="52c12-124">Australia</span></span>
- <span data-ttu-id="52c12-125">カナダ</span><span class="sxs-lookup"><span data-stu-id="52c12-125">Canada</span></span>
- <span data-ttu-id="52c12-126">チリ</span><span class="sxs-lookup"><span data-stu-id="52c12-126">Chile</span></span>
- <span data-ttu-id="52c12-127">フランス</span><span class="sxs-lookup"><span data-stu-id="52c12-127">France</span></span>
- <span data-ttu-id="52c12-128">ドイツ</span><span class="sxs-lookup"><span data-stu-id="52c12-128">Germany</span></span>
- <span data-ttu-id="52c12-129">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="52c12-129">Greece</span></span>
- <span data-ttu-id="52c12-130">プエルトリコ</span><span class="sxs-lookup"><span data-stu-id="52c12-130">Puerto Rico</span></span>
- <span data-ttu-id="52c12-131">南アフリカ</span><span class="sxs-lookup"><span data-stu-id="52c12-131">South Africa</span></span>
- <span data-ttu-id="52c12-132">英国</span><span class="sxs-lookup"><span data-stu-id="52c12-132">United Kingdom</span></span>
- <span data-ttu-id="52c12-133">米国</span><span class="sxs-lookup"><span data-stu-id="52c12-133">United States</span></span>
- <span data-ttu-id="52c12-134">西ヨーロッパ</span><span class="sxs-lookup"><span data-stu-id="52c12-134">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="52c12-135">サードパーティ製アプリをアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="52c12-135">Activate third-party apps</span></span>

<span data-ttu-id="52c12-136">管理者は、ユーザーに割り当てる前にサードパーティ製アプリをアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52c12-136">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="52c12-137">これらのアプリは、サードパーティの発行元のポータルでアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="52c12-137">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="52c12-138">管理センターで、[製品アプリの**課金**] ページに移動し  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a>ます。</span><span class="sxs-lookup"><span data-stu-id="52c12-138">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="52c12-139">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="52c12-139">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="52c12-140">[**設定 & アクション**] で、[**パブリッシャーのポータルで管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="52c12-140">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="52c12-141">アプリをアクティブ化できるアプリの発行元のサイトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="52c12-141">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="52c12-142">サードパーティ製のアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="52c12-142">Manage third-party apps</span></span>

<span data-ttu-id="52c12-143">管理者は、サードパーティ製アプリを2か所で管理します。 Microsoft 365 管理センター、およびサードパーティのアプリプロバイダーのポータル。</span><span class="sxs-lookup"><span data-stu-id="52c12-143">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="52c12-144">各ポータルで実行できる操作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="52c12-144">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="52c12-145">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="52c12-145">Microsoft 365 admin center</span></span> | <span data-ttu-id="52c12-146">アプリ発行元ポータル</span><span class="sxs-lookup"><span data-stu-id="52c12-146">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="52c12-147">ライセンス数を変更する</span><span class="sxs-lookup"><span data-stu-id="52c12-147">Change license quantity</span></span> <br> <span data-ttu-id="52c12-148">支払い方法を管理する</span><span class="sxs-lookup"><span data-stu-id="52c12-148">Manage how you pay your bill</span></span> <br> <span data-ttu-id="52c12-149">支払い方法を管理する</span><span class="sxs-lookup"><span data-stu-id="52c12-149">Manage how you pay your bill</span></span> <br> <span data-ttu-id="52c12-150">支払い方法の変更 (クレジットカード)</span><span class="sxs-lookup"><span data-stu-id="52c12-150">Change payment method (credit card)</span></span> <br> <span data-ttu-id="52c12-151">請求書の表示</span><span class="sxs-lookup"><span data-stu-id="52c12-151">View invoice</span></span> <br> <span data-ttu-id="52c12-152">アプリのサブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="52c12-152">Cancel app subscription</span></span> | <span data-ttu-id="52c12-153">アプリをセットアップする (アプリごとに1回)</span><span class="sxs-lookup"><span data-stu-id="52c12-153">Set up app (once for each app)</span></span> <br> <span data-ttu-id="52c12-154">ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="52c12-154">Assign licenses to users</span></span> <br> <span data-ttu-id="52c12-155">テクニカル サポート</span><span class="sxs-lookup"><span data-stu-id="52c12-155">Technical support</span></span> |

<span data-ttu-id="52c12-156">アプリがアクティブ化されると、そのアプリはキャンセルされるか、期限切れになるか、または支払いが最新の状態に保たれない限り、アクティブのままになります。</span><span class="sxs-lookup"><span data-stu-id="52c12-156">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="52c12-157">これらのイベントは、アプリの状態を無効に変更します。</span><span class="sxs-lookup"><span data-stu-id="52c12-157">These events change the app status to disabled.</span></span> <span data-ttu-id="52c12-158">アプリを無効にすると、再度アクティブにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="52c12-158">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="52c12-159">アプリを引き続き使用するには、別のコピーを購入してください。</span><span class="sxs-lookup"><span data-stu-id="52c12-159">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="52c12-160">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="52c12-160">Assign licenses</span></span>

<span data-ttu-id="52c12-161">管理者は、ユーザーに割り当てる前に、サードパーティ製のアプリをアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52c12-161">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="52c12-162">これらは、サードパーティの発行元のポータルでアクティブ化されています。</span><span class="sxs-lookup"><span data-stu-id="52c12-162">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="52c12-163">[アプリ] ページの [**設定 & アクション**] で、ライセンスを割り当てるリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="52c12-163">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="52c12-164">管理センターで、[製品アプリの**課金**] ページに移動し  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a>ます。</span><span class="sxs-lookup"><span data-stu-id="52c12-164">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="52c12-165">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="52c12-165">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="52c12-166">**[設定とアクション]** で、**[発行元のポータルで管理する]** へのリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="52c12-166">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="52c12-167">ライセンス数を変更する</span><span class="sxs-lookup"><span data-stu-id="52c12-167">Change license quantity</span></span>

<span data-ttu-id="52c12-168">管理者は、組織によって所有されているライセンスの数を変更できます。</span><span class="sxs-lookup"><span data-stu-id="52c12-168">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="52c12-169">これは、座席ベースの価格設定を使用して購入したアプリにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="52c12-169">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="52c12-170">管理センターで、[製品アプリの**課金**] ページに移動し  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a>ます。</span><span class="sxs-lookup"><span data-stu-id="52c12-170">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="52c12-171">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="52c12-171">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="52c12-172">[**ライセンス数量の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="52c12-172">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="52c12-173">支払方法を管理する</span><span class="sxs-lookup"><span data-stu-id="52c12-173">Manage payment methods</span></span>

<span data-ttu-id="52c12-174">サービスとしてのソフトウェアアプリにはそれぞれ、請求プロファイルが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="52c12-174">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="52c12-175">請求プロファイルを使用すると、請求書に含める製品をカスタマイズしたり、請求書に支払いを行ったりすることができます。</span><span class="sxs-lookup"><span data-stu-id="52c12-175">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="52c12-176">これには以下の関係者が含まれます。</span><span class="sxs-lookup"><span data-stu-id="52c12-176">They include:</span></span>

- <span data-ttu-id="52c12-177">**支払い方法**–クレジットカードまたは小切手/ワイヤ転送</span><span class="sxs-lookup"><span data-stu-id="52c12-177">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="52c12-178">**連絡先情報**-請求先住所と連絡先の名前</span><span class="sxs-lookup"><span data-stu-id="52c12-178">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="52c12-179">**役割**–請求プロファイルを変更したり、支払いを行ったり、購入するために請求書プロファイルの支払い方法を使用したりできるようにする役割。</span><span class="sxs-lookup"><span data-stu-id="52c12-179">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="52c12-180">請求プロファイルの詳細については、「[課金プロファイル](https://docs.microsoft.com/microsoft-store/billing-profile)について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52c12-180">For more information on billing profiles, see [Understand billing profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="52c12-181">サービスとしてのソフトウェアアプリサブスクリプションの課金プロファイルを変更する</span><span class="sxs-lookup"><span data-stu-id="52c12-181">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="52c12-182">管理センターで、[製品アプリの**課金**] ページに移動し  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a>ます。</span><span class="sxs-lookup"><span data-stu-id="52c12-182">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="52c12-183">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="52c12-183">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="52c12-184">[**課金プロファイル**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="52c12-184">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="52c12-185">請求書の詳細について[は、「bill または請求書](billing-and-payments/understand-your-invoice.md)について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52c12-185">For more information on invoices, see [Understand your bill or invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="52c12-186">サービスとしてのソフトウェアアプリのサブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="52c12-186">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="52c12-187">アプリページから、サービスとしてのソフトウェアアプリを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="52c12-187">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="52c12-188">管理センターで、[製品アプリの**課金**] ページに移動し  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a>ます。</span><span class="sxs-lookup"><span data-stu-id="52c12-188">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="52c12-189">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="52c12-189">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="52c12-190">[**設定とアクション**] の下で、[**サブスクリプションのキャンセル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="52c12-190">Under **Settings & actions**, select **Cancel subscription**.</span></span>
