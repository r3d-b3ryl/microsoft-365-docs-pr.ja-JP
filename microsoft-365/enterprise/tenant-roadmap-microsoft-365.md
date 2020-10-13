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
ms.openlocfilehash: 0f1fa91bb81fd6cc87820f2b2d48e00e1b75a0c4
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446009"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="117a0-103">Microsoft 365 のテナントロードマップ</span><span class="sxs-lookup"><span data-stu-id="117a0-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="117a0-104">Microsoft 365 テナントは、組織に割り当てられた一連のサービスです。</span><span class="sxs-lookup"><span data-stu-id="117a0-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="117a0-105">通常、このテナントは1つ以上の DNS ドメイン名に関連付けられており、さまざまなサブスクリプションのための中央のコンテナーとして機能し、ユーザーアカウントに割り当てられているライセンスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="117a0-105">Typically, this tenant is associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span>

<span data-ttu-id="117a0-106">Microsoft 365 テナントを作成するときは、特定の地理的な場所に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="117a0-106">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="117a0-107">また、複数の地理的な場所を持つテナントを作成し、テナントをある場所から別の場所に移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="117a0-107">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="117a0-108">ネットワークと id の基本サービスのためにテナントを準備するには、テナントの構成を慎重に計画して実行することが重要です。</span><span class="sxs-lookup"><span data-stu-id="117a0-108">To get your tenant ready for the foundational services of networking and identity, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="plan"></a><span data-ttu-id="117a0-109">計画</span><span class="sxs-lookup"><span data-stu-id="117a0-109">Plan</span></span>

<span data-ttu-id="117a0-110">テナントの実装を計画するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="117a0-110">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="117a0-111">サブスクリプション、ライセンス、および Azure Active Directory (Azure AD) テナントについて理解する</span><span class="sxs-lookup"><span data-stu-id="117a0-111">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="117a0-112">サードパーティの SSL 証明書の使用方法を理解する</span><span class="sxs-lookup"><span data-stu-id="117a0-112">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="117a0-113">Microsoft 365 テナントを Azure AD サービスと統合する方法を理解する</span><span class="sxs-lookup"><span data-stu-id="117a0-113">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="117a0-114">クライアントアプリのサポートを計画する</span><span class="sxs-lookup"><span data-stu-id="117a0-114">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="117a0-115">ハイブリッド先進認証の使用方法を決定する</span><span class="sxs-lookup"><span data-stu-id="117a0-115">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="117a0-116">Office 2007 および Office 2010 のアップグレードを計画する</span><span class="sxs-lookup"><span data-stu-id="117a0-116">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="117a0-117">テナントの分離について</span><span class="sxs-lookup"><span data-stu-id="117a0-117">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="117a0-118">Microsoft 365 サービスアシュアランスの詳細を取得する</span><span class="sxs-lookup"><span data-stu-id="117a0-118">Get the details on Microsoft 365 service assurance</span></span>](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a><span data-ttu-id="117a0-119">展開する</span><span class="sxs-lookup"><span data-stu-id="117a0-119">Deploy</span></span>

<span data-ttu-id="117a0-120">テナントを展開するには、組織の [DNS ドメインを追加](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) し、 [Microsoft 365 管理センターのセットアップガイド](setup-guides-for-microsoft-365.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="117a0-120">To deploy your tenant, [add the DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization and use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>

## <a name="tenants-with-multiple-geographic-locations"></a><span data-ttu-id="117a0-121">複数の地理的な場所を持つテナント</span><span class="sxs-lookup"><span data-stu-id="117a0-121">Tenants with multiple geographic locations</span></span>

<span data-ttu-id="117a0-122">Microsoft 365 Multi-Geo を使用すれば、組織はその組織の Microsoft 365 のプレゼンスを、その既存のテナント内の複数の地域または国に対して展開することができます。</span><span class="sxs-lookup"><span data-stu-id="117a0-122">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="117a0-123">Microsoft 365 の複数地域 (計画、構成、管理方法を含む) の詳細について [は、ここから開始](microsoft-365-multi-geo.md)してください。</span><span class="sxs-lookup"><span data-stu-id="117a0-123">For information about Microsoft 365 Multi-Geo, including how to plan, configure, and administer it, [start here](microsoft-365-multi-geo.md).</span></span>

## <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="117a0-124">テナントの地理的な場所を移動する</span><span class="sxs-lookup"><span data-stu-id="117a0-124">Move a tenant's geographic locations</span></span>

<span data-ttu-id="117a0-125">Microsoft は、Microsoft 365 services の新しいデータセンターの地理的な場所 (geo) を引き続き開きます。</span><span class="sxs-lookup"><span data-stu-id="117a0-125">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="117a0-126">これらの新しいデータセンター geo は、お客様の需要と利用状況の拡大をサポートするための容量とコンピューティングリソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="117a0-126">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="117a0-127">さらに、新しいデータセンター geo では、コア カスタマー データを geo 内に常駐できます。</span><span class="sxs-lookup"><span data-stu-id="117a0-127">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="117a0-128">Geo データの移動を要求する方法を含む、Microsoft 365 データセンター geo の詳細について [は、ここから開始](moving-data-to-new-datacenter-geos.md)してください。</span><span class="sxs-lookup"><span data-stu-id="117a0-128">For information about Microsoft 365 datacenter geo, including how to request a geo data move, [start here](moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="117a0-129">次のステップ</span><span class="sxs-lookup"><span data-stu-id="117a0-129">Next step</span></span>

<span data-ttu-id="117a0-130">[サブスクリプション、ライセンス、アカウント、テナント](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)を使用して、テナントの計画を開始します。</span><span class="sxs-lookup"><span data-stu-id="117a0-130">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

