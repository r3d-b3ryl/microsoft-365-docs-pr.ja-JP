---
title: Microsoft 365 のテナントロードマップ
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: Microsoft 365 用のテナントをセットアップするためのロードマップ。
ms.openlocfilehash: db0f9552fce460ca6d25ee74ea2031bea388b8dc
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656009"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="98c69-103">Microsoft 365 のテナントロードマップ</span><span class="sxs-lookup"><span data-stu-id="98c69-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="98c69-104">Microsoft 365 テナントは、組織に割り当てられた一連のサービスです。</span><span class="sxs-lookup"><span data-stu-id="98c69-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="98c69-105">通常、このテナントは1つ以上の DNS ドメイン名に関連付けられており、さまざまなサブスクリプションのための中央のコンテナーとして機能し、ユーザーアカウントに割り当てられているライセンスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="98c69-105">Typically, this tenant is associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="98c69-106">詳細については、「 [Microsoft のクラウドサービスのサブスクリプション、ライセンス、アカウント、およびテナント](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98c69-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="98c69-107">Microsoft 365 テナントを作成するときは、特定の地理的な場所に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="98c69-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="98c69-108">また、複数の地理的な場所を持つテナントを作成し、テナントをある場所から別の場所に移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="98c69-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="98c69-109">テナントの id を取得できるようにするには、テナントの構成を慎重に計画して実行することが重要です。</span><span class="sxs-lookup"><span data-stu-id="98c69-109">To get your tenant ready for identity, it's critical to carefully plan and execute your tenant configuration.</span></span>


## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="98c69-110">Microsoft 365 テナントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="98c69-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="98c69-111">オンプレミスとリモートの両方のワーカーに対して Microsoft 365 へのアクセスのためにネットワークを最適化することを確認した後、次の大きなタスクでは、DNS ドメイン名、一般的なサービス、およびセキュリティで保護されたユーザーのサインインをサポートするその id インフラストラクチャに対して Microsoft 365 テナントを計画し、構成します。</span><span class="sxs-lookup"><span data-stu-id="98c69-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

## <a name="plan"></a><span data-ttu-id="98c69-112">プラン</span><span class="sxs-lookup"><span data-stu-id="98c69-112">Plan</span></span>

<span data-ttu-id="98c69-113">テナントの実装を計画するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="98c69-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="98c69-114">サブスクリプション、ライセンス、および Azure Active Directory (Azure AD) テナントについて理解する</span><span class="sxs-lookup"><span data-stu-id="98c69-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="98c69-115">サードパーティの SSL 証明書の使用方法を理解する</span><span class="sxs-lookup"><span data-stu-id="98c69-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="98c69-116">Microsoft 365 テナントを Azure AD サービスと統合する方法を理解する</span><span class="sxs-lookup"><span data-stu-id="98c69-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="98c69-117">クライアントアプリのサポートを計画する</span><span class="sxs-lookup"><span data-stu-id="98c69-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="98c69-118">ハイブリッド先進認証の使用方法を決定する</span><span class="sxs-lookup"><span data-stu-id="98c69-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="98c69-119">Office 2007 および Office 2010 のアップグレードを計画する</span><span class="sxs-lookup"><span data-stu-id="98c69-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="98c69-120">テナントの分離について</span><span class="sxs-lookup"><span data-stu-id="98c69-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="98c69-121">Microsoft 365 サービスアシュアランスの詳細を取得する</span><span class="sxs-lookup"><span data-stu-id="98c69-121">Get the details on Microsoft 365 service assurance</span></span>](microsoft-365-administrative-access-controls-overview.md)

### <a name="deploy"></a><span data-ttu-id="98c69-122">展開</span><span class="sxs-lookup"><span data-stu-id="98c69-122">Deploy</span></span>

<span data-ttu-id="98c69-123">テナントを展開するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="98c69-123">To deploy your tenant:</span></span> 

- <span data-ttu-id="98c69-124">組織の [DNS ドメイン](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) を追加します。</span><span class="sxs-lookup"><span data-stu-id="98c69-124">Add the [DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>
- <span data-ttu-id="98c69-125">[Microsoft 365 管理センターのセットアップガイド](setup-guides-for-microsoft-365.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="98c69-125">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="98c69-126">[Id インフラストラクチャ](identity-roadmap-microsoft-365.md)を構築し、[ユーザーのサインインをセキュリティで保護](microsoft-365-secure-sign-in.md)します。</span><span class="sxs-lookup"><span data-stu-id="98c69-126">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="98c69-127">テナントの地理的な場所を移動する</span><span class="sxs-lookup"><span data-stu-id="98c69-127">Move a tenant's geographic locations</span></span>

<span data-ttu-id="98c69-128">Microsoft は、Microsoft 365 services の新しいデータセンターの地理的な場所 (geo) を引き続き開きます。</span><span class="sxs-lookup"><span data-stu-id="98c69-128">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="98c69-129">これらの新しいデータセンター geo は、お客様の需要と利用状況の拡大をサポートするための容量とコンピューティングリソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="98c69-129">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="98c69-130">さらに、新しいデータセンター geo では、コア カスタマー データを geo 内に常駐できます。</span><span class="sxs-lookup"><span data-stu-id="98c69-130">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="98c69-131">詳細については、「 [主要データを新しい Microsoft 365 データセンター geo に移行する」を](moving-data-to-new-datacenter-geos.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="98c69-131">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="98c69-132">Microsoft 365 複数地域の展開</span><span class="sxs-lookup"><span data-stu-id="98c69-132">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="98c69-133">Microsoft 365 Multi-Geo を使用すれば、組織はその組織の Microsoft 365 のプレゼンスを、その既存のテナント内の複数の地域または国に対して展開することができます。</span><span class="sxs-lookup"><span data-stu-id="98c69-133">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="98c69-134">詳細については、「 [Microsoft 365 複数地域](microsoft-365-multi-geo.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98c69-134">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenancies"></a><span data-ttu-id="98c69-135">複数の Microsoft 365 テナンシーを管理する</span><span class="sxs-lookup"><span data-stu-id="98c69-135">Manage multiple Microsoft 365 tenancies</span></span> 

<span data-ttu-id="98c69-136">Oガントの作成に単一のテナントがあると理想的ですが、複数のテナンシーを持つ多くの組織のうちの1つである場合があります。</span><span class="sxs-lookup"><span data-stu-id="98c69-136">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenancies.</span></span> <span data-ttu-id="98c69-137">複数のテナンシーを使用する理由には、合併と買収、管理上の分離が必要である、または分散化が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="98c69-137">Reasons for multiple tenancies can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="98c69-138">Microsoft 365 テナンシーが複数ある場合は、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98c69-138">If you have multiple Microsoft 365 tenancies, see these articles for more information about:</span></span>

- [<span data-ttu-id="98c69-139">テナント間コラボレーション</span><span class="sxs-lookup"><span data-stu-id="98c69-139">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="98c69-140">テナント間でのメールボックスの移行</span><span class="sxs-lookup"><span data-stu-id="98c69-140">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="98c69-141">テナントからテナントへの移行</span><span class="sxs-lookup"><span data-stu-id="98c69-141">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)


## <a name="next-step"></a><span data-ttu-id="98c69-142">次の手順</span><span class="sxs-lookup"><span data-stu-id="98c69-142">Next step</span></span>

<span data-ttu-id="98c69-143">[サブスクリプション、ライセンス、アカウント、テナント](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)を使用して、テナントの計画を開始します。</span><span class="sxs-lookup"><span data-stu-id="98c69-143">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>
