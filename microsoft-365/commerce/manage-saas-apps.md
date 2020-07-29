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
ms.openlocfilehash: c8d2764dfa7795707712cbd9ce212f78c4d43d45
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "45429992"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="4ba98-103">組織のサードパーティ製アプリのサブスクリプションを管理する</span><span class="sxs-lookup"><span data-stu-id="4ba98-103">Manage third-party app subscriptions for your organization</span></span>

<span data-ttu-id="4ba98-104">新しい Microsoft 365 管理センターで、サードパーティ製アプリのライセンスと請求書を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="4ba98-104">You can manage licenses and billing for third-party apps in the new Microsoft 365 admin center.</span></span> <span data-ttu-id="4ba98-105">更新された機能には、サブスクリプション管理の強化、請求情報へのアクセスの向上、請求書管理の柔軟性の向上などがあります。</span><span class="sxs-lookup"><span data-stu-id="4ba98-105">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="4ba98-106">サブスクリプション管理は、Microsoft の更新された commerce プラットフォームに基づいています。</span><span class="sxs-lookup"><span data-stu-id="4ba98-106">Subscription management is based on Microsoft’s updated commerce platform.</span></span> <span data-ttu-id="4ba98-107">これは、顧客が直接購入するか、またはサードパーティのプロバイダーから購入した、サービスとしてのソフトウェアアプリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4ba98-107">This applies to software-as-a-service apps that customers purchase directly, or from a third-party provider.</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="4ba98-108">管理センターは変更されました。</span><span class="sxs-lookup"><span data-stu-id="4ba98-108">The admin center is changing.</span></span> <span data-ttu-id="4ba98-109">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ba98-109">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="4ba98-110">プレビューモードがオンになっている Microsoft 365 管理センターで、サードパーティ製アプリのライセンスと請求を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="4ba98-110">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="4ba98-111">更新された機能には、サブスクリプション管理の強化、請求情報へのアクセスの向上、請求書管理の柔軟性の向上などがあります。</span><span class="sxs-lookup"><span data-stu-id="4ba98-111">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="4ba98-112">サブスクリプション管理は、Microsoft の更新された commerce プラットフォームに基づいています。</span><span class="sxs-lookup"><span data-stu-id="4ba98-112">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="4ba98-113">これは、顧客が直接購入した、またはサードパーティプロバイダーからの、サービスとしてのソフトウェアアプリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4ba98-113">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>


## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="4ba98-114">サービスとしてのソフトウェアアプリを入手する方法</span><span class="sxs-lookup"><span data-stu-id="4ba98-114">How to get software-as-a-service apps</span></span>

<span data-ttu-id="4ba98-115">サードパーティ製アプリを購入するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="4ba98-115">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="4ba98-116">**直接購入**–お客様は、 [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/)または[appsource](https://www.appsource.com/)からサブスクリプションを直接購入できます。</span><span class="sxs-lookup"><span data-stu-id="4ba98-116">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span>
- <span data-ttu-id="4ba98-117">**パートナー購入**–パートナーと協力してサブスクリプションを購入します。</span><span class="sxs-lookup"><span data-stu-id="4ba98-117">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="4ba98-118">**Microsoft 提案**: サードパーティ製のアプリを含む microsoft Sales からの提案に対応します。</span><span class="sxs-lookup"><span data-stu-id="4ba98-118">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="4ba98-119">お客様は、お客様がアプリを購入し、microsoft のカスタマーアグリーメントに同意すると、Microsoft 365 管理センターまたは Microsoft Store for Business でそれらを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="4ba98-119">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="4ba98-120">アプリプロバイダーは、フラットなレートで、またはユーザーのライセンスを購入することで、アプリを販売します。</span><span class="sxs-lookup"><span data-stu-id="4ba98-120">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="4ba98-121">**一律レート**–サイトベースの価格とも呼ばれ、アプリの価格は月または年間の価格になります。</span><span class="sxs-lookup"><span data-stu-id="4ba98-121">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="4ba98-122">[アプリ] ページで、ライセンスの数量が無制限に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ba98-122">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="4ba98-123">**ライセンス**–アプリの価格はライセンスによるものです。</span><span class="sxs-lookup"><span data-stu-id="4ba98-123">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="4ba98-124">顧客が組織内の各ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4ba98-124">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="4ba98-125">サポートされる地域</span><span class="sxs-lookup"><span data-stu-id="4ba98-125">Supported regions</span></span>

<span data-ttu-id="4ba98-126">サードパーティ製アプリのサポートは、次の地域で利用できます。</span><span class="sxs-lookup"><span data-stu-id="4ba98-126">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="4ba98-127">アルゼンチン</span><span class="sxs-lookup"><span data-stu-id="4ba98-127">Argentina</span></span>
- <span data-ttu-id="4ba98-128">オーストラリア</span><span class="sxs-lookup"><span data-stu-id="4ba98-128">Australia</span></span>
- <span data-ttu-id="4ba98-129">カナダ</span><span class="sxs-lookup"><span data-stu-id="4ba98-129">Canada</span></span>
- <span data-ttu-id="4ba98-130">チリ</span><span class="sxs-lookup"><span data-stu-id="4ba98-130">Chile</span></span>
- <span data-ttu-id="4ba98-131">フランス</span><span class="sxs-lookup"><span data-stu-id="4ba98-131">France</span></span>
- <span data-ttu-id="4ba98-132">ドイツ</span><span class="sxs-lookup"><span data-stu-id="4ba98-132">Germany</span></span>
- <span data-ttu-id="4ba98-133">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="4ba98-133">Greece</span></span>
- <span data-ttu-id="4ba98-134">プエルトリコ</span><span class="sxs-lookup"><span data-stu-id="4ba98-134">Puerto Rico</span></span>
- <span data-ttu-id="4ba98-135">南アフリカ</span><span class="sxs-lookup"><span data-stu-id="4ba98-135">South Africa</span></span>
- <span data-ttu-id="4ba98-136">英国</span><span class="sxs-lookup"><span data-stu-id="4ba98-136">United Kingdom</span></span>
- <span data-ttu-id="4ba98-137">米国</span><span class="sxs-lookup"><span data-stu-id="4ba98-137">United States</span></span>
- <span data-ttu-id="4ba98-138">西ヨーロッパ</span><span class="sxs-lookup"><span data-stu-id="4ba98-138">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="4ba98-139">サードパーティ製アプリをアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="4ba98-139">Activate third-party apps</span></span>

<span data-ttu-id="4ba98-140">管理者は、ユーザーに割り当てる前にサードパーティ製アプリをアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba98-140">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="4ba98-141">これらのアプリは、サードパーティの発行元のポータルでアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="4ba98-141">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="4ba98-142">管理センターで、[製品アプリの**課金**] ページに移動し  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a>ます。</span><span class="sxs-lookup"><span data-stu-id="4ba98-142">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="4ba98-143">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="4ba98-143">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="4ba98-144">[**設定 & アクション**] で、[**パブリッシャーのポータルで管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ba98-144">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="4ba98-145">アプリをアクティブ化できるアプリの発行元のサイトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ba98-145">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="4ba98-146">サードパーティ製のアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="4ba98-146">Manage third-party apps</span></span>

<span data-ttu-id="4ba98-147">管理者は、サードパーティ製アプリを2か所で管理します。 Microsoft 365 管理センター、およびサードパーティのアプリプロバイダーのポータル。</span><span class="sxs-lookup"><span data-stu-id="4ba98-147">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="4ba98-148">各ポータルで実行できる操作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4ba98-148">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="4ba98-149">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="4ba98-149">Microsoft 365 admin center</span></span> | <span data-ttu-id="4ba98-150">アプリ発行元ポータル</span><span class="sxs-lookup"><span data-stu-id="4ba98-150">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="4ba98-151">ライセンス数を変更する</span><span class="sxs-lookup"><span data-stu-id="4ba98-151">Change license quantity</span></span> <br> <span data-ttu-id="4ba98-152">支払い方法を管理する</span><span class="sxs-lookup"><span data-stu-id="4ba98-152">Manage how you pay your bill</span></span> <br> <span data-ttu-id="4ba98-153">支払い方法を管理する</span><span class="sxs-lookup"><span data-stu-id="4ba98-153">Manage how you pay your bill</span></span> <br> <span data-ttu-id="4ba98-154">支払い方法の変更 (クレジットカード)</span><span class="sxs-lookup"><span data-stu-id="4ba98-154">Change payment method (credit card)</span></span> <br> <span data-ttu-id="4ba98-155">請求書の表示</span><span class="sxs-lookup"><span data-stu-id="4ba98-155">View invoice</span></span> <br> <span data-ttu-id="4ba98-156">アプリのサブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="4ba98-156">Cancel app subscription</span></span> | <span data-ttu-id="4ba98-157">アプリをセットアップする (アプリごとに1回)</span><span class="sxs-lookup"><span data-stu-id="4ba98-157">Set up app (once for each app)</span></span> <br> <span data-ttu-id="4ba98-158">ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4ba98-158">Assign licenses to users</span></span> <br> <span data-ttu-id="4ba98-159">テクニカル サポート</span><span class="sxs-lookup"><span data-stu-id="4ba98-159">Technical support</span></span> |

<span data-ttu-id="4ba98-160">アプリがアクティブ化されると、そのアプリはキャンセルされるか、期限切れになるか、または支払いが最新の状態に保たれない限り、アクティブのままになります。</span><span class="sxs-lookup"><span data-stu-id="4ba98-160">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="4ba98-161">これらのイベントは、アプリの状態を無効に変更します。</span><span class="sxs-lookup"><span data-stu-id="4ba98-161">These events change the app status to disabled.</span></span> <span data-ttu-id="4ba98-162">アプリを無効にすると、再度アクティブにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4ba98-162">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="4ba98-163">アプリを引き続き使用するには、別のコピーを購入してください。</span><span class="sxs-lookup"><span data-stu-id="4ba98-163">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="4ba98-164">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4ba98-164">Assign licenses</span></span>

<span data-ttu-id="4ba98-165">管理者は、ユーザーに割り当てる前に、サードパーティ製のアプリをアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba98-165">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="4ba98-166">これらは、サードパーティの発行元のポータルでアクティブ化されています。</span><span class="sxs-lookup"><span data-stu-id="4ba98-166">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="4ba98-167">[アプリ] ページの [**設定 & アクション**] で、ライセンスを割り当てるリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="4ba98-167">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="4ba98-168">管理センターで、[製品アプリの**課金**] ページに移動し  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a>ます。</span><span class="sxs-lookup"><span data-stu-id="4ba98-168">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="4ba98-169">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="4ba98-169">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="4ba98-170">**[設定とアクション]** で、**[発行元のポータルで管理する]** へのリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="4ba98-170">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="4ba98-171">ライセンス数を変更する</span><span class="sxs-lookup"><span data-stu-id="4ba98-171">Change license quantity</span></span>

<span data-ttu-id="4ba98-172">管理者は、組織によって所有されているライセンスの数を変更できます。</span><span class="sxs-lookup"><span data-stu-id="4ba98-172">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="4ba98-173">これは、座席ベースの価格設定を使用して購入したアプリにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="4ba98-173">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="4ba98-174">管理センターで、[製品アプリの**課金**] ページに移動し  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a>ます。</span><span class="sxs-lookup"><span data-stu-id="4ba98-174">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="4ba98-175">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="4ba98-175">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="4ba98-176">[**ライセンス数量の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ba98-176">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="4ba98-177">支払方法を管理する</span><span class="sxs-lookup"><span data-stu-id="4ba98-177">Manage payment methods</span></span>

<span data-ttu-id="4ba98-178">サービスとしてのソフトウェアアプリにはそれぞれ、請求プロファイルが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="4ba98-178">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="4ba98-179">請求プロファイルを使用すると、請求書に含める製品をカスタマイズしたり、請求書に支払いを行ったりすることができます。</span><span class="sxs-lookup"><span data-stu-id="4ba98-179">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="4ba98-180">これには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4ba98-180">They include:</span></span>

- <span data-ttu-id="4ba98-181">**支払い方法**–クレジットカードまたは小切手/ワイヤ転送</span><span class="sxs-lookup"><span data-stu-id="4ba98-181">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="4ba98-182">**連絡先情報**-請求先住所と連絡先の名前</span><span class="sxs-lookup"><span data-stu-id="4ba98-182">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="4ba98-183">**役割**–請求プロファイルを変更したり、支払いを行ったり、購入するために請求書プロファイルの支払い方法を使用したりできるようにする役割。</span><span class="sxs-lookup"><span data-stu-id="4ba98-183">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="4ba98-184">請求プロファイルの詳細については、「[課金プロファイル](https://docs.microsoft.com/microsoft-store/billing-profile)について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ba98-184">For more information on billing profiles, see [Understand billing profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="4ba98-185">サービスとしてのソフトウェアアプリサブスクリプションの課金プロファイルを変更する</span><span class="sxs-lookup"><span data-stu-id="4ba98-185">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="4ba98-186">管理センターで、[製品アプリの**課金**] ページに移動し  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a>ます。</span><span class="sxs-lookup"><span data-stu-id="4ba98-186">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="4ba98-187">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="4ba98-187">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="4ba98-188">[**課金プロファイル**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ba98-188">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="4ba98-189">請求書の詳細について[は、「bill または請求書](billing-and-payments/understand-your-invoice.md)について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ba98-189">For more information on invoices, see [Understand your bill or invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="4ba98-190">サービスとしてのソフトウェアアプリのサブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="4ba98-190">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="4ba98-191">アプリページから、サービスとしてのソフトウェアアプリを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="4ba98-191">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="4ba98-192">管理センターで、[製品アプリの**課金**] ページに移動し  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a>ます。</span><span class="sxs-lookup"><span data-stu-id="4ba98-192">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="4ba98-193">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="4ba98-193">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="4ba98-194">[**設定とアクション**] の下で、[**サブスクリプションのキャンセル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ba98-194">Under **Settings & actions**, select **Cancel subscription**.</span></span>