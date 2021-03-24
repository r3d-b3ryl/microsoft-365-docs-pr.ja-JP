---
title: 役割ベースのアクセス制御を使用して、Microsoft Defender セキュリティ センターへの詳細なアクセスを許可する
description: セキュリティ操作内に役割とグループを作成して、ポータルへのアクセスを許可します。
keywords: rbac、 role, based, access, control, groups, control, tier, aad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d95163bd7caf6e05295fc35b3f9c2bf95230dc83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063843"
---
# <a name="manage-portal-access-using-role-based-access-control"></a><span data-ttu-id="73d8d-104">役割ベースのアクセス制御を使用してポータル アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="73d8d-104">Manage portal access using role-based access control</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="73d8d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="73d8d-105">**Applies to:**</span></span>
- <span data-ttu-id="73d8d-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="73d8d-106">Azure Active Directory</span></span>
- <span data-ttu-id="73d8d-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="73d8d-107">Office 365</span></span>

> <span data-ttu-id="73d8d-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="73d8d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="73d8d-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="73d8d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-rbac-abovefoldlink)

<span data-ttu-id="73d8d-110">役割ベースのアクセス制御 (RBAC) を使用して、セキュリティ運用チーム内に役割とグループを作成して、ポータルへの適切なアクセスを許可できます。</span><span class="sxs-lookup"><span data-stu-id="73d8d-110">Using role-based access control (RBAC), you can create roles and groups within your security operations team to grant appropriate access to the  portal.</span></span> <span data-ttu-id="73d8d-111">作成する役割とグループに基づいて、ポータルにアクセスできるユーザーが表示および実行できる操作を詳細に制御できます。</span><span class="sxs-lookup"><span data-stu-id="73d8d-111">Based on the roles and groups you create, you have fine-grained control over what users with access to the portal can see and do.</span></span> 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bJ2a]

<span data-ttu-id="73d8d-112">大規模な地域分散セキュリティ運用チームは、通常、階層ベースのモデルを採用して、セキュリティ ポータルへのアクセスを割り当て、承認します。</span><span class="sxs-lookup"><span data-stu-id="73d8d-112">Large geo-distributed security operations teams typically adopt a tier-based model to assign and authorize access to security portals.</span></span> <span data-ttu-id="73d8d-113">一般的な層には、次の 3 つのレベルがあります。</span><span class="sxs-lookup"><span data-stu-id="73d8d-113">Typical tiers include the following three levels:</span></span>

<span data-ttu-id="73d8d-114">階層</span><span class="sxs-lookup"><span data-stu-id="73d8d-114">Tier</span></span> | <span data-ttu-id="73d8d-115">説明</span><span class="sxs-lookup"><span data-stu-id="73d8d-115">Description</span></span>
:---|:---
<span data-ttu-id="73d8d-116">階層 1</span><span class="sxs-lookup"><span data-stu-id="73d8d-116">Tier 1</span></span> | <span data-ttu-id="73d8d-117">**ローカル セキュリティ運用チーム /IT チーム**</span><span class="sxs-lookup"><span data-stu-id="73d8d-117">**Local security operations team / IT team**</span></span> <br> <span data-ttu-id="73d8d-118">このチームは通常、地理的位置内に含まれるアラートをトリアージして調査し、アクティブな修復が必要な場合は階層 2 にエスカレートします。</span><span class="sxs-lookup"><span data-stu-id="73d8d-118">This team usually triages and investigates alerts contained within their geolocation and escalates to Tier 2 in cases where an active remediation is required.</span></span>
<span data-ttu-id="73d8d-119">階層 2</span><span class="sxs-lookup"><span data-stu-id="73d8d-119">Tier 2</span></span> | <span data-ttu-id="73d8d-120">**地域のセキュリティ運用チーム**</span><span class="sxs-lookup"><span data-stu-id="73d8d-120">**Regional security operations team**</span></span> <br> <span data-ttu-id="73d8d-121">このチームは、地域のすべてのデバイスを表示し、修復アクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="73d8d-121">This team can see all the devices for their region and perform remediation actions.</span></span>
<span data-ttu-id="73d8d-122">階層 3</span><span class="sxs-lookup"><span data-stu-id="73d8d-122">Tier 3</span></span> | <span data-ttu-id="73d8d-123">**グローバル セキュリティ運用チーム**</span><span class="sxs-lookup"><span data-stu-id="73d8d-123">**Global security operations team**</span></span> <br> <span data-ttu-id="73d8d-124">このチームはセキュリティ専門家で構成され、ポータルからすべてのアクションを表示して実行する権限があります。</span><span class="sxs-lookup"><span data-stu-id="73d8d-124">This team consists of security experts and are authorized to see and perform all actions from the portal.</span></span>

<span data-ttu-id="73d8d-125">Defender for Endpoint RBAC は、階層ベースまたは役割ベースの選択モデルをサポートするように設計され、表示できる役割、アクセスできるデバイス、実行できるアクションを詳細に制御できます。</span><span class="sxs-lookup"><span data-stu-id="73d8d-125">Defender for Endpoint RBAC is designed to support your tier- or role-based model of choice and gives you granular control over what roles can see, devices they can access, and actions they can take.</span></span> <span data-ttu-id="73d8d-126">RBAC フレームワークは、次のコントロールを中心にしています。</span><span class="sxs-lookup"><span data-stu-id="73d8d-126">The RBAC framework is centered around the following controls:</span></span>

- <span data-ttu-id="73d8d-127">**特定のアクションを実行できるユーザーを制御する**</span><span class="sxs-lookup"><span data-stu-id="73d8d-127">**Control who can take specific action**</span></span>
  - <span data-ttu-id="73d8d-128">カスタム ロールを作成し、詳細にアクセスできる Defender for Endpoint 機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="73d8d-128">Create custom roles and control what Defender for Endpoint capabilities they can access with granularity.</span></span>
 
- <span data-ttu-id="73d8d-129">**特定のデバイス グループまたはグループに関する情報を表示できるユーザーを制御する**</span><span class="sxs-lookup"><span data-stu-id="73d8d-129">**Control who can see information on specific device group or groups**</span></span>
  - <span data-ttu-id="73d8d-130">[名前、タグ](machine-groups.md) 、ドメインなどの特定の条件によってデバイス グループを作成し、特定の AD Azure Active Directory (Azure Active Directory) ユーザー グループを使用して、そのグループにロール アクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="73d8d-130">[Create device groups](machine-groups.md) by specific criteria such as names, tags, domains, and others, then grant role access to them using a specific  Azure Active Directory (Azure AD) user group.</span></span>

<span data-ttu-id="73d8d-131">役割ベースのアクセスを実装するには、管理者ロールを定義し、対応するアクセス許可を割り当て、役割に割り当てられた Azure ADグループを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="73d8d-131">To implement role-based access, you'll need to define admin roles, assign corresponding permissions, and assign Azure AD user groups assigned to the roles.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="73d8d-132">はじめに</span><span class="sxs-lookup"><span data-stu-id="73d8d-132">Before you begin</span></span>
<span data-ttu-id="73d8d-133">RBAC を使用する前に、アクセス許可を付与できる役割と RBAC をオンにした結果を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="73d8d-133">Before using RBAC, it's important that you understand the roles that can grant permissions and the consequences of turning on RBAC.</span></span>


> [!WARNING]
> <span data-ttu-id="73d8d-134">機能を有効にする前に、Azure AD でグローバル管理者の役割またはセキュリティ管理者の役割を持ち、ポータルからロックアウトされるリスクを軽減するために Azure AD グループを準備することが重要です。</span><span class="sxs-lookup"><span data-stu-id="73d8d-134">Before enabling the feature, it's important that you have a Global Administrator role or Security Administrator role in Azure AD and that you have your Azure AD groups ready to reduce the risk of being locked out of the portal.</span></span> 

<span data-ttu-id="73d8d-135">Microsoft Defender セキュリティ センターに初めてログインすると、フル アクセスまたは読み取り専用アクセスが付与されます。</span><span class="sxs-lookup"><span data-stu-id="73d8d-135">When you first log in to Microsoft Defender Security Center, you're granted either full access or read only access.</span></span> <span data-ttu-id="73d8d-136">Azure 管理者のセキュリティ管理者またはグローバル管理者の役割を持つユーザーには、完全なアクセス権AD。</span><span class="sxs-lookup"><span data-stu-id="73d8d-136">Full access rights are granted to users with Security Administrator or Global Administrator roles in Azure AD.</span></span> <span data-ttu-id="73d8d-137">読み取り専用アクセスは、Azure のセキュリティ リーダー ロールを持つユーザーに付与AD。</span><span class="sxs-lookup"><span data-stu-id="73d8d-137">Read only access is granted to users with a Security Reader role in Azure AD.</span></span> 

<span data-ttu-id="73d8d-138">Defender for Endpoint Global 管理者の役割を持つユーザーは、デバイス グループの関連付けと Azure AD グループの割り当てに関係なく、すべてのデバイスに無制限にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="73d8d-138">Someone with a Defender for Endpoint Global administrator role has unrestricted access to all devices, regardless of their device group association and the Azure AD user groups assignments</span></span>

> [!WARNING]
> <span data-ttu-id="73d8d-139">最初は、Azure AD グローバル管理者またはセキュリティ管理者の権限を持つユーザーだけが Microsoft Defender セキュリティ センターで役割を作成して割り当てることができます。そのため、Azure AD で適切なグループを準備することが重要です。</span><span class="sxs-lookup"><span data-stu-id="73d8d-139">Initially, only those with Azure AD Global Administrator or Security Administrator rights will be able to create and assign roles in Microsoft Defender Security Center, therefore, having the right groups ready in Azure AD is important.</span></span>
>
> <span data-ttu-id="73d8d-140">**ロール ベースのアクセス制御を有効にすると、読み取り専用アクセス許可を持つユーザー (たとえば、Azure AD セキュリティ リーダー ロールに割り当てられたユーザー) は、ロールに割り当てられるまでアクセス権を失います。**</span><span class="sxs-lookup"><span data-stu-id="73d8d-140">**Turning on role-based access control will cause users with read-only permissions (for example, users assigned to Azure AD Security reader role) to lose access until they are assigned to a role.**</span></span> 
>
><span data-ttu-id="73d8d-141">管理者アクセス許可を持つユーザーには、完全なアクセス許可を持つ既定の組み込みの Defender for Endpoint グローバル管理者ロールが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="73d8d-141">Users with admin permissions are automatically assigned the default built-in Defender for Endpoint global administrator role with full permissions.</span></span> <span data-ttu-id="73d8d-142">RBAC の使用をオプトインした後、Azure AD グローバル管理者またはセキュリティ管理者ではない追加のユーザーを Defender for Endpoint グローバル管理者ロールに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="73d8d-142">After opting in to use RBAC, you can assign additional users that are not Azure AD Global or Security Administrators to the Defender for Endpoint global administrator role.</span></span> 
>
> <span data-ttu-id="73d8d-143">RBAC の使用をオプトインした後は、最初にポータルにログインした場合と同様に、最初の役割に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="73d8d-143">After opting in to use RBAC, you cannot revert to the initial roles as when you first logged into the portal.</span></span> 



## <a name="related-topic"></a><span data-ttu-id="73d8d-144">関連トピック</span><span class="sxs-lookup"><span data-stu-id="73d8d-144">Related topic</span></span>
- [<span data-ttu-id="73d8d-145">Microsoft Defender for Endpoint でデバイス グループを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="73d8d-145">Create and manage device groups in Microsoft Defender for Endpoint</span></span>](machine-groups.md)
