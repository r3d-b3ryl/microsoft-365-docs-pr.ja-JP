---
title: Microsoft 365 分離コントロール
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
description: Microsoft 365 内で分離制御がどのように機能するかについて説明します。サービスは必要に応じて運用間または自律的な状態を維持できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 514b12e44d9e81a18b691ebf3196a3d21157e71b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918944"
---
# <a name="microsoft-365-isolation-controls"></a><span data-ttu-id="eddac-103">Microsoft 365 分離コントロール</span><span class="sxs-lookup"><span data-stu-id="eddac-103">Microsoft 365 isolation controls</span></span> 

<span data-ttu-id="eddac-104">Microsoft は継続的に、Microsoft 365 のマルチテナント アーキテクチャがエンタープライズ レベルのセキュリティ、機密性、プライバシー、整合性、ローカル、国際、可用性の[](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)標準をサポートします。</span><span class="sxs-lookup"><span data-stu-id="eddac-104">Microsoft continuously works to ensure that the multi-tenant architecture of Microsoft 365 supports enterprise-level security, confidentiality, privacy, integrity, local, international, and availability [standards](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons).</span></span> <span data-ttu-id="eddac-105">Microsoft が提供するサービスの規模と範囲により、Microsoft 365 を大幅な人間のやり取りで管理することは困難で経済的ではありません。</span><span class="sxs-lookup"><span data-stu-id="eddac-105">The scale and the scope of services provided by Microsoft make it difficult and non-economical to manage Microsoft 365 with significant human interaction.</span></span> <span data-ttu-id="eddac-106">Microsoft 365 サービスは、複数のグローバルに分散されたデータ センターを介して提供され、それぞれが高度に自動化され、人間のタッチや顧客コンテンツへのアクセスを必要とする操作が少ない。</span><span class="sxs-lookup"><span data-stu-id="eddac-106">Microsoft 365 services are provided through multiple globally distributed data centers, each highly automated with few operations requiring a human touch or any access to customer content.</span></span> <span data-ttu-id="eddac-107">弊社のスタッフは、自動化されたツールと高度に安全なリモート アクセスを使用して、これらのサービスとデータ センターをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="eddac-107">Our staff supports these services and data centers using automated tools and highly secure remote access.</span></span> 

<span data-ttu-id="eddac-108">Microsoft 365 は、重要なビジネス機能を提供し、Microsoft 365 エクスペリエンス全体に貢献する複数のサービスで構成されています。</span><span class="sxs-lookup"><span data-stu-id="eddac-108">Microsoft 365 is composed of multiple services that provide important business functionality and contribute to the entire Microsoft 365 experience.</span></span> <span data-ttu-id="eddac-109">これらの各サービスは、自己格納型であり、互いに統合するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="eddac-109">Each of these services is self-contained and designed to integrate with one another.</span></span>

<span data-ttu-id="eddac-110">Microsoft 365 は、次の原則に従って設計されています。</span><span class="sxs-lookup"><span data-stu-id="eddac-110">Microsoft 365 is designed with the following principles:</span></span>

 - <span data-ttu-id="eddac-111">**[サービス指向アーキテクチャ](/previous-versions/aa480021(v=msdn.10)): 適切** に定義されたビジネス機能を提供する相互運用可能なサービスの形式でソフトウェアを設計および開発します。</span><span class="sxs-lookup"><span data-stu-id="eddac-111">**[Service-Oriented Architecture](/previous-versions/aa480021(v=msdn.10)):** designing and developing software in the form of interoperable services providing well-defined business functionality.</span></span>
 - <span data-ttu-id="eddac-112">**[運用セキュリティアシュア](https://www.microsoft.com/download/details.aspx?id=40872)ランス:** [Microsoft](https://www.microsoft.com/sdl/default.aspx)セキュリティ開発ライフサイクル [、Microsoft](https://technet.microsoft.com/library/dn440717.aspx)セキュリティ応答センター、サイバーセキュリティ脅威の状況に対する深い認識など、Microsoft 固有のさまざまな機能によって得られる知識を組み込んだフレームワーク。</span><span class="sxs-lookup"><span data-stu-id="eddac-112">**[Operational Security Assurance](https://www.microsoft.com/download/details.aspx?id=40872):** a framework that incorporates the knowledge gained through various capabilities that are unique to Microsoft, including the Microsoft [Security Development Lifecycle](https://www.microsoft.com/sdl/default.aspx), the [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx), and deep awareness of the cybersecurity threat landscape.</span></span>

<span data-ttu-id="eddac-113">Microsoft 365 サービスは相互に運用されますが、互いに独立した自律サービスとして展開および運用できるよう設計および実装されています。</span><span class="sxs-lookup"><span data-stu-id="eddac-113">Microsoft 365 services inter-operate with each other, but are designed and implemented so they can be deployed and operated as autonomous services, independent of each other.</span></span> <span data-ttu-id="eddac-114">Microsoft は、組織の資産の無許可または意図しない変更または誤用の機会を減らすために、Microsoft 365 の義務と責任領域を分離します。</span><span class="sxs-lookup"><span data-stu-id="eddac-114">Microsoft segregates duties and areas of responsibility for Microsoft 365 to reduce opportunities for unauthorized or unintentional modification or misuse of the organization's assets.</span></span> <span data-ttu-id="eddac-115">Microsoft 365 チームは、役割を包括的な役割ベースのアクセス制御メカニズムの一部として定義しています。</span><span class="sxs-lookup"><span data-stu-id="eddac-115">Microsoft 365 teams have defined roles as part of a comprehensive role-based access control mechanism.</span></span>

## <a name="customer-content-isolation"></a><span data-ttu-id="eddac-116">顧客コンテンツの分離</span><span class="sxs-lookup"><span data-stu-id="eddac-116">Customer content isolation</span></span>

<span data-ttu-id="eddac-117">テナント内のすべての顧客コンテンツは、他のテナントと、Microsoft 365 の管理で使用される運用およびシステム データから分離されます。</span><span class="sxs-lookup"><span data-stu-id="eddac-117">All customer content in a tenant is isolated from other tenants and from operations and systems data used in the management of Microsoft 365.</span></span> <span data-ttu-id="eddac-118">Microsoft 365 には複数の保護形態が実装されており、Microsoft 365 のサービスやアプリケーションが侵害される危険を最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="eddac-118">Multiple forms of protection are implemented throughout Microsoft 365 to minimize the risk of compromise of any Microsoft 365 service or application.</span></span> <span data-ttu-id="eddac-119">複数の形式の保護により、テナントまたは Microsoft 365 システム自体の情報への不正アクセスも防止されます。</span><span class="sxs-lookup"><span data-stu-id="eddac-119">Multiple forms of protection also prevent unauthorized access to the information of tenants or the Microsoft 365 system itself.</span></span>

<span data-ttu-id="eddac-120">Microsoft が Microsoft 365 内でテナント データの論理的な分離を実装する方法については [、「Microsoft 365](microsoft-365-tenant-isolation-overview.md)のテナント分離」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eddac-120">For information about how Microsoft implements logical isolation of tenant data within Microsoft 365, see [Tenant Isolation in Microsoft 365](microsoft-365-tenant-isolation-overview.md).</span></span>