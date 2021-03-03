---
title: エンタープライズ向け Microsoft 365 のテナント管理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- m365solution-overview
- tenant-management
ms.custom:
- Ent_Solutions
description: Microsoft 365 テナントの計画、展開、および継続的な運用の概要。
ms.openlocfilehash: 42bde00fbd4ddc1cf92236f099a22b2260dbb980
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2021
ms.locfileid: "50405680"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a><span data-ttu-id="ba85f-103">エンタープライズ向け Microsoft 365 のテナント管理</span><span class="sxs-lookup"><span data-stu-id="ba85f-103">Tenant management for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="ba85f-104">クラウド コンピューティングを使用して組織のデジタル変換へのパスを作成するには、作業員が生産性、コラボレーション、パフォーマンス、プライバシー、コンプライアンス、セキュリティに頼れる基盤が必要です。</span><span class="sxs-lookup"><span data-stu-id="ba85f-104">Creating a path to your organization's digital transformation with cloud computing requires a firm foundation upon which your workers can rely for productivity, collaboration, performance, privacy, compliance, and security.</span></span>

<span data-ttu-id="ba85f-105">Microsoft 365 テナントの正しい構成により、その基盤が提供され、従業員は作業の完了に集中し、IT 部門は追加のビジネス価値を提供するエンドツーエンドのソリューションに集中できます。</span><span class="sxs-lookup"><span data-stu-id="ba85f-105">Correct configuration of your Microsoft 365 tenants provides that foundation, leaving your workers to focus on getting their work done and your IT department to focus on end-to-end solutions that provide additional business value.</span></span> 

<span data-ttu-id="ba85f-106">このソリューションでは、次の手順で、その基盤の構成を説明します。</span><span class="sxs-lookup"><span data-stu-id="ba85f-106">This solution takes you through the configuration of that foundation in these steps:</span></span>

1. <span data-ttu-id="ba85f-107">テナントを決定する</span><span class="sxs-lookup"><span data-stu-id="ba85f-107">Determine your tenants</span></span>
2. <span data-ttu-id="ba85f-108">ネットワークを最適化する</span><span class="sxs-lookup"><span data-stu-id="ba85f-108">Optimize your networking</span></span>
3. <span data-ttu-id="ba85f-109">ID を同期し、セキュリティで保護されたサインインを適用する</span><span class="sxs-lookup"><span data-stu-id="ba85f-109">Synchronize your identities and enforce secure sign-ins</span></span>
4. <span data-ttu-id="ba85f-110">Windows デバイス、Office、オンプレミスのサーバーとデータOffice移行する</span><span class="sxs-lookup"><span data-stu-id="ba85f-110">Migrate your Windows devices, Office clients, and on-premises Office servers and data</span></span>
5. <span data-ttu-id="ba85f-111">デバイスとアプリの管理を展開する</span><span class="sxs-lookup"><span data-stu-id="ba85f-111">Deploy device and app management</span></span>

<span data-ttu-id="ba85f-112">しかし、最初に、テナントとは何か、また、堅固な基盤を提供するテナントの外観を理解するために少し時間を取って説明します。</span><span class="sxs-lookup"><span data-stu-id="ba85f-112">But first, let's take a moment to understand what a tenant is and what a tenant that provides a firm foundation looks like.</span></span>

## <a name="a-microsoft-365-tenant-defined"></a><span data-ttu-id="ba85f-113">定義された Microsoft 365 テナント</span><span class="sxs-lookup"><span data-stu-id="ba85f-113">A Microsoft 365 tenant defined</span></span>

<span data-ttu-id="ba85f-114">Microsoft 365 テナントは、Microsoft 365 のサービスと、ヨーロッパや北アメリカなどの特定の既定の場所に格納されている組織データの専用インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="ba85f-114">A Microsoft 365 tenant is a dedicated instance of the services of Microsoft 365 and your organization data stored within a specific default location, such as Europe or North America.</span></span> <span data-ttu-id="ba85f-115">この場所は、組織のテナントを作成するときに指定されます。</span><span class="sxs-lookup"><span data-stu-id="ba85f-115">This location is specified when you create the tenant for your organization.</span></span> <span data-ttu-id="ba85f-116">各 Microsoft 365 テナントは、他のすべての Microsoft 365 テナントとは異なる、固有のテナントです。</span><span class="sxs-lookup"><span data-stu-id="ba85f-116">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="ba85f-117">Microsoft 365 E3 や E5 など、Microsoft から 1 つ以上の製品を購入する場合は、Microsoft 365 テナントを作成し、それぞれのライセンスのセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="ba85f-117">You create a Microsoft 365 tenant when you purchase one or more products from Microsoft, such as Microsoft 365 E3 or E5, and a set of licenses for each.</span></span>

<span data-ttu-id="ba85f-118">Microsoft 365 テナントには Azure Active Directory (Azure AD) テナントも含まれています。これは、ユーザー アカウント、グループ、その他のオブジェクト用の Azure AD の専用インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="ba85f-118">Your Microsoft 365 tenant also includes an Azure Active Directory (Azure AD) tenant, which is a dedicated instance of Azure AD for user accounts, groups, and other objects.</span></span> <span data-ttu-id="ba85f-119">各 Azure ADテナントは、個別で一意であり、他のすべての Azure テナントとADされます。</span><span class="sxs-lookup"><span data-stu-id="ba85f-119">Each Azure AD tenant is distinct, unique, and separate from all other Azure AD tenants.</span></span> <span data-ttu-id="ba85f-120">組織では、Azure サブスクリプションでセットアップできる複数の Azure AD テナントを使用できますが、Microsoft 365 テナントは、テナントの作成時に作成された Azure AD テナントを 1 つのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ba85f-120">While your organization can have multiple Azure AD tenants that you can set up with Azure subscriptions, Microsoft 365 tenants can only use a single Azure AD tenant, the one that was created when you created the tenant.</span></span> 

<span data-ttu-id="ba85f-121">次に例を示します：</span><span class="sxs-lookup"><span data-stu-id="ba85f-121">Here is an example:</span></span>

![Azure サービス テナントを持つ Microsoft 365 テナントAD例](../media/tenant-management-overview/tenant-management-example-tenant.png)

<span data-ttu-id="ba85f-123">*テナント管理* は、Microsoft 365 テナントの計画、展開、および継続的な操作です。</span><span class="sxs-lookup"><span data-stu-id="ba85f-123">*Tenant management* is the planning, deployment, and ongoing operation of your Microsoft 365 tenants.</span></span> 

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a><span data-ttu-id="ba85f-124">十分に設計され、運用されているテナントの属性</span><span class="sxs-lookup"><span data-stu-id="ba85f-124">Attributes of a well-designed and operating tenant</span></span>

<span data-ttu-id="ba85f-125">テナントの正しい名前と場所を超えて、Microsoft Teams や Exchange Online などのクラウド生産性アプリに関するユーザー エクスペリエンスが効果的で安全で、パフォーマンスを高めるには、計画、展開、管理のための追加の要素があります。 &mdash; &mdash;</span><span class="sxs-lookup"><span data-stu-id="ba85f-125">Beyond the correct name and location for your tenant, there are additional elements to plan, deploy, and manage to ensure that your user experiences with cloud productivity apps&mdash;such as Microsoft Teams and Exchange Online&mdash;are effective, secure, and performant.</span></span>

<span data-ttu-id="ba85f-126">要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ba85f-126">Here are the elements:</span></span>

- <span data-ttu-id="ba85f-127">製品 (サブスクリプション) とライセンスの正しいセットがあります。</span><span class="sxs-lookup"><span data-stu-id="ba85f-127">You have the correct set of products (subscriptions) and licenses.</span></span>
  - <span data-ttu-id="ba85f-128">一連の製品は、ビジネス、IT、およびセキュリティのニーズに一致します。</span><span class="sxs-lookup"><span data-stu-id="ba85f-128">The set of products match your business, IT, and security needs.</span></span>
  - <span data-ttu-id="ba85f-129">従業員に対して適切な数のライセンスと、スタッフの予想される変更点があります。</span><span class="sxs-lookup"><span data-stu-id="ba85f-129">There is an adequate number of licenses for your workers and anticipated changes in staffing.</span></span>
- <span data-ttu-id="ba85f-130">ネットワークの場合:</span><span class="sxs-lookup"><span data-stu-id="ba85f-130">For networking:</span></span>
  - <span data-ttu-id="ba85f-131">正しい名前をDNS ドメインしました。</span><span class="sxs-lookup"><span data-stu-id="ba85f-131">You have configured the correct DNS domain names.</span></span>
  - <span data-ttu-id="ba85f-132">エンタープライズ ネットワークの場合、オンサイト ワーカー向けに Microsoft ネットワークへのネットワーク トラフィックを最適化しました。</span><span class="sxs-lookup"><span data-stu-id="ba85f-132">For enterprise networks, you have optimized network traffic to the Microsoft network for onsite workers.</span></span>
  - <span data-ttu-id="ba85f-133">VPN クライアントを使用しているリモート ワーカーのネットワーク トラフィックを最適化しました。</span><span class="sxs-lookup"><span data-stu-id="ba85f-133">You have optimized network traffic for remote workers who are using a VPN client.</span></span>
- <span data-ttu-id="ba85f-134">Active Directory ドメイン サービス (DS) アカウント、AD、その他のオブジェクトを同期しました。</span><span class="sxs-lookup"><span data-stu-id="ba85f-134">You have synchronized your Active Directory Domain Services (AD DS) accounts, groups, and other objects.</span></span>
  - <span data-ttu-id="ba85f-135">Azure ADテナント アカウントは、電子メール アドレスの正しい DNS ドメインを使用して Exchange Online メールボックスにマップされます。</span><span class="sxs-lookup"><span data-stu-id="ba85f-135">Your Azure AD tenant accounts are mapped to Exchange Online mailboxes with the correct DNS domains for email addresses.</span></span>
  - <span data-ttu-id="ba85f-136">ユーザー アカウントには、正しい購入済み製品 (Microsoft 365 E3 や E5 など) から適切なライセンスが割り当てされています。</span><span class="sxs-lookup"><span data-stu-id="ba85f-136">Your user accounts have been assigned the correct licenses from the correct purchased products (such as Microsoft 365 E3 or E5).</span></span>
- <span data-ttu-id="ba85f-137">強力な ID とアクセス管理を構成しました。</span><span class="sxs-lookup"><span data-stu-id="ba85f-137">You have configured strong identity and access management.</span></span>
  - <span data-ttu-id="ba85f-138">パスワードレス認証または多要素認証 (MFA) によるセキュリティで保護されたユーザー サインインが必要です。</span><span class="sxs-lookup"><span data-stu-id="ba85f-138">You are requiring secure user sign-in with passwordless or multi-factor authentication (MFA).</span></span>
  - <span data-ttu-id="ba85f-139">より高いレベルのセキュリティのためにサインイン要件と制限を適用する条件付きアクセス ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="ba85f-139">You have Conditional Access policies that enforce sign-in requirements and restrictions for higher levels of security.</span></span>
- <span data-ttu-id="ba85f-140">オンプレミスのサーバー Officeデータはクラウド アプリに移行しているか、ハイブリッド構成で使用されています。</span><span class="sxs-lookup"><span data-stu-id="ba85f-140">On-premises Office servers and their data have been migrated to cloud apps or are being used in a hybrid configuration.</span></span>
- <span data-ttu-id="ba85f-141">Intune または Microsoft 365 に組み込んだ Basic Mobility and Security を使用してデバイス管理を行っています。</span><span class="sxs-lookup"><span data-stu-id="ba85f-141">You are doing device management with Intune or Basic Mobility and Security built into Microsoft 365.</span></span>
  - <span data-ttu-id="ba85f-142">組織が所有するデバイスが登録され、管理されます。</span><span class="sxs-lookup"><span data-stu-id="ba85f-142">Your organization-owned devices are enrolled and managed.</span></span>
  - <span data-ttu-id="ba85f-143">個人用デバイス用のアプリは管理されます。</span><span class="sxs-lookup"><span data-stu-id="ba85f-143">The apps for personal devices are managed.</span></span>

<span data-ttu-id="ba85f-144">これらすべての要素が配置された Microsoft 365 テナントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ba85f-144">Here is an example of a Microsoft 365 tenant with all these elements in place.</span></span>

![Microsoft 365 テナントの例](../media/tenant-management-overview/tenant-management-tenant-config.png)

<span data-ttu-id="ba85f-146">この図では、Microsoft 365 テナントには次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ba85f-146">In this illustration, the Microsoft 365 tenant includes:</span></span>

- <span data-ttu-id="ba85f-147">Microsoft 365 E3 および E5 の製品とライセンス。</span><span class="sxs-lookup"><span data-stu-id="ba85f-147">Products and licenses for Microsoft 365 E3 and E5.</span></span>
- <span data-ttu-id="ba85f-148">Microsoft 365 生産性アプリ。</span><span class="sxs-lookup"><span data-stu-id="ba85f-148">Microsoft 365 productivity apps.</span></span>
- <span data-ttu-id="ba85f-149">Intune には、登録済みデバイスとデバイスポリシーとアプリケーション ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="ba85f-149">Intune with enrolled devices and device and application policies.</span></span>
- <span data-ttu-id="ba85f-150">ユーザー アカウントAD (グループなどのディレクトリ オブジェクトは表示されません)、ドメイン、条件付きアクセス ポリシーが同期されている Azure テナント。</span><span class="sxs-lookup"><span data-stu-id="ba85f-150">An Azure AD tenant that has synchronized user account (groups and other directory objects are not shown), domains, and Conditional Access policies.</span></span>

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a><span data-ttu-id="ba85f-151">エンタープライズ向け Microsoft 365 のテナント機能</span><span class="sxs-lookup"><span data-stu-id="ba85f-151">Tenant capabilities for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="ba85f-152">次のセクションと表は、このソリューションの手順の主な機能とライセンスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="ba85f-152">The following sections and table list the key capabilities and licensing for the steps in this solution.</span></span>

### <a name="tenant"></a><span data-ttu-id="ba85f-153">テナント</span><span class="sxs-lookup"><span data-stu-id="ba85f-153">Tenant</span></span>

| <span data-ttu-id="ba85f-154">機能</span><span class="sxs-lookup"><span data-stu-id="ba85f-154">Capability or feature</span></span> | <span data-ttu-id="ba85f-155">説明</span><span class="sxs-lookup"><span data-stu-id="ba85f-155">Description</span></span> | <span data-ttu-id="ba85f-156">ライセンス</span><span class="sxs-lookup"><span data-stu-id="ba85f-156">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="ba85f-157">複数のテナント</span><span class="sxs-lookup"><span data-stu-id="ba85f-157">Multiple tenants</span></span> | <span data-ttu-id="ba85f-158">各 Microsoft 365 テナントは、他のすべての Microsoft 365 テナントとは異なる、固有のテナントです。</span><span class="sxs-lookup"><span data-stu-id="ba85f-158">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="ba85f-159">複数のテナントがある場合、それらを管理し、ユーザーにサービスを提供する際には、制限と追加の考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="ba85f-159">With multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span> | <span data-ttu-id="ba85f-160">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="ba85f-160">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="ba85f-161">テナント間でのメールボックスの移行</span><span class="sxs-lookup"><span data-stu-id="ba85f-161">Cross-tenant mailbox migration</span></span> | <span data-ttu-id="ba85f-162">テナント管理者は、オンプレミス システムで最小限のインフラストラクチャ依存関係を持つテナント間でメールボックスを移動できます。</span><span class="sxs-lookup"><span data-stu-id="ba85f-162">Tenant administrators can move mailboxes between tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="ba85f-163">これにより、オフボードメールボックスとオンボードメールボックスが不要になります。</span><span class="sxs-lookup"><span data-stu-id="ba85f-163">This removes the need to off-board and onboard mailboxes.</span></span> | <span data-ttu-id="ba85f-164">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="ba85f-164">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="ba85f-165">Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="ba85f-165">Multi-Geo</span></span> | <span data-ttu-id="ba85f-166">テナントは、データ常駐の要件を満たすために選択した他のデータセンターの地理的な場所にデータを保存できます。</span><span class="sxs-lookup"><span data-stu-id="ba85f-166">Your tenant can store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements.</span></span> | <span data-ttu-id="ba85f-167">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="ba85f-167">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="ba85f-168">コア データを新しいデータセンター geo に移動する</span><span class="sxs-lookup"><span data-stu-id="ba85f-168">Move core data to a new datacenter geo</span></span> | <span data-ttu-id="ba85f-169">Microsoft が追加の容量とコンピューティング リソース用に新しいデータセンター geo を追加すると、主要な顧客データに対する地域内データ常駐のデータセンター geo の移動を要求できます。</span><span class="sxs-lookup"><span data-stu-id="ba85f-169">As Microsoft adds new datacenter geos for additional capacity and compute resources, you can request a datacenter geo move for in-geo data residency for your core customer data.</span></span> | <span data-ttu-id="ba85f-170">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="ba85f-170">Microsoft 365 E3 or E5</span></span> | 
||||

### <a name="networking"></a><span data-ttu-id="ba85f-171">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="ba85f-171">Networking</span></span>

| <span data-ttu-id="ba85f-172">機能</span><span class="sxs-lookup"><span data-stu-id="ba85f-172">Capability or feature</span></span> | <span data-ttu-id="ba85f-173">説明</span><span class="sxs-lookup"><span data-stu-id="ba85f-173">Description</span></span> | <span data-ttu-id="ba85f-174">ライセンス</span><span class="sxs-lookup"><span data-stu-id="ba85f-174">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="ba85f-175">ネットワークインサイト</span><span class="sxs-lookup"><span data-stu-id="ba85f-175">Network Insights</span></span> | <span data-ttu-id="ba85f-176">Microsoft 365 テナントから収集されたネットワーク パフォーマンス指標は、オフィスの場所のネットワーク境界を設計するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ba85f-176">Network performance metrics collected from your Microsoft 365 tenant to help you design network perimeters for your office locations.</span></span> | <span data-ttu-id="ba85f-177">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="ba85f-177">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="ba85f-178">エンドポイントの更新を自動化する</span><span class="sxs-lookup"><span data-stu-id="ba85f-178">Automate endpoint updates</span></span> | <span data-ttu-id="ba85f-179">クライアント PAC ファイルとネットワーク デバイスとサービス内の Microsoft 365 エンドポイントの構成と継続的な更新を自動化します。</span><span class="sxs-lookup"><span data-stu-id="ba85f-179">Automate the configuration and ongoing updates for Microsoft 365 endpoints in your client PAC files and network devices and services.</span></span> | <span data-ttu-id="ba85f-180">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="ba85f-180">Microsoft 365 E3 or E5</span></span> | 
||||

### <a name="identity"></a><span data-ttu-id="ba85f-181">ID</span><span class="sxs-lookup"><span data-stu-id="ba85f-181">Identity</span></span>

| <span data-ttu-id="ba85f-182">機能</span><span class="sxs-lookup"><span data-stu-id="ba85f-182">Capability or feature</span></span> | <span data-ttu-id="ba85f-183">説明</span><span class="sxs-lookup"><span data-stu-id="ba85f-183">Description</span></span> | <span data-ttu-id="ba85f-184">ライセンス</span><span class="sxs-lookup"><span data-stu-id="ba85f-184">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="ba85f-185">オンプレミスの Active Directory ドメイン サービス (AD DS) を Azure ドメイン テナントADする</span><span class="sxs-lookup"><span data-stu-id="ba85f-185">Synchronize on-premises Active Directory Domain Services (AD DS) with your Azure AD tenant</span></span>    | <span data-ttu-id="ba85f-186">ユーザー アカウント、グループ、その他のオブジェクトのオンプレミス ID プロバイダーを活用します。</span><span class="sxs-lookup"><span data-stu-id="ba85f-186">Leverage your on-premises identity provider for user accounts, groups, and other objects.</span></span> | <span data-ttu-id="ba85f-187">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="ba85f-187">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="ba85f-188">セキュリティの既定値が適用されている MFA</span><span class="sxs-lookup"><span data-stu-id="ba85f-188">MFA enforced with security defaults</span></span>   | <span data-ttu-id="ba85f-189">サインインには、2 つ目の認証形式を要求することで、ID とデバイスを侵害から保護します。セキュリティの既定値では、すべてのユーザー アカウントに MFA が必要です。</span><span class="sxs-lookup"><span data-stu-id="ba85f-189">Protect against compromised identities and devices by requiring a second form of authentication for sign-ins. Security defaults requires MFA for all user accounts.</span></span>   | <span data-ttu-id="ba85f-190">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="ba85f-190">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="ba85f-191">条件付きアクセスが適用されている MFA</span><span class="sxs-lookup"><span data-stu-id="ba85f-191">MFA enforced with Conditional Access</span></span>| <span data-ttu-id="ba85f-192">条件付きアクセス ポリシーを使用してサインインの属性に基づいて MFA を要求します。</span><span class="sxs-lookup"><span data-stu-id="ba85f-192">Require MFA based on the attributes of the sign-in with Conditional Access policies.</span></span>    | <span data-ttu-id="ba85f-193">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="ba85f-193">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="ba85f-194">リスクベースの条件付きアクセスが適用されている MFA</span><span class="sxs-lookup"><span data-stu-id="ba85f-194">MFA enforced with risk-based Conditional Access</span></span>   | <span data-ttu-id="ba85f-195">ユーザーが Microsoft Defender for Identity でサインインするリスクに基づいて MFA を要求します。</span><span class="sxs-lookup"><span data-stu-id="ba85f-195">Require MFA based on the risk of the user sign-in with Microsoft Defender for Identity.</span></span> | <span data-ttu-id="ba85f-196">Azure AD Premium P2 ライセンスを含む Microsoft 365 E5 または E3</span><span class="sxs-lookup"><span data-stu-id="ba85f-196">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> | 
| <span data-ttu-id="ba85f-197">セルフサービスによるパスワードのリセット (SSPR)</span><span class="sxs-lookup"><span data-stu-id="ba85f-197">Self-Service Password Reset (SSPR)</span></span>    | <span data-ttu-id="ba85f-198">ユーザーによるパスワードまたはアカウントのリセットまたはロック解除を許可します。</span><span class="sxs-lookup"><span data-stu-id="ba85f-198">Allow your users to reset or unlock their passwords or accounts.</span></span>  | <span data-ttu-id="ba85f-199">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="ba85f-199">Microsoft 365 E3 or E5</span></span> |
||||

### <a name="migration"></a><span data-ttu-id="ba85f-200">移行</span><span class="sxs-lookup"><span data-stu-id="ba85f-200">Migration</span></span>

| <span data-ttu-id="ba85f-201">機能</span><span class="sxs-lookup"><span data-stu-id="ba85f-201">Capability or feature</span></span> | <span data-ttu-id="ba85f-202">説明</span><span class="sxs-lookup"><span data-stu-id="ba85f-202">Description</span></span> | <span data-ttu-id="ba85f-203">ライセンス</span><span class="sxs-lookup"><span data-stu-id="ba85f-203">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="ba85f-204">Windows 10 に移行する</span><span class="sxs-lookup"><span data-stu-id="ba85f-204">Migrate to Windows 10</span></span> | <span data-ttu-id="ba85f-205">Windows 7 または Windows 8.1 を実行するデバイスを Windows 10 Enterprise に移行します。</span><span class="sxs-lookup"><span data-stu-id="ba85f-205">Migrate your devices that run Windows 7 or Windows 8.1 to Windows 10 Enterprise.</span></span> | <span data-ttu-id="ba85f-206">Microsoft 365 E3 または E5 に含まれる Windows 10 Enterprise ライセンス</span><span class="sxs-lookup"><span data-stu-id="ba85f-206">Windows 10 Enterprise licenses included with Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="ba85f-207">エンタープライズ向け Microsoft 365 Apps への移行</span><span class="sxs-lookup"><span data-stu-id="ba85f-207">Migrate to Microsoft 365 Apps for enterprise</span></span> | <span data-ttu-id="ba85f-208">Word や powerPoint Officeクライアント アプリを、新しい機能で更新されたクラウドからインストールされたバージョンに移行します。</span><span class="sxs-lookup"><span data-stu-id="ba85f-208">Migrate your Office client apps such as Word and PowerPoint to the versions installed from the cloud that are updated with new features.</span></span> | <span data-ttu-id="ba85f-209">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="ba85f-209">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="ba85f-210">オンプレミスのサーバーとデータを Microsoft 365 に移行する</span><span class="sxs-lookup"><span data-stu-id="ba85f-210">Migrate on-premises servers and data to Microsoft 365</span></span> | <span data-ttu-id="ba85f-211">Exchange メールボックス、SharePoint サイト、Skype for Business Online を Microsoft 365 クラウド サービスに移行します。</span><span class="sxs-lookup"><span data-stu-id="ba85f-211">Migrate your Exchange mailboxes, SharePoint sites, and Skype for Business Online to Microsoft 365 cloud services.</span></span> | <span data-ttu-id="ba85f-212">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="ba85f-212">Microsoft 365 E3 or E5</span></span> | 
||||

### <a name="device-and-app-management"></a><span data-ttu-id="ba85f-213">デバイスおよびアプリの管理</span><span class="sxs-lookup"><span data-stu-id="ba85f-213">Device and app management</span></span>

| <span data-ttu-id="ba85f-214">機能</span><span class="sxs-lookup"><span data-stu-id="ba85f-214">Capability or feature</span></span> | <span data-ttu-id="ba85f-215">説明</span><span class="sxs-lookup"><span data-stu-id="ba85f-215">Description</span></span> | <span data-ttu-id="ba85f-216">ライセンス</span><span class="sxs-lookup"><span data-stu-id="ba85f-216">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="ba85f-217">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ba85f-217">Microsoft Intune</span></span> | <span data-ttu-id="ba85f-218">モバイル デバイス管理 (MDM) とモバイル アプリケーション管理 (MAM) を提供するクラウドベースのサービスで、携帯電話、タブレット、ラップトップなど、組織のアプリケーションとデバイスの使用方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="ba85f-218">A cloud-based service that provides mobile device management (MDM) and mobile application management (MAM) to control how your organization’s application and the devices are used, including mobile phones, tablets, and laptops.</span></span> | <span data-ttu-id="ba85f-219">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="ba85f-219">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="ba85f-220">基本的なモビリティとセキュリティ</span><span class="sxs-lookup"><span data-stu-id="ba85f-220">Basic Mobility and Security</span></span> | <span data-ttu-id="ba85f-221">この組み込みサービスを使用して、iPhone、iPad、Android、Windows 電話など、ユーザーのモバイル デバイスをセキュリティで保護して管理します。</span><span class="sxs-lookup"><span data-stu-id="ba85f-221">Secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones with this built-in service.</span></span>  | <span data-ttu-id="ba85f-222">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="ba85f-222">Microsoft 365 E3 or E5</span></span> | 
||||

## <a name="next-steps"></a><span data-ttu-id="ba85f-223">次の手順</span><span class="sxs-lookup"><span data-stu-id="ba85f-223">Next steps</span></span>

<span data-ttu-id="ba85f-224">Microsoft 365 テナントを設定および管理するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ba85f-224">Use these steps to set up and manage your Microsoft 365 tenants.</span></span>

1. [<span data-ttu-id="ba85f-225">テナントを決定する</span><span class="sxs-lookup"><span data-stu-id="ba85f-225">Determine your tenants</span></span>](tenant-management-tenants.md)
2. [<span data-ttu-id="ba85f-226">ネットワークを最適化する</span><span class="sxs-lookup"><span data-stu-id="ba85f-226">Optimize your networking</span></span>](tenant-management-networking.md)
3. [<span data-ttu-id="ba85f-227">ID を同期し、セキュリティで保護されたサインインを適用する</span><span class="sxs-lookup"><span data-stu-id="ba85f-227">Synchronize your identities and enforce secure sign-ins</span></span>](tenant-management-identity.md)
4. [<span data-ttu-id="ba85f-228">オンプレミスのサーバーとデータOffice移行する</span><span class="sxs-lookup"><span data-stu-id="ba85f-228">Migrate your on-premises Office servers and data</span></span>](tenant-management-migration.md)
5. [<span data-ttu-id="ba85f-229">デバイスとアプリの管理を展開する</span><span class="sxs-lookup"><span data-stu-id="ba85f-229">Deploy device and app management</span></span>](tenant-management-device-management.md)

<span data-ttu-id="ba85f-230">[![Microsoft 365 テナントを展開および管理する手順](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)</span><span class="sxs-lookup"><span data-stu-id="ba85f-230">[![The steps to deploy and manage a Microsoft 365 tenant](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)</span></span>

<span data-ttu-id="ba85f-231">各手順では、展開オプション、結果、および継続的なメンテナンス タスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ba85f-231">Each step describes deployment options, summarizes the results, and ongoing maintenance tasks.</span></span>

<span data-ttu-id="ba85f-232">架空の代表的な多国籍組織が Microsoft 365 テナントの要素を展開した方法を理解するには、「Contoso のケース スタディ」 [を参照してください](../enterprise/contoso-case-study.md)。</span><span class="sxs-lookup"><span data-stu-id="ba85f-232">To understand how a fictional but representative multi-national organization deployed the elements of their Microsoft 365 tenant, see the [Contoso case study](../enterprise/contoso-case-study.md).</span></span>
