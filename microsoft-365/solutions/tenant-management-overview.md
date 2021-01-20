---
title: Microsoft 365 enterprise のテナント管理
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
ms.custom:
- Ent_Solutions
description: Microsoft 365 テナントの計画、展開、および継続的な運用の概要。
ms.openlocfilehash: f7daeaed149b5b6199ac9012b3ffa3d811029099
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908634"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a><span data-ttu-id="53f39-103">Microsoft 365 enterprise のテナント管理</span><span class="sxs-lookup"><span data-stu-id="53f39-103">Tenant management for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="53f39-104">クラウド コンピューティングを使用して組織のデジタル変換への道を作成するには、生産性、コラボレーション、パフォーマンス、プライバシー、コンプライアンス、セキュリティを作業者が利用できる、しっかりとした基盤が必要です。</span><span class="sxs-lookup"><span data-stu-id="53f39-104">Creating a path to your organization's digital transformation with cloud computing requires a firm foundation upon which your workers can rely for productivity, collaboration, performance, privacy, compliance, and security.</span></span>

<span data-ttu-id="53f39-105">Microsoft 365 テナントの正しい構成により、その基盤が提供され、作業の完了に集中して作業を行い、IT 部門は追加のビジネス価値を提供するエンドツーエンドのソリューションに集中できます。</span><span class="sxs-lookup"><span data-stu-id="53f39-105">Correct configuration of your Microsoft 365 tenants provides that foundation, leaving your workers to focus on getting their work done and your IT department to focus on end-to-end solutions that provide additional business value.</span></span> 

<span data-ttu-id="53f39-106">このソリューションでは、以下の手順で基礎の構成を行います。</span><span class="sxs-lookup"><span data-stu-id="53f39-106">This solution takes you through the configuration of that foundation in these steps:</span></span>

1. <span data-ttu-id="53f39-107">テナントを決定する</span><span class="sxs-lookup"><span data-stu-id="53f39-107">Determine your tenants</span></span>
2. <span data-ttu-id="53f39-108">ネットワークを最適化する</span><span class="sxs-lookup"><span data-stu-id="53f39-108">Optimize your networking</span></span>
3. <span data-ttu-id="53f39-109">ID を同期し、セキュリティで保護されたサインインを適用する</span><span class="sxs-lookup"><span data-stu-id="53f39-109">Synchronize your identities and enforce secure sign-ins</span></span>
4. <span data-ttu-id="53f39-110">Windows デバイス、Office クライアント、オンプレミスのサーバーとデータOffice移行する</span><span class="sxs-lookup"><span data-stu-id="53f39-110">Migrate your Windows devices, Office clients, and on-premises Office servers and data</span></span>
5. <span data-ttu-id="53f39-111">デバイスとアプリの管理を展開する</span><span class="sxs-lookup"><span data-stu-id="53f39-111">Deploy device and app management</span></span>

<span data-ttu-id="53f39-112">しかし、最初に、テナントとは何か、そして、しっかりとした基盤を提供するテナントの外観について少し理解しましょう。</span><span class="sxs-lookup"><span data-stu-id="53f39-112">But first, let's take a moment to understand what a tenant is and what a tenant that provides a firm foundation looks like.</span></span>

## <a name="a-microsoft-365-tenant-defined"></a><span data-ttu-id="53f39-113">定義された Microsoft 365 テナント</span><span class="sxs-lookup"><span data-stu-id="53f39-113">A Microsoft 365 tenant defined</span></span>

<span data-ttu-id="53f39-114">Microsoft 365 テナントは、Microsoft 365 のサービスの専用インスタンスであり、ヨーロッパや北米などの特定の既定の場所に格納されている組織データです。</span><span class="sxs-lookup"><span data-stu-id="53f39-114">A Microsoft 365 tenant is a dedicated instance of the services of Microsoft 365 and your organization data stored within a specific default location, such as Europe or North America.</span></span> <span data-ttu-id="53f39-115">この場所は、組織のテナントを作成するときに指定します。</span><span class="sxs-lookup"><span data-stu-id="53f39-115">This location is specified when you create the tenant for your organization.</span></span> <span data-ttu-id="53f39-116">各 Microsoft 365 テナントは、他のすべての Microsoft 365 テナントとは異なる、固有のテナントです。</span><span class="sxs-lookup"><span data-stu-id="53f39-116">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="53f39-117">Microsoft 365 E3 や E5 など、Microsoft から 1 つ以上の製品を購入するときに Microsoft 365 テナントを作成し、それぞれのライセンスのセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="53f39-117">You create a Microsoft 365 tenant when you purchase one or more products from Microsoft, such as Microsoft 365 E3 or E5, and a set of licenses for each.</span></span>

<span data-ttu-id="53f39-118">Microsoft 365 テナントには、Azure Active Directory (Azure AD) テナントも含まれています。これは、ユーザー アカウント、グループ、その他のオブジェクト用の Azure AD の専用インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="53f39-118">Your Microsoft 365 tenant also includes an Azure Active Directory (Azure AD) tenant, which is a dedicated instance of Azure AD for user accounts, groups, and other objects.</span></span> <span data-ttu-id="53f39-119">各 Azure ADテナントは、個別で一意であり、他のすべての Azure ADテナントとは異なります。</span><span class="sxs-lookup"><span data-stu-id="53f39-119">Each Azure AD tenant is distinct, unique, and separate from all other Azure AD tenants.</span></span> <span data-ttu-id="53f39-120">組織は複数の Azure AD テナントを持つ可能性があります。このテナントは Azure サブスクリプションで設定できます。Microsoft 365 テナントは、テナントの作成時に作成された Azure AD テナントを 1 つしか使用できません。</span><span class="sxs-lookup"><span data-stu-id="53f39-120">While your organization can have multiple Azure AD tenants that you can set up with Azure subscriptions, Microsoft 365 tenants can only use a single Azure AD tenant, the one that was created when you created the tenant.</span></span> 

<span data-ttu-id="53f39-121">次に例を示します：</span><span class="sxs-lookup"><span data-stu-id="53f39-121">Here is an example:</span></span>

![Azure AD テナントを持つ Microsoft 365 ADの例](../media/tenant-management-overview/tenant-management-example-tenant.png)

<span data-ttu-id="53f39-123">*テナント管理* は、Microsoft 365 テナントの計画、展開、および継続的な運用です。</span><span class="sxs-lookup"><span data-stu-id="53f39-123">*Tenant management* is the planning, deployment, and ongoing operation of your Microsoft 365 tenants.</span></span> 

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a><span data-ttu-id="53f39-124">十分に設計され運用されているテナントの属性</span><span class="sxs-lookup"><span data-stu-id="53f39-124">Attributes of a well-designed and operating tenant</span></span>

<span data-ttu-id="53f39-125">テナントの正しい名前と場所を超えて、Microsoft Teams や Exchange Online などのクラウド生産性向上アプリのユーザー エクスペリエンスを効果的、安全、かつ高パフォーマンスにするための追加要素を計画、展開、および管理できます。 &mdash; &mdash;</span><span class="sxs-lookup"><span data-stu-id="53f39-125">Beyond the correct name and location for your tenant, there are additional elements to plan, deploy, and manage to ensure that your user experiences with cloud productivity apps&mdash;such as Microsoft Teams and Exchange Online&mdash;are effective, secure, and performant.</span></span>

<span data-ttu-id="53f39-126">要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="53f39-126">Here are the elements:</span></span>

- <span data-ttu-id="53f39-127">製品 (サブスクリプション) とライセンスのセットが正しい。</span><span class="sxs-lookup"><span data-stu-id="53f39-127">You have the correct set of products (subscriptions) and licenses.</span></span>
  - <span data-ttu-id="53f39-128">一連の製品は、ビジネス、IT、およびセキュリティのニーズに一致します。</span><span class="sxs-lookup"><span data-stu-id="53f39-128">The set of products match your business, IT, and security needs.</span></span>
  - <span data-ttu-id="53f39-129">従業員に対して十分な数のライセンスと、スタッフの変更が予想されています。</span><span class="sxs-lookup"><span data-stu-id="53f39-129">There is an adequate number of licenses for your workers and anticipated changes in staffing.</span></span>
- <span data-ttu-id="53f39-130">ネットワークの場合:</span><span class="sxs-lookup"><span data-stu-id="53f39-130">For networking:</span></span>
  - <span data-ttu-id="53f39-131">正しい名前を構成DNS ドメイン。</span><span class="sxs-lookup"><span data-stu-id="53f39-131">You have configured the correct DNS domain names.</span></span>
  - <span data-ttu-id="53f39-132">エンタープライズ ネットワークの場合は、オンサイトワーカー向けに Microsoft ネットワークへのネットワーク トラフィックを最適化しました。</span><span class="sxs-lookup"><span data-stu-id="53f39-132">For enterprise networks, you have optimized network traffic to the Microsoft network for onsite workers.</span></span>
  - <span data-ttu-id="53f39-133">VPN クライアントを使用しているリモート ワーカーのネットワーク トラフィックを最適化しました。</span><span class="sxs-lookup"><span data-stu-id="53f39-133">You have optimized network traffic for remote workers who are using a VPN client.</span></span>
- <span data-ttu-id="53f39-134">Active Directory ドメイン サービス (AD DS) アカウント、グループ、その他のオブジェクトを同期している。</span><span class="sxs-lookup"><span data-stu-id="53f39-134">You have synchronized your Active Directory Domain Services (AD DS) accounts, groups, and other objects.</span></span>
  - <span data-ttu-id="53f39-135">Azure ADテナント アカウントは、電子メール アドレスの正しい DNS ドメインを持つ Exchange Online メールボックスにマップされます。</span><span class="sxs-lookup"><span data-stu-id="53f39-135">Your Azure AD tenant accounts are mapped to Exchange Online mailboxes with the correct DNS domains for email addresses.</span></span>
  - <span data-ttu-id="53f39-136">購入した正しい製品 (Microsoft 365 E3 や E5 など) から、ユーザー アカウントに正しいライセンスが割り当てられている。</span><span class="sxs-lookup"><span data-stu-id="53f39-136">Your user accounts have been assigned the correct licenses from the correct purchased products (such as Microsoft 365 E3 or E5).</span></span>
- <span data-ttu-id="53f39-137">強力な ID とアクセス管理が構成されている。</span><span class="sxs-lookup"><span data-stu-id="53f39-137">You have configured strong identity and access management.</span></span>
  - <span data-ttu-id="53f39-138">パスワードレス認証または多要素認証 (MFA) によるセキュリティで保護されたユーザー サインインが必要です。</span><span class="sxs-lookup"><span data-stu-id="53f39-138">You are requiring secure user sign-in with passwordless or multi-factor authentication (MFA).</span></span>
  - <span data-ttu-id="53f39-139">より高いレベルのセキュリティのためにサインイン要件と制限を適用する条件付きアクセス ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="53f39-139">You have Conditional Access policies that enforce sign-in requirements and restrictions for higher levels of security.</span></span>
- <span data-ttu-id="53f39-140">オンプレミスのOfficeサーバーとそのデータがクラウド アプリに移行されたか、ハイブリッド構成で使用されています。</span><span class="sxs-lookup"><span data-stu-id="53f39-140">On-premises Office servers and their data have been migrated to cloud apps or are being used in a hybrid configuration.</span></span>
- <span data-ttu-id="53f39-141">Intune または Microsoft 365 に組み込みの Basic Mobility and Security を使用してデバイス管理を行っている。</span><span class="sxs-lookup"><span data-stu-id="53f39-141">You are doing device management with Intune or Basic Mobility and Security built into Microsoft 365.</span></span>
  - <span data-ttu-id="53f39-142">組織が所有するデバイスが登録および管理されている。</span><span class="sxs-lookup"><span data-stu-id="53f39-142">Your organization-owned devices are enrolled and managed.</span></span>
  - <span data-ttu-id="53f39-143">個人用デバイス用のアプリは管理されます。</span><span class="sxs-lookup"><span data-stu-id="53f39-143">The apps for personal devices are managed.</span></span>

<span data-ttu-id="53f39-144">次に、これらすべての要素を配置した Microsoft 365 テナントの例を示します。</span><span class="sxs-lookup"><span data-stu-id="53f39-144">Here is an example of a Microsoft 365 tenant with all these elements in place.</span></span>

![Microsoft 365 テナントの例](../media/tenant-management-overview/tenant-management-tenant-config.png)

<span data-ttu-id="53f39-146">この図では、Microsoft 365 テナントには次が含まれます。</span><span class="sxs-lookup"><span data-stu-id="53f39-146">In this illustration, the Microsoft 365 tenant includes:</span></span>

- <span data-ttu-id="53f39-147">Microsoft 365 E3 および E5 の製品とライセンス。</span><span class="sxs-lookup"><span data-stu-id="53f39-147">Products and licenses for Microsoft 365 E3 and E5.</span></span>
- <span data-ttu-id="53f39-148">Microsoft 365 生産性アプリ。</span><span class="sxs-lookup"><span data-stu-id="53f39-148">Microsoft 365 productivity apps.</span></span>
- <span data-ttu-id="53f39-149">登録済みデバイスとデバイスポリシーとアプリケーション ポリシーを持つ Intune。</span><span class="sxs-lookup"><span data-stu-id="53f39-149">Intune with enrolled devices and device and application policies.</span></span>
- <span data-ttu-id="53f39-150">Azure AD同期されたユーザー アカウント (グループおよび他のディレクトリ オブジェクトは表示されません)、ドメイン、条件付きアクセス ポリシーを持つテナントです。</span><span class="sxs-lookup"><span data-stu-id="53f39-150">An Azure AD tenant that has synchronized user account (groups and other directory objects are not shown), domains, and Conditional Access policies.</span></span>

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a><span data-ttu-id="53f39-151">Microsoft 365 enterprise のテナント機能</span><span class="sxs-lookup"><span data-stu-id="53f39-151">Tenant capabilities for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="53f39-152">以下のセクションと表は、このソリューションの手順の主要な機能とライセンスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="53f39-152">The following sections and table list the key capabilities and licensing for the steps in this solution.</span></span>

### <a name="tenant"></a><span data-ttu-id="53f39-153">テナント</span><span class="sxs-lookup"><span data-stu-id="53f39-153">Tenant</span></span>

| <span data-ttu-id="53f39-154">機能</span><span class="sxs-lookup"><span data-stu-id="53f39-154">Capability or feature</span></span> | <span data-ttu-id="53f39-155">説明</span><span class="sxs-lookup"><span data-stu-id="53f39-155">Description</span></span> | <span data-ttu-id="53f39-156">ライセンス</span><span class="sxs-lookup"><span data-stu-id="53f39-156">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="53f39-157">複数のテナント</span><span class="sxs-lookup"><span data-stu-id="53f39-157">Multiple tenants</span></span> | <span data-ttu-id="53f39-158">各 Microsoft 365 テナントは、他のすべての Microsoft 365 テナントとは異なる、固有のテナントです。</span><span class="sxs-lookup"><span data-stu-id="53f39-158">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="53f39-159">複数のテナントでは、テナントを管理し、ユーザーにサービスを提供する際の制限と追加の考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="53f39-159">With multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span> | <span data-ttu-id="53f39-160">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="53f39-160">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="53f39-161">テナント間でのメールボックスの移行</span><span class="sxs-lookup"><span data-stu-id="53f39-161">Cross-tenant mailbox migration</span></span> | <span data-ttu-id="53f39-162">テナント管理者は、オンプレミス システムで最小限のインフラストラクチャの依存関係を持つテナント間でメールボックスを移動できます。</span><span class="sxs-lookup"><span data-stu-id="53f39-162">Tenant administrators can move mailboxes between tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="53f39-163">これにより、メールボックスをオフボードおよびオンボードする必要が削除されます。</span><span class="sxs-lookup"><span data-stu-id="53f39-163">This removes the need to off-board and onboard mailboxes.</span></span> | <span data-ttu-id="53f39-164">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="53f39-164">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="53f39-165">Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="53f39-165">Multi-Geo</span></span> | <span data-ttu-id="53f39-166">テナントは、データ常駐の要件を満たすために選択した他のデータセンターの地理的位置に、保存データを保存できます。</span><span class="sxs-lookup"><span data-stu-id="53f39-166">Your tenant can store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements.</span></span> | <span data-ttu-id="53f39-167">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="53f39-167">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="53f39-168">コア データを新しいデータセンター geo に移動する</span><span class="sxs-lookup"><span data-stu-id="53f39-168">Move core data to a new datacenter geo</span></span> | <span data-ttu-id="53f39-169">Microsoft が追加の容量とコンピューティング リソース用に新しいデータセンター geo を追加する場合、コア カスタマー データの地理的なデータ常駐のためのデータセンターの地域移動を要求できます。</span><span class="sxs-lookup"><span data-stu-id="53f39-169">As Microsoft adds new datacenter geos for additional capacity and compute resources, you can request a datacenter geo move for in-geo data residency for your core customer data.</span></span> | <span data-ttu-id="53f39-170">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="53f39-170">Microsoft 365 E3 or E5</span></span> | 
||||

### <a name="networking"></a><span data-ttu-id="53f39-171">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="53f39-171">Networking</span></span>

| <span data-ttu-id="53f39-172">機能</span><span class="sxs-lookup"><span data-stu-id="53f39-172">Capability or feature</span></span> | <span data-ttu-id="53f39-173">説明</span><span class="sxs-lookup"><span data-stu-id="53f39-173">Description</span></span> | <span data-ttu-id="53f39-174">ライセンス</span><span class="sxs-lookup"><span data-stu-id="53f39-174">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="53f39-175">ネットワークインサイト</span><span class="sxs-lookup"><span data-stu-id="53f39-175">Network Insights</span></span> | <span data-ttu-id="53f39-176">Microsoft 365 テナントから収集されたネットワーク パフォーマンスメトリックは、オフィスの場所のネットワーク境界を設計するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="53f39-176">Network performance metrics collected from your Microsoft 365 tenant to help you design network perimeters for your office locations.</span></span> | <span data-ttu-id="53f39-177">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="53f39-177">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="53f39-178">エンドポイントの更新を自動化する</span><span class="sxs-lookup"><span data-stu-id="53f39-178">Automate endpoint updates</span></span> | <span data-ttu-id="53f39-179">クライアント PAC ファイルとネットワーク デバイスとサービスで、Microsoft 365 エンドポイントの構成と継続的な更新を自動化します。</span><span class="sxs-lookup"><span data-stu-id="53f39-179">Automate the configuration and ongoing updates for Microsoft 365 endpoints in your client PAC files and network devices and services.</span></span> | <span data-ttu-id="53f39-180">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="53f39-180">Microsoft 365 E3 or E5</span></span> | 
||||

### <a name="identity"></a><span data-ttu-id="53f39-181">ID</span><span class="sxs-lookup"><span data-stu-id="53f39-181">Identity</span></span>

| <span data-ttu-id="53f39-182">機能</span><span class="sxs-lookup"><span data-stu-id="53f39-182">Capability or feature</span></span> | <span data-ttu-id="53f39-183">説明</span><span class="sxs-lookup"><span data-stu-id="53f39-183">Description</span></span> | <span data-ttu-id="53f39-184">ライセンス</span><span class="sxs-lookup"><span data-stu-id="53f39-184">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="53f39-185">オンプレミスの Active Directory ドメイン サービス (AD DS) を Azure ADテナントと同期する</span><span class="sxs-lookup"><span data-stu-id="53f39-185">Synchronize on-premises Active Directory Domain Services (AD DS) with your Azure AD tenant</span></span>    | <span data-ttu-id="53f39-186">ユーザー アカウント、グループ、その他のオブジェクトにオンプレミスの ID プロバイダーを活用します。</span><span class="sxs-lookup"><span data-stu-id="53f39-186">Leverage your on-premises identity provider for user accounts, groups, and other objects.</span></span> | <span data-ttu-id="53f39-187">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="53f39-187">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="53f39-188">セキュリティの既定値が適用されている MFA</span><span class="sxs-lookup"><span data-stu-id="53f39-188">MFA enforced with security defaults</span></span>   | <span data-ttu-id="53f39-189">サインインには、2 つ目の認証形式を要求することで、ID とデバイスを侵害から保護します。セキュリティの既定値では、すべてのユーザー アカウントに MFA が必要です。</span><span class="sxs-lookup"><span data-stu-id="53f39-189">Protect against compromised identities and devices by requiring a second form of authentication for sign-ins. Security defaults requires MFA for all user accounts.</span></span>   | <span data-ttu-id="53f39-190">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="53f39-190">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="53f39-191">条件付きアクセスが適用されている MFA</span><span class="sxs-lookup"><span data-stu-id="53f39-191">MFA enforced with Conditional Access</span></span>| <span data-ttu-id="53f39-192">条件付きアクセス ポリシーを使用するサインインの属性に基づいて MFA を要求します。</span><span class="sxs-lookup"><span data-stu-id="53f39-192">Require MFA based on the attributes of the sign-in with Conditional Access policies.</span></span>    | <span data-ttu-id="53f39-193">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="53f39-193">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="53f39-194">リスクベースの条件付きアクセスが適用されている MFA</span><span class="sxs-lookup"><span data-stu-id="53f39-194">MFA enforced with risk-based Conditional Access</span></span>   | <span data-ttu-id="53f39-195">ユーザーが Microsoft Defender for Identity でサインインするリスクに基づいて MFA を要求します。</span><span class="sxs-lookup"><span data-stu-id="53f39-195">Require MFA based on the risk of the user sign-in with Microsoft Defender for Identity.</span></span> | <span data-ttu-id="53f39-196">Azure AD Premium P2 ライセンスを含む Microsoft 365 E5 または E3</span><span class="sxs-lookup"><span data-stu-id="53f39-196">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> | 
| <span data-ttu-id="53f39-197">セルフサービスによるパスワードのリセット (SSPR)</span><span class="sxs-lookup"><span data-stu-id="53f39-197">Self-Service Password Reset (SSPR)</span></span>    | <span data-ttu-id="53f39-198">ユーザーによるパスワードまたはアカウントのリセットまたはロック解除を許可します。</span><span class="sxs-lookup"><span data-stu-id="53f39-198">Allow your users to reset or unlock their passwords or accounts.</span></span>  | <span data-ttu-id="53f39-199">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="53f39-199">Microsoft 365 E3 or E5</span></span> |
||||

### <a name="migration"></a><span data-ttu-id="53f39-200">移行</span><span class="sxs-lookup"><span data-stu-id="53f39-200">Migration</span></span>

| <span data-ttu-id="53f39-201">機能</span><span class="sxs-lookup"><span data-stu-id="53f39-201">Capability or feature</span></span> | <span data-ttu-id="53f39-202">説明</span><span class="sxs-lookup"><span data-stu-id="53f39-202">Description</span></span> | <span data-ttu-id="53f39-203">ライセンス</span><span class="sxs-lookup"><span data-stu-id="53f39-203">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="53f39-204">Windows 10 に移行する</span><span class="sxs-lookup"><span data-stu-id="53f39-204">Migrate to Windows 10</span></span> | <span data-ttu-id="53f39-205">Windows 7 または Windows 8.1 を実行しているデバイスを Windows 10 Enterprise に移行します。</span><span class="sxs-lookup"><span data-stu-id="53f39-205">Migrate your devices that run Windows 7 or Windows 8.1 to Windows 10 Enterprise.</span></span> | <span data-ttu-id="53f39-206">Microsoft 365 E3 または E5 に含まれる Windows 10 Enterprise ライセンス</span><span class="sxs-lookup"><span data-stu-id="53f39-206">Windows 10 Enterprise licenses included with Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="53f39-207">Microsoft 365 Apps for enterprise への移行</span><span class="sxs-lookup"><span data-stu-id="53f39-207">Migrate to Microsoft 365 Apps for enterprise</span></span> | <span data-ttu-id="53f39-208">Word Office PowerPoint などのクライアント アプリを、新機能で更新されたクラウドからインストールされているバージョンに移行します。</span><span class="sxs-lookup"><span data-stu-id="53f39-208">Migrate your Office client apps such as Word and PowerPoint to the versions installed from the cloud that are updated with new features.</span></span> | <span data-ttu-id="53f39-209">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="53f39-209">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="53f39-210">オンプレミスのサーバーとデータを Microsoft 365 に移行する</span><span class="sxs-lookup"><span data-stu-id="53f39-210">Migrate on-premises servers and data to Microsoft 365</span></span> | <span data-ttu-id="53f39-211">Exchange メールボックス、SharePoint サイト、Skype for Business Online を Microsoft 365 クラウド サービスに移行します。</span><span class="sxs-lookup"><span data-stu-id="53f39-211">Migrate your Exchange mailboxes, SharePoint sites, and Skype for Business Online to Microsoft 365 cloud services.</span></span> | <span data-ttu-id="53f39-212">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="53f39-212">Microsoft 365 E3 or E5</span></span> | 
||||

### <a name="device-and-app-management"></a><span data-ttu-id="53f39-213">デバイスとアプリの管理</span><span class="sxs-lookup"><span data-stu-id="53f39-213">Device and app management</span></span>

| <span data-ttu-id="53f39-214">機能</span><span class="sxs-lookup"><span data-stu-id="53f39-214">Capability or feature</span></span> | <span data-ttu-id="53f39-215">説明</span><span class="sxs-lookup"><span data-stu-id="53f39-215">Description</span></span> | <span data-ttu-id="53f39-216">ライセンス</span><span class="sxs-lookup"><span data-stu-id="53f39-216">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="53f39-217">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="53f39-217">Microsoft Intune</span></span> | <span data-ttu-id="53f39-218">モバイル デバイス管理 (MDM) とモバイル アプリケーション管理 (MAM) を提供するクラウドベースのサービス。携帯電話、タブレット、ノート PC など、組織のアプリケーションとデバイスの使用方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="53f39-218">A cloud-based service that provides mobile device management (MDM) and mobile application management (MAM) to control how your organization’s application and the devices are used, including mobile phones, tablets, and laptops.</span></span> | <span data-ttu-id="53f39-219">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="53f39-219">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="53f39-220">基本的なモビリティとセキュリティ</span><span class="sxs-lookup"><span data-stu-id="53f39-220">Basic Mobility and Security</span></span> | <span data-ttu-id="53f39-221">この組み込みサービスを使用して、iPhone、iPad、Android、Windows スマートフォンなど、ユーザーのモバイル デバイスをセキュリティで保護し、管理します。</span><span class="sxs-lookup"><span data-stu-id="53f39-221">Secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones with this built-in service.</span></span>  | <span data-ttu-id="53f39-222">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="53f39-222">Microsoft 365 E3 or E5</span></span> | 
||||

## <a name="next-steps"></a><span data-ttu-id="53f39-223">次の手順</span><span class="sxs-lookup"><span data-stu-id="53f39-223">Next steps</span></span>

<span data-ttu-id="53f39-224">次の手順を使用して、Microsoft 365 テナントを設定および管理します。</span><span class="sxs-lookup"><span data-stu-id="53f39-224">Use these steps to set up and manage your Microsoft 365 tenants.</span></span>

1. [<span data-ttu-id="53f39-225">テナントを決定する</span><span class="sxs-lookup"><span data-stu-id="53f39-225">Determine your tenants</span></span>](tenant-management-tenants.md)
2. [<span data-ttu-id="53f39-226">ネットワークを最適化する</span><span class="sxs-lookup"><span data-stu-id="53f39-226">Optimize your networking</span></span>](tenant-management-networking.md)
3. [<span data-ttu-id="53f39-227">ID を同期し、セキュリティで保護されたサインインを適用する</span><span class="sxs-lookup"><span data-stu-id="53f39-227">Synchronize your identities and enforce secure sign-ins</span></span>](tenant-management-identity.md)
4. [<span data-ttu-id="53f39-228">オンプレミスのサーバーとデータOffice移行する</span><span class="sxs-lookup"><span data-stu-id="53f39-228">Migrate your on-premises Office servers and data</span></span>](tenant-management-migration.md)
5. [<span data-ttu-id="53f39-229">デバイスとアプリの管理を展開する</span><span class="sxs-lookup"><span data-stu-id="53f39-229">Deploy device and app management</span></span>](tenant-management-device-management.md)

<span data-ttu-id="53f39-230">[![Microsoft 365 テナントを展開および管理する手順](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)</span><span class="sxs-lookup"><span data-stu-id="53f39-230">[![The steps to deploy and manage a Microsoft 365 tenant](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)</span></span>

<span data-ttu-id="53f39-231">各手順では、展開オプション、結果、および継続的なメンテナンス タスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="53f39-231">Each step describes deployment options, summarizes the results, and ongoing maintenance tasks.</span></span>

<span data-ttu-id="53f39-232">架空の代表的な多国籍組織が Microsoft 365 テナントの要素を展開した方法を理解するには、Contoso 社のケース スタディを [参照してください](../enterprise/contoso-case-study.md)。</span><span class="sxs-lookup"><span data-stu-id="53f39-232">To understand how a fictional but representative multi-national organization deployed the elements of their Microsoft 365 tenant, see the [Contoso case study](../enterprise/contoso-case-study.md).</span></span>
