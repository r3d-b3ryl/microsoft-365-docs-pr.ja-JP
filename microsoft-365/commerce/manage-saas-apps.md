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
ms.openlocfilehash: 521a535115cd3a082348485f4d03dade27c71d92
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44045966"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="76d85-103">組織のサードパーティ製アプリのサブスクリプションを管理する</span><span class="sxs-lookup"><span data-stu-id="76d85-103">Manage third-party app subscriptions for your organization</span></span>

<span data-ttu-id="76d85-104">プレビューモードがオンになっている Microsoft 365 管理センターで、サードパーティ製アプリのライセンスと請求を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="76d85-104">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="76d85-105">更新された機能には、サブスクリプション管理の強化、請求情報へのアクセスの向上、請求書管理の柔軟性の向上などがあります。</span><span class="sxs-lookup"><span data-stu-id="76d85-105">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="76d85-106">サブスクリプション管理は、Microsoft の更新された commerce プラットフォームに基づいています。</span><span class="sxs-lookup"><span data-stu-id="76d85-106">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="76d85-107">これは、顧客が直接購入した、またはサードパーティプロバイダーからの、サービスとしてのソフトウェアアプリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="76d85-107">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>

## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="76d85-108">サービスとしてのソフトウェアアプリを入手する方法</span><span class="sxs-lookup"><span data-stu-id="76d85-108">How to get software-as-a-service apps</span></span>

<span data-ttu-id="76d85-109">サードパーティ製アプリを購入するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="76d85-109">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="76d85-110">**直接購入**–お客様は、 [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/)または[appsource](https://www.appsource.com/)からサブスクリプションを直接購入できます。</span><span class="sxs-lookup"><span data-stu-id="76d85-110">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span>
- <span data-ttu-id="76d85-111">**パートナー購入**–パートナーと協力してサブスクリプションを購入します。</span><span class="sxs-lookup"><span data-stu-id="76d85-111">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="76d85-112">**Microsoft 提案**: サードパーティ製のアプリを含む microsoft Sales からの提案に対応します。</span><span class="sxs-lookup"><span data-stu-id="76d85-112">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="76d85-113">お客様は、お客様がアプリを購入し、microsoft のカスタマーアグリーメントに同意すると、Microsoft 365 管理センターまたは Microsoft Store for Business でそれらを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="76d85-113">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="76d85-114">アプリプロバイダーは、フラットなレートで、またはユーザーのライセンスを購入することで、アプリを販売します。</span><span class="sxs-lookup"><span data-stu-id="76d85-114">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="76d85-115">**一律レート**–サイトベースの価格とも呼ばれ、アプリの価格は月または年間の価格になります。</span><span class="sxs-lookup"><span data-stu-id="76d85-115">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="76d85-116">[アプリ] ページで、ライセンスの数量が無制限に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="76d85-116">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="76d85-117">**ライセンス**–アプリの価格はライセンスによるものです。</span><span class="sxs-lookup"><span data-stu-id="76d85-117">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="76d85-118">顧客が組織内の各ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="76d85-118">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="76d85-119">サポートされる地域</span><span class="sxs-lookup"><span data-stu-id="76d85-119">Supported regions</span></span>

<span data-ttu-id="76d85-120">サードパーティ製アプリのサポートは、次の地域で利用できます。</span><span class="sxs-lookup"><span data-stu-id="76d85-120">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="76d85-121">アルゼンチン</span><span class="sxs-lookup"><span data-stu-id="76d85-121">Argentina</span></span>
- <span data-ttu-id="76d85-122">オーストラリア</span><span class="sxs-lookup"><span data-stu-id="76d85-122">Australia</span></span>
- <span data-ttu-id="76d85-123">カナダ</span><span class="sxs-lookup"><span data-stu-id="76d85-123">Canada</span></span>
- <span data-ttu-id="76d85-124">チリ</span><span class="sxs-lookup"><span data-stu-id="76d85-124">Chile</span></span>
- <span data-ttu-id="76d85-125">フランス</span><span class="sxs-lookup"><span data-stu-id="76d85-125">France</span></span>
- <span data-ttu-id="76d85-126">ドイツ</span><span class="sxs-lookup"><span data-stu-id="76d85-126">Germany</span></span>
- <span data-ttu-id="76d85-127">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="76d85-127">Greece</span></span>
- <span data-ttu-id="76d85-128">プエルトリコ</span><span class="sxs-lookup"><span data-stu-id="76d85-128">Puerto Rico</span></span>
- <span data-ttu-id="76d85-129">南アフリカ</span><span class="sxs-lookup"><span data-stu-id="76d85-129">South Africa</span></span>
- <span data-ttu-id="76d85-130">英国</span><span class="sxs-lookup"><span data-stu-id="76d85-130">United Kingdom</span></span>
- <span data-ttu-id="76d85-131">米国</span><span class="sxs-lookup"><span data-stu-id="76d85-131">United States</span></span>
- <span data-ttu-id="76d85-132">西ヨーロッパ</span><span class="sxs-lookup"><span data-stu-id="76d85-132">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="76d85-133">サードパーティ製アプリをアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="76d85-133">Activate third-party apps</span></span>

<span data-ttu-id="76d85-134">管理者は、ユーザーに割り当てる前にサードパーティ製アプリをアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76d85-134">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="76d85-135">これらのアプリは、サードパーティの発行元のポータルでアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="76d85-135">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="76d85-136">管理センターで、[**製品** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">アプリ</a>の**課金** > ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="76d85-136">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="76d85-137">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="76d85-137">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="76d85-138">[**設定 & アクション**] で、[**パブリッシャーのポータルで管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="76d85-138">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="76d85-139">アプリをアクティブ化できるアプリの発行元のサイトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="76d85-139">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="76d85-140">サードパーティ製のアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="76d85-140">Manage third-party apps</span></span>

<span data-ttu-id="76d85-141">管理者は、サードパーティ製アプリを2か所で管理します。 Microsoft 365 管理センター、およびサードパーティのアプリプロバイダーのポータル。</span><span class="sxs-lookup"><span data-stu-id="76d85-141">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="76d85-142">各ポータルで実行できる操作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="76d85-142">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="76d85-143">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="76d85-143">Microsoft 365 admin center</span></span> | <span data-ttu-id="76d85-144">アプリ発行元ポータル</span><span class="sxs-lookup"><span data-stu-id="76d85-144">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="76d85-145">ライセンス数を変更する</span><span class="sxs-lookup"><span data-stu-id="76d85-145">Change license quantity</span></span> <br> <span data-ttu-id="76d85-146">支払い方法を管理する</span><span class="sxs-lookup"><span data-stu-id="76d85-146">Manage how you pay your bill</span></span> <br> <span data-ttu-id="76d85-147">支払い方法を管理する</span><span class="sxs-lookup"><span data-stu-id="76d85-147">Manage how you pay your bill</span></span> <br> <span data-ttu-id="76d85-148">支払い方法の変更 (クレジットカード)</span><span class="sxs-lookup"><span data-stu-id="76d85-148">Change payment method (credit card)</span></span> <br> <span data-ttu-id="76d85-149">請求書の表示</span><span class="sxs-lookup"><span data-stu-id="76d85-149">View invoice</span></span> <br> <span data-ttu-id="76d85-150">アプリのサブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="76d85-150">Cancel app subscription</span></span> | <span data-ttu-id="76d85-151">アプリをセットアップする (アプリごとに1回)</span><span class="sxs-lookup"><span data-stu-id="76d85-151">Set up app (once for each app)</span></span> <br> <span data-ttu-id="76d85-152">ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="76d85-152">Assign licenses to users</span></span> <br> <span data-ttu-id="76d85-153">テクニカル サポート</span><span class="sxs-lookup"><span data-stu-id="76d85-153">Technical support</span></span> |

<span data-ttu-id="76d85-154">アプリがアクティブ化されると、そのアプリはキャンセルされるか、期限切れになるか、または支払いが最新の状態に保たれない限り、アクティブのままになります。</span><span class="sxs-lookup"><span data-stu-id="76d85-154">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="76d85-155">これらのイベントは、アプリの状態を無効に変更します。</span><span class="sxs-lookup"><span data-stu-id="76d85-155">These events change the app status to disabled.</span></span> <span data-ttu-id="76d85-156">アプリを無効にすると、再度アクティブにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="76d85-156">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="76d85-157">アプリを引き続き使用するには、別のコピーを購入してください。</span><span class="sxs-lookup"><span data-stu-id="76d85-157">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="76d85-158">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="76d85-158">Assign licenses</span></span>

<span data-ttu-id="76d85-159">管理者は、ユーザーに割り当てる前に、サードパーティ製のアプリをアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76d85-159">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="76d85-160">これらは、サードパーティの発行元のポータルでアクティブ化されています。</span><span class="sxs-lookup"><span data-stu-id="76d85-160">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="76d85-161">[アプリ] ページの [**設定 & アクション**] で、ライセンスを割り当てるリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="76d85-161">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="76d85-162">管理センターで、[**製品** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">アプリ</a>の**課金** > ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="76d85-162">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="76d85-163">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="76d85-163">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="76d85-164">**[設定とアクション]** で、**[発行元のポータルで管理する]** へのリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="76d85-164">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="76d85-165">ライセンス数を変更する</span><span class="sxs-lookup"><span data-stu-id="76d85-165">Change license quantity</span></span>

<span data-ttu-id="76d85-166">管理者は、組織によって所有されているライセンスの数を変更できます。</span><span class="sxs-lookup"><span data-stu-id="76d85-166">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="76d85-167">これは、座席ベースの価格設定を使用して購入したアプリにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="76d85-167">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="76d85-168">管理センターで、[**製品** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">アプリ</a>の**課金** > ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="76d85-168">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="76d85-169">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="76d85-169">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="76d85-170">[**ライセンス数量の変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="76d85-170">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="76d85-171">支払方法を管理する</span><span class="sxs-lookup"><span data-stu-id="76d85-171">Manage payment methods</span></span>

<span data-ttu-id="76d85-172">サービスとしてのソフトウェアアプリにはそれぞれ、請求プロファイルが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="76d85-172">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="76d85-173">請求プロファイルを使用すると、請求書に含める製品をカスタマイズしたり、請求書に支払いを行ったりすることができます。</span><span class="sxs-lookup"><span data-stu-id="76d85-173">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="76d85-174">これには以下の関係者が含まれます。</span><span class="sxs-lookup"><span data-stu-id="76d85-174">They include:</span></span>

- <span data-ttu-id="76d85-175">**支払い方法**–クレジットカードまたは小切手/ワイヤ転送</span><span class="sxs-lookup"><span data-stu-id="76d85-175">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="76d85-176">**連絡先情報**-請求先住所と連絡先の名前</span><span class="sxs-lookup"><span data-stu-id="76d85-176">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="76d85-177">**役割**–請求プロファイルを変更したり、支払いを行ったり、購入するために請求書プロファイルの支払い方法を使用したりできるようにする役割。</span><span class="sxs-lookup"><span data-stu-id="76d85-177">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="76d85-178">請求プロファイルの詳細については、「[課金プロファイル](https://docs.microsoft.com/microsoft-store/billing-profile)について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76d85-178">For more information on billing profiles, see [Understand billing profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="76d85-179">サービスとしてのソフトウェアアプリサブスクリプションの課金プロファイルを変更する</span><span class="sxs-lookup"><span data-stu-id="76d85-179">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="76d85-180">管理センターで、[**製品** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">アプリ</a>の**課金** > ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="76d85-180">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="76d85-181">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="76d85-181">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="76d85-182">[**課金プロファイル**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="76d85-182">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="76d85-183">請求書の詳細については、「[請求書を理解する](billing-and-payments/understand-your-invoice.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76d85-183">For more information on invoices, see [Understand your invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="76d85-184">サービスとしてのソフトウェアアプリのサブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="76d85-184">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="76d85-185">アプリページから、サービスとしてのソフトウェアアプリを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="76d85-185">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="76d85-186">管理センターで、[**製品** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">アプリ</a>の**課金** > ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="76d85-186">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="76d85-187">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="76d85-187">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="76d85-188">[**設定とアクション**] の下で、[**サブスクリプションのキャンセル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="76d85-188">Under **Settings & actions**, select **Cancel subscription**.</span></span>