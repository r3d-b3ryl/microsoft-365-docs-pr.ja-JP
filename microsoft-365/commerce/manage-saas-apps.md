---
title: 組織のサービスとしてのソフトウェア アプリを管理する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jamitche, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid: MET150
description: Microsoft 365 管理センターでサード パーティ製アプリをアクティブ化および管理する方法について説明します。
ms.date: 04/15/2021
ms.openlocfilehash: 5a486dba03fbd34fe2e409bba8ba41c1f9873141
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331624"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="a64d9-103">組織のサード パーティ製アプリのサブスクリプションを管理する</span><span class="sxs-lookup"><span data-stu-id="a64d9-103">Manage third-party app subscriptions for your organization</span></span>

<span data-ttu-id="a64d9-104">新しい Microsoft 365 管理センターでは、サード パーティ製アプリのライセンスと課金を管理できます。</span><span class="sxs-lookup"><span data-stu-id="a64d9-104">You can manage licenses and billing for third-party apps in the new Microsoft 365 admin center.</span></span> <span data-ttu-id="a64d9-105">更新された機能には、サブスクリプション管理の強化、請求情報へのアクセスの改善、請求書管理の柔軟性の向上が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a64d9-105">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="a64d9-106">サブスクリプション管理は、Microsoft の更新されたコマース プラットフォームに基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="a64d9-106">Subscription management is based on Microsoft’s updated commerce platform.</span></span> <span data-ttu-id="a64d9-107">これは、顧客が直接購入するサービスとしてのソフトウェア アプリ、またはサード パーティ プロバイダーから適用されます。</span><span class="sxs-lookup"><span data-stu-id="a64d9-107">This applies to software-as-a-service apps that customers purchase directly, or from a third-party provider.</span></span>

<span data-ttu-id="a64d9-108">プレビュー モードを有効にした状態で、Microsoft 365 管理センターでサード パーティ製アプリのライセンスと課金を管理できます。</span><span class="sxs-lookup"><span data-stu-id="a64d9-108">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="a64d9-109">更新された機能には、サブスクリプション管理の強化、請求情報へのアクセスの改善、請求書管理の柔軟性の向上が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a64d9-109">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="a64d9-110">サブスクリプション管理は、Microsoft の更新されたコマース プラットフォームに基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="a64d9-110">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="a64d9-111">これは、顧客が直接購入するサービスとしてのソフトウェア アプリ、またはサード パーティ プロバイダーから適用されます。</span><span class="sxs-lookup"><span data-stu-id="a64d9-111">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>

## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="a64d9-112">サービスとしてのソフトウェア アプリを取得する方法</span><span class="sxs-lookup"><span data-stu-id="a64d9-112">How to get software-as-a-service apps</span></span>

<span data-ttu-id="a64d9-113">サード パーティ製アプリを購入するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="a64d9-113">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="a64d9-114">**直接購入** – 顧客は Azure [Marketplace](https://azuremarketplace.microsoft.com/marketplace/)または [AppSource](https://appsource.microsoft.com/)からサブスクリプションを直接購入できます。</span><span class="sxs-lookup"><span data-stu-id="a64d9-114">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://appsource.microsoft.com/).</span></span>
- <span data-ttu-id="a64d9-115">**パートナー購入** – パートナー センターを通じてパートナーと一緒にサブスクリプションを購入します。</span><span class="sxs-lookup"><span data-stu-id="a64d9-115">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="a64d9-116">**Microsoft の提案** – サード パーティ製アプリを含む Microsoft Sales からの提案に応答します。</span><span class="sxs-lookup"><span data-stu-id="a64d9-116">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="a64d9-117">お客様がアプリを購入し、Microsoft カスタマー 契約に同意すると、Microsoft 365 管理センターまたは Microsoft Store for Business で管理できます。</span><span class="sxs-lookup"><span data-stu-id="a64d9-117">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="a64d9-118">アプリ プロバイダーは、アプリを一定額で販売するか、ユーザーのライセンスを購入します。</span><span class="sxs-lookup"><span data-stu-id="a64d9-118">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="a64d9-119">**定額 –** サイトベースの価格とも呼ばれるアプリの価格は、月次または年間の価格です。</span><span class="sxs-lookup"><span data-stu-id="a64d9-119">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="a64d9-120">アプリ ページでは、ライセンスの数量が Unlimited に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a64d9-120">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="a64d9-121">**ライセンス** – アプリの価格はライセンス別です。</span><span class="sxs-lookup"><span data-stu-id="a64d9-121">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="a64d9-122">顧客は組織内の各ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a64d9-122">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="a64d9-123">サポートされる地域</span><span class="sxs-lookup"><span data-stu-id="a64d9-123">Supported regions</span></span>

<span data-ttu-id="a64d9-124">サード パーティ製アプリのサポートは、次の地域で利用できます。</span><span class="sxs-lookup"><span data-stu-id="a64d9-124">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="a64d9-125">アルゼンチン</span><span class="sxs-lookup"><span data-stu-id="a64d9-125">Argentina</span></span>
- <span data-ttu-id="a64d9-126">オーストラリア</span><span class="sxs-lookup"><span data-stu-id="a64d9-126">Australia</span></span>
- <span data-ttu-id="a64d9-127">カナダ</span><span class="sxs-lookup"><span data-stu-id="a64d9-127">Canada</span></span>
- <span data-ttu-id="a64d9-128">チリ</span><span class="sxs-lookup"><span data-stu-id="a64d9-128">Chile</span></span>
- <span data-ttu-id="a64d9-129">フランス</span><span class="sxs-lookup"><span data-stu-id="a64d9-129">France</span></span>
- <span data-ttu-id="a64d9-130">ドイツ</span><span class="sxs-lookup"><span data-stu-id="a64d9-130">Germany</span></span>
- <span data-ttu-id="a64d9-131">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="a64d9-131">Greece</span></span>
- <span data-ttu-id="a64d9-132">プエルトリコ</span><span class="sxs-lookup"><span data-stu-id="a64d9-132">Puerto Rico</span></span>
- <span data-ttu-id="a64d9-133">南アフリカ</span><span class="sxs-lookup"><span data-stu-id="a64d9-133">South Africa</span></span>
- <span data-ttu-id="a64d9-134">英国</span><span class="sxs-lookup"><span data-stu-id="a64d9-134">United Kingdom</span></span>
- <span data-ttu-id="a64d9-135">米国</span><span class="sxs-lookup"><span data-stu-id="a64d9-135">United States</span></span>
- <span data-ttu-id="a64d9-136">西ヨーロッパ</span><span class="sxs-lookup"><span data-stu-id="a64d9-136">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="a64d9-137">サード パーティ製アプリのアクティブ化</span><span class="sxs-lookup"><span data-stu-id="a64d9-137">Activate third-party apps</span></span>

<span data-ttu-id="a64d9-138">管理者は、ユーザーに割り当てる前にサード パーティ製アプリをアクティブにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a64d9-138">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="a64d9-139">これらのアプリは、サード パーティの発行元のポータルでアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="a64d9-139">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="a64d9-140">管理センターで、[製品アプリの請求 **]**  >  **ページ**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="a64d9-140">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="a64d9-141">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="a64d9-141">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="a64d9-142">[ **設定と&] で**、[発行元 **のポータルで管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a64d9-142">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="a64d9-143">アプリの発行元のサイトにアクセスし、アプリをアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="a64d9-143">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="a64d9-144">サードパーティ製のアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="a64d9-144">Manage third-party apps</span></span>

<span data-ttu-id="a64d9-145">管理者は、Microsoft 365 管理センターとサード パーティ アプリ プロバイダーのポータルの 2 つの場所でサード パーティ 製アプリを管理します。</span><span class="sxs-lookup"><span data-stu-id="a64d9-145">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="a64d9-146">各ポータルで実行できる操作を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a64d9-146">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="a64d9-147">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="a64d9-147">Microsoft 365 admin center</span></span> | <span data-ttu-id="a64d9-148">アプリ発行元ポータル</span><span class="sxs-lookup"><span data-stu-id="a64d9-148">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="a64d9-149">ライセンス数量の変更</span><span class="sxs-lookup"><span data-stu-id="a64d9-149">Change license quantity</span></span> <br> <span data-ttu-id="a64d9-150">請求書の支払い方法を管理する</span><span class="sxs-lookup"><span data-stu-id="a64d9-150">Manage how you pay your bill</span></span> <br> <span data-ttu-id="a64d9-151">請求書の支払い方法を管理する</span><span class="sxs-lookup"><span data-stu-id="a64d9-151">Manage how you pay your bill</span></span> <br> <span data-ttu-id="a64d9-152">支払い方法の変更 (クレジット カード)</span><span class="sxs-lookup"><span data-stu-id="a64d9-152">Change payment method (credit card)</span></span> <br> <span data-ttu-id="a64d9-153">請求書の表示</span><span class="sxs-lookup"><span data-stu-id="a64d9-153">View invoice</span></span> <br> <span data-ttu-id="a64d9-154">アプリのサブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="a64d9-154">Cancel app subscription</span></span> | <span data-ttu-id="a64d9-155">アプリをセットアップする (アプリごとに 1 回)</span><span class="sxs-lookup"><span data-stu-id="a64d9-155">Set up app (once for each app)</span></span> <br> <span data-ttu-id="a64d9-156">ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a64d9-156">Assign licenses to users</span></span> <br> <span data-ttu-id="a64d9-157">テクニカル サポート</span><span class="sxs-lookup"><span data-stu-id="a64d9-157">Technical support</span></span> |

<span data-ttu-id="a64d9-158">アプリをアクティブ化した後も、アプリがキャンセル、期限切れ、または支払いが最新の状態に保たれる場合を含め、アクティブなままです。</span><span class="sxs-lookup"><span data-stu-id="a64d9-158">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="a64d9-159">これらのイベントは、アプリの状態を無効に変更します。</span><span class="sxs-lookup"><span data-stu-id="a64d9-159">These events change the app status to disabled.</span></span> <span data-ttu-id="a64d9-160">アプリを無効にすると、アプリを再アクティブ化できません。</span><span class="sxs-lookup"><span data-stu-id="a64d9-160">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="a64d9-161">アプリを引き続き使用するには、別のコピーを購入します。</span><span class="sxs-lookup"><span data-stu-id="a64d9-161">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="a64d9-162">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a64d9-162">Assign licenses</span></span>

<span data-ttu-id="a64d9-163">管理者は、ユーザーに割り当てる前にサード パーティ製アプリをアクティブにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a64d9-163">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="a64d9-164">サード パーティの発行元のポータルでアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="a64d9-164">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="a64d9-165">アプリ ページの [設定] の **[&]** で、ライセンスを割り当てるリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="a64d9-165">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="a64d9-166">管理センターで、[製品アプリの請求 **]**  >  **ページ**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="a64d9-166">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="a64d9-167">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="a64d9-167">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="a64d9-168">**[設定とアクション]** で、**[発行元のポータルで管理する]** へのリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="a64d9-168">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="a64d9-169">ライセンス数量の変更</span><span class="sxs-lookup"><span data-stu-id="a64d9-169">Change license quantity</span></span>

<span data-ttu-id="a64d9-170">管理者は、組織が所有するライセンスの数を変更できます。</span><span class="sxs-lookup"><span data-stu-id="a64d9-170">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="a64d9-171">これは、シート ベースの価格で購入したアプリにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="a64d9-171">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="a64d9-172">管理センターで、[製品アプリの請求 **]**  >  **ページ**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="a64d9-172">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="a64d9-173">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="a64d9-173">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="a64d9-174">[ライセンス **数量の変更] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a64d9-174">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="a64d9-175">支払方法を管理する</span><span class="sxs-lookup"><span data-stu-id="a64d9-175">Manage payment methods</span></span>

<span data-ttu-id="a64d9-176">サービスとしてのソフトウェア アプリには、それぞれ課金プロファイルが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="a64d9-176">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="a64d9-177">請求プロファイルを使用すると、請求書に含まれる製品と請求書の支払い方法をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="a64d9-177">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="a64d9-178">これには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a64d9-178">They include:</span></span>

- <span data-ttu-id="a64d9-179">**支払い方法** – クレジット カードまたはチェック/電信送金</span><span class="sxs-lookup"><span data-stu-id="a64d9-179">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="a64d9-180">**連絡先情報** – 請求先住所と連絡先名</span><span class="sxs-lookup"><span data-stu-id="a64d9-180">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="a64d9-181">**役割** – 請求プロファイルの変更、請求書の支払い、または請求プロファイルの支払い方法を使用して購入できる役割。</span><span class="sxs-lookup"><span data-stu-id="a64d9-181">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="a64d9-182">請求プロファイルの詳細については、「請求プロファイルについて [」を参照してください](/microsoft-store/billing-profile)。</span><span class="sxs-lookup"><span data-stu-id="a64d9-182">For more information on billing profiles, see [Understand billing profiles](/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="a64d9-183">サービスとしてのソフトウェア アプリサブスクリプションの課金プロファイルを変更する</span><span class="sxs-lookup"><span data-stu-id="a64d9-183">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="a64d9-184">管理センターで、[製品アプリの請求 **]**  >  **ページ**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="a64d9-184">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="a64d9-185">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="a64d9-185">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="a64d9-186">[課金プロファイル] **の横にある**[編集] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a64d9-186">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="a64d9-187">請求書の詳細については、「請求書または請求書 [について」を参照してください](billing-and-payments/understand-your-invoice.md)。</span><span class="sxs-lookup"><span data-stu-id="a64d9-187">For more information on invoices, see [Understand your bill or invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="a64d9-188">サービスとしてのソフトウェア アプリのサブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="a64d9-188">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="a64d9-189">アプリ ページからサービスとしてのソフトウェア アプリをキャンセルできます。</span><span class="sxs-lookup"><span data-stu-id="a64d9-189">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="a64d9-190">管理センターで、[製品アプリの請求 **]**  >  **ページ**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="a64d9-190">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="a64d9-191">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="a64d9-191">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="a64d9-192">[**設定とアクション**] の下で、[**サブスクリプションのキャンセル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a64d9-192">Under **Settings & actions**, select **Cancel subscription**.</span></span>
