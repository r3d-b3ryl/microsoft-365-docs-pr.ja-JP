---
title: Microsoft 365 でのテナントの分離
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: この記事では、Microsoft 365 のようなクラウド サービスでテナント分離を適用する方法の概要について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7c5be65186b75f6056a64b776e4f0d25bcd55eb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923078"
---
# <a name="tenant-isolation-in-microsoft-365"></a><span data-ttu-id="6a06e-103">Microsoft 365 でのテナントの分離</span><span class="sxs-lookup"><span data-stu-id="6a06e-103">Tenant Isolation in Microsoft 365</span></span>

<span data-ttu-id="6a06e-104">クラウド コンピューティングの主な利点の 1 つは、多数の顧客間で同時に共有される共通のインフラストラクチャの概念で、規模の経済性につながる点です。</span><span class="sxs-lookup"><span data-stu-id="6a06e-104">One of the primary benefits of cloud computing is concept of a shared, common infrastructure across numerous customers simultaneously, leading to economies of scale.</span></span> <span data-ttu-id="6a06e-105">この概念は、マルチ *テナンシーと呼ばれる。*</span><span class="sxs-lookup"><span data-stu-id="6a06e-105">This concept is called *multi-tenancy*.</span></span> <span data-ttu-id="6a06e-106">Microsoft は、クラウド サービスのマルチテナント アーキテクチャによって、エンタープライズレベルのセキュリティ、機密性、プライバシー、完全性、可用性の基準をサポートするため、継続的に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="6a06e-106">Microsoft works continuously to ensure that the multi-tenant architectures of our cloud services support enterprise-level security, confidentiality, privacy, integrity, and availability standards.</span></span>

<span data-ttu-id="6a06e-107">信頼できるコンピューティングとセキュリティ開発ライフサイクルから収集された多[](https://www.microsoft.com/trust-center)大な投資と経験に[](https://www.microsoft.com/securityengineering/sdl/)基づいて、Microsoft クラウド サービスは、すべてのテナントが他のすべてのテナントに対して敵対的である可能性があるという前提で設計され、あるテナントのアクションが別のテナントのセキュリティやサービスに影響を与え、または別のテナントのコンテンツにアクセスするのを防ぐためのセキュリティ対策を実装しました。</span><span class="sxs-lookup"><span data-stu-id="6a06e-107">Based upon the significant investments and experience gathered from [Trustworthy Computing](https://www.microsoft.com/trust-center) and the [Security Development Lifecycle](https://www.microsoft.com/securityengineering/sdl/), Microsoft cloud services were designed with the assumption that all tenants are potentially hostile to all other tenants, and we have implemented security measures to prevent the actions of one tenant from affecting the security or service of another tenant, or accessing the content of another tenant.</span></span>

<span data-ttu-id="6a06e-108">マルチテナント環境でテナントの分離を維持する 2 つの主な目標は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6a06e-108">The two primary goals of maintaining tenant isolation in a multi-tenant environment are:</span></span>

1.    <span data-ttu-id="6a06e-109">テナント間の顧客コンテンツの漏洩または不正アクセスの防止。そして</span><span class="sxs-lookup"><span data-stu-id="6a06e-109">Preventing leakage of, or unauthorized access to, customer content across tenants; and</span></span>
2.    <span data-ttu-id="6a06e-110">あるテナントのアクションが別のテナントのサービスに悪影響を及ぼすのを防ぐ</span><span class="sxs-lookup"><span data-stu-id="6a06e-110">Preventing the actions of one tenant from adversely affecting the service for another tenant</span></span>

<span data-ttu-id="6a06e-111">Microsoft 365 のサービスやアプリケーションを侵害したり、他のテナントや Microsoft 365 システム自体の情報に対する不正アクセスを防止したりするために、Microsoft 365 全体に複数の保護が実装されています。</span><span class="sxs-lookup"><span data-stu-id="6a06e-111">Multiple forms of protection have been implemented throughout Microsoft 365 to prevent customers from compromising Microsoft 365 services or applications or gaining unauthorized access to the information of other tenants or the Microsoft 365 system itself, including:</span></span>

- <span data-ttu-id="6a06e-112">Microsoft 365 サービスの各テナント内の顧客コンテンツの論理的な分離は、Azure Active Directory の承認と役割ベースのアクセス制御によって実現されます。</span><span class="sxs-lookup"><span data-stu-id="6a06e-112">Logical isolation of customer content within each tenant for Microsoft 365 services is achieved through Azure Active Directory authorization and role-based access control.</span></span>
- <span data-ttu-id="6a06e-113">SharePoint Online は、ストレージ レベルでデータ分離メカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="6a06e-113">SharePoint Online provides data isolation mechanisms at the storage level.</span></span>
- <span data-ttu-id="6a06e-114">Microsoft では、厳密な物理的セキュリティ、バックグラウンド スクリーニング、多層暗号化戦略を使用して、顧客コンテンツの機密性と整合性を保護します。</span><span class="sxs-lookup"><span data-stu-id="6a06e-114">Microsoft uses rigorous physical security, background screening, and a multi-layered encryption strategy to protect the confidentiality and integrity of customer content.</span></span> <span data-ttu-id="6a06e-115">すべての Microsoft 365 データセンターには生体認証アクセス制御が備わっています。ほとんどの場合、物理的なアクセスを得るために手のひらの印刷が必要です。</span><span class="sxs-lookup"><span data-stu-id="6a06e-115">All Microsoft 365 datacenters have biometric access controls, with most requiring palm prints to gain physical access.</span></span> <span data-ttu-id="6a06e-116">さらに、米国に拠点を置く Microsoft のすべての従業員は、採用プロセスの一環として標準のバックグラウンド チェックを正常に完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a06e-116">In addition, all U.S.-based Microsoft employees are required to successfully complete a standard background check as part of the hiring process.</span></span> <span data-ttu-id="6a06e-117">Microsoft 365 の管理アクセスに使用されるコントロールの詳細については [、「Microsoft 365 管理アクセス制御」を参照してください](/compliance/assurance/assurance-administrative-access-controls-overview)。</span><span class="sxs-lookup"><span data-stu-id="6a06e-117">For more information on the controls used for administrative access in Microsoft 365, see [Microsoft 365 Administrative Access Controls](/compliance/assurance/assurance-administrative-access-controls-overview).</span></span>
- <span data-ttu-id="6a06e-118">Microsoft 365 では、BitLocker、ファイルごとの暗号化、トランスポート層セキュリティ (TLS)、インターネット プロトコル セキュリティ (IPsec) など、保存中および転送中の顧客コンテンツを暗号化するサービス側テクノロジを使用します。</span><span class="sxs-lookup"><span data-stu-id="6a06e-118">Microsoft 365 uses service-side technologies that encrypt customer content at rest and in transit, including BitLocker, per-file encryption, Transport Layer Security (TLS) and Internet Protocol Security (IPsec).</span></span> <span data-ttu-id="6a06e-119">Microsoft 365 での暗号化の詳細については [、「Microsoft 365 のデータ暗号化テクノロジ」を参照してください](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="6a06e-119">For specific details about encryption in Microsoft 365, see [Data Encryption Technologies in Microsoft 365](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md).</span></span>

<span data-ttu-id="6a06e-120">上記の保護を組み合わせて、物理的な分離によって提供されるのと同等の脅威保護と軽減策を提供する堅牢な論理分離制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="6a06e-120">Together, the above-listed protections provide robust logical isolation controls that provide threat protection and mitigation equivalent to that provided by physical isolation alone.</span></span>

## <a name="related-links"></a><span data-ttu-id="6a06e-121">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6a06e-121">Related Links</span></span>

- [<span data-ttu-id="6a06e-122">Azure Active Directory での分離とアクセス制御</span><span class="sxs-lookup"><span data-stu-id="6a06e-122">Isolation and Access Control in Azure Active Directory</span></span>](microsoft-365-isolation-in-azure-active-directory.md)
- [<span data-ttu-id="6a06e-123">Office Graph と Delve でのテナントの分離</span><span class="sxs-lookup"><span data-stu-id="6a06e-123">Tenant Isolation in the Office Graph and Delve</span></span>](microsoft-365-isolation-in-graph-and-delve.md)
- [<span data-ttu-id="6a06e-124">Microsoft 365 の検索でのテナントの分離</span><span class="sxs-lookup"><span data-stu-id="6a06e-124">Tenant Isolation in Microsoft 365 Search</span></span>](microsoft-365-isolation-in-microsoft-365-search.md)
- [<span data-ttu-id="6a06e-125">Office 365 でのテナントの分離のビデオ</span><span class="sxs-lookup"><span data-stu-id="6a06e-125">Tenant Isolation in Office 365 Video</span></span>](microsoft-365-isolation-in-microsoft-365-video.md)
- [<span data-ttu-id="6a06e-126">リソースの制限</span><span class="sxs-lookup"><span data-stu-id="6a06e-126">Resource Limits</span></span>](/compliance/assurance/assurance-resource-limits)
- [<span data-ttu-id="6a06e-127">テナント境界の監視とテスト</span><span class="sxs-lookup"><span data-stu-id="6a06e-127">Monitoring and Testing Tenant Boundaries</span></span>](/compliance/assurance/assurance-monitoring-and-testing)
- [<span data-ttu-id="6a06e-128">Microsoft 365 での分離とアクセス制御</span><span class="sxs-lookup"><span data-stu-id="6a06e-128">Isolation and Access Control in Microsoft 365</span></span>](microsoft-365-isolation-in-microsoft-365.md)