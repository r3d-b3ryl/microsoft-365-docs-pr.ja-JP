---
title: Microsoft 365 のテナントロードマップ
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: Microsoft 365 のテナントをセットアップするためのロードマップ。
ms.openlocfilehash: fb3b6eecd893a5ab9b71bfa7bdfaea53af43470d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909456"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="b7fb6-103">Microsoft 365 のテナントロードマップ</span><span class="sxs-lookup"><span data-stu-id="b7fb6-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="b7fb6-104">Microsoft 365 テナントは、組織に割り当てられたサービスのセットです。</span><span class="sxs-lookup"><span data-stu-id="b7fb6-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="b7fb6-105">通常、このテナントは 1 つ以上のパブリック DNS ドメイン 名に関連付けられるので、さまざまなサブスクリプションとユーザー アカウントに割り当てるライセンスの中央分離コンテナーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="b7fb6-105">Typically, this tenant is associated with one or more of your public DNS domain names and acts as a central and isolated container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="b7fb6-106">詳細については、「サブスクリプション、ライセンス、アカウント、および Microsoft のクラウド 製品のテナント」 [を参照してください](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)。</span><span class="sxs-lookup"><span data-stu-id="b7fb6-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="b7fb6-107">Microsoft 365 テナントを作成すると、そのテナントを特定の地理的な場所に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7fb6-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="b7fb6-108">また、複数の地理的な場所を持つテナントを持ち、テナントをある場所から別の場所に移動できます。</span><span class="sxs-lookup"><span data-stu-id="b7fb6-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="b7fb6-109">テナントをユーザー、グループ、ライセンス、クラウド アプリの準備を整えるには、テナント構成を慎重に計画して実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7fb6-109">To get your tenant ready for user, groups, licenses, and cloud apps, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="b7fb6-110">教育機関向け Microsoft 365 テナントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="b7fb6-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="b7fb6-111">ネットワークがオンプレミスワーカーとリモート ワーカーの両方に対して Microsoft 365 へのアクセス用に最適化された後、次の大きなタスクは、microsoft 365 テナントを DNS ドメイン 名、一般的なサービス、およびセキュリティで保護されたユーザー サインインをサポートする ID インフラストラクチャ用に計画し、構成します。</span><span class="sxs-lookup"><span data-stu-id="b7fb6-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

### <a name="plan"></a><span data-ttu-id="b7fb6-112">計画</span><span class="sxs-lookup"><span data-stu-id="b7fb6-112">Plan</span></span>

<span data-ttu-id="b7fb6-113">テナントの実装を計画するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="b7fb6-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="b7fb6-114">サブスクリプション、ライセンス、および Azure Active Directory (Azure Active Directory) テナントAD理解する</span><span class="sxs-lookup"><span data-stu-id="b7fb6-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="b7fb6-115">サードパーティの SSL 証明書の使い方を理解する</span><span class="sxs-lookup"><span data-stu-id="b7fb6-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="b7fb6-116">Microsoft 365 テナントと Azure サービスの統合方法ADする</span><span class="sxs-lookup"><span data-stu-id="b7fb6-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="b7fb6-117">クライアント アプリのサポートを計画する</span><span class="sxs-lookup"><span data-stu-id="b7fb6-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="b7fb6-118">ハイブリッドモダン認証の使い方を決定する</span><span class="sxs-lookup"><span data-stu-id="b7fb6-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="b7fb6-119">2007 Office 2010 年のアップグレードOffice計画する</span><span class="sxs-lookup"><span data-stu-id="b7fb6-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="b7fb6-120">テナントの分離について</span><span class="sxs-lookup"><span data-stu-id="b7fb6-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a><span data-ttu-id="b7fb6-121">展開</span><span class="sxs-lookup"><span data-stu-id="b7fb6-121">Deploy</span></span>

<span data-ttu-id="b7fb6-122">テナントを展開するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="b7fb6-122">To deploy your tenant:</span></span> 

- <span data-ttu-id="b7fb6-123">組織の [DNS ドメイン](../admin/setup/add-domain.md) を追加します。</span><span class="sxs-lookup"><span data-stu-id="b7fb6-123">Add the [DNS domains](../admin/setup/add-domain.md) for your organization.</span></span>
- <span data-ttu-id="b7fb6-124">Microsoft [365 管理センターのセットアップ ガイドを使用します](setup-guides-for-microsoft-365.md)。</span><span class="sxs-lookup"><span data-stu-id="b7fb6-124">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="b7fb6-125">ID インフラストラクチャを[構築し、](identity-roadmap-microsoft-365.md)[ユーザー サインインをセキュリティで保護します](microsoft-365-secure-sign-in.md)。</span><span class="sxs-lookup"><span data-stu-id="b7fb6-125">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="b7fb6-126">テナントの地理的な場所を移動する</span><span class="sxs-lookup"><span data-stu-id="b7fb6-126">Move a tenant's geographic locations</span></span>

<span data-ttu-id="b7fb6-127">Microsoft は、Microsoft 365 サービスの新しいデータセンター地理的な場所 (geos) を引き続き開きます。</span><span class="sxs-lookup"><span data-stu-id="b7fb6-127">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="b7fb6-128">これらの新しいデータセンター geos は、顧客の需要と使用状況の増加をサポートするために容量と計算リソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="b7fb6-128">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="b7fb6-129">さらに、新しいデータセンター geo では、コア カスタマー データを geo 内に常駐できます。</span><span class="sxs-lookup"><span data-stu-id="b7fb6-129">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="b7fb6-130">詳細については、「コア データを [新しい Microsoft 365](moving-data-to-new-datacenter-geos.md)データセンター geos に移動する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7fb6-130">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="b7fb6-131">Microsoft 365 Multi-Geo の展開</span><span class="sxs-lookup"><span data-stu-id="b7fb6-131">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="b7fb6-132">Microsoft 365 Multi-Geo を使用すれば、組織はその組織の Microsoft 365 のプレゼンスを、その既存のテナント内の複数の地域または国に対して展開することができます。</span><span class="sxs-lookup"><span data-stu-id="b7fb6-132">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="b7fb6-133">詳細については、「[Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7fb6-133">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenants"></a><span data-ttu-id="b7fb6-134">複数の Microsoft 365 テナントを管理する</span><span class="sxs-lookup"><span data-stu-id="b7fb6-134">Manage multiple Microsoft 365 tenants</span></span> 

<span data-ttu-id="b7fb6-135">oganization に 1 つのテナントを持つことは理想的ですが、複数のテナントを持つ多くの組織の 1 つになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b7fb6-135">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenants.</span></span> <span data-ttu-id="b7fb6-136">理由としては、合併や買収、管理上の分離が必要な場合、または分散 IT が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="b7fb6-136">Reasons can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="b7fb6-137">複数の Microsoft 365 テナントがある場合は、以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7fb6-137">If you have multiple Microsoft 365 tenants, see these articles for more information about:</span></span>

- [<span data-ttu-id="b7fb6-138">テナント間コラボレーション</span><span class="sxs-lookup"><span data-stu-id="b7fb6-138">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="b7fb6-139">テナント間でのメールボックスの移行</span><span class="sxs-lookup"><span data-stu-id="b7fb6-139">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="b7fb6-140">テナントからテナントへの移行</span><span class="sxs-lookup"><span data-stu-id="b7fb6-140">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a><span data-ttu-id="b7fb6-141">次の手順</span><span class="sxs-lookup"><span data-stu-id="b7fb6-141">Next step</span></span>

<span data-ttu-id="b7fb6-142">サブスクリプション、ライセンス、アカウント、 [テナントを使用してテナント計画を開始します](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)。</span><span class="sxs-lookup"><span data-stu-id="b7fb6-142">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>