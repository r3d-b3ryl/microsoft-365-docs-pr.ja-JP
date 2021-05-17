---
title: Microsoft 365分離とアクセス制御 (Azure Active Directory
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
description: この記事では、分離とアクセス制御が機能して、複数のテナントのデータを複数のテナント間で分離Azure Active Directory。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 198e1f37a7378d14d5a4ad28d5bce9d480b2c49e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332414"
---
# <a name="microsoft-365-isolation-and-access-control-in-azure-active-directory"></a><span data-ttu-id="cdd78-103">Microsoft 365分離とアクセス制御 (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="cdd78-103">Microsoft 365 Isolation and Access Control in Azure Active Directory</span></span>

<span data-ttu-id="cdd78-104">Azure Active Directory (Azure AD) は、論理的なデータ分離を通じて、高度に安全な方法で複数のテナントをホストするように設計されています。</span><span class="sxs-lookup"><span data-stu-id="cdd78-104">Azure Active Directory (Azure AD) was designed to host multiple tenants in a highly secure way through logical data isolation.</span></span> <span data-ttu-id="cdd78-105">Azure ADへのアクセスは、承認層によってゲートされます。</span><span class="sxs-lookup"><span data-stu-id="cdd78-105">Access to Azure AD is gated by an authorization layer.</span></span> <span data-ttu-id="cdd78-106">Azure ADは、テナント コンテナーを使用している顧客をセキュリティの境界として分離し、共同テナントがコンテンツにアクセスしたり侵害したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cdd78-106">Azure AD isolates customers using tenant containers as security boundaries to safeguard a customer's content so that the content cannot be accessed or compromised by co-tenants.</span></span> <span data-ttu-id="cdd78-107">Azure ADの承認層では、次の 3 つのチェックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="cdd78-107">Three checks are performed by Azure AD's authorization layer:</span></span>

- <span data-ttu-id="cdd78-108">プリンシパルで Azure テナントへのアクセスが有効ADか。</span><span class="sxs-lookup"><span data-stu-id="cdd78-108">Is the principal enabled for access to Azure AD tenant?</span></span>
- <span data-ttu-id="cdd78-109">プリンシパルは、このテナント内のデータへのアクセスを有効にしていますか?</span><span class="sxs-lookup"><span data-stu-id="cdd78-109">Is the principal enabled for access to data in this tenant?</span></span>
- <span data-ttu-id="cdd78-110">このテナントのプリンシパルの役割は、要求されたデータ アクセスの種類に対して承認されていますか?</span><span class="sxs-lookup"><span data-stu-id="cdd78-110">Is the principal's role in this tenant authorized for the type of data access requested?</span></span>

<span data-ttu-id="cdd78-111">アプリケーション、ユーザー、サーバー、またはサービスは、適切な認証AD証明書なしで Azure サーバーにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="cdd78-111">No application, user, server, or service can access Azure AD without the proper authentication and token or certificate.</span></span> <span data-ttu-id="cdd78-112">要求が適切な資格情報を伴う場合、要求は拒否されます。</span><span class="sxs-lookup"><span data-stu-id="cdd78-112">Requests are rejected if they are not accompanied by proper credentials.</span></span>

<span data-ttu-id="cdd78-113">事実上、Azure ADは、テナントが所有および管理するコンテナーに対するポリシーとアクセス許可を持つ、独自の保護されたコンテナー内で各テナントをホストします。</span><span class="sxs-lookup"><span data-stu-id="cdd78-113">Effectively, Azure AD hosts each tenant in its own protected container, with policies and permissions to and within the container solely owned and managed by the tenant.</span></span>
 
![Azure コンテナー](../media/office-365-isolation-azure-container.png)

<span data-ttu-id="cdd78-115">テナント コンテナーの概念は、ポータルから永続的な記憶域まで、すべてのレイヤーでディレクトリ サービスに深く根付きます。</span><span class="sxs-lookup"><span data-stu-id="cdd78-115">The concept of tenant containers is deeply ingrained in the directory service at all layers, from portals all the way to persistent storage.</span></span> <span data-ttu-id="cdd78-116">複数の Azure AD テナント メタデータが同じ物理ディスクに格納されている場合でも、ディレクトリ サービスで定義されている内容以外のコンテナー間には関係が存在し、テナント管理者が指示します。</span><span class="sxs-lookup"><span data-stu-id="cdd78-116">Even when multiple Azure AD tenant metadata is stored on the same physical disk, there is no relationship between the containers other than what is defined by the directory service, which in turn is dictated by the tenant administrator.</span></span> <span data-ttu-id="cdd78-117">要求するアプリケーションまたはサービスから Azure ADストレージへの直接接続は、最初に承認層を介さずに行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdd78-117">There can be no direct connections to Azure AD storage from any requesting application or service without first going through the authorization layer.</span></span>

<span data-ttu-id="cdd78-118">次の例では、Contoso と Fabrikam の両方に個別の専用コンテナーが用意されています。また、これらのコンテナーは、サーバーやストレージなど、同じ基になるインフラストラクチャの一部を共有している場合でも、互いに分離され、承認とアクセス制御の層によってゲートされます。</span><span class="sxs-lookup"><span data-stu-id="cdd78-118">In the example below, Contoso and Fabrikam both have separate, dedicated containers, and even though those containers may share some of the same underlying infrastructure, such as servers and storage, they remain separate and isolated from each other, and gated by layers of authorization and access control.</span></span>
 
![Azure 専用コンテナー](../media/office-365-isolation-azure-dedicated-containers.png)

<span data-ttu-id="cdd78-120">また、Azure AD 内から実行できるアプリケーション コンポーネントは存在しません。また、あるテナントが別のテナントの整合性を強制的に侵害したり、別のテナントの暗号化キーにアクセスしたり、サーバーから生データを読み取りしたりできません。</span><span class="sxs-lookup"><span data-stu-id="cdd78-120">In addition, there are no application components that can execute from within Azure AD, and it is not possible for one tenant to forcibly breach the integrity of another tenant, access encryption keys of another tenant, or read raw data from the server.</span></span>

<span data-ttu-id="cdd78-121">既定では、Azure ADは、他のテナントの ID によって発行されるすべての操作を禁止します。</span><span class="sxs-lookup"><span data-stu-id="cdd78-121">By default, Azure AD disallows all operations issued by identities in other tenants.</span></span> <span data-ttu-id="cdd78-122">各テナントは、クレーム ベースのアクセス制御AD Azure サーバー内で論理的に分離されます。</span><span class="sxs-lookup"><span data-stu-id="cdd78-122">Each tenant is logically isolated within Azure AD through claims-based access controls.</span></span> <span data-ttu-id="cdd78-123">ディレクトリ データの読み取りと書き込みはテナント コンテナーに対してスコープ設定され、内部抽象化層と役割ベースのアクセス制御 (RBAC) レイヤーによってゲートされ、テナントがセキュリティ境界として強制されます。</span><span class="sxs-lookup"><span data-stu-id="cdd78-123">Reads and writes of directory data are scoped to tenant containers, and gated by an internal abstraction layer and a role-based access control (RBAC) layer, which together enforce the tenant as the security boundary.</span></span> <span data-ttu-id="cdd78-124">すべてのディレクトリ データ アクセス要求は、これらの層によって処理され、Microsoft 365内のすべてのアクセス要求は、上記のロジックによってポリシー化されます。</span><span class="sxs-lookup"><span data-stu-id="cdd78-124">Every directory data access request is processed by these layers and every access request in Microsoft 365 is policed by the logic above.</span></span>

<span data-ttu-id="cdd78-125">Azure ADには、北アメリカ、米国政府機関、EU、ドイツ、ワールドワイドパーティションがあります。</span><span class="sxs-lookup"><span data-stu-id="cdd78-125">Azure AD has North America, U.S. Government, European Union, Germany, and World Wide partitions.</span></span> <span data-ttu-id="cdd78-126">テナントは 1 つのパーティションに存在し、パーティションには複数のテナントを含めできます。</span><span class="sxs-lookup"><span data-stu-id="cdd78-126">A tenant exists in a single partition, and partitions can contain multiple tenants.</span></span> <span data-ttu-id="cdd78-127">パーティション情報は、ユーザーから抽象化されます。</span><span class="sxs-lookup"><span data-stu-id="cdd78-127">Partition information is abstracted away from users.</span></span> <span data-ttu-id="cdd78-128">特定のパーティション (その中のすべてのテナントを含む) は、複数のデータセンターにレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="cdd78-128">A given partition (including all the tenants within it) is replicated to multiple datacenters.</span></span> <span data-ttu-id="cdd78-129">テナントのパーティションは、テナントのプロパティ (国コードなど) に基づいて選択されます。</span><span class="sxs-lookup"><span data-stu-id="cdd78-129">The partition for a tenant is chosen based on properties of the tenant (e.g., the country code).</span></span> <span data-ttu-id="cdd78-130">各パーティション内のシークレットや他の機密情報は、専用のキーで暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="cdd78-130">Secrets and other sensitive information in each partition is encrypted with a dedicated key.</span></span> <span data-ttu-id="cdd78-131">キーは、新しいパーティションが作成されると自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="cdd78-131">The keys are generated automatically when a new partition is created.</span></span>

<span data-ttu-id="cdd78-132">Azure AD機能は、各ユーザー セッションに固有のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="cdd78-132">Azure AD system functionalities are a unique instance to each user session.</span></span> <span data-ttu-id="cdd78-133">さらに、Azure ADは暗号化テクノロジを使用して、ネットワーク レベルで共有システム リソースを分離し、許可されていない情報の転送や意図しない転送を防止します。</span><span class="sxs-lookup"><span data-stu-id="cdd78-133">In addition, Azure AD uses encryption technologies to provide isolation of shared system resources at the network level to prevent unauthorized and unintended transfer of information.</span></span>
