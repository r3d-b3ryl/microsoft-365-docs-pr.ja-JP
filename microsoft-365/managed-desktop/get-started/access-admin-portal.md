---
title: 管理ポータルにアクセスする
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 17696b18b4109b568bb1d616813ba40e2a9dccdc
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430473"
---
# <a name="access-the-admin-portal"></a><span data-ttu-id="4a4ba-103">管理ポータルにアクセスする</span><span class="sxs-lookup"><span data-stu-id="4a4ba-103">Access the admin portal</span></span>

<span data-ttu-id="4a4ba-104">Microsoft Managed Desktop service へのゲートウェイは、Microsoft [Azure portal](https://portal.azure.com)です。</span><span class="sxs-lookup"><span data-stu-id="4a4ba-104">Your gateway to the Microsoft Managed Desktop service is the Microsoft [Azure portal](https://portal.azure.com).</span></span> <span data-ttu-id="4a4ba-105">Azure ポータルを使用してカスタマイズする方法の詳細については、「 [azure portal のドキュメント](https://docs.microsoft.com/azure/azure-portal/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a4ba-105">For more about using and customizing your Azure portal experience generally, see the [Azure portal documentation](https://docs.microsoft.com/azure/azure-portal/).</span></span> <span data-ttu-id="4a4ba-106">プレビューでは、microsoft[エンドポイントマネージャー](https://endpoint.microsoft.com/)で Microsoft Managed Desktop を検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="4a4ba-106">Available in preview now, you can also find Microsoft Managed Desktop in the [Microsoft Endpoint Manager](https://endpoint.microsoft.com/).</span></span> <span data-ttu-id="4a4ba-107">このポータルのデバイス管理の機能についてよく知らない場合は、 [Microsoft エンドポイントマネージャーのドキュメント](https://docs.microsoft.com/mem/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a4ba-107">If you are unfamiliar with the capabilities of this portal for device management see the [Microsoft Endpoint Manager documentation](https://docs.microsoft.com/mem/).</span></span>

<span data-ttu-id="4a4ba-108">管理アカウントには、Microsoft Managed Desktop 管理ポータルにアクセスするための特定のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="4a4ba-108">Your administrative account needs specific permissions in order to access the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="4a4ba-109">役割ベースのアクセス制御 (RBAC) を使用して、組織内のこれらの機能への管理者アクセスを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="4a4ba-109">You can manage admin access to these features within your organization by using Role-based Access Control (RBAC).</span></span> <span data-ttu-id="4a4ba-110">Azure Active Directory ロールの詳細については、「 [Azure Active directory での管理者ロールのアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a4ba-110">For more information about Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

<span data-ttu-id="4a4ba-111">アクセスを確実にするために、管理者ユーザーアカウントに次の役割のいずれかを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4a4ba-111">Assign your admin user accounts any of the following roles to ensure access:</span></span>

|<span data-ttu-id="4a4ba-112">Azure AD の役割</span><span class="sxs-lookup"><span data-stu-id="4a4ba-112">Azure AD role</span></span>  |<span data-ttu-id="4a4ba-113">Microsoft マネージドデスクトップのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="4a4ba-113">Microsoft Managed Desktop permissions</span></span>  |
|---------|---------|
|<span data-ttu-id="4a4ba-114">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="4a4ba-114">Global Administrator</span></span>     | <span data-ttu-id="4a4ba-115">この役割を持つ管理者は、Microsoft Managed Desktop 管理ポータルのすべての機能に対する**読み取りおよび書き込みアクセス許可**を持ちます。</span><span class="sxs-lookup"><span data-stu-id="4a4ba-115">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="4a4ba-116">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="4a4ba-116">Global Reader</span></span>     | <span data-ttu-id="4a4ba-117">この役割を持つ管理者は、Microsoft Managed Desktop 管理ポータルのすべての機能に対して**読み取り専用のアクセス許可**を持ちます。</span><span class="sxs-lookup"><span data-stu-id="4a4ba-117">Admins with this role will have **read-only permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="4a4ba-118">Intune サービス管理者</span><span class="sxs-lookup"><span data-stu-id="4a4ba-118">Intune Service Administrator</span></span>     |  <span data-ttu-id="4a4ba-119">この役割を持つ管理者は、Microsoft Managed Desktop 管理ポータルのすべての機能に対する**読み取りおよび書き込みアクセス許可**を持ちます。</span><span class="sxs-lookup"><span data-stu-id="4a4ba-119">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>       |
|<span data-ttu-id="4a4ba-120">サービスサポート管理者</span><span class="sxs-lookup"><span data-stu-id="4a4ba-120">Service Support Administrator</span></span>     | <span data-ttu-id="4a4ba-121">この役割を持つ管理者は、Microsoft Managed Desktop 管理ポータルのすべての機能に対する**読み取りおよび書き込みアクセス許可**を持ちます。</span><span class="sxs-lookup"><span data-stu-id="4a4ba-121">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |

> [!IMPORTANT]
> <span data-ttu-id="4a4ba-122">グローバル管理者の役割のみが、Microsoft マネージドデスクトップに組織を*登録*するために必要なアクセス許可を持っています。</span><span class="sxs-lookup"><span data-stu-id="4a4ba-122">Only the Global Administrator role has the necessary permissions to *enroll* your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="4a4ba-123">Azure Active Directory の役割によって、ユーザーアカウントにさまざまな Microsoft サービスの権限が付与されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4a4ba-123">Be aware that Azure Active Directory roles will give user accounts privileges across a variety of Microsoft services.</span></span> <span data-ttu-id="4a4ba-124">Microsoft マネージドデスクトップでの登録を完了した後は、他のタスクを実行するために必要な*最低限*の特権を持つ役割を常に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a4ba-124">After completing enrollment with Microsoft Managed Desktop, you should always use the role with the *least* privileges necessary to accomplish your other tasks.</span></span>

## <a name="assigning-roles-to-administrators"></a><span data-ttu-id="4a4ba-125">管理者への役割の割り当て</span><span class="sxs-lookup"><span data-stu-id="4a4ba-125">Assigning roles to administrators</span></span>

<span data-ttu-id="4a4ba-126">Azure Active Directory の役割の割り当てに関するヘルプが必要な場合は、「 [Azure Active directory の管理者ロールのアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a4ba-126">If you need help assigning Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>
