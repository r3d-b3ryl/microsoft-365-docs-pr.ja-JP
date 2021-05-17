---
title: 手順 1. エンタープライズ Microsoft 365のユーザー 情報
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
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: 複数地域および移動場所のオプションMicrosoft 365単一または複数のテナントを展開および管理します。
ms.openlocfilehash: 4d9bd685fce6fb2f11b8e17bebae6460e0c10bd2
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406386"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="40760-104">手順 1.</span><span class="sxs-lookup"><span data-stu-id="40760-104">Step 1.</span></span> <span data-ttu-id="40760-105">エンタープライズ Microsoft 365のユーザー 情報</span><span class="sxs-lookup"><span data-stu-id="40760-105">Your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="40760-106">テナントの最初の決定の 1 つは、必要な数です。</span><span class="sxs-lookup"><span data-stu-id="40760-106">One of your first tenant decisions is how many to have.</span></span> <span data-ttu-id="40760-107">各Microsoft 365は、個別、一意、および他のすべてのテナントMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="40760-107">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="40760-108">対応する Azure ADは、他のすべてのテナントとは異なる、一意Microsoft 365です。</span><span class="sxs-lookup"><span data-stu-id="40760-108">It’s corresponding Azure AD tenant is also distinct, unique, and separate from all other Microsoft 365 tenants.</span></span>

## <a name="single-tenant"></a><span data-ttu-id="40760-109">シングル テナント</span><span class="sxs-lookup"><span data-stu-id="40760-109">Single tenant</span></span>
<span data-ttu-id="40760-110">1 つのテナントを使用すると、組織による組織のアプリケーションの使用の多くの側面がMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="40760-110">Having a single tenant simplifies many aspects of your organization’s use of Microsoft 365.</span></span> <span data-ttu-id="40760-111">1 つのテナントとは、単一の Azure ADアカウント、グループ、およびポリシーのセットを持つテナントを意味します。</span><span class="sxs-lookup"><span data-stu-id="40760-111">A single tenant means a single Azure AD tenant with a single set of accounts, groups, and policies.</span></span> <span data-ttu-id="40760-112">組織全体のリソースのアクセス許可と共有は、この一元的な ID プロバイダーを通じて行えます。</span><span class="sxs-lookup"><span data-stu-id="40760-112">Permissions and sharing of resources across your organization can be done through this central identity provider.</span></span>

<span data-ttu-id="40760-113">1 つのテナントは、ユーザーに最も機能が豊富で簡略化されたコラボレーションと生産性のエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="40760-113">A single tenant provides the most feature-rich and simplified collaboration and productivity experience for your users.</span></span>

<span data-ttu-id="40760-114">次に、テナントの既定の場所と Azure ADテナントをMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="40760-114">Here is an example showing the default location and Azure AD tenant of a Microsoft 365 tenant.</span></span>

![Azure Microsoft 365テナントを持つ単一のADテナント](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a><span data-ttu-id="40760-116">複数のテナント</span><span class="sxs-lookup"><span data-stu-id="40760-116">Multiple tenants</span></span>

<span data-ttu-id="40760-117">組織が複数のテナントを持つ理由は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="40760-117">There are many reasons why your organization could have multiple tenants:</span></span>

- <span data-ttu-id="40760-118">管理上の分離</span><span class="sxs-lookup"><span data-stu-id="40760-118">Administrative isolation</span></span>
- <span data-ttu-id="40760-119">分散 IT</span><span class="sxs-lookup"><span data-stu-id="40760-119">Decentralized IT</span></span>
- <span data-ttu-id="40760-120">過去の決定</span><span class="sxs-lookup"><span data-stu-id="40760-120">Historical decisions</span></span>
- <span data-ttu-id="40760-121">合併、買収、または売却</span><span class="sxs-lookup"><span data-stu-id="40760-121">Mergers, acquisitions, or divestitures</span></span>
- <span data-ttu-id="40760-122">複合企業組織のブランド化の明確な分離</span><span class="sxs-lookup"><span data-stu-id="40760-122">Clear separation of branding for conglomerate organizations</span></span>
- <span data-ttu-id="40760-123">プレプロダクション、テスト、またはサンドボックス テナント</span><span class="sxs-lookup"><span data-stu-id="40760-123">Pre-production, test, or sandbox tenants</span></span>

<span data-ttu-id="40760-124">同じ既定のデータセンター geo に 2 つのテナント (テナント A とテナント B) がある組織の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="40760-124">Here is an example of an organization that has two tenants (Tenant A and Tenant B) in the same default datacenter geo.</span></span> <span data-ttu-id="40760-125">各テナントは、個別の Azure ADテナントとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="40760-125">Each tenant as a separate Azure AD tenant.</span></span>

![Azure Microsoft 365テナントを持つ複数のADテナント](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

<span data-ttu-id="40760-127">複数のテナントがある場合は、それらを管理し、ユーザーにサービスを提供する際に、制限と追加の考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="40760-127">When you have multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span>

### <a name="inter-tenant-collaboration"></a><span data-ttu-id="40760-128">テナント間コラボレーション</span><span class="sxs-lookup"><span data-stu-id="40760-128">Inter-tenant collaboration</span></span>

<span data-ttu-id="40760-129">ユーザーが異なる Microsoft 365 テナント間で安全な方法で共同作業を行う場合、テナント間のコラボレーション オプションには、ファイルと会話の中心的な場所の使用、予定表の共有、IM の使用、通信のための音声/ビデオ通話、リソースとアプリケーションへのアクセスのセキュリティ保護が含まれます。</span><span class="sxs-lookup"><span data-stu-id="40760-129">If you want your users to collaborate more effectively across different Microsoft 365 tenants in a secure manner, inter-tenant collaboration options include using a central location for files and conversations, sharing calendars, using IM, audio/video calls for communication, and securing access to resources and applications.</span></span>

<span data-ttu-id="40760-130">詳細については、「テナント間[Microsoft 365」を参照してください](../enterprise/microsoft-365-inter-tenant-collaboration.md)。</span><span class="sxs-lookup"><span data-stu-id="40760-130">For more information, see [Microsoft 365 inter-tenant collaboration](../enterprise/microsoft-365-inter-tenant-collaboration.md).</span></span>

### <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="40760-131">テナント間メールボックスの移行 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="40760-131">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="40760-132">テナント間メールボックスの移行 (プレビュー) の前に、Exchange Online メールボックスをテナント間で移動する場合は、ユーザー メールボックスを現在のテナント (ソース テナント) からオンプレミスに完全にオフボードし、新しいテナント (ターゲット テナント) にオンボードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="40760-132">Prior to cross-tenant mailbox migration (in preview), when moving Exchange Online mailboxes between tenants, you have to completely offboard a user mailbox from their current tenant (the source tenant) to on-premises and then onboard them to a new tenant (the target tenant).</span></span> <span data-ttu-id="40760-133">新しいクロステナント メールボックス移行機能により、移行元テナントとターゲット テナントの両方のテナント管理者は、オンプレミス システムでのインフラストラクチャの依存関係を最小限に抑えたテナント間でメールボックスを移動できます。</span><span class="sxs-lookup"><span data-stu-id="40760-133">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="40760-134">これにより、オフボードメールボックスとオンボードメールボックスが不要になります。</span><span class="sxs-lookup"><span data-stu-id="40760-134">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="40760-135">クロステナント メールボックス移行前の 2 つのテナントとそのメールボックスの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="40760-135">Here are two example tenants and their mailboxes before cross-tenant mailbox migration.</span></span>

![複数Microsoft 365テナントとそのメールボックス](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

<span data-ttu-id="40760-137">この図では、2 つの独立したテナントに独自のドメインと一連のメールボックスExchangeがあります。</span><span class="sxs-lookup"><span data-stu-id="40760-137">In this illustration, two separate tenants have their own domains and set of Exchange mailboxes.</span></span>

<span data-ttu-id="40760-138">クロステナント メールボックスの移行後のターゲット テナント (テナント A) を次に示します。</span><span class="sxs-lookup"><span data-stu-id="40760-138">Here is the target tenant (Tenant A) after cross-tenant mailbox migration.</span></span>

![テナント間メールボックスの移行後のターゲット テナント](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

<span data-ttu-id="40760-140">この図では、1 つのテナントにドメインとメールボックスの両方のセットExchangeしています。</span><span class="sxs-lookup"><span data-stu-id="40760-140">In this illustration, a single tenant has both domains and both sets of Exchange mailboxes.</span></span>

<span data-ttu-id="40760-141">詳細については、「クロステナント [メールボックスの移行」を参照してください](../enterprise/cross-tenant-mailbox-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="40760-141">For more information, see [Cross-tenant mailbox migration](../enterprise/cross-tenant-mailbox-migration.md).</span></span>

### <a name="tenant-to-tenant-migrations"></a><span data-ttu-id="40760-142">テナントからテナントへの移行</span><span class="sxs-lookup"><span data-stu-id="40760-142">Tenant-to-tenant migrations</span></span>

<span data-ttu-id="40760-143">合併、買収、売却、その他のシナリオには、既存の Microsoft 365 テナントを新しいテナントに移行するためのいくつかのアーキテクチャアプローチがあります。</span><span class="sxs-lookup"><span data-stu-id="40760-143">There are several architectural approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> 

<span data-ttu-id="40760-144">詳細なガイダンスについては、「テナント[間Microsoft 365移行」を参照してください](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)。</span><span class="sxs-lookup"><span data-stu-id="40760-144">For detailed guidance, see [Microsoft 365 tenant-to-tenant migrations](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span></span>

## <a name="multi-geo-for-a-tenant"></a><span data-ttu-id="40760-145">テナントの複数地域</span><span class="sxs-lookup"><span data-stu-id="40760-145">Multi-Geo for a tenant</span></span>

<span data-ttu-id="40760-146">Microsoft 365 Multi-Geo を使用すると、データ常駐要件を満たすために選択した他のデータセンターの地理的な場所にデータをプロビジョニングして保存し、同時に、最新の生産性エクスペリエンスのグローバルロールアウトをワーカーにロック解除できます。</span><span class="sxs-lookup"><span data-stu-id="40760-146">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global rollout of modern productivity experiences to your workers.</span></span>

<span data-ttu-id="40760-147">複数地域環境では、Microsoft 365 テナントは、Microsoft 365 サブスクリプションが最初に作成された既定または中央の場所と、1 つ以上のサテライトの場所で構成されます。</span><span class="sxs-lookup"><span data-stu-id="40760-147">In a Multi-Geo environment, your Microsoft 365 tenant consists of a default or central location where your Microsoft 365 subscription was originally created and one or more satellite locations.</span></span> <span data-ttu-id="40760-148">複数地域のテナントでは、地域の場所、グループ、およびユーザー情報に関する情報は、グローバル Azure ADテナントでADされます。</span><span class="sxs-lookup"><span data-stu-id="40760-148">In a multi-geo tenant, the information about geo locations, groups, and user information is mastered in a global Azure AD tenant.</span></span> <span data-ttu-id="40760-149">テナント情報は一元的にマスターされ、各地域の場所に同期されますので、会社の誰もが関与するコラボレーション エクスペリエンスが場所全体で共有されます。</span><span class="sxs-lookup"><span data-stu-id="40760-149">Because your tenant information is mastered centrally and synchronized into each geo location, collaboration experiences involving anyone from your company are shared across the locations.</span></span>

<span data-ttu-id="40760-150">ヨーロッパに既定の場所を持ち、北アメリカのサテライトの場所を持つ組織の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="40760-150">Here is an example of an organization that has its default location in Europe and a satellite location in North America.</span></span> <span data-ttu-id="40760-151">どちらの場所も、単一のテナントAD同じグローバル Azure Microsoft 365共有します。</span><span class="sxs-lookup"><span data-stu-id="40760-151">Both locations share the same global Azure AD tenant for the single Microsoft 365 tenant.</span></span>

![複数地域のテナントのMicrosoft 365例](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

<span data-ttu-id="40760-153">詳細については、「[Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40760-153">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>

## <a name="moving-core-data-to-a-new-datacenter-geo"></a><span data-ttu-id="40760-154">コア データを新しいデータセンター geo に移動する</span><span class="sxs-lookup"><span data-stu-id="40760-154">Moving core data to a new datacenter geo</span></span>

<span data-ttu-id="40760-155">Microsoft は、引き続き新しいデータセンター geos を開き、Microsoft 365します。</span><span class="sxs-lookup"><span data-stu-id="40760-155">Microsoft continues to open new datacenter geos for Microsoft 365 services.</span></span> <span data-ttu-id="40760-156">こうした新しいデータセンター geo により、現在続いているお客様の需要と使用量の拡大をサポートするための容量と計算リソースが増加されます。</span><span class="sxs-lookup"><span data-stu-id="40760-156">These new datacenter geos add capacity and compute resources to support our ongoing customer demand and usage growth.</span></span> <span data-ttu-id="40760-157">さらに、新しいデータセンター geo では、コア カスタマー データを geo 内に常駐できます。</span><span class="sxs-lookup"><span data-stu-id="40760-157">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="40760-158">新しいデータセンター geo を開いても、既存のデータセンター geo に格納されているコア データには影響を及ぼすとは言え、Microsoft では、組織の主要な顧客データの早期移行を新しいデータセンター geo に要求できます。</span><span class="sxs-lookup"><span data-stu-id="40760-158">Although opening a new datacenter geo does not impact you and your core data stored in an already existing datacenter geo, Microsoft allows you to request an early migration of your organization's core customer data at rest to a new datacenter geo.</span></span>

<span data-ttu-id="40760-159">次に示すのは、Microsoft 365テナントが欧州連合 (EU) データセンター geo から英国 (英国) に移動された例です。</span><span class="sxs-lookup"><span data-stu-id="40760-159">Here is an example in which a Microsoft 365 tenant was moved from the European Union (EU) datacenter geo to the one located in the United Kingdom (UK).</span></span>

![データセンター geo 間でMicrosoft 365テナントを移動する例](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

<span data-ttu-id="40760-161">詳細については、「コア データを新しいデータセンター geos[にMicrosoft 365する」を参照してください](../enterprise/moving-data-to-new-datacenter-geos.md)。</span><span class="sxs-lookup"><span data-stu-id="40760-161">For more information, see [Moving core data to new Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="products-and-licenses-for-a-tenant"></a><span data-ttu-id="40760-162">テナントの製品とライセンス</span><span class="sxs-lookup"><span data-stu-id="40760-162">Products and licenses for a tenant</span></span>

<span data-ttu-id="40760-163">最初Microsoft 365を購入すると、テナントが作成されます (Microsoft 365 E3)。</span><span class="sxs-lookup"><span data-stu-id="40760-163">Your Microsoft 365 tenant gets created when you purchase your first product, such as Microsoft 365 E3.</span></span> <span data-ttu-id="40760-164">製品と共にライセンスは、月次または年会費が課金されます。</span><span class="sxs-lookup"><span data-stu-id="40760-164">Along with the product are licenses, which are charged a monthly or annual fee.</span></span> <span data-ttu-id="40760-165">その後、管理者は、いずれかの製品の利用可能なライセンスを、直接またはグループ メンバーシップを通じてユーザー アカウントに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="40760-165">An administrator then assigns an available license from one of your products to a user account, either directly or through group membership.</span></span> <span data-ttu-id="40760-166">組織のビジネス ニーズに応じて、それぞれ独自のライセンス プールを持つ一連の製品が用意されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="40760-166">Depending on your organization's business needs, you might have a set of products, each with their own pool of licenses.</span></span> 

<span data-ttu-id="40760-167">製品のセットと各ライセンスの数を決定するには、次の計画が必要です。</span><span class="sxs-lookup"><span data-stu-id="40760-167">Determining the set of products and the number of licenses for each requires some planning to:</span></span>

- <span data-ttu-id="40760-168">高度な機能を必要とするユーザー アカウントのライセンスが十分に確保されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="40760-168">Ensure you have enough licenses for the user accounts that need advanced features.</span></span>
- <span data-ttu-id="40760-169">組織でのスタッフの変更に基づいて、ライセンスが使い切れたり、割り当てられていないライセンスが多すぎたりするのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="40760-169">Prevent you from running out of licenses or having too many unassigned licenses, based on changes in staffing at your organization.</span></span>


## <a name="results-of-step-1"></a><span data-ttu-id="40760-170">手順 1 の結果</span><span class="sxs-lookup"><span data-stu-id="40760-170">Results of Step 1</span></span>

<span data-ttu-id="40760-171">エンタープライズ テナントMicrosoft 365、次の条件を決定しました。</span><span class="sxs-lookup"><span data-stu-id="40760-171">For your Microsoft 365 for enterprise tenants, you have determined:</span></span>

- <span data-ttu-id="40760-172">必要なテナントの数。</span><span class="sxs-lookup"><span data-stu-id="40760-172">How many tenants you have or need.</span></span>
- <span data-ttu-id="40760-173">テナントごとに、購入する必要がある製品とライセンス。</span><span class="sxs-lookup"><span data-stu-id="40760-173">For each tenant, which products and licenses must be purchased.</span></span>
- <span data-ttu-id="40760-174">データ常駐要件に準拠するためにテナントが複数地域である必要があるかどうか。</span><span class="sxs-lookup"><span data-stu-id="40760-174">Whether a tenant needs to be Multi-Geo to comply with data residency requirements.</span></span>
- <span data-ttu-id="40760-175">テナント間のコラボレーションをセットアップする必要があるかどうか。</span><span class="sxs-lookup"><span data-stu-id="40760-175">Whether you need to set up inter-tenant collaboration.</span></span>
- <span data-ttu-id="40760-176">テナントを別のテナントに移行する必要があるかどうか。</span><span class="sxs-lookup"><span data-stu-id="40760-176">Whether you need to migrate one tenant to another.</span></span>
- <span data-ttu-id="40760-177">コア データを 1 つのデータセンター geo から新しいデータセンター geo に移動する必要があるかどうか。</span><span class="sxs-lookup"><span data-stu-id="40760-177">Whether you need to move core data from one datacenter geo to new one.</span></span>

<span data-ttu-id="40760-178">新しいテナントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="40760-178">Here is an example of a new tenant.</span></span>

![新しいテナントの例](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

<span data-ttu-id="40760-180">この図では、テナントには次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="40760-180">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="40760-181">データ センター geo に対応する既定Microsoft 365場所です。</span><span class="sxs-lookup"><span data-stu-id="40760-181">A default location corresponding to a Microsoft 365 datacenter geo.</span></span>
- <span data-ttu-id="40760-182">製品とライセンスのセット。</span><span class="sxs-lookup"><span data-stu-id="40760-182">A set of products and licenses.</span></span>
- <span data-ttu-id="40760-183">一連のクラウド生産性アプリは、製品に固有の一部です。</span><span class="sxs-lookup"><span data-stu-id="40760-183">The set of cloud productivity apps, some of which are specific to products.</span></span>
- <span data-ttu-id="40760-184">グローバル管理者ADアカウントと初期管理者名を含む Azure DNS ドメインテナント。</span><span class="sxs-lookup"><span data-stu-id="40760-184">An Azure AD tenant that contains global administrator accounts and an initial DNS domain name.</span></span>

<span data-ttu-id="40760-185">このソリューションの追加の手順を進め、この図を作成します。</span><span class="sxs-lookup"><span data-stu-id="40760-185">As we move through the additional steps of this solution, we will build out this figure.</span></span>

## <a name="ongoing-maintenance-for-tenants"></a><span data-ttu-id="40760-186">テナントの継続的なメンテナンス</span><span class="sxs-lookup"><span data-stu-id="40760-186">Ongoing maintenance for tenants</span></span>

<span data-ttu-id="40760-187">継続的に、次の必要が生じ得る場合があります。</span><span class="sxs-lookup"><span data-stu-id="40760-187">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="40760-188">新しいテナントを追加します。</span><span class="sxs-lookup"><span data-stu-id="40760-188">Add a new tenant.</span></span>
- <span data-ttu-id="40760-189">ライセンスの初期数を持つテナントに新しい製品を追加します。</span><span class="sxs-lookup"><span data-stu-id="40760-189">Add new products to a tenant with an initial number of licenses.</span></span>
- <span data-ttu-id="40760-190">テナント内の製品のライセンスセットを変更して、スタッフの要件の変更に合わせて調整します。</span><span class="sxs-lookup"><span data-stu-id="40760-190">Change the set of licenses for a product in a tenant to adjust for changing staff requirements.</span></span>
- <span data-ttu-id="40760-191">コア データをテナントから新しいデータセンターの地理的な場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="40760-191">Move your core data from a tenant to a new datacenter geo location.</span></span>
- <span data-ttu-id="40760-192">データ常駐要件に複数地域を追加します。</span><span class="sxs-lookup"><span data-stu-id="40760-192">Add Multi-Geo for data residency requirements.</span></span>
- <span data-ttu-id="40760-193">テナント間のコラボレーションを設定します。</span><span class="sxs-lookup"><span data-stu-id="40760-193">Set up inter-tenant collaboration.</span></span>

## <a name="next-step"></a><span data-ttu-id="40760-194">次の手順</span><span class="sxs-lookup"><span data-stu-id="40760-194">Next step</span></span>

<span data-ttu-id="40760-195">[![手順 2.アクセス用にネットワーク用にテナントを最適化する](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span><span class="sxs-lookup"><span data-stu-id="40760-195">[![Step 2. Optimize your tenant for network for access](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span></span>

<span data-ttu-id="40760-196">ネットワークを[続行して、](tenant-management-networking.md)ワーカーからクラウド サービスへの最適なネットワークMicrosoft 365提供します。</span><span class="sxs-lookup"><span data-stu-id="40760-196">Continue with [networking](tenant-management-networking.md) to provide optimal networking from your workers to Microsoft 365 cloud services.</span></span>
