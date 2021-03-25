---
title: Microsoft Defender セキュリティ センターへのユーザー アクセスの割り当て
description: Microsoft Defender for Endpoint ポータルへの読み取りおよび書き込みまたは読み取り専用アクセスを割り当てる。
keywords: ユーザー ロールの割り当て、読み取りおよび書き込みアクセスの割り当て、読み取り専用アクセスの割り当て、ユーザー、ユーザー の役割、役割
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
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: 71215c4988351644cfa4d79503c097c932caf9d6
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164771"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a><span data-ttu-id="fa02c-104">Microsoft Defender セキュリティ センターへのユーザー アクセスの割り当て</span><span class="sxs-lookup"><span data-stu-id="fa02c-104">Assign user access to Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fa02c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="fa02c-105">**Applies to:**</span></span>
- <span data-ttu-id="fa02c-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="fa02c-106">Azure Active Directory</span></span>
- <span data-ttu-id="fa02c-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="fa02c-107">Office 365</span></span>
- [<span data-ttu-id="fa02c-108">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fa02c-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fa02c-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fa02c-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="fa02c-110">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="fa02c-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fa02c-111">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="fa02c-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="fa02c-112">Defender for Endpoint では、アクセス許可を管理する 2 つの方法がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="fa02c-112">Defender for Endpoint supports two ways to manage permissions:</span></span>

- <span data-ttu-id="fa02c-113">**基本的なアクセス許可の管理**: アクセス許可をフル アクセスまたは読み取り専用に設定します。</span><span class="sxs-lookup"><span data-stu-id="fa02c-113">**Basic permissions management**: Set permissions to either full access or read-only.</span></span>
- <span data-ttu-id="fa02c-114">**役割ベースのアクセス制御 (RBAC)**: 役割を定義し、Azure AD ユーザー グループをロールに割り当て、ユーザー グループにデバイス グループへのアクセス権を付与することで、詳細なアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="fa02c-114">**Role-based access control (RBAC)**: Set granular permissions by defining roles, assigning Azure AD user groups to the roles, and granting the user groups access to device groups.</span></span> <span data-ttu-id="fa02c-115">RBAC の詳細については、「役割ベースのアクセス [制御を使用してポータル アクセスを管理する」を参照してください](rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="fa02c-115">For more information on RBAC, see [Manage portal access using role-based access control](rbac.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fa02c-116">基本的なアクセス許可が既に割り当てられている場合は、いつでも RBAC に切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="fa02c-116">If you have already assigned basic permissions, you may switch to RBAC anytime.</span></span> <span data-ttu-id="fa02c-117">スイッチを作成する前に、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="fa02c-117">Consider the following before making the switch:</span></span>
> 
> - <span data-ttu-id="fa02c-118">フル アクセスを持つユーザー (Azure AD のグローバル管理者またはセキュリティ管理者ディレクトリ ロールが割り当てられているユーザー) には、既定の Defender for Endpoint 管理者ロールが自動的に割り当てられます。また、フル アクセス権も持っています。</span><span class="sxs-lookup"><span data-stu-id="fa02c-118">Users with full access (users that are assigned the Global Administrator or Security Administrator directory role in Azure AD), are automatically assigned the default Defender for Endpoint administrator role, which also has full access.</span></span> <span data-ttu-id="fa02c-119">RBAC に切りAD後、追加の Azure ユーザー グループを Defender for Endpoint 管理者ロールに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="fa02c-119">Additional Azure AD user groups can be assigned to the Defender for Endpoint administrator role after switching to RBAC.</span></span>  <span data-ttu-id="fa02c-120">Defender for Endpoint 管理者ロールに割り当てられたユーザーだけが、RBAC を使用してアクセス許可を管理できます。</span><span class="sxs-lookup"><span data-stu-id="fa02c-120">Only users assigned to the Defender for Endpoint administrator role can manage permissions using RBAC.</span></span> 
> - <span data-ttu-id="fa02c-121">読み取り専用アクセス権 (Security Readers) を持つユーザーは、役割が割り当てられるまでポータルへのアクセスを失います。</span><span class="sxs-lookup"><span data-stu-id="fa02c-121">Users that have read-only access (Security Readers) will lose access to the portal until they are assigned a role.</span></span> <span data-ttu-id="fa02c-122">RBAC の下で役割AD割り当てできるのは Azure ユーザー グループのみです。</span><span class="sxs-lookup"><span data-stu-id="fa02c-122">Note that only Azure AD user groups can be assigned a role under RBAC.</span></span>
> - <span data-ttu-id="fa02c-123">RBAC に切り替えても、基本的なアクセス許可管理を使用して切り替えすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fa02c-123">After switching to RBAC, you will not be able to switch back to using basic permissions management.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fa02c-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa02c-124">Related topics</span></span>

- [<span data-ttu-id="fa02c-125">基本的なアクセス許可を使用してポータルにアクセスする</span><span class="sxs-lookup"><span data-stu-id="fa02c-125">Use basic permissions to access the portal</span></span>](basic-permissions.md)
- [<span data-ttu-id="fa02c-126">RBAC を使用してポータル アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="fa02c-126">Manage portal access using RBAC</span></span>](rbac.md)
