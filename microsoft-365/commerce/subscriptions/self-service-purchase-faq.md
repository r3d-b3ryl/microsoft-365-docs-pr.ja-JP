---
title: セルフサービス購入に関するよくあるご質問
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
- commerce_ssp
search.appverid:
- MET150
description: セルフサービス購入についてよく寄せられる質問への回答を紹介します。
ms.date: 09/15/2020
ms.openlocfilehash: 964eca8e94f64fd2f212745abfff0cf25d45bfca
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333196"
---
# <a name="self-service-purchase-faq"></a><span data-ttu-id="24302-103">セルフサービス購入に関するよくあるご質問</span><span class="sxs-lookup"><span data-stu-id="24302-103">Self-service purchase FAQ</span></span>

<span data-ttu-id="24302-104">セルフサービス購入により、ユーザーは新しいテクノロジを試して、最終的により大規模な組織に利益をもたらすソリューションを開発する機会が得られます。</span><span class="sxs-lookup"><span data-stu-id="24302-104">Self-service purchase gives users a chance to try out new technologies and develop solutions that ultimately benefit their larger organizations.</span></span> <span data-ttu-id="24302-105">中央調達と IT チームは、<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>を介してセルフサービス購入ソリューションを購入して展開するすべてのユーザーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="24302-105">Central procurement and IT teams have visibility to all users who buy and deploy self-service purchase solutions through the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="24302-106">管理者は、PowerShell を使用して製品ごとにセルフサービス購入を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="24302-106">Admins can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="24302-107">詳細については、「[MSCommerce PowerShell モジュールに AllowSelfServicePurchase を使用する](allowselfservicepurchase-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24302-107">To learn more, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

<span data-ttu-id="24302-108">セルフサービス購入は、Power Platform (Power BI、Power Apps、Power Automate)、Project、Visio で利用できます。</span><span class="sxs-lookup"><span data-stu-id="24302-108">Self-service purchase is available for Power Platform (Power BI, Power Apps, and Power Automate), Project, and Visio.</span></span>

> [!NOTE]
> <span data-ttu-id="24302-109">セルフサービス購入は、インドまたは政府機関や教育機関のお客様にはご利用いただけません。</span><span class="sxs-lookup"><span data-stu-id="24302-109">Self-service purchase isn’t available in India or for government or education customers.</span></span> <span data-ttu-id="24302-110">Project と Visio は、ブラジルとコンゴ民主共和国ではセルフサービスで購入することはできません。</span><span class="sxs-lookup"><span data-stu-id="24302-110">Project and Visio are not available for self-service purchase in Brazil and the Democratic Republic of Congo.</span></span>

## <a name="making-a-self-service-purchase"></a><span data-ttu-id="24302-111">セルフサービス購入を行う</span><span class="sxs-lookup"><span data-stu-id="24302-111">Making a self-service purchase</span></span>

### <a name="how-does-a-customer-make-a-self-service-purchase"></a><span data-ttu-id="24302-112">セルフサービス購入はどのように行えますか?</span><span class="sxs-lookup"><span data-stu-id="24302-112">How does a customer make a self-service purchase?</span></span>

<span data-ttu-id="24302-113">製品 Web サイトから、またはアプリ内購入プロンプトから、オンラインでセルフサービス購入を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="24302-113">Customers can make a self-service purchase online from the product websites or from in-app purchase prompts.</span></span> <span data-ttu-id="24302-114">既存の Azure Active Directory (AD) テナント内のユーザーであることを確認するために、最初にメール アドレスを入力するよう求められます。</span><span class="sxs-lookup"><span data-stu-id="24302-114">Customers are first asked to enter an email address to ensure that they're a user in an existing Azure Active Directory (AD) tenant.</span></span> <span data-ttu-id="24302-115">次に、Azure AD 資格情報を使用してサインインするように指示されています。</span><span class="sxs-lookup"><span data-stu-id="24302-115">Next, they're directed to sign in by using their Azure AD credentials.</span></span> <span data-ttu-id="24302-116">サインインした後、購入するサブスクリプションの数を選択し、クレジット カードの支払いを指定するように求められます。</span><span class="sxs-lookup"><span data-stu-id="24302-116">After signing in, the customer is asked to select how many subscriptions they want to buy, and to provide credit card payment.</span></span> <span data-ttu-id="24302-117">購入が完了すると、サブスクリプションの使用を開始できるようになります。</span><span class="sxs-lookup"><span data-stu-id="24302-117">When the purchase is complete, they can start using their subscription.</span></span> <span data-ttu-id="24302-118">購入者は、製品のライセンスを組織内の他の人に割り当てることができる、<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>の制限されたビューにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="24302-118">The purchaser has access to a limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> where they can assign licenses to the product to other people in their organization.</span></span>

### <a name="what-are-the-payment-options-for-self-service-purchases"></a><span data-ttu-id="24302-119">セルフサービス購入にはどのような支払い方法がありますか?</span><span class="sxs-lookup"><span data-stu-id="24302-119">What are the payment options for self-service purchases?</span></span>

<span data-ttu-id="24302-120">現時点では、ご利用いただける支払い方法はクレジット カードのみです。</span><span class="sxs-lookup"><span data-stu-id="24302-120">Currently, credit card is the only available payment method.</span></span> <span data-ttu-id="24302-121">請求書による支払いはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="24302-121">Payment through invoicing isn't supported.</span></span>

### <a name="who-can-buy-through-self-service-purchase"></a><span data-ttu-id="24302-122">誰がセルフサービス購入で購入できますか?</span><span class="sxs-lookup"><span data-stu-id="24302-122">Who can buy through self-service purchase?</span></span>

<span data-ttu-id="24302-123">管理対象 Azure AD テナントのゲスト以外のユーザー アカウントを持つユーザーは、セルフサービス購入を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="24302-123">Any user with a non-guest user account in a managed Azure AD tenant can make a self-service purchase.</span></span> <span data-ttu-id="24302-124">セルフサービス購入は、政府または教育機関のテナントでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="24302-124">Self-service purchasing isn’t available to tenants that are government or education organizations.</span></span> <span data-ttu-id="24302-125">これが自分の組織に当てはまる場合は、セルフサービス購入を制御するために追加の操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="24302-125">If this applies to your organization, then no additional action is required to control self-service purchase.</span></span>

<span data-ttu-id="24302-126">セルフサービス購入の対象になっていない組織または市場のユーザーには、IT 管理者に連絡するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="24302-126">Users in organizations or markets who aren’t eligible for self-service purchase see a message asking them to contact their IT admin.</span></span>

### <a name="can-guest-users-buy-through-self-service-purchase"></a><span data-ttu-id="24302-127">ゲスト ユーザーはセルフサービス購入で購入できますか?</span><span class="sxs-lookup"><span data-stu-id="24302-127">Can guest users buy through self-service purchase?</span></span>

<span data-ttu-id="24302-128">いいえ、ゲスト ユーザーはゲストになっているテナントでセルフサービス購入を完了できません。</span><span class="sxs-lookup"><span data-stu-id="24302-128">No, guest users can’t complete a self-service purchase in a tenant in which they're a guest.</span></span>

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a><span data-ttu-id="24302-129">オンプレミスの Active Directory から同期されたユーザーは、セルフサービスの購入で行うことができますか?</span><span class="sxs-lookup"><span data-stu-id="24302-129">Can users synced from an on-premises Active Directory buy through self-service purchase?</span></span>

<span data-ttu-id="24302-130">ユーザーが、対象の Azure AD テナントにアクティブなユーザー アカウントを持っている場合は、セルフサービス購入を完了できます。</span><span class="sxs-lookup"><span data-stu-id="24302-130">If a user has an active user account in an eligible Azure AD tenant, they can complete a self-service purchase.</span></span>

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a><span data-ttu-id="24302-131">セルフサービス購入者は誰にライセンスを割り当てることができますか?</span><span class="sxs-lookup"><span data-stu-id="24302-131">Who can self-service purchasers assign licenses to?</span></span>

<span data-ttu-id="24302-132">セルフサービス購入者は、同じ Azure AD テナント内のユーザーにのみライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="24302-132">Self-service purchasers can only assign licenses to users in the same Azure AD tenant.</span></span> <span data-ttu-id="24302-133">購入者は、ライセンスを割り当てるために<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>の制限されたビューにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="24302-133">The purchaser has access to a limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> to assign licenses.</span></span> <span data-ttu-id="24302-134">購入者は、セルフサービス購入で購入した製品のライセンスを割り当てることができ、同じ Azure AD テナント内のユーザーに対してのみライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="24302-134">Purchasers can assign licenses to those products that they've bought through self-service purchase, and can only assign those licenses to users in the same Azure AD tenant.</span></span>

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a><span data-ttu-id="24302-135">セルフサービス購入者はどこで購入を確認および管理しますか?</span><span class="sxs-lookup"><span data-stu-id="24302-135">Where does the self-service purchaser see and manage their purchases?</span></span>

<span data-ttu-id="24302-136">セルフサービス購入者は、<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>の制限されたビューで購入を管理できます。</span><span class="sxs-lookup"><span data-stu-id="24302-136">Self-service purchasers can manage their purchases in the limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="24302-137">購入者は常に、すべての Microsoft 365 および Dynamics Online アプリに組み込まれているアプリ起動ツールの **[管理者]** タイルから管理センターにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="24302-137">Purchasers can always get to the admin center from the **Admin** tile in the app launcher built into all Microsoft 365 and Dynamics online apps.</span></span> <span data-ttu-id="24302-138">購入者は、実行した購入を表示したり、同じサービスに対して追加のサブスクリプションを購入したり、それらのサブスクリプションのライセンスを組織内の他のユーザーに割り当てたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="24302-138">Purchasers can view the purchases they've made, buy additional subscriptions to the same service, and assign licenses for those subscriptions to other users in their organization.</span></span> <span data-ttu-id="24302-139">また、購入者は、請求書の表示と支払い、支払い方法の更新、サブスクリプションのキャンセルを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="24302-139">Additionally, purchasers can view and pay their bill, update their payment method, and cancel their subscription.</span></span>

## <a name="pricing"></a><span data-ttu-id="24302-140">価格</span><span class="sxs-lookup"><span data-stu-id="24302-140">Pricing</span></span>

### <a name="what-is-the-pricing-for-self-service-purchases"></a><span data-ttu-id="24302-141">セルフサービス購入の価格はどのようになっていますか?</span><span class="sxs-lookup"><span data-stu-id="24302-141">What is the pricing for self-service purchases?</span></span>

<span data-ttu-id="24302-142">セルフサービス購入の各製品の価格は、Microsoft の Web サイトでご確認いただけます。</span><span class="sxs-lookup"><span data-stu-id="24302-142">Pricing for each of the products for self-service purchase is available on the Microsoft website.</span></span> <span data-ttu-id="24302-143">また、ユーザーがセルフサービス購入を行うときに、精算手続きの一部として価格も表示されます。</span><span class="sxs-lookup"><span data-stu-id="24302-143">Prices are also displayed as part of the checkout experience when users make a self-service purchase.</span></span> <span data-ttu-id="24302-144">これらの価格は、組織が一括購入する場合に支払う価格、またはパートナーを通じて提供される価格とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="24302-144">These prices may differ from the prices an organization pays when making central purchases or prices offered through a partner.</span></span>

### <a name="who-is-responsible-for-payment"></a><span data-ttu-id="24302-145">支払いの責任者は誰ですか?</span><span class="sxs-lookup"><span data-stu-id="24302-145">Who is responsible for payment?</span></span>

<span data-ttu-id="24302-146">セルフサービス購入を通じてサブスクリプションを購入するユーザーです。このユーザーが請求先であり、購入の条件と価格に基づいて支払いを行う責任があります。</span><span class="sxs-lookup"><span data-stu-id="24302-146">The person who buys the subscription through self-service purchase is the person who is billed and who is responsible for payment based on the terms and pricing of the purchase.</span></span>

## <a name="admin-capabilities"></a><span data-ttu-id="24302-147">管理者の機能</span><span class="sxs-lookup"><span data-stu-id="24302-147">Admin capabilities</span></span>

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a><span data-ttu-id="24302-148">セルフサービス購入において、管理者にはどのような機能がありますか?</span><span class="sxs-lookup"><span data-stu-id="24302-148">What capabilities does an admin have for self-service purchases?</span></span>

<span data-ttu-id="24302-149">管理者は、組織内で行われたすべてのセルフサービス購入を<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>で表示できます。</span><span class="sxs-lookup"><span data-stu-id="24302-149">Admins can view all self-service purchases made in their organization in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="24302-150">管理者は、製品、購入者名、購入済みのサブスクリプション、有効期限、注文履歴、購入価格、各セルフサービス購入に割り当てられているユーザーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="24302-150">They can see the product, purchaser name, subscriptions purchased, expiry date, order history, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="24302-151">Power Platform 管理センターでは、管理者はセルフサービス購入容量を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="24302-151">In the Power Platform Admin Center, admins can also view self-service purchases capacity.</span></span> <span data-ttu-id="24302-152">組織から要求された場合、管理者は PowerShell を使用して製品ごとにセルフサービス購入を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="24302-152">If required for their organization, admins can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="24302-153">管理者は、セルフサービス購入された製品と一元的に購入された製品に対して、同じデータ管理およびアクセス ポリシーを有します。</span><span class="sxs-lookup"><span data-stu-id="24302-153">Admins have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="24302-154">管理者は、組織内のユーザーがセルフサービス購入を行うことができるかどうかを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="24302-154">Admins can also control whether users in their organization can make self-service purchases.</span></span> <span data-ttu-id="24302-155">詳細については、「[MSCommerce PowerShell モジュールに AllowSelfServicePurchase を使用する](allowselfservicepurchase-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24302-155">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a><span data-ttu-id="24302-156">セルフサービス購入を有効にすることによるデータ ガバナンスとコンプライアンスを Microsoft はどのように重視していますか?</span><span class="sxs-lookup"><span data-stu-id="24302-156">How is Microsoft respecting data governance and compliance by enabling self-service purchase?</span></span>

<span data-ttu-id="24302-157">管理者は、データ ガバナンスとコンプライアンスの要件に基づいて、テナント内で使用可能なサービスと製品を制御します。</span><span class="sxs-lookup"><span data-stu-id="24302-157">Admins maintain control over what services and products are available within their tenant based on their data governance and compliance requirements.</span></span> <span data-ttu-id="24302-158">組織で有効になっているすべてのデータ管理およびアクセス ポリシーが、使用可能なセルフサービス購入サービスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="24302-158">All data management and access policies that your organization turned on apply to available self-service purchased services.</span></span>

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a><span data-ttu-id="24302-159">セルフサービス購入から作成された製品データを所有するのは誰ですか?</span><span class="sxs-lookup"><span data-stu-id="24302-159">Who owns the product data created from self-service purchases?</span></span>

<span data-ttu-id="24302-160">セルフサービス購入で購入した製品から作成されたデータは、組織によって所有および制御されます。</span><span class="sxs-lookup"><span data-stu-id="24302-160">Data created from products bought through self-service purchase is owned and controlled by the organization.</span></span>

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a><span data-ttu-id="24302-161">セルフサービス購入で行われた購入をどのように一元管理できますか?</span><span class="sxs-lookup"><span data-stu-id="24302-161">How do I centralize the purchases made through self-service purchase?</span></span>

<span data-ttu-id="24302-162">管理者は、セルフサービス購入に割り当てられたユーザーの既存の契約と価格設定を通じて、既存のライセンスを割り当てることも、セルフサービス購入製品の追加サブスクリプションを購入することもできます。</span><span class="sxs-lookup"><span data-stu-id="24302-162">Admins can assign existing licenses or buy additional subscriptions of self-service purchase products through existing agreements and pricing for users assigned to self-service purchases.</span></span> <span data-ttu-id="24302-163">これらの一元的に購入されたライセンスを割り当てた後、管理者は購入者に既存のサブスクリプションをキャンセルするように要求することができます。</span><span class="sxs-lookup"><span data-stu-id="24302-163">After assigning these centrally purchased licenses, admins can then request that the purchasers cancel their existing subscriptions.</span></span>

### <a name="where-does-the-admin-see-self-service-purchases"></a><span data-ttu-id="24302-164">管理者はどこでセルフサービス購入を確認できますか?</span><span class="sxs-lookup"><span data-stu-id="24302-164">Where does the admin see self-service purchases?</span></span>

<span data-ttu-id="24302-165">グローバル管理者と請求管理者は、<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>の **[課金情報]** > **[お使いの製品]** でセルフサービス購入を通じて購入したサブスクリプションを確認できます。</span><span class="sxs-lookup"><span data-stu-id="24302-165">Global and billing admins can see subscriptions bought through self-service purchase in **Billing** > **Your products** in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="24302-166">製品リストをフィルター処理して、中央調達で購入されたサブスクリプションのみを表示したり、セルフサービス購入で購入されたサブスクリプションを含めたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="24302-166">They can filter the products list to only show the subscriptions purchased through central procurement, or to include subscriptions bought through self-service purchase.</span></span>

<span data-ttu-id="24302-167">管理者は、製品、購入者名、購入済みのサブスクリプション、有効期限、注文履歴、購入価格、割り当てられているユーザーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="24302-167">Admins can see the product, purchaser name, subscription purchased, expiry date, order history, the purchase price, and assigned users.</span></span>

## <a name="support-and-training"></a><span data-ttu-id="24302-168">サポートとトレーニング</span><span class="sxs-lookup"><span data-stu-id="24302-168">Support and training</span></span>

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a><span data-ttu-id="24302-169">セルフサービス購入で購入された製品は、ユーザーの IT 部門やパートナーでサポートされますか?</span><span class="sxs-lookup"><span data-stu-id="24302-169">Are customers' IT departments or partners expected to support products bought through self-service purchase?</span></span>

<span data-ttu-id="24302-170">IT 部門やパートナーでは、セルフサービス購入で購入された製品に対するサポートは提供されません。</span><span class="sxs-lookup"><span data-stu-id="24302-170">IT departments and partners aren't expected to provide support for products bought through self-service purchase.</span></span> <span data-ttu-id="24302-171">Microsoft は、セルフサービス購入者に対して標準サポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="24302-171">Microsoft provides standard support for self-service purchasers.</span></span>

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a><span data-ttu-id="24302-172">セルフサービス購入者がサポートに問い合わせる場合、プレミア サポート インシデントが使用されますか?</span><span class="sxs-lookup"><span data-stu-id="24302-172">If a self-service purchaser calls support, does that use the customer's Premier Support incidents?</span></span>

<span data-ttu-id="24302-173">セルフサービス購入者が、セルフサービス購入のサポートを受けるためにプレミア サポート インシデントを使用することはありません。</span><span class="sxs-lookup"><span data-stu-id="24302-173">Self-service purchasers won't use a customer's Premier Support incidents for receiving support for their self-service purchases.</span></span>

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a><span data-ttu-id="24302-174">セルフサービス購入で購入した製品について、ユーザーはどのようにトレーニングを受けられますか?</span><span class="sxs-lookup"><span data-stu-id="24302-174">How are users expected to receive training on the products they buy through self-service purchase?</span></span>

<span data-ttu-id="24302-175">ユーザー向けの豊富なトレーニングが、製品 Web サイトで提供されています。</span><span class="sxs-lookup"><span data-stu-id="24302-175">Extensive training for users is provided on the product websites.</span></span> <span data-ttu-id="24302-176">これらの製品には、他のユーザーから直接回答やヒントを得るためのガイド学習、ドキュメント、サンプル、および強力なコミュニティが用意されています。</span><span class="sxs-lookup"><span data-stu-id="24302-176">The products have guided learning, documentation, samples, and strong communities to get answers and tips directly from other users.</span></span>

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a><span data-ttu-id="24302-177">ユーザーが組織を離れた場合、セルフサービス購入はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="24302-177">What happens to a self-service purchase if a user leaves the organization?</span></span>

<span data-ttu-id="24302-178">最初にセルフサービス購入製品を購入したユーザーが組織を離れた場合、有効なユーザーは、サブスクリプション期間中は引き続きその製品を完全に使用できます。</span><span class="sxs-lookup"><span data-stu-id="24302-178">If the person who originally bought the self-service purchase product leaves the organization, valid users continue to have full use of the product for the duration of the subscription.</span></span> <span data-ttu-id="24302-179">サブスクリプションは、購入者が直接キャンセルするか、管理者がカスタマー サポートを介してサブスクリプションのキャンセルを要求するまでアクティブの状態が続きます。</span><span class="sxs-lookup"><span data-stu-id="24302-179">The subscription remains active until the purchaser directly cancels it or an admin requests cancellation of the subscription through customer support.</span></span> <span data-ttu-id="24302-180">管理者は、キャンセルされたサブスクリプションのユーザーに対して、一元的に購入されたライセンスを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="24302-180">Admins may also choose to assign a centrally purchased license to users of the canceled subscription.</span></span>

## <a name="partners"></a><span data-ttu-id="24302-181">パートナー</span><span class="sxs-lookup"><span data-stu-id="24302-181">Partners</span></span>

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a><span data-ttu-id="24302-182">セルフサービス購入における Microsoft のパートナーの役割は何ですか?</span><span class="sxs-lookup"><span data-stu-id="24302-182">What's the role of Microsoft's partners in self-service purchases?</span></span>

<span data-ttu-id="24302-183">代理管理者権限を持つパートナーは、管理者と同様に、<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>でセルフサービス購入を表示できます。パートナーは、セルフサービス購入によって購入された製品を集中管理する組織をサポートします。</span><span class="sxs-lookup"><span data-stu-id="24302-183">Partners who have delegated administration privileges can see self-service purchases in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>, just like an admin. Partners can help support an organization that wants to centralize products bought through self-service purchases.</span></span> <span data-ttu-id="24302-184">また、パートナーは、セルフサービス購入の機能を拡張するためのソリューションを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="24302-184">Additionally, partners may offer solutions to extend the capabilities of a self-service purchase.</span></span>