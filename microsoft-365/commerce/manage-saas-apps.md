---
title: 組織のサービスとしてのソフトウェアアプリを管理する
description: Microsoft 365 管理センターでサードパーティ製アプリをアクティブ化および管理する方法について説明します。
ms.prod: ''
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: ''
search.appverid: MET150
author: trudyha
f1.keywords:
- NOCSH
ms.author: TrudyHa
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/31/2019
ms.openlocfilehash: c8cda07655546ea2744abccc5536e00263c3afb3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080354"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="6a52a-103">組織のサードパーティ製アプリのサブスクリプションを管理する</span><span class="sxs-lookup"><span data-stu-id="6a52a-103">Manage third-party app subscriptions for your organization</span></span>

<span data-ttu-id="6a52a-104">プレビューモードがオンになっている Microsoft 365 管理センターで、サードパーティ製アプリのライセンスと請求を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="6a52a-104">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="6a52a-105">更新された機能には、サブスクリプション管理の強化、請求情報へのアクセスの向上、請求書管理の柔軟性の向上などがあります。</span><span class="sxs-lookup"><span data-stu-id="6a52a-105">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="6a52a-106">サブスクリプション管理は、Microsoft の更新された commerce プラットフォームに基づいています。</span><span class="sxs-lookup"><span data-stu-id="6a52a-106">Subscription management is based on Microsoft’s updated commerce platform.</span></span> <span data-ttu-id="6a52a-107">これは、顧客が直接購入した、またはサードパーティプロバイダーからの、サービスとしてのソフトウェアアプリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6a52a-107">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>

## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="6a52a-108">サービスとしてのソフトウェアアプリを入手する方法</span><span class="sxs-lookup"><span data-stu-id="6a52a-108">How to get software-as-a-service apps</span></span>
<span data-ttu-id="6a52a-109">サードパーティ製アプリを購入するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="6a52a-109">There are a few ways to purchase third-party apps.</span></span>
- <span data-ttu-id="6a52a-110">**直接購入**–お客様は、 [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/)または[appsource](https://www.appsource.com/)からサブスクリプションを直接購入できます。</span><span class="sxs-lookup"><span data-stu-id="6a52a-110">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span> 
- <span data-ttu-id="6a52a-111">**パートナー購入**–パートナーと協力してサブスクリプションを購入します。</span><span class="sxs-lookup"><span data-stu-id="6a52a-111">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span> 
- <span data-ttu-id="6a52a-112">**Microsoft 提案**: サードパーティ製のアプリを含む microsoft Sales からの提案に対応します。</span><span class="sxs-lookup"><span data-stu-id="6a52a-112">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span> 

<span data-ttu-id="6a52a-113">お客様は、お客様がアプリを購入し、microsoft のカスタマーアグリーメントに同意すると、Microsoft 365 管理センターまたは Microsoft Store for Business でそれらを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="6a52a-113">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="6a52a-114">アプリプロバイダーは、フラットなレートで、またはユーザーのライセンスを購入することで、アプリを販売します。</span><span class="sxs-lookup"><span data-stu-id="6a52a-114">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span> 
- <span data-ttu-id="6a52a-115">**一律レート**–サイトベースの価格とも呼ばれ、アプリの価格は月または年間の価格になります。</span><span class="sxs-lookup"><span data-stu-id="6a52a-115">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="6a52a-116">[アプリ] ページで、ライセンスの数量が無制限に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a52a-116">On the app page, license quantity is listed at Unlimited.</span></span> 
- <span data-ttu-id="6a52a-117">**ライセンス**–アプリの価格はライセンスによるものです。</span><span class="sxs-lookup"><span data-stu-id="6a52a-117">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="6a52a-118">顧客が組織内の各ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6a52a-118">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="6a52a-119">サポートされる地域</span><span class="sxs-lookup"><span data-stu-id="6a52a-119">Supported regions</span></span>
<span data-ttu-id="6a52a-120">サードパーティ製アプリのサポートは、次の地域で利用できます。</span><span class="sxs-lookup"><span data-stu-id="6a52a-120">Support for third-party apps is available in these regions:</span></span>
- <span data-ttu-id="6a52a-121">アルゼンチン</span><span class="sxs-lookup"><span data-stu-id="6a52a-121">Argentina</span></span>
- <span data-ttu-id="6a52a-122">オーストラリア</span><span class="sxs-lookup"><span data-stu-id="6a52a-122">Australia</span></span>
- <span data-ttu-id="6a52a-123">カナダ</span><span class="sxs-lookup"><span data-stu-id="6a52a-123">Canada</span></span>
- <span data-ttu-id="6a52a-124">チリ</span><span class="sxs-lookup"><span data-stu-id="6a52a-124">Chile</span></span>
- <span data-ttu-id="6a52a-125">フランス</span><span class="sxs-lookup"><span data-stu-id="6a52a-125">France</span></span>
- <span data-ttu-id="6a52a-126">ドイツ</span><span class="sxs-lookup"><span data-stu-id="6a52a-126">Germany</span></span>
- <span data-ttu-id="6a52a-127">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="6a52a-127">Greece</span></span>
- <span data-ttu-id="6a52a-128">プエルトリコ</span><span class="sxs-lookup"><span data-stu-id="6a52a-128">Puerto Rico</span></span>
- <span data-ttu-id="6a52a-129">南アフリカ</span><span class="sxs-lookup"><span data-stu-id="6a52a-129">South Africa</span></span>
- <span data-ttu-id="6a52a-130">英国</span><span class="sxs-lookup"><span data-stu-id="6a52a-130">United Kingdom</span></span>
- <span data-ttu-id="6a52a-131">米国</span><span class="sxs-lookup"><span data-stu-id="6a52a-131">United States</span></span>
- <span data-ttu-id="6a52a-132">西ヨーロッパ</span><span class="sxs-lookup"><span data-stu-id="6a52a-132">Western Europe</span></span>

## <a name="set-up-app"></a><span data-ttu-id="6a52a-133">アプリをセットアップする</span><span class="sxs-lookup"><span data-stu-id="6a52a-133">Set up app</span></span>
<span data-ttu-id="6a52a-134">管理者は、ユーザーに割り当てる前に、サードパーティ製のアプリをアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a52a-134">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="6a52a-135">これらのアプリは、サードパーティの発行元のポータルでアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="6a52a-135">These apps are activated in the third-party publisher’s portal.</span></span> 

<span data-ttu-id="6a52a-136">**サードパーティ製アプリをアクティブ化するには**</span><span class="sxs-lookup"><span data-stu-id="6a52a-136">**To activate third-party apps**</span></span>
1. <span data-ttu-id="6a52a-137">[Microsoft 365 管理センター](https://go.microsoft.com/fwlink/p/?linkid=837890)に移動し、[**プレビューの試行**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="6a52a-137">Go to [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=837890), and turn on **Try the preview**.</span></span>
2. <span data-ttu-id="6a52a-138">[ **Billing** > **Products & services** > **Apps**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a52a-138">Select **Billing** > **Products & services** > **Apps**.</span></span>
3. <span data-ttu-id="6a52a-139">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="6a52a-139">Find and select the app you want to manage.</span></span> 
4. <span data-ttu-id="6a52a-140">[**設定 & アクション**] で、[**パブリッシャーのポータルで管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a52a-140">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span> 

<span data-ttu-id="6a52a-141">アプリをアクティブ化できるアプリの発行元のサイトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a52a-141">You’ll be directed to the app publisher’s site where you can activate the app.</span></span> 

## <a name="managing-third-party-apps"></a><span data-ttu-id="6a52a-142">サードパーティ製アプリの管理</span><span class="sxs-lookup"><span data-stu-id="6a52a-142">Managing third-party apps</span></span>
<span data-ttu-id="6a52a-143">管理者は、サードパーティ製アプリを2か所で管理します。 Microsoft 365 管理センター、およびサードパーティのアプリプロバイダーのポータル。</span><span class="sxs-lookup"><span data-stu-id="6a52a-143">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider’s portal.</span></span> <span data-ttu-id="6a52a-144">各ポータルで実行できる操作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6a52a-144">Here’s what you can do in each portal.</span></span>

### <a name="app-status"></a><span data-ttu-id="6a52a-145">アプリの状態</span><span class="sxs-lookup"><span data-stu-id="6a52a-145">App status</span></span>
<span data-ttu-id="6a52a-146">アクティブ化すると、アプリはキャンセルされるか、期限切れになるか、または支払いが最新の状態に保たれない限り、アクティブのままになります。</span><span class="sxs-lookup"><span data-stu-id="6a52a-146">Once activated, the app remains active unless it is canceled, expires, or if payment is not kept current.</span></span> <span data-ttu-id="6a52a-147">これらのイベントは、アプリの状態を無効に変更します。</span><span class="sxs-lookup"><span data-stu-id="6a52a-147">These events change the app status to disabled.</span></span> <span data-ttu-id="6a52a-148">アプリを無効にすると、再度アクティブにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6a52a-148">Once an app is disabled, it can’t be reactivated.</span></span> <span data-ttu-id="6a52a-149">引き続き使用するには、別のアプリのコピーを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a52a-149">You need to buy another copy of the app to continue using it.</span></span>

| <span data-ttu-id="6a52a-150">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="6a52a-150">Microsoft 365 admin center</span></span> | <span data-ttu-id="6a52a-151">アプリ発行元ポータル</span><span class="sxs-lookup"><span data-stu-id="6a52a-151">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="6a52a-152">ライセンス数を変更する</span><span class="sxs-lookup"><span data-stu-id="6a52a-152">Change license quantity</span></span> <br> <span data-ttu-id="6a52a-153">支払い方法を管理する</span><span class="sxs-lookup"><span data-stu-id="6a52a-153">Manage how you pay your bill</span></span> <br> <span data-ttu-id="6a52a-154">支払い方法を管理する</span><span class="sxs-lookup"><span data-stu-id="6a52a-154">Manage how you pay your bill</span></span> <br> <span data-ttu-id="6a52a-155">支払い方法の変更 (クレジットカード)</span><span class="sxs-lookup"><span data-stu-id="6a52a-155">Change payment method (credit card)</span></span> <br> <span data-ttu-id="6a52a-156">請求書の表示</span><span class="sxs-lookup"><span data-stu-id="6a52a-156">View invoice</span></span> <br> <span data-ttu-id="6a52a-157">アプリのサブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="6a52a-157">Cancel app subscription</span></span> | <span data-ttu-id="6a52a-158">アプリをセットアップする (アプリごとに1回)</span><span class="sxs-lookup"><span data-stu-id="6a52a-158">Set up app (once for each app)</span></span> <br> <span data-ttu-id="6a52a-159">ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6a52a-159">Assign licenses to users</span></span> <br> <span data-ttu-id="6a52a-160">テクニカル サポート</span><span class="sxs-lookup"><span data-stu-id="6a52a-160">Technical support</span></span> |

## <a name="assign-licenses"></a><span data-ttu-id="6a52a-161">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6a52a-161">Assign licenses</span></span>
<span data-ttu-id="6a52a-162">管理者は、ユーザーに割り当てる前に、サードパーティ製のアプリをアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a52a-162">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="6a52a-163">これらは、サードパーティの発行元のポータルでアクティブ化されています。</span><span class="sxs-lookup"><span data-stu-id="6a52a-163">They're activated in the third-party publisher’s portal.</span></span> <span data-ttu-id="6a52a-164">[アプリ] ページの [**設定 & アクション**] で、ライセンスを割り当てるリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="6a52a-164">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

<span data-ttu-id="6a52a-165">**サードパーティ製アプリを割り当てるには**</span><span class="sxs-lookup"><span data-stu-id="6a52a-165">**To assign third-party apps**</span></span>

1. <span data-ttu-id="6a52a-166">[Microsoft 365 管理センター](https://go.microsoft.com/fwlink/p/?linkid=837890)に移動し、[**プレビューの試行**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="6a52a-166">Go to [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=837890), and turn on **Try the preview**.</span></span>
2. <span data-ttu-id="6a52a-167">[ **Billing** > **Products & services** > **Apps**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a52a-167">Select **Billing** > **Products & services** > **Apps**.</span></span>
3. <span data-ttu-id="6a52a-168">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="6a52a-168">Find and select the app you want to manage.</span></span> 
4. <span data-ttu-id="6a52a-169">[**設定とアクション**] の下で、[**発行元のポータルで管理する**] へのリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="6a52a-169">Under **Settings & actions**, select the link to **Manage in publisher’s portal**.</span></span> 
 
## <a name="change-license-quantity"></a><span data-ttu-id="6a52a-170">ライセンス数を変更する</span><span class="sxs-lookup"><span data-stu-id="6a52a-170">Change license quantity</span></span>
<span data-ttu-id="6a52a-171">管理者は、組織によって所有されているライセンスの数を変更できます。</span><span class="sxs-lookup"><span data-stu-id="6a52a-171">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="6a52a-172">これは、座席ベースの価格設定を使用して購入したアプリにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="6a52a-172">This only applies to apps purchased with seat-based pricing.</span></span>

<span data-ttu-id="6a52a-173">**ライセンス数を変更するには**</span><span class="sxs-lookup"><span data-stu-id="6a52a-173">**To change license quantity**</span></span>

1. <span data-ttu-id="6a52a-174">[Microsoft 365 管理センター](https://go.microsoft.com/fwlink/p/?linkid=837890)に移動し、[**プレビューの試行**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="6a52a-174">Go to [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=837890), and turn on **Try the preview**.</span></span>
2. <span data-ttu-id="6a52a-175">[ **Billing** > **Products & services** > **Apps**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a52a-175">Select **Billing** > **Products & services** > **Apps**.</span></span>
3. <span data-ttu-id="6a52a-176">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="6a52a-176">Find and select the app you want to manage.</span></span> 
4. <span data-ttu-id="6a52a-177">[**ライセンス数量の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a52a-177">Select **Change license quantity**.</span></span> 

## <a name="manage-payment-methods"></a><span data-ttu-id="6a52a-178">支払い方法を管理する</span><span class="sxs-lookup"><span data-stu-id="6a52a-178">Manage payment methods</span></span>
<span data-ttu-id="6a52a-179">サービスとしてのソフトウェアアプリにはそれぞれ、請求プロファイルが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="6a52a-179">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="6a52a-180">請求プロファイルを使用すると、請求書に含める製品をカスタマイズしたり、請求書に支払いを行ったりすることができます。</span><span class="sxs-lookup"><span data-stu-id="6a52a-180">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="6a52a-181">これには以下の関係者が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6a52a-181">They include:</span></span>

- <span data-ttu-id="6a52a-182">**支払い方法**–クレジットカードまたは小切手/ワイヤ転送</span><span class="sxs-lookup"><span data-stu-id="6a52a-182">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="6a52a-183">**連絡先情報**-請求先住所と連絡先の名前</span><span class="sxs-lookup"><span data-stu-id="6a52a-183">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="6a52a-184">**役割**–請求プロファイルを変更したり、支払いを行ったり、購入するために請求書プロファイルの支払い方法を使用したりできるようにする役割。</span><span class="sxs-lookup"><span data-stu-id="6a52a-184">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span> 

<span data-ttu-id="6a52a-185">請求プロファイルの詳細については、「[課金プロファイル](https://docs.microsoft.com/microsoft-store/billing-profile)について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a52a-185">For more information on billing profiles, see [Understand billing profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span></span> 

<span data-ttu-id="6a52a-186">**サービスとしてのソフトウェアアプリサブスクリプションの課金プロファイルを変更するには**</span><span class="sxs-lookup"><span data-stu-id="6a52a-186">**To change the billing profile on a software-as-a-service app subscription**</span></span>

1. <span data-ttu-id="6a52a-187">[Microsoft 365 管理センター](https://go.microsoft.com/fwlink/p/?linkid=837890)に移動し、[**プレビューの試行**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="6a52a-187">Go to [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=837890), and turn on **Try the preview**.</span></span>
2. <span data-ttu-id="6a52a-188">[ **Billing** > **Products & services** > **Apps**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a52a-188">Select **Billing** > **Products & services** > **Apps**.</span></span>
3. <span data-ttu-id="6a52a-189">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="6a52a-189">Find and select the app you want to manage.</span></span> 
4. <span data-ttu-id="6a52a-190">[**課金プロファイル**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a52a-190">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="6a52a-191">請求書の詳細については、「 [Microsoft カスタマーアグリーメントの請求書](https://docs.microsoft.com/microsoft-store/billing-understand-your-invoice-msfb)について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a52a-191">For more information on invoices, see [Understand your Microsoft Customer Agreement invoice](https://docs.microsoft.com/microsoft-store/billing-understand-your-invoice-msfb).</span></span>

## <a name="cancel-subscription"></a><span data-ttu-id="6a52a-192">サブスクリプションのキャンセル</span><span class="sxs-lookup"><span data-stu-id="6a52a-192">Cancel subscription</span></span>
<span data-ttu-id="6a52a-193">お客様は、アプリページから、サービスとしてのソフトウェアアプリを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="6a52a-193">Customers can cancel software-as-a-service app from the app page.</span></span> 

<span data-ttu-id="6a52a-194">**サービスとしてのソフトウェアアプリのサブスクリプションを取り消すには**</span><span class="sxs-lookup"><span data-stu-id="6a52a-194">**To cancel software-as-a-service app subscription**</span></span>

1. <span data-ttu-id="6a52a-195">[Microsoft 365 管理センター](https://go.microsoft.com/fwlink/p/?linkid=837890)に移動し、[**プレビューの試行**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="6a52a-195">Go to [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=837890), and turn on **Try the preview**.</span></span>
2. <span data-ttu-id="6a52a-196">[ **Billing** > **Products & services** > **Apps**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a52a-196">Select **Billing** > **Products & services** > **Apps**.</span></span>
3. <span data-ttu-id="6a52a-197">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="6a52a-197">Find and select the app you want to manage.</span></span> 
4. <span data-ttu-id="6a52a-198">[**設定とアクション**] の下で、[**サブスクリプションのキャンセル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a52a-198">Under **Settings & actions**, select **Cancel subscription**.</span></span>
