---
title: 管理ポータルにアクセスする
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
description: 管理ポータルへのアクセスの制御など、管理ポータルを検索して使用する方法。
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 345ae56a1c328dad7b777468dd03bcab40f9b4e1
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286875"
---
# <a name="access-the-admin-portal"></a><span data-ttu-id="51c06-104">管理ポータルへのアクセス</span><span class="sxs-lookup"><span data-stu-id="51c06-104">Access the admin portal</span></span>

<span data-ttu-id="51c06-105">サービスへのゲートウェイ[Microsoft マネージド デスクトップが](https://endpoint.microsoft.com/)Microsoft エンドポイント マネージャー。</span><span class="sxs-lookup"><span data-stu-id="51c06-105">Your gateway to the Microsoft Managed Desktop service is [Microsoft Endpoint Manager](https://endpoint.microsoft.com/).</span></span> <span data-ttu-id="51c06-106">デバイス管理のためのこのポータルの機能に慣れていない場合は、次のドキュメントMicrosoft エンドポイント マネージャー[してください](/mem/)。</span><span class="sxs-lookup"><span data-stu-id="51c06-106">If you are unfamiliar with the capabilities of this portal for device management, see the [Microsoft Endpoint Manager documentation](/mem/).</span></span>

> [!NOTE]
> <span data-ttu-id="51c06-107">この[Microsoft エンドポイント マネージャー、](https://endpoint.microsoft.com/)次のブラウザーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="51c06-107">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) the following browsers are supported:</span></span>
> - <span data-ttu-id="51c06-108">Microsoft Edge (最新バージョン)</span><span class="sxs-lookup"><span data-stu-id="51c06-108">Microsoft Edge (latest version)</span></span>
> - <span data-ttu-id="51c06-109">Safari (最新バージョン、Mac のみ)</span><span class="sxs-lookup"><span data-stu-id="51c06-109">Safari (latest version, Mac only)</span></span>
> - <span data-ttu-id="51c06-110">Chrome (最新バージョン)</span><span class="sxs-lookup"><span data-stu-id="51c06-110">Chrome (latest version)</span></span>
> - <span data-ttu-id="51c06-111">Firefox (最新バージョン)</span><span class="sxs-lookup"><span data-stu-id="51c06-111">Firefox (latest version)</span></span>

<span data-ttu-id="51c06-112">管理者アカウントは、管理者アカウントの管理機能にアクセスするために特定Microsoft マネージド デスクトップ必要Microsoft エンドポイント マネージャー。</span><span class="sxs-lookup"><span data-stu-id="51c06-112">Your administrative account will need specific permissions in order to access the Microsoft Managed Desktop administrative features in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="51c06-113">役割ベースのアクセス制御を使用して、組織内のこれらの機能への管理者アクセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="51c06-113">You can manage admin access to these features within your organization by using role-based access control.</span></span> <span data-ttu-id="51c06-114">複数Azure Active Directory (Azure AD) 管理者ロールと組み込みの Microsoft マネージド デスクトップ ロールを使用して、Microsoft マネージド デスクトップ 管理ポータル内のさまざまな機能を詳細に制御できます。</span><span class="sxs-lookup"><span data-stu-id="51c06-114">Several Azure Active Directory (Azure AD) administrator roles and built-in Microsoft Managed Desktop roles are available to provide more granular control to different features within the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="51c06-115">役割の詳細については、「Azure Active Directoryの[管理者役割のアクセス許可」を参照Azure Active Directory。](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="51c06-115">For more information about Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="51c06-116">さまざまな Microsoft 製品ADサービスに適用される Azure AD 管理者ロールとは異なり、組み込みの役割は Microsoft マネージド デスクトップ 固有の役割であり、このサービスの管理者機能へのアクセスのみを保証します。</span><span class="sxs-lookup"><span data-stu-id="51c06-116">Unlike Azure AD administrator roles that apply to various Microsoft products and services, the built-in roles are specific to Microsoft Managed Desktop and will only guarantee access to the Admin features for this service.</span></span> <span data-ttu-id="51c06-117">管理者は、組み込みの役割をユーザーに個別に割り当てるか、Azure AD 管理者ロールと組み合わせて割り当て、既存の管理者アカウントにMicrosoft マネージド デスクトップアクセス許可を追加できます。</span><span class="sxs-lookup"><span data-stu-id="51c06-117">Admins can assign built-in roles to users individually or in combination with Azure AD administrator roles to add Microsoft Managed Desktop permissions to existing admin accounts.</span></span>

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a><span data-ttu-id="51c06-118">Azure Active Directoryアクセス権を持つMicrosoft マネージド デスクトップロール</span><span class="sxs-lookup"><span data-stu-id="51c06-118">Azure Active Directory roles with Microsoft Managed Desktop access</span></span>

|<span data-ttu-id="51c06-119">Azure AD ロール</span><span class="sxs-lookup"><span data-stu-id="51c06-119">Azure AD role</span></span>  |<span data-ttu-id="51c06-120">Microsoft マネージド デスクトップアクセス許可</span><span class="sxs-lookup"><span data-stu-id="51c06-120">Microsoft Managed Desktop permissions</span></span>  |
|---------|---------|
|<span data-ttu-id="51c06-121">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="51c06-121">Global Administrator</span></span>     | <span data-ttu-id="51c06-122">この役割を持つ **管理者には、** 管理者ポータル内のすべての機能に対する読み取りおよびMicrosoft マネージド デスクトップがあります。</span><span class="sxs-lookup"><span data-stu-id="51c06-122">Admins with this role will have **read and write permissions to all features** in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="51c06-123">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="51c06-123">Global Reader</span></span>     | <span data-ttu-id="51c06-124">この役割を持つ管理者には **、管理者** ポータル内のすべての機能に対する読み取りMicrosoft マネージド デスクトップがあります。</span><span class="sxs-lookup"><span data-stu-id="51c06-124">Admins with this role will have **read-only permissions to all features** in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="51c06-125">Intune サービス管理者</span><span class="sxs-lookup"><span data-stu-id="51c06-125">Intune Service Administrator</span></span>     |  <span data-ttu-id="51c06-126">この役割を持つ管理者には **、管理者** ポータルのセキュリティに関連しない機能に対する読み取りおよび書き込Microsoft マネージド デスクトップがあります。</span><span class="sxs-lookup"><span data-stu-id="51c06-126">Admins with this role will have **read and write permissions to features not related to security** in the Microsoft Managed Desktop Admin portal.</span></span>       |
|<span data-ttu-id="51c06-127">サービス サポート管理者</span><span class="sxs-lookup"><span data-stu-id="51c06-127">Service Support Administrator</span></span>     | <span data-ttu-id="51c06-128">この役割を持つ管理者には、セキュリティに関連しない機能に対する読み取り専用アクセス許可と、管理者ポータルでサポート要求を管理するための書き込みMicrosoft マネージド デスクトップがあります。</span><span class="sxs-lookup"><span data-stu-id="51c06-128">Admins with this role will have **read-only permissions to features not related to security** and **write permissions to manage support requests** in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="51c06-129">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="51c06-129">Security Admin</span></span> | <span data-ttu-id="51c06-130">この役割を持つ管理者は、管理ポータル内のすべての機能に対する読み取り専用のアクセス許可と、Microsoft マネージド デスクトップのセキュリティ関連機能に対する書き込みアクセス許可を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="51c06-130">Admins with this role will have **read-only permissions to all features** and **write permissions for security related features** in Microsoft Managed Desktop in the Admin portal.</span></span> |
|<span data-ttu-id="51c06-131">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="51c06-131">Security Reader</span></span> |<span data-ttu-id="51c06-132">この役割を持つ管理者には **、管理者** ポータル内のすべての機能に対する読み取りMicrosoft マネージド デスクトップがあります。</span><span class="sxs-lookup"><span data-stu-id="51c06-132">Admins with this role will have **read-only permissions to all features** in the Microsoft Managed Desktop Admin portal.</span></span>|

<span data-ttu-id="51c06-133">役割の割り当てに関するヘルプAzure Active Directory、「管理者[ロールの](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)アクセス許可」を参照Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="51c06-133">If you need help with assigning Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51c06-134">グローバル管理者の役割にのみ、組織を登録するために必要なアクセス許可Microsoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="51c06-134">Only the Global Administrator role has the necessary permissions to *enroll* your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="51c06-135">役割によって、Azure Active Directoryさまざまなユーザー アカウントの権限が付与Microsoft サービス。</span><span class="sxs-lookup"><span data-stu-id="51c06-135">Be aware that Azure Active Directory roles will give user accounts privileges across a variety of Microsoft services.</span></span> <span data-ttu-id="51c06-136">ユーザーの登録が完了Microsoft マネージド デスクトップ、他のタスクを実行するために必要な最小の特権を持つロールを常に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51c06-136">After completing enrollment with Microsoft Managed Desktop, you should always use the role with the *least* privileges necessary to accomplish your other tasks.</span></span>

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a><span data-ttu-id="51c06-137">ユーザーが提供する組み込みMicrosoft マネージド デスクトップ</span><span class="sxs-lookup"><span data-stu-id="51c06-137">Built-in roles provided by Microsoft Managed Desktop</span></span>


|<span data-ttu-id="51c06-138">組み込みの役割</span><span class="sxs-lookup"><span data-stu-id="51c06-138">Built-in role</span></span>  |<span data-ttu-id="51c06-139">Microsoft マネージド デスクトップアクセス許可</span><span class="sxs-lookup"><span data-stu-id="51c06-139">Microsoft Managed Desktop permissions</span></span>  |
|---------|---------|
|<span data-ttu-id="51c06-140">Microsoft マネージド デスクトップサービス管理者</span><span class="sxs-lookup"><span data-stu-id="51c06-140">Microsoft Managed Desktop Service Administrator</span></span>  | <span data-ttu-id="51c06-141">ユーザーに割り当てられると、管理者は管理者ポータルのセキュリティに関連しない機能に対する読み取りおよび書き込Microsoft マネージド デスクトップします。</span><span class="sxs-lookup"><span data-stu-id="51c06-141">When assigned to a user, this role gives the admin **read and write permissions to features not related to security** in the Microsoft Managed Desktop Admin portal.</span></span>  |
|<span data-ttu-id="51c06-142">Microsoft マネージド デスクトップサービス リーダー</span><span class="sxs-lookup"><span data-stu-id="51c06-142">Microsoft Managed Desktop Service Reader</span></span> | <span data-ttu-id="51c06-143">ユーザーに割り当てると、管理者は管理者ポータルのセキュリティに関連しない機能に対する読み取り専用Microsoft マネージド デスクトップします。</span><span class="sxs-lookup"><span data-stu-id="51c06-143">When assigned to a user, this role gives the admin **read-only permissions to features not related to security** in the Microsoft Managed Desktop Admin portal.</span></span> |
|<span data-ttu-id="51c06-144">Microsoft マネージド デスクトップセキュリティ マネージャー</span><span class="sxs-lookup"><span data-stu-id="51c06-144">Microsoft Managed Desktop Security Manager</span></span> |<span data-ttu-id="51c06-145">ユーザーに割り当てると、管理者は管理者ポータルのセキュリティ関連機能に対する読み取りおよび書き込みMicrosoft マネージド デスクトップします。</span><span class="sxs-lookup"><span data-stu-id="51c06-145">When assigned to a user, this role gives that admin **read and write permissions only for security related features** in the Microsoft Managed Desktop Admin portal.</span></span>   |

> [!NOTE]
> <span data-ttu-id="51c06-146">セキュリティ機能には、セキュリティ関連の通信、セキュリティ連絡先の管理、セキュリティ関連のサポート要求の管理、およびセキュリティ関連レポートへのアクセスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="51c06-146">Security features include security-related communications, management of security contacts, management of security-related support requests, and access to security related reports.</span></span> 

### <a name="assigning-built-in-roles-to-user"></a><span data-ttu-id="51c06-147">組み込みの役割をユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="51c06-147">Assigning built-in roles to user</span></span>

<span data-ttu-id="51c06-148">組み込みの役割を簡単に管理するには、"モダン ワークプレースの役割 _-_ 役割名" という名前のカスタム ロールごとにセキュリティ グループがあります (たとえば、「モダン ワークプレースの役割 - セキュリティ マネージャー」など)。</span><span class="sxs-lookup"><span data-stu-id="51c06-148">For easy management of built-in roles, there is a security group for each custom role with the name "Modern Workplace Roles - _Role Name_"(for example, “Modern Workplace Roles – Security Manager”).</span></span> <span data-ttu-id="51c06-149">ユーザーをこれらのセキュリティ グループに割り当てるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="51c06-149">To assign users to one of these security groups, follow these steps:</span></span>
1. <span data-ttu-id="51c06-150">ポータルに移動Microsoft エンドポイント マネージャーします。</span><span class="sxs-lookup"><span data-stu-id="51c06-150">Go the Microsoft Endpoint Manager portal.</span></span>
2. <span data-ttu-id="51c06-151">左側 **の [グループ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="51c06-151">Select **Groups** on the left side.</span></span>
3. <span data-ttu-id="51c06-152">[モダン **ワークプレースの役割] を** 検索し、割り当てる役割に関連付けられているグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="51c06-152">Search for **Modern Workplace Roles**, and then select the group associated with the role you want to assign.</span></span> 
4. <span data-ttu-id="51c06-153">左側 **の [メンバー** ] を選択し、コマンド バー **の [+ メンバー** の追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="51c06-153">Select **Members** on the left side, and then select **+ Add members** on the command bar.</span></span>
5. <span data-ttu-id="51c06-154">追加するユーザーのメールを入力します。</span><span class="sxs-lookup"><span data-stu-id="51c06-154">Enter the email of the person being added.</span></span> <span data-ttu-id="51c06-155">ゲストの場合は、グループを割り当てる前に招待する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51c06-155">If they are a guest, you must invite them before you can assign the group.</span></span>
6. <span data-ttu-id="51c06-156">下部 **にある [選択** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="51c06-156">Select **Select** at the bottom.</span></span>

> [!NOTE]
> <span data-ttu-id="51c06-157">役割割り当てのセキュリティ グループの入れ子は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="51c06-157">Nesting security groups for role assignment is not currently supported.</span></span> 

### <a name="assigning-built-in-roles-to-groups"></a><span data-ttu-id="51c06-158">組み込みの役割をグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="51c06-158">Assigning built-in roles to groups</span></span>

<span data-ttu-id="51c06-159">1 つ以上の組み込みロールを既存のグループに割り当てる必要がある場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="51c06-159">If you need to assign one or more of the built-in roles to a existing group, follow these steps:</span></span>

1. <span data-ttu-id="51c06-160">に移動[portal.azure.com。](https://portal.azure.com/)</span><span class="sxs-lookup"><span data-stu-id="51c06-160">Go to [portal.azure.com](https://portal.azure.com/).</span></span>
2. <span data-ttu-id="51c06-161">アプリケーションを検索して開Enterprise **します**。</span><span class="sxs-lookup"><span data-stu-id="51c06-161">Search for and open **Enterprise applications**.</span></span>
3. <span data-ttu-id="51c06-162">[アプリケーションの **種類] フィルターを** _[Microsoft アプリケーション] に変更し_ 、[適用] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="51c06-162">Change the **Application type** filter to _Microsoft Applications_ and, then select **Apply**.</span></span>
4. <span data-ttu-id="51c06-163">モダン ワークプレースカスタマー API _を検索して選択します_。</span><span class="sxs-lookup"><span data-stu-id="51c06-163">Search for and select _Modern Workplace Customer APIs_.</span></span>
5. <span data-ttu-id="51c06-164">左側 **のウィンドウから [ユーザー** とグループ] を選択し **、[+ ユーザー/グループの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="51c06-164">Select **Users and groups** from the pane on the left side, and then select **+ Add user/group**.</span></span>
6. <span data-ttu-id="51c06-165">[ユーザーとグループ] から必要な **グループを検索します**。</span><span class="sxs-lookup"><span data-stu-id="51c06-165">Search for the group you want from **Users and groups**.</span></span>
7. <span data-ttu-id="51c06-166">[役割の選択] から該当する役割 **を検索** し、その役割を選択します。</span><span class="sxs-lookup"><span data-stu-id="51c06-166">Search for the applicable role from **Select a role**, and then select it.</span></span>
8. <span data-ttu-id="51c06-167">[割り当 **て] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="51c06-167">Select **Assign**.</span></span>
