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
ms.openlocfilehash: 540d1bc53ac06b85d22a8a60a62e51761e10339c
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315755"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="16a51-103">Microsoft 365 のテナントロードマップ</span><span class="sxs-lookup"><span data-stu-id="16a51-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="16a51-104">Microsoft 365 テナントは、組織に割り当てられた一連のサービスです。</span><span class="sxs-lookup"><span data-stu-id="16a51-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="16a51-105">このテナントは、通常、1つ以上の DNS ドメイン名に関連付けられており、さまざまなサブスクリプションのための中央のコンテナーとして機能し、ユーザーアカウントに割り当てられているライセンスに含まれるものとして機能します。</span><span class="sxs-lookup"><span data-stu-id="16a51-105">This tenant is typically associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> 

<span data-ttu-id="16a51-106">Microsoft 365 テナントを作成するときは、特定の地理的な場所に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="16a51-106">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="16a51-107">また、複数の地理的な場所を持つテナントを作成し、テナントをある場所から別の場所に移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="16a51-107">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="16a51-108">ネットワークと id の基本的なサービスを準備するには、適切に計画され、実行されるテナントの構成が重要です。</span><span class="sxs-lookup"><span data-stu-id="16a51-108">A well-planned and executed tenant configuration is critical to getting it ready for the foundational services of networking and identity.</span></span>

## <a name="plan"></a><span data-ttu-id="16a51-109">計画</span><span class="sxs-lookup"><span data-stu-id="16a51-109">Plan</span></span>

<span data-ttu-id="16a51-110">テナントの実装を計画するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="16a51-110">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="16a51-111">サブスクリプション、ライセンス、および Azure Active Directory (Azure AD) テナントについて理解する</span><span class="sxs-lookup"><span data-stu-id="16a51-111">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="16a51-112">サードパーティの SSL 証明書の使用方法を理解する</span><span class="sxs-lookup"><span data-stu-id="16a51-112">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="16a51-113">Microsoft 365 管理センターでのセットアップガイドへのアクセス</span><span class="sxs-lookup"><span data-stu-id="16a51-113">Access setup guides in the Microsoft 365 admin center</span></span>](setup-guides-for-microsoft-365.md)
- [<span data-ttu-id="16a51-114">Microsoft 365 テナントを Azure AD サービスと統合する方法を理解する</span><span class="sxs-lookup"><span data-stu-id="16a51-114">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="16a51-115">クライアントアプリのサポートを計画する</span><span class="sxs-lookup"><span data-stu-id="16a51-115">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="16a51-116">ハイブリッド先進認証の使用方法を決定する</span><span class="sxs-lookup"><span data-stu-id="16a51-116">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="16a51-117">Office 2007 および Office 2010 のアップグレードを計画する</span><span class="sxs-lookup"><span data-stu-id="16a51-117">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="16a51-118">テナントの分離について</span><span class="sxs-lookup"><span data-stu-id="16a51-118">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="16a51-119">Microsoft 365 サービスアシュアランスの詳細を取得する</span><span class="sxs-lookup"><span data-stu-id="16a51-119">Get the details on Microsoft 365 service assurance</span></span>](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a><span data-ttu-id="16a51-120">展開</span><span class="sxs-lookup"><span data-stu-id="16a51-120">Deploy</span></span>

<span data-ttu-id="16a51-121">テナントを展開するには、組織の [DNS ドメインを追加](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) します。</span><span class="sxs-lookup"><span data-stu-id="16a51-121">To deploy your tenant, [add the DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>

## <a name="tenants-with-multiple-geographic-locations"></a><span data-ttu-id="16a51-122">複数の地理的な場所を持つテナント</span><span class="sxs-lookup"><span data-stu-id="16a51-122">Tenants with multiple geographic locations</span></span>

<span data-ttu-id="16a51-123">Microsoft 365 Multi-Geo を使用すれば、組織はその組織の Microsoft 365 のプレゼンスを、その既存のテナント内の複数の地域または国に対して展開することができます。</span><span class="sxs-lookup"><span data-stu-id="16a51-123">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="16a51-124">Microsoft 365 複数地域を使用して、理解、計画、構成、管理を[開始](microsoft-365-multi-geo.md)します。</span><span class="sxs-lookup"><span data-stu-id="16a51-124">[Get started](microsoft-365-multi-geo.md) in understanding, planning, configuring, and then administering with Microsoft 365 Multi-Geo.</span></span>

## <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="16a51-125">テナントの地理的な場所を移動する</span><span class="sxs-lookup"><span data-stu-id="16a51-125">Move a tenant's geographic locations</span></span>

<span data-ttu-id="16a51-126">Microsoft は、Microsoft 365 services の新しいデータセンターの地理的な場所 (geo) を引き続き開きます。</span><span class="sxs-lookup"><span data-stu-id="16a51-126">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="16a51-127">これらの新しいデータセンター geo は、お客様の需要と利用状況の拡大をサポートするための容量とコンピューティングリソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="16a51-127">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="16a51-128">さらに、新しいデータセンター geo では、コア カスタマー データを geo 内に常駐できます。</span><span class="sxs-lookup"><span data-stu-id="16a51-128">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="16a51-129">[コアデータを新しい Microsoft 365 データセンター geo に移行する](moving-data-to-new-datacenter-geos.md)ことで、geo データの移行について理解し、要求する作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="16a51-129">Get started in understanding and requesting a geo data move with [Moving core data to new Microsoft 365 datacenter geo](moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="16a51-130">次の手順</span><span class="sxs-lookup"><span data-stu-id="16a51-130">Next step</span></span>

<span data-ttu-id="16a51-131">[サブスクリプション、ライセンス、アカウント、テナント](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)を使用して、テナントの計画を開始します。</span><span class="sxs-lookup"><span data-stu-id="16a51-131">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

