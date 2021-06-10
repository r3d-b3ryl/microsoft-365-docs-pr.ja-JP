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
description: 管理センターでサード パーティ製アプリをアクティブ化および管理するMicrosoft 365します。
ms.date: 04/15/2021
ms.openlocfilehash: f061137270416d13db1f1cd32aa17f50f2f8c5d2
ms.sourcegitcommit: 2cf7293d610a676726ac891b89366e23810d9142
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52866609"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="3ab49-103">組織のサード パーティ製アプリのサブスクリプションを管理する</span><span class="sxs-lookup"><span data-stu-id="3ab49-103">Manage third-party app subscriptions for your organization</span></span>

<span data-ttu-id="3ab49-104">新しい管理センターでサード パーティ製アプリのライセンスと請求をMicrosoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="3ab49-104">You can manage licenses and billing for third-party apps in the new Microsoft 365 admin center.</span></span> <span data-ttu-id="3ab49-105">更新された機能には、サブスクリプション管理の強化、請求情報へのアクセスの改善、請求書管理の柔軟性の向上が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3ab49-105">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="3ab49-106">サブスクリプション管理は、Microsoft の更新されたコマース プラットフォームに基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="3ab49-106">Subscription management is based on Microsoft’s updated commerce platform.</span></span> <span data-ttu-id="3ab49-107">これは、顧客が直接購入するサービスとしてのソフトウェア アプリ、またはサード パーティ プロバイダーから適用されます。</span><span class="sxs-lookup"><span data-stu-id="3ab49-107">This applies to software-as-a-service apps that customers purchase directly, or from a third-party provider.</span></span>

## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="3ab49-108">サービスとしてのソフトウェア アプリを取得する方法</span><span class="sxs-lookup"><span data-stu-id="3ab49-108">How to get software-as-a-service apps</span></span>

<span data-ttu-id="3ab49-109">サード パーティ製アプリを購入するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="3ab49-109">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="3ab49-110">**直接購入** – 顧客は Azure [Marketplace](https://azuremarketplace.microsoft.com/marketplace/)または [AppSource](https://appsource.microsoft.com/)からサブスクリプションを直接購入できます。</span><span class="sxs-lookup"><span data-stu-id="3ab49-110">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://appsource.microsoft.com/).</span></span>
- <span data-ttu-id="3ab49-111">**パートナー購入** – パートナー センターを通じてパートナーと一緒にサブスクリプションを購入します。</span><span class="sxs-lookup"><span data-stu-id="3ab49-111">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="3ab49-112">**Microsoft の提案** – サード パーティ製アプリを含む Microsoft Sales からの提案に応答します。</span><span class="sxs-lookup"><span data-stu-id="3ab49-112">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="3ab49-113">お客様がアプリを購入し、Microsoft カスタマー 契約に同意すると、管理センターまたは管理センター Microsoft 365で管理ビジネス向け Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="3ab49-113">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="3ab49-114">アプリ プロバイダーは、アプリを一定額で販売するか、ユーザーのライセンスを購入します。</span><span class="sxs-lookup"><span data-stu-id="3ab49-114">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="3ab49-115">**定額 –** サイトベースの価格とも呼ばれるアプリの価格は、月次または年間の価格です。</span><span class="sxs-lookup"><span data-stu-id="3ab49-115">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="3ab49-116">アプリ ページでは、ライセンスの数量が Unlimited に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ab49-116">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="3ab49-117">**ライセンス** – アプリの価格はライセンス別です。</span><span class="sxs-lookup"><span data-stu-id="3ab49-117">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="3ab49-118">顧客は組織内の各ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3ab49-118">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="3ab49-119">サポートされる地域</span><span class="sxs-lookup"><span data-stu-id="3ab49-119">Supported regions</span></span>

<span data-ttu-id="3ab49-120">サード パーティ製アプリのサポートは、次の地域で利用できます。</span><span class="sxs-lookup"><span data-stu-id="3ab49-120">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="3ab49-121">アルゼンチン</span><span class="sxs-lookup"><span data-stu-id="3ab49-121">Argentina</span></span>
- <span data-ttu-id="3ab49-122">オーストラリア</span><span class="sxs-lookup"><span data-stu-id="3ab49-122">Australia</span></span>
- <span data-ttu-id="3ab49-123">カナダ</span><span class="sxs-lookup"><span data-stu-id="3ab49-123">Canada</span></span>
- <span data-ttu-id="3ab49-124">チリ</span><span class="sxs-lookup"><span data-stu-id="3ab49-124">Chile</span></span>
- <span data-ttu-id="3ab49-125">フランス</span><span class="sxs-lookup"><span data-stu-id="3ab49-125">France</span></span>
- <span data-ttu-id="3ab49-126">ドイツ</span><span class="sxs-lookup"><span data-stu-id="3ab49-126">Germany</span></span>
- <span data-ttu-id="3ab49-127">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="3ab49-127">Greece</span></span>
- <span data-ttu-id="3ab49-128">プエルトリコ</span><span class="sxs-lookup"><span data-stu-id="3ab49-128">Puerto Rico</span></span>
- <span data-ttu-id="3ab49-129">南アフリカ</span><span class="sxs-lookup"><span data-stu-id="3ab49-129">South Africa</span></span>
- <span data-ttu-id="3ab49-130">英国</span><span class="sxs-lookup"><span data-stu-id="3ab49-130">United Kingdom</span></span>
- <span data-ttu-id="3ab49-131">米国</span><span class="sxs-lookup"><span data-stu-id="3ab49-131">United States</span></span>
- <span data-ttu-id="3ab49-132">西ヨーロッパ</span><span class="sxs-lookup"><span data-stu-id="3ab49-132">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="3ab49-133">サード パーティ製アプリのアクティブ化</span><span class="sxs-lookup"><span data-stu-id="3ab49-133">Activate third-party apps</span></span>

<span data-ttu-id="3ab49-134">管理者は、ユーザーに割り当てる前にサード パーティ製アプリをアクティブにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ab49-134">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="3ab49-135">これらのアプリは、サード パーティの発行元のポータルでアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="3ab49-135">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="3ab49-136">管理センターで、[製品アプリの請求 **]**  >  **ページ**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="3ab49-136">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="3ab49-137">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="3ab49-137">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="3ab49-138">**[設定 &] で**、[発行元 **のポータルで管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3ab49-138">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="3ab49-139">アプリの発行元のサイトにアクセスし、アプリをアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="3ab49-139">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="3ab49-140">サードパーティ製のアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="3ab49-140">Manage third-party apps</span></span>

<span data-ttu-id="3ab49-141">管理者は、管理センターとサード パーティ アプリ プロバイダーのポータルの 2 つの場所Microsoft 365サードパーティ アプリを管理します。</span><span class="sxs-lookup"><span data-stu-id="3ab49-141">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="3ab49-142">各ポータルで実行できる操作を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3ab49-142">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="3ab49-143">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="3ab49-143">Microsoft 365 admin center</span></span> | <span data-ttu-id="3ab49-144">アプリ発行元ポータル</span><span class="sxs-lookup"><span data-stu-id="3ab49-144">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="3ab49-145">ライセンス数量の変更</span><span class="sxs-lookup"><span data-stu-id="3ab49-145">Change license quantity</span></span> <br> <span data-ttu-id="3ab49-146">請求書の支払い方法を管理する</span><span class="sxs-lookup"><span data-stu-id="3ab49-146">Manage how you pay your bill</span></span> <br> <span data-ttu-id="3ab49-147">請求書の支払い方法を管理する</span><span class="sxs-lookup"><span data-stu-id="3ab49-147">Manage how you pay your bill</span></span> <br> <span data-ttu-id="3ab49-148">支払い方法の変更 (クレジット カード)</span><span class="sxs-lookup"><span data-stu-id="3ab49-148">Change payment method (credit card)</span></span> <br> <span data-ttu-id="3ab49-149">請求書の表示</span><span class="sxs-lookup"><span data-stu-id="3ab49-149">View invoice</span></span> <br> <span data-ttu-id="3ab49-150">アプリのサブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="3ab49-150">Cancel app subscription</span></span> | <span data-ttu-id="3ab49-151">アプリをセットアップする (アプリごとに 1 回)</span><span class="sxs-lookup"><span data-stu-id="3ab49-151">Set up app (once for each app)</span></span> <br> <span data-ttu-id="3ab49-152">ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3ab49-152">Assign licenses to users</span></span> <br> <span data-ttu-id="3ab49-153">テクニカル サポート</span><span class="sxs-lookup"><span data-stu-id="3ab49-153">Technical support</span></span> |

<span data-ttu-id="3ab49-154">アプリをアクティブ化した後も、アプリがキャンセル、期限切れ、または支払いが最新の状態に保たれる場合を含め、アクティブなままです。</span><span class="sxs-lookup"><span data-stu-id="3ab49-154">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="3ab49-155">これらのイベントは、アプリの状態を無効に変更します。</span><span class="sxs-lookup"><span data-stu-id="3ab49-155">These events change the app status to disabled.</span></span> <span data-ttu-id="3ab49-156">アプリを無効にすると、アプリを再アクティブ化できません。</span><span class="sxs-lookup"><span data-stu-id="3ab49-156">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="3ab49-157">アプリを引き続き使用するには、別のコピーを購入します。</span><span class="sxs-lookup"><span data-stu-id="3ab49-157">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="3ab49-158">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3ab49-158">Assign licenses</span></span>

<span data-ttu-id="3ab49-159">管理者は、ユーザーに割り当てる前にサード パーティ製アプリをアクティブにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ab49-159">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="3ab49-160">サード パーティの発行元のポータルでアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="3ab49-160">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="3ab49-161">[アプリ] ページの [ライセンスの **設定 &]** で、ライセンスを割り当てるリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="3ab49-161">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="3ab49-162">管理センターで、[製品アプリの請求 **]**  >  **ページ**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="3ab49-162">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="3ab49-163">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="3ab49-163">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="3ab49-164">**[設定とアクション]** で、**[発行元のポータルで管理する]** へのリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="3ab49-164">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="3ab49-165">ライセンス数量の変更</span><span class="sxs-lookup"><span data-stu-id="3ab49-165">Change license quantity</span></span>

<span data-ttu-id="3ab49-166">管理者は、組織が所有するライセンスの数を変更できます。</span><span class="sxs-lookup"><span data-stu-id="3ab49-166">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="3ab49-167">これは、シート ベースの価格で購入したアプリにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="3ab49-167">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="3ab49-168">管理センターで、[製品アプリの請求 **]**  >  **ページ**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="3ab49-168">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="3ab49-169">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="3ab49-169">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="3ab49-170">[ライセンス **数量の変更] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3ab49-170">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="3ab49-171">支払方法を管理する</span><span class="sxs-lookup"><span data-stu-id="3ab49-171">Manage payment methods</span></span>

<span data-ttu-id="3ab49-172">サービスとしてのソフトウェア アプリには、それぞれ課金プロファイルが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="3ab49-172">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="3ab49-173">請求プロファイルを使用すると、請求書に含まれる製品と請求書の支払い方法をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="3ab49-173">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="3ab49-174">これには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3ab49-174">They include:</span></span>

- <span data-ttu-id="3ab49-175">**支払い方法** – クレジット カードまたはチェック/電信送金</span><span class="sxs-lookup"><span data-stu-id="3ab49-175">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="3ab49-176">**連絡先情報** – 請求先住所と連絡先名</span><span class="sxs-lookup"><span data-stu-id="3ab49-176">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="3ab49-177">**役割** – 請求プロファイルの変更、請求書の支払い、または請求プロファイルの支払い方法を使用して購入できる役割。</span><span class="sxs-lookup"><span data-stu-id="3ab49-177">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="3ab49-178">請求プロファイルの詳細については、「請求プロファイルについて [」を参照してください](/microsoft-store/billing-profile)。</span><span class="sxs-lookup"><span data-stu-id="3ab49-178">For more information on billing profiles, see [Understand billing profiles](/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="3ab49-179">サービスとしてのソフトウェア アプリサブスクリプションの課金プロファイルを変更する</span><span class="sxs-lookup"><span data-stu-id="3ab49-179">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="3ab49-180">管理センターで、[製品アプリの請求 **]**  >  **ページ**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="3ab49-180">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="3ab49-181">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="3ab49-181">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="3ab49-182">[課金プロファイル] **の横にある**[編集] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3ab49-182">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="3ab49-183">請求書の詳細については、「請求書または請求書 [について」を参照してください](billing-and-payments/understand-your-invoice.md)。</span><span class="sxs-lookup"><span data-stu-id="3ab49-183">For more information on invoices, see [Understand your bill or invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="3ab49-184">サービスとしてのソフトウェア アプリのサブスクリプションをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="3ab49-184">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="3ab49-185">アプリ ページからサービスとしてのソフトウェア アプリをキャンセルできます。</span><span class="sxs-lookup"><span data-stu-id="3ab49-185">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="3ab49-186">管理センターで、[製品アプリの請求 **]**  >  **ページ**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="3ab49-186">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="3ab49-187">管理するアプリを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="3ab49-187">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="3ab49-188">[**設定とアクション**] の下で、[**サブスクリプションのキャンセル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ab49-188">Under **Settings & actions**, select **Cancel subscription**.</span></span>
