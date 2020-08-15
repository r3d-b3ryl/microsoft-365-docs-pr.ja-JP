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
ms.collection: M365-subscription-management
ms.custom: it-pro
description: Microsoft 365 用のテナントをセットアップするためのロードマップ。
ms.openlocfilehash: db7054d1f6afc7e4835507dc6415e0b240918c1f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692175"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="2d63b-103">Microsoft 365 のテナントロードマップ</span><span class="sxs-lookup"><span data-stu-id="2d63b-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="2d63b-104">Microsoft 365 テナントは、組織に割り当てられた一連のサービスです。</span><span class="sxs-lookup"><span data-stu-id="2d63b-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="2d63b-105">このテナントは、通常、1つ以上の DNS ドメイン名に関連付けられており、さまざまなサブスクリプションのための中央のコンテナーとして機能し、ユーザーアカウントに割り当てられているライセンスに含まれるものとして機能します。</span><span class="sxs-lookup"><span data-stu-id="2d63b-105">This tenant is typically associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> 

<span data-ttu-id="2d63b-106">Microsoft 365 テナントを作成するときは、特定の地理的な場所に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2d63b-106">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="2d63b-107">また、複数の地理的な場所を持つテナントを作成し、テナントをある場所から別の場所に移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="2d63b-107">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="2d63b-108">ネットワークと id の基本的なサービスを準備するには、適切に計画され、実行されるテナントの構成が重要です。</span><span class="sxs-lookup"><span data-stu-id="2d63b-108">A well-planned and executed tenant configuration is critical to getting it ready for the foundational services of networking and identity.</span></span>

## <a name="plan"></a><span data-ttu-id="2d63b-109">プラン</span><span class="sxs-lookup"><span data-stu-id="2d63b-109">Plan</span></span>

<span data-ttu-id="2d63b-110">テナント実装の計画段階で、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2d63b-110">In the planning phase of your tenant implementation:</span></span>

- [<span data-ttu-id="2d63b-111">サブスクリプション、ライセンス、および Azure Active Directory (Azure AD) テナントについて理解する</span><span class="sxs-lookup"><span data-stu-id="2d63b-111">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="2d63b-112">サードパーティの SSL 証明書の使用方法を理解する</span><span class="sxs-lookup"><span data-stu-id="2d63b-112">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="2d63b-113">Microsoft 365 管理センターでのセットアップガイドへのアクセス</span><span class="sxs-lookup"><span data-stu-id="2d63b-113">Access setup guides in the Microsoft 365 admin center</span></span>](setup-guides-for-microsoft-365.md)
- [<span data-ttu-id="2d63b-114">Microsoft 365 テナントを Azure AD サービスと統合する方法を理解する</span><span class="sxs-lookup"><span data-stu-id="2d63b-114">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="2d63b-115">クライアントアプリのサポートを計画する</span><span class="sxs-lookup"><span data-stu-id="2d63b-115">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="2d63b-116">ハイブリッド先進認証の使用方法を決定する</span><span class="sxs-lookup"><span data-stu-id="2d63b-116">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="2d63b-117">Office 2007 および Office 2010 のアップグレードを計画する</span><span class="sxs-lookup"><span data-stu-id="2d63b-117">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="2d63b-118">テナントの分離について</span><span class="sxs-lookup"><span data-stu-id="2d63b-118">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="2d63b-119">Microsoft 365 サービスアシュアランスの詳細を取得する</span><span class="sxs-lookup"><span data-stu-id="2d63b-119">Get the details on Microsoft 365 service assurance</span></span>](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a><span data-ttu-id="2d63b-120">展開</span><span class="sxs-lookup"><span data-stu-id="2d63b-120">Deploy</span></span>

<span data-ttu-id="2d63b-121">テナント実装の展開フェーズで、組織の [DNS ドメインを追加](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) します。</span><span class="sxs-lookup"><span data-stu-id="2d63b-121">In the deployment phase of your tenant implementation, [add the DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>

## <a name="tenants-with-multiple-geographic-locations"></a><span data-ttu-id="2d63b-122">複数の地理的な場所を持つテナント</span><span class="sxs-lookup"><span data-stu-id="2d63b-122">Tenants with multiple geographic locations</span></span>

<span data-ttu-id="2d63b-123">Microsoft 365 Multi-Geo を使用すれば、組織はその組織の Microsoft 365 のプレゼンスを、その既存のテナント内の複数の地域または国に対して展開することができます。</span><span class="sxs-lookup"><span data-stu-id="2d63b-123">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="2d63b-124">Microsoft 365 複数地域を使用して、理解、計画、構成、管理を[開始](microsoft-365-multi-geo.md)します。</span><span class="sxs-lookup"><span data-stu-id="2d63b-124">[Get started](microsoft-365-multi-geo.md) in understanding, planning, configuring, and then administering with Microsoft 365 Multi-Geo.</span></span>

## <a name="moving-a-tenants-geographic-locations"></a><span data-ttu-id="2d63b-125">テナントの地理的な場所の移動</span><span class="sxs-lookup"><span data-stu-id="2d63b-125">Moving a tenant's geographic locations</span></span>

<span data-ttu-id="2d63b-126">Microsoft は、Microsoft 365 services の新しいデータセンターの地理的な場所 (geo) を引き続き開きます。</span><span class="sxs-lookup"><span data-stu-id="2d63b-126">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="2d63b-127">これらの新しいデータセンター geo は、お客様の需要と利用状況の拡大をサポートするための容量とコンピューティングリソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="2d63b-127">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="2d63b-128">さらに、新しいデータセンター geo では、コア カスタマー データを geo 内に常駐できます。</span><span class="sxs-lookup"><span data-stu-id="2d63b-128">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="2d63b-129">[コアデータを新しい Microsoft 365 データセンター geo に移行する](moving-data-to-new-datacenter-geos.md)ことで、geo データの移行について理解し、要求する作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="2d63b-129">Get started in understanding and requesting a geo data move with [Moving core data to new Microsoft 365 datacenter geo](moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="2d63b-130">次の手順</span><span class="sxs-lookup"><span data-stu-id="2d63b-130">Next step</span></span>

<span data-ttu-id="2d63b-131">[サブスクリプション、ライセンス、アカウント、テナント](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)を使用して、テナントの計画を開始します。</span><span class="sxs-lookup"><span data-stu-id="2d63b-131">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

