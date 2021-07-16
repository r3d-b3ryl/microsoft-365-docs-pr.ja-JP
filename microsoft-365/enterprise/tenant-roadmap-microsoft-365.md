---
title: テナントのロードマップMicrosoft 365
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
description: ユーザーのテナントをセットアップするためのロードマップMicrosoft 365。
ms.openlocfilehash: 4b94540293b86bd922ce4b29f970e52eb1245a01
ms.sourcegitcommit: 84e70051bb61b1171cebfbabe500b4904dfac04f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464035"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="d551b-103">テナントのロードマップMicrosoft 365</span><span class="sxs-lookup"><span data-stu-id="d551b-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="d551b-104">テナントMicrosoft 365は、組織に割り当てられた一連のサービスです。</span><span class="sxs-lookup"><span data-stu-id="d551b-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="d551b-105">通常、このテナントは 1 つ以上のパブリック DNS ドメイン 名に関連付けられるので、さまざまなサブスクリプションとユーザー アカウントに割り当てるライセンスの中央分離コンテナーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="d551b-105">Typically, this tenant is associated with one or more of your public DNS domain names and acts as a central and isolated container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="d551b-106">詳細については、「サブスクリプション、ライセンス、アカウント、および Microsoft のクラウド 製品のテナント」 [を参照してください](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)。</span><span class="sxs-lookup"><span data-stu-id="d551b-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="d551b-107">テナントを作成するMicrosoft 365、そのテナントを特定の地理的な場所に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d551b-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="d551b-108">また、複数の地理的な場所を持つテナントを持ち、テナントをある場所から別の場所に移動できます。</span><span class="sxs-lookup"><span data-stu-id="d551b-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="d551b-109">テナントをユーザー、グループ、ライセンス、クラウド アプリの準備を整えるには、テナント構成を慎重に計画して実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d551b-109">To get your tenant ready for user, groups, licenses, and cloud apps, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="d551b-110">教育機関向け Microsoft 365 テナントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="d551b-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="d551b-111">ネットワークがオンプレミスワーカーとリモート ワーカーの両方に対して Microsoft 365 へのアクセス用に最適化された後、次の大きなタスクは、DNS ドメイン 名、一般的なサービス、およびセキュリティで保護されたユーザー サインインをサポートする id インフラストラクチャ用に Microsoft 365 テナントを計画し、構成します。</span><span class="sxs-lookup"><span data-stu-id="d551b-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

### <a name="plan"></a><span data-ttu-id="d551b-112">計画</span><span class="sxs-lookup"><span data-stu-id="d551b-112">Plan</span></span>

<span data-ttu-id="d551b-113">テナントの実装を計画するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="d551b-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="d551b-114">サブスクリプション、ライセンス、およびサブスクリプション (Azure Azure Active Directory) ADについて</span><span class="sxs-lookup"><span data-stu-id="d551b-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="d551b-115">サードパーティの SSL 証明書の使い方を理解する</span><span class="sxs-lookup"><span data-stu-id="d551b-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="d551b-116">テナントが Azure Microsoft 365 サービスと統合される方法ADする</span><span class="sxs-lookup"><span data-stu-id="d551b-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="d551b-117">クライアント アプリのサポートを計画する</span><span class="sxs-lookup"><span data-stu-id="d551b-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="d551b-118">ハイブリッドモダン認証の使い方を決定する</span><span class="sxs-lookup"><span data-stu-id="d551b-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="d551b-119">2007 Officeおよび 2010 Officeアップグレードを計画する</span><span class="sxs-lookup"><span data-stu-id="d551b-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="d551b-120">テナントの分離について</span><span class="sxs-lookup"><span data-stu-id="d551b-120">Understand tenant isolation</span></span>](/compliance/assurance/microsoft-365-isolation-controls)

### <a name="deploy"></a><span data-ttu-id="d551b-121">展開</span><span class="sxs-lookup"><span data-stu-id="d551b-121">Deploy</span></span>

<span data-ttu-id="d551b-122">テナントを展開するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="d551b-122">To deploy your tenant:</span></span> 

- <span data-ttu-id="d551b-123">組織の [DNS ドメイン](../admin/setup/add-domain.md) を追加します。</span><span class="sxs-lookup"><span data-stu-id="d551b-123">Add the [DNS domains](../admin/setup/add-domain.md) for your organization.</span></span>
- <span data-ttu-id="d551b-124">[設定[ガイド] の [設定ガイドMicrosoft 365 管理センター。](setup-guides-for-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="d551b-124">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="d551b-125">ID インフラストラクチャを[構築し、](identity-roadmap-microsoft-365.md)[ユーザー サインインをセキュリティで保護します](microsoft-365-secure-sign-in.md)。</span><span class="sxs-lookup"><span data-stu-id="d551b-125">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="d551b-126">テナントの地理的な場所を移動する</span><span class="sxs-lookup"><span data-stu-id="d551b-126">Move a tenant's geographic locations</span></span>

<span data-ttu-id="d551b-127">Microsoft は、引き続き新しいデータセンターの地理的な場所 (geos) を開き、Microsoft 365します。</span><span class="sxs-lookup"><span data-stu-id="d551b-127">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="d551b-128">これらの新しいデータセンター geos は、顧客の需要と使用状況の増加をサポートするために容量と計算リソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="d551b-128">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="d551b-129">さらに、新しいデータセンター geo では、コア カスタマー データを geo 内に常駐できます。</span><span class="sxs-lookup"><span data-stu-id="d551b-129">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="d551b-130">詳細については、「コア データを新しいデータセンター geos[にMicrosoft 365する」を参照してください](moving-data-to-new-datacenter-geos.md)。</span><span class="sxs-lookup"><span data-stu-id="d551b-130">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="d551b-131">複数地域Microsoft 365展開する</span><span class="sxs-lookup"><span data-stu-id="d551b-131">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="d551b-132">Microsoft 365 Multi-Geo を使用すれば、組織はその組織の Microsoft 365 のプレゼンスを、その既存のテナント内の複数の地域または国に対して展開することができます。</span><span class="sxs-lookup"><span data-stu-id="d551b-132">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="d551b-133">詳細については、「[Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d551b-133">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenants"></a><span data-ttu-id="d551b-134">複数のテナントMicrosoft 365管理する</span><span class="sxs-lookup"><span data-stu-id="d551b-134">Manage multiple Microsoft 365 tenants</span></span> 

<span data-ttu-id="d551b-135">oganization に 1 つのテナントを持つことは理想的ですが、複数のテナントを持つ多くの組織の 1 つになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d551b-135">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenants.</span></span> <span data-ttu-id="d551b-136">理由としては、合併や買収、管理上の分離が必要な場合、または分散 IT が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d551b-136">Reasons can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="d551b-137">複数のテナントがMicrosoft 365場合は、以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d551b-137">If you have multiple Microsoft 365 tenants, see these articles for more information about:</span></span>

- [<span data-ttu-id="d551b-138">テナント間コラボレーション</span><span class="sxs-lookup"><span data-stu-id="d551b-138">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="d551b-139">テナント間でのメールボックスの移行</span><span class="sxs-lookup"><span data-stu-id="d551b-139">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="d551b-140">テナントからテナントへの移行</span><span class="sxs-lookup"><span data-stu-id="d551b-140">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a><span data-ttu-id="d551b-141">次の手順</span><span class="sxs-lookup"><span data-stu-id="d551b-141">Next step</span></span>

<span data-ttu-id="d551b-142">サブスクリプション、ライセンス、アカウント、 [テナントを使用してテナント計画を開始します](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)。</span><span class="sxs-lookup"><span data-stu-id="d551b-142">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>