---
title: 組織のサービスとしてのソフトウェア アプリを管理する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Microsoft 365 管理センターでサード パーティ製アプリをアクティブ化および管理する方法について説明します。
ms.openlocfilehash: f560b23871fc6d6ecb319a5704453f2400cb9982
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911412"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="e6dc4-103">組織のサード パーティ製アプリのサブスクリプションを管理する</span><span class="sxs-lookup"><span data-stu-id="e6dc4-103">Manage third-party app subscriptions for your organization</span></span>

<span data-ttu-id="e6dc4-104">新しい Microsoft 365 管理センターでは、サード パーティ製アプリのライセンスと課金を管理できます。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-104">You can manage licenses and billing for third-party apps in the new Microsoft 365 admin center.</span></span> <span data-ttu-id="e6dc4-105">更新された機能には、サブスクリプション管理の強化、請求情報へのアクセスの改善、請求書管理の柔軟性の向上が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-105">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="e6dc4-106">サブスクリプション管理は、Microsoft の更新されたコマース プラットフォームに基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-106">Subscription management is based on Microsoft’s updated commerce platform.</span></span> <span data-ttu-id="e6dc4-107">これは、顧客が直接購入するサービスとしてのソフトウェア アプリ、またはサード パーティ プロバイダーから適用されます。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-107">This applies to software-as-a-service apps that customers purchase directly, or from a third-party provider.</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e6dc4-108">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-108">The admin center is changing.</span></span> <span data-ttu-id="e6dc4-109">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-109">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="e6dc4-110">プレビュー モードを有効にした状態で、Microsoft 365 管理センターでサード パーティ製アプリのライセンスと課金を管理できます。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-110">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="e6dc4-111">更新された機能には、サブスクリプション管理の強化、請求情報へのアクセスの改善、請求書管理の柔軟性の向上が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-111">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="e6dc4-112">サブスクリプション管理は、Microsoft の更新されたコマース プラットフォームに基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-112">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="e6dc4-113">これは、顧客が直接購入するサービスとしてのソフトウェア アプリ、またはサード パーティ プロバイダーから適用されます。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-113">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>


## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="e6dc4-114">サービスとしてのソフトウェア アプリを取得する方法</span><span class="sxs-lookup"><span data-stu-id="e6dc4-114">How to get software-as-a-service apps</span></span>

<span data-ttu-id="e6dc4-115">サード パーティ製アプリを購入するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-115">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="e6dc4-116">**直接購入** – 顧客は Azure [Marketplace](https://azuremarketplace.microsoft.com/marketplace/)または [AppSource](https://www.appsource.com/)からサブスクリプションを直接購入できます。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-116">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span>
- <span data-ttu-id="e6dc4-117">**パートナー購入** – パートナー センターを通じてパートナーと一緒にサブスクリプションを購入します。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-117">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="e6dc4-118">**Microsoft の提案** – サード パーティ製アプリを含む Microsoft Sales からの提案に応答します。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-118">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="e6dc4-119">お客様がアプリを購入し、Microsoft カスタマー 契約に同意すると、Microsoft 365 管理センターまたは Microsoft Store for Business で管理できます。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-119">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="e6dc4-120">アプリ プロバイダーは、アプリを一定額で販売するか、ユーザーのライセンスを購入します。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-120">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="e6dc4-121">**定額 –** サイトベースの価格とも呼ばれるアプリの価格は、月次または年間の価格です。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-121">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="e6dc4-122">アプリ ページでは、ライセンスの数量が Unlimited に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-122">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="e6dc4-123">**ライセンス** – アプリの価格はライセンス別です。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-123">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="e6dc4-124">顧客は組織内の各ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e6dc4-124">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="e6dc4-125">サポートされる地域</span><span class="sxs-lookup"><span data-stu-id="e6dc4-125">Supported regions</span></span>

<span data-ttu-id="e6dc4-126">サード パーティ製アプリのサポートは、次の地域で利用できます。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-126">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="e6dc4-127">アルゼンチン</span><span class="sxs-lookup"><span data-stu-id="e6dc4-127">Argentina</span></span>
- <span data-ttu-id="e6dc4-128">オーストラリア</span><span class="sxs-lookup"><span data-stu-id="e6dc4-128">Australia</span></span>
- <span data-ttu-id="e6dc4-129">カナダ</span><span class="sxs-lookup"><span data-stu-id="e6dc4-129">Canada</span></span>
- <span data-ttu-id="e6dc4-130">チリ</span><span class="sxs-lookup"><span data-stu-id="e6dc4-130">Chile</span></span>
- <span data-ttu-id="e6dc4-131">フランス</span><span class="sxs-lookup"><span data-stu-id="e6dc4-131">France</span></span>
- <span data-ttu-id="e6dc4-132">ドイツ</span><span class="sxs-lookup"><span data-stu-id="e6dc4-132">Germany</span></span>
- <span data-ttu-id="e6dc4-133">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="e6dc4-133">Greece</span></span>
- <span data-ttu-id="e6dc4-134">プエルトリコ</span><span class="sxs-lookup"><span data-stu-id="e6dc4-134">Puerto Rico</span></span>
- <span data-ttu-id="e6dc4-135">南アフリカ</span><span class="sxs-lookup"><span data-stu-id="e6dc4-135">South Africa</span></span>
- <span data-ttu-id="e6dc4-136">英国</span><span class="sxs-lookup"><span data-stu-id="e6dc4-136">United Kingdom</span></span>
- <span data-ttu-id="e6dc4-137">米国</span><span class="sxs-lookup"><span data-stu-id="e6dc4-137">United States</span></span>
- <span data-ttu-id="e6dc4-138">西ヨーロッパ</span><span class="sxs-lookup"><span data-stu-id="e6dc4-138">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="e6dc4-139">サード パーティ製アプリのアクティブ化</span><span class="sxs-lookup"><span data-stu-id="e6dc4-139">Activate third-party apps</span></span>

<span data-ttu-id="e6dc4-140">管理者は、ユーザーに割り当てる前にサード パーティ製アプリをアクティブにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-140">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="e6dc4-141">これらのアプリは、サード パーティの発行元のポータルでアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-141">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="e6dc4-142">管理センターで、[製品アプリの請求 **]**  >  **ページ**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-142">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="e6dc4-143">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-143">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="e6dc4-144">[ **設定と&] で**、[発行元 **のポータルで管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-144">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="e6dc4-145">アプリの発行元のサイトにアクセスし、アプリをアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-145">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="e6dc4-146">サードパーティ製のアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="e6dc4-146">Manage third-party apps</span></span>

<span data-ttu-id="e6dc4-147">管理者は、Microsoft 365 管理センターとサード パーティ アプリ プロバイダーのポータルの 2 つの場所でサード パーティ 製アプリを管理します。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-147">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="e6dc4-148">各ポータルで実行できる操作を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-148">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="e6dc4-149">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="e6dc4-149">Microsoft 365 admin center</span></span> | <span data-ttu-id="e6dc4-150">アプリ発行元ポータル</span><span class="sxs-lookup"><span data-stu-id="e6dc4-150">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="e6dc4-151">ライセンス数量の変更</span><span class="sxs-lookup"><span data-stu-id="e6dc4-151">Change license quantity</span></span> <br> <span data-ttu-id="e6dc4-152">請求書の支払い方法を管理する</span><span class="sxs-lookup"><span data-stu-id="e6dc4-152">Manage how you pay your bill</span></span> <br> <span data-ttu-id="e6dc4-153">請求書の支払い方法を管理する</span><span class="sxs-lookup"><span data-stu-id="e6dc4-153">Manage how you pay your bill</span></span> <br> <span data-ttu-id="e6dc4-154">支払い方法の変更 (クレジット カード)</span><span class="sxs-lookup"><span data-stu-id="e6dc4-154">Change payment method (credit card)</span></span> <br> <span data-ttu-id="e6dc4-155">請求書の表示</span><span class="sxs-lookup"><span data-stu-id="e6dc4-155">View invoice</span></span> <br> <span data-ttu-id="e6dc4-156">アプリのサブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="e6dc4-156">Cancel app subscription</span></span> | <span data-ttu-id="e6dc4-157">アプリをセットアップする (アプリごとに 1 回)</span><span class="sxs-lookup"><span data-stu-id="e6dc4-157">Set up app (once for each app)</span></span> <br> <span data-ttu-id="e6dc4-158">ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e6dc4-158">Assign licenses to users</span></span> <br> <span data-ttu-id="e6dc4-159">テクニカル サポート</span><span class="sxs-lookup"><span data-stu-id="e6dc4-159">Technical support</span></span> |

<span data-ttu-id="e6dc4-160">アプリをアクティブ化した後も、アプリがキャンセル、期限切れ、または支払いが最新の状態に保たれる場合を含め、アクティブなままです。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-160">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="e6dc4-161">これらのイベントは、アプリの状態を無効に変更します。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-161">These events change the app status to disabled.</span></span> <span data-ttu-id="e6dc4-162">アプリを無効にすると、アプリを再アクティブ化できません。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-162">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="e6dc4-163">アプリを引き続き使用するには、別のコピーを購入します。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-163">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="e6dc4-164">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e6dc4-164">Assign licenses</span></span>

<span data-ttu-id="e6dc4-165">管理者は、ユーザーに割り当てる前にサード パーティ製アプリをアクティブにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-165">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="e6dc4-166">サード パーティの発行元のポータルでアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-166">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="e6dc4-167">アプリ ページの [設定] の **[&]** で、ライセンスを割り当てるリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-167">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="e6dc4-168">管理センターで、[製品アプリの請求 **]**  >  **ページ**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-168">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="e6dc4-169">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-169">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="e6dc4-170">**[設定とアクション]** で、**[発行元のポータルで管理する]** へのリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-170">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="e6dc4-171">ライセンス数量の変更</span><span class="sxs-lookup"><span data-stu-id="e6dc4-171">Change license quantity</span></span>

<span data-ttu-id="e6dc4-172">管理者は、組織が所有するライセンスの数を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-172">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="e6dc4-173">これは、シート ベースの価格で購入したアプリにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-173">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="e6dc4-174">管理センターで、[製品アプリの請求 **]**  >  **ページ**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-174">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="e6dc4-175">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-175">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="e6dc4-176">[ライセンス **数量の変更] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-176">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="e6dc4-177">支払方法を管理する</span><span class="sxs-lookup"><span data-stu-id="e6dc4-177">Manage payment methods</span></span>

<span data-ttu-id="e6dc4-178">サービスとしてのソフトウェア アプリには、それぞれ課金プロファイルが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-178">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="e6dc4-179">請求プロファイルを使用すると、請求書に含まれる製品と請求書の支払い方法をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-179">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="e6dc4-180">これには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-180">They include:</span></span>

- <span data-ttu-id="e6dc4-181">**支払い方法** – クレジット カードまたはチェック/電信送金</span><span class="sxs-lookup"><span data-stu-id="e6dc4-181">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="e6dc4-182">**連絡先情報** – 請求先住所と連絡先名</span><span class="sxs-lookup"><span data-stu-id="e6dc4-182">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="e6dc4-183">**役割** – 請求プロファイルの変更、請求書の支払い、または請求プロファイルの支払い方法を使用して購入できる役割。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-183">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="e6dc4-184">請求プロファイルの詳細については、「請求プロファイルについて [」を参照してください](/microsoft-store/billing-profile)。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-184">For more information on billing profiles, see [Understand billing profiles](/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="e6dc4-185">サービスとしてのソフトウェア アプリサブスクリプションの課金プロファイルを変更する</span><span class="sxs-lookup"><span data-stu-id="e6dc4-185">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="e6dc4-186">管理センターで、[製品アプリの請求 **]**  >  **ページ**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-186">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="e6dc4-187">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-187">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="e6dc4-188">[課金プロファイル] **の横にある**[編集] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-188">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="e6dc4-189">請求書の詳細については、「請求書または請求書 [について」を参照してください](billing-and-payments/understand-your-invoice.md)。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-189">For more information on invoices, see [Understand your bill or invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="e6dc4-190">サービスとしてのソフトウェア アプリのサブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="e6dc4-190">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="e6dc4-191">アプリ ページからサービスとしてのソフトウェア アプリをキャンセルできます。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-191">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="e6dc4-192">管理センターで、[製品アプリの請求 **]**  >  **ページ**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-192">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="e6dc4-193">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-193">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="e6dc4-194">[**設定とアクション**] の下で、[**サブスクリプションのキャンセル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6dc4-194">Under **Settings & actions**, select **Cancel subscription**.</span></span>