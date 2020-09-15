---
title: セルフサービス購入についてよく寄せられる質問
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
- commerce
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
search.appverid:
- MET150
description: セルフサービス購入に関してよく寄せられる質問に対する回答を確認できます。
ms.date: 09/15/2020
ms.openlocfilehash: 81143dfe3794bc4f42bea879905bf08750f498b4
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816927"
---
# <a name="self-service-purchase-faq"></a><span data-ttu-id="5a1cc-103">セルフサービス購入についてよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="5a1cc-103">Self-service purchase FAQ</span></span>

<span data-ttu-id="5a1cc-104">セルフサービス購入により、ユーザーは新しいテクノロジを試して、より大規模な組織を最終的に利益するソリューションを開発する機会を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-104">Self-service purchase gives users a chance to try out new technologies and develop solutions that ultimately benefit their larger organizations.</span></span> <span data-ttu-id="5a1cc-105">中央の調達と IT teams は、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>を介してセルフサービス購入ソリューションを購入して展開するすべてのユーザーに対して表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-105">Central procurement and IT teams have visibility to all users who buy and deploy self-service purchase solutions through the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="5a1cc-106">管理者は、PowerShell を使用して製品ごとにセルフサービス購入を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-106">Admins can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="5a1cc-107">詳細については、「 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-107">To learn more, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

<span data-ttu-id="5a1cc-108">セルフサービス購入は、電源プラットフォーム (Power BI、電源アプリ、および電源自動化)、プロジェクト、Visio で利用できます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-108">Self-service purchase is available for Power Platform (Power BI, Power Apps, and Power Automate), Project, and Visio.</span></span>

> [!NOTE]
> <span data-ttu-id="5a1cc-109">セルフサービス購入は、インドまたは官公庁または教育機関のお客様にはご利用いただけません。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-109">Self-service purchase isn’t available in India or for government or education customers.</span></span> <span data-ttu-id="5a1cc-110">ブラジルおよびコンゴ民主共和国では、プロジェクトと Visio をセルフサービスで購入することはできません。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-110">Project and Visio are not available for self-service purchase in Brazil and the Democratic Republic of Congo.</span></span>

## <a name="making-a-self-service-purchase"></a><span data-ttu-id="5a1cc-111">セルフサービス購入の作成</span><span class="sxs-lookup"><span data-stu-id="5a1cc-111">Making a self-service purchase</span></span>

### <a name="how-does-a-customer-make-a-self-service-purchase"></a><span data-ttu-id="5a1cc-112">お客様はどのようにしてセルフサービス購入を行いますか?</span><span class="sxs-lookup"><span data-stu-id="5a1cc-112">How does a customer make a self-service purchase?</span></span>

<span data-ttu-id="5a1cc-113">お客様は、製品の web サイトから、またはアプリ内購入プロンプトからセルフサービス購入を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-113">Customers can make a self-service purchase online from the product websites or from in-app purchase prompts.</span></span> <span data-ttu-id="5a1cc-114">お客様は、既存の Azure Active Directory (AD) テナント内のユーザーであることを確認するために、最初にメールアドレスを入力するよう求められています。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-114">Customers are first asked to enter an email address to ensure that they're a user in an existing Azure Active Directory (AD) tenant.</span></span> <span data-ttu-id="5a1cc-115">次に、Azure AD 資格情報を使用してサインインするように指示されています。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-115">Next, they're directed to sign in by using their Azure AD credentials.</span></span> <span data-ttu-id="5a1cc-116">サインインした後、お客様は購入するサブスクリプションの数を選択し、クレジットカードの支払いを指定するように求められます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-116">After signing in, the customer is asked to select how many subscriptions they want to buy, and to provide credit card payment.</span></span> <span data-ttu-id="5a1cc-117">購入が完了すると、サブスクリプションの使用を開始できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-117">When the purchase is complete, they can start using their subscription.</span></span> <span data-ttu-id="5a1cc-118">買い手は、組織内の他のユーザーにライセンスを製品に割り当てることができる、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a> の制限されたビューにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-118">The purchaser has access to a limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> where they can assign licenses to the product to other people in their organization.</span></span>

### <a name="what-are-the-payment-options-for-self-service-purchases"></a><span data-ttu-id="5a1cc-119">セルフサービス購入の支払いオプションとは</span><span class="sxs-lookup"><span data-stu-id="5a1cc-119">What are the payment options for self-service purchases?</span></span>

<span data-ttu-id="5a1cc-120">現時点では、クレジットカードのみが利用可能な支払い方法です。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-120">Currently, credit card is the only available payment method.</span></span> <span data-ttu-id="5a1cc-121">請求による支払いはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-121">Payment through invoicing isn't supported.</span></span>

### <a name="who-can-buy-through-self-service-purchase"></a><span data-ttu-id="5a1cc-122">セルフサービス購入で購入できるユーザー</span><span class="sxs-lookup"><span data-stu-id="5a1cc-122">Who can buy through self-service purchase?</span></span>

<span data-ttu-id="5a1cc-123">管理された Azure AD テナントのゲスト以外のユーザーアカウントを持つユーザーは、セルフサービス購入を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-123">Any user with a non-guest user account in a managed Azure AD tenant can make a self-service purchase.</span></span> <span data-ttu-id="5a1cc-124">セルフサービス購入は、官公庁または教育機関のテナントでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-124">Self-service purchasing isn’t available to tenants that are government or education organizations.</span></span> <span data-ttu-id="5a1cc-125">これが組織に当てはまる場合は、セルフサービス購入を制御するために追加の操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-125">If this applies to your organization, then no additional action is required to control self-service purchase.</span></span>

<span data-ttu-id="5a1cc-126">セルフサービス購入の対象になっていない組織または市場のユーザーには、IT 管理者に連絡するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-126">Users in organizations or markets who aren’t eligible for self-service purchase see a message asking them to contact their IT admin.</span></span>

### <a name="can-guest-users-buy-through-self-service-purchase"></a><span data-ttu-id="5a1cc-127">ゲストユーザーはセルフサービス購入で購入できますか?</span><span class="sxs-lookup"><span data-stu-id="5a1cc-127">Can guest users buy through self-service purchase?</span></span>

<span data-ttu-id="5a1cc-128">いいえ、ゲストユーザーはゲストになっているテナントでセルフサービス購入を完了できません。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-128">No, guest users can’t complete a self-service purchase in a tenant in which they're a guest.</span></span>

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a><span data-ttu-id="5a1cc-129">オンプレミスの Active Directory からのユーザーの同期は、セルフサービスの購入で行うことができますか。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-129">Can users synced from an on-premises Active Directory buy through self-service purchase?</span></span>

<span data-ttu-id="5a1cc-130">ユーザーが適格な Azure AD テナントにアクティブなユーザーアカウントを持っている場合は、セルフサービス購入を完了できます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-130">If a user has an active user account in an eligible Azure AD tenant, they can complete a self-service purchase.</span></span>

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a><span data-ttu-id="5a1cc-131">セルフサービスの purchasers にライセンスを割り当てることができるユーザー</span><span class="sxs-lookup"><span data-stu-id="5a1cc-131">Who can self-service purchasers assign licenses to?</span></span>

<span data-ttu-id="5a1cc-132">セルフサービス purchasers では、同じ Azure AD テナント内のユーザーにのみライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-132">Self-service purchasers can only assign licenses to users in the same Azure AD tenant.</span></span> <span data-ttu-id="5a1cc-133">購入者は、ライセンスを割り当てるために <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a> の限定されたビューにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-133">The purchaser has access to a limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> to assign licenses.</span></span> <span data-ttu-id="5a1cc-134">Purchasers は、セルフサービス購入で購入した製品にライセンスを割り当てることができ、同じ Azure AD テナント内のユーザーに対してのみライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-134">Purchasers can assign licenses to those products that they've bought through self-service purchase, and can only assign those licenses to users in the same Azure AD tenant.</span></span>

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a><span data-ttu-id="5a1cc-135">セルフサービスの購入者は購入を確認して管理しますか?</span><span class="sxs-lookup"><span data-stu-id="5a1cc-135">Where does the self-service purchaser see and manage their purchases?</span></span>

<span data-ttu-id="5a1cc-136">セルフサービス purchasers では、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>の限定されたビューで購入を管理できます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-136">Self-service purchasers can manage their purchases in the limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="5a1cc-137">Purchasers は、常に、Microsoft 365 および Dynamics online のすべてのアプリに組み込まれているアプリ起動ツールの **管理者** タイルから管理センターにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-137">Purchasers can always get to the admin center from the **Admin** tile in the app launcher built into all Microsoft 365 and Dynamics online apps.</span></span> <span data-ttu-id="5a1cc-138">Purchasers では、作成した購入を表示したり、同じサービスに対して追加のサブスクリプションを購入したり、それらのサブスクリプションのライセンスを組織内の他のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-138">Purchasers can view the purchases they've made, buy additional subscriptions to the same service, and assign licenses for those subscriptions to other users in their organization.</span></span> <span data-ttu-id="5a1cc-139">また、purchasers は、請求書の表示と支払い、支払い方法の更新、およびサブスクリプションのキャンセルを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-139">Additionally, purchasers can view and pay their bill, update their payment method, and cancel their subscription.</span></span>

## <a name="pricing"></a><span data-ttu-id="5a1cc-140">価格設定</span><span class="sxs-lookup"><span data-stu-id="5a1cc-140">Pricing</span></span>

### <a name="what-is-the-pricing-for-self-service-purchases"></a><span data-ttu-id="5a1cc-141">セルフサービス購入の価格設定について</span><span class="sxs-lookup"><span data-stu-id="5a1cc-141">What is the pricing for self-service purchases?</span></span>

<span data-ttu-id="5a1cc-142">セルフサービス購入の各製品の価格は、Microsoft の web サイトでご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-142">Pricing for each of the products for self-service purchase is available on the Microsoft website.</span></span> <span data-ttu-id="5a1cc-143">また、ユーザーがセルフサービス購入を行うときに、支払いの処理の一部として価格も表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-143">Prices are also displayed as part of the checkout experience when users make a self-service purchase.</span></span> <span data-ttu-id="5a1cc-144">これらの価格は、パートナーによって集中購入または料金を提示する際に組織が支払う価格とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-144">These prices may differ from the prices an organization pays when making central purchases or prices offered through a partner.</span></span>

### <a name="who-is-responsible-for-payment"></a><span data-ttu-id="5a1cc-145">支払いの責任者</span><span class="sxs-lookup"><span data-stu-id="5a1cc-145">Who is responsible for payment?</span></span>

<span data-ttu-id="5a1cc-146">セルフサービス購入によってサブスクリプションを購入するユーザーとは、請求先の人物、および購入の諸条件と価格に基づいて支払いの責任者をいいます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-146">The person who buys the subscription through self-service purchase is the person who is billed and who is responsible for payment based on the terms and pricing of the purchase.</span></span>

## <a name="admin-capabilities"></a><span data-ttu-id="5a1cc-147">管理機能</span><span class="sxs-lookup"><span data-stu-id="5a1cc-147">Admin capabilities</span></span>

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a><span data-ttu-id="5a1cc-148">セルフサービス購入における管理者の権限を教えてください</span><span class="sxs-lookup"><span data-stu-id="5a1cc-148">What capabilities does an admin have for self-service purchases?</span></span>

<span data-ttu-id="5a1cc-149">管理者は、組織内で行われたすべてのセルフサービスの購入を <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>で確認できます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-149">Admins can view all self-service purchases made in their organization in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="5a1cc-150">これらのユーザーは、製品、購入者名、購入したサブスクリプション、有効期限、注文履歴、購入価格、および割り当てられたユーザーを各セルフサービス購入に対して確認できます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-150">They can see the product, purchaser name, subscriptions purchased, expiry date, order history, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="5a1cc-151">電源プラットフォーム管理センターでは、管理者はセルフサービス購入容量を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-151">In the Power Platform Admin Center, admins can also view self-service purchases capacity.</span></span> <span data-ttu-id="5a1cc-152">組織に必要な場合、管理者は、PowerShell を使用して製品ごとにセルフサービス購入を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-152">If required for their organization, admins can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="5a1cc-153">管理者は、セルフサービス購入された製品と一元的に購入された製品に対して、同じデータ管理およびアクセスポリシーを有します。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-153">Admins have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="5a1cc-154">管理者は、組織内のユーザーがセルフサービス購入を行うことができるかどうかを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-154">Admins can also control whether users in their organization can make self-service purchases.</span></span> <span data-ttu-id="5a1cc-155">詳細については、「 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-155">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a><span data-ttu-id="5a1cc-156">セルフサービス購入を有効にすることによって、Microsoft はデータガバナンスとコンプライアンスをどのように重視していますか?</span><span class="sxs-lookup"><span data-stu-id="5a1cc-156">How is Microsoft respecting data governance and compliance by enabling self-service purchase?</span></span>

<span data-ttu-id="5a1cc-157">管理者は、データガバナンスとコンプライアンスの要件に基づいて、テナント内で使用可能なサービスと製品を制御します。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-157">Admins maintain control over what services and products are available within their tenant based on their data governance and compliance requirements.</span></span> <span data-ttu-id="5a1cc-158">組織で有効になっているすべてのデータ管理およびアクセスポリシーは、利用可能なセルフサービス購入サービスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-158">All data management and access policies that your organization turned on apply to available self-service purchased services.</span></span>

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a><span data-ttu-id="5a1cc-159">セルフサービス購入から作成された製品データの所有者</span><span class="sxs-lookup"><span data-stu-id="5a1cc-159">Who owns the product data created from self-service purchases?</span></span>

<span data-ttu-id="5a1cc-160">セルフサービス購入で購入した製品から作成されたデータは、組織によって所有および制御されます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-160">Data created from products bought through self-service purchase is owned and controlled by the organization.</span></span>

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a><span data-ttu-id="5a1cc-161">セルフサービス購入で行われた購入を一元管理するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="5a1cc-161">How do I centralize the purchases made through self-service purchase?</span></span>

<span data-ttu-id="5a1cc-162">管理者は既存のライセンスを割り当てることも、セルフサービス購入製品の追加サブスクリプションを購入することもできます。これには、既存の契約と、セルフサービス購入に割り当てられたユーザーの料金があります。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-162">Admins can assign existing licenses or buy additional subscriptions of self-service purchase products through existing agreements and pricing for users assigned to self-service purchases.</span></span> <span data-ttu-id="5a1cc-163">これらの集中的に購入したライセンスを割り当てた後、管理者は purchasers に既存のサブスクリプションをキャンセルするよう要求できます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-163">After assigning these centrally purchased licenses, admins can then request that the purchasers cancel their existing subscriptions.</span></span>

### <a name="where-does-the-admin-see-self-service-purchases"></a><span data-ttu-id="5a1cc-164">管理者はどこにセルフサービス購入を表示しますか?</span><span class="sxs-lookup"><span data-stu-id="5a1cc-164">Where does the admin see self-service purchases?</span></span>

<span data-ttu-id="5a1cc-165">グローバルおよび課金管理者は、 **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>で**製品**を請求する際に、セルフサービス購入により購入したサブスクリプションを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-165">Global and billing admins can see subscriptions bought through self-service purchase in **Billing** > **Your products** in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="5a1cc-166">[製品] リストにフィルターを適用して、中央の調達で購入されたサブスクリプションのみを表示したり、セルフサービス購入で購入したサブスクリプションを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-166">They can filter the products list to only show the subscriptions purchased through central procurement, or to include subscriptions bought through self-service purchase.</span></span>

<span data-ttu-id="5a1cc-167">管理者は、製品、買い手名、購入したサブスクリプション、有効期限、注文履歴、購入価格、割り当てられたユーザーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-167">Admins can see the product, purchaser name, subscription purchased, expiry date, order history, the purchase price, and assigned users.</span></span>

## <a name="support-and-training"></a><span data-ttu-id="5a1cc-168">サポートとトレーニング</span><span class="sxs-lookup"><span data-stu-id="5a1cc-168">Support and training</span></span>

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a><span data-ttu-id="5a1cc-169">お客様の IT 部門やパートナーは、セルフサービス購入によって購入された製品をサポートすることを期待していますか。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-169">Are customers' IT departments or partners expected to support products bought through self-service purchase?</span></span>

<span data-ttu-id="5a1cc-170">IT 部門およびパートナーは、セルフサービス購入を通じて購入された製品に対するサポートを提供することを期待していません。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-170">IT departments and partners aren't expected to provide support for products bought through self-service purchase.</span></span> <span data-ttu-id="5a1cc-171">Microsoft は、セルフサービスの purchasers の標準サポートを提供しています。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-171">Microsoft provides standard support for self-service purchasers.</span></span>

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a><span data-ttu-id="5a1cc-172">セルフサービスの購入者がサポートに電話をかける場合、お客様のプレミアサポートインシデントを使用していますか?</span><span class="sxs-lookup"><span data-stu-id="5a1cc-172">If a self-service purchaser calls support, does that use the customer's Premier Support incidents?</span></span>

<span data-ttu-id="5a1cc-173">セルフサービス purchasers では、お客様のプレミアサポートインシデントを使用してセルフサービス購入のサポートを受けることはできません。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-173">Self-service purchasers won't use a customer's Premier Support incidents for receiving support for their self-service purchases.</span></span>

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a><span data-ttu-id="5a1cc-174">セルフサービス購入で購入した製品について、ユーザーはどのようにトレーニングを受けられるようになりますか?</span><span class="sxs-lookup"><span data-stu-id="5a1cc-174">How are users expected to receive training on the products they buy through self-service purchase?</span></span>

<span data-ttu-id="5a1cc-175">ユーザー向けの豊富なトレーニングは、製品 web サイトで提供されています。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-175">Extensive training for users is provided on the product websites.</span></span> <span data-ttu-id="5a1cc-176">これらの製品には、他のユーザーから直接回答やヒントを得るためのガイド学習、ドキュメント、サンプル、および強力なコミュニティが用意されています。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-176">The products have guided learning, documentation, samples, and strong communities to get answers and tips directly from other users.</span></span>

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a><span data-ttu-id="5a1cc-177">ユーザーが組織を離れた場合、セルフサービス購入はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="5a1cc-177">What happens to a self-service purchase if a user leaves the organization?</span></span>

<span data-ttu-id="5a1cc-178">最初にセルフサービス購入製品を購入したユーザーが組織を離れた場合、有効なユーザーは、サブスクリプションの期間中は製品を引き続き完全に使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-178">If the person who originally bought the self-service purchase product leaves the organization, valid users continue to have full use of the product for the duration of the subscription.</span></span> <span data-ttu-id="5a1cc-179">サブスクリプションは、購入者が直接取り消すか、カスタマーサポートによってサブスクリプションのキャンセルを要求するまでアクティブなままになります。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-179">The subscription remains active until the purchaser directly cancels it or an admin requests cancellation of the subscription through customer support.</span></span> <span data-ttu-id="5a1cc-180">管理者は、解約されたサブスクリプションのユーザーに対して、集中購入したライセンスを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-180">Admins may also choose to assign a centrally purchased license to users of the canceled subscription.</span></span>

## <a name="partners"></a><span data-ttu-id="5a1cc-181">パートナー</span><span class="sxs-lookup"><span data-stu-id="5a1cc-181">Partners</span></span>

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a><span data-ttu-id="5a1cc-182">セルフサービス購入における Microsoft のパートナーの役割</span><span class="sxs-lookup"><span data-stu-id="5a1cc-182">What's the role of Microsoft's partners in self-service purchases?</span></span>

<span data-ttu-id="5a1cc-183">管理権限を委任されたパートナーは、管理者と同様に、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>でセルフサービス購入を表示できます。パートナーは、セルフサービス購入によって購入された製品を集中管理する組織のサポートに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-183">Partners who have delegated administration privileges can see self-service purchases in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>, just like an admin. Partners can help support an organization that wants to centralize products bought through self-service purchases.</span></span> <span data-ttu-id="5a1cc-184">また、パートナーは、セルフサービス購入の機能を拡張するためのソリューションを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="5a1cc-184">Additionally, partners may offer solutions to extend the capabilities of a self-service purchase.</span></span>