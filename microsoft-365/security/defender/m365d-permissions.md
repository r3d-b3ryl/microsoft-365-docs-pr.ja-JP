---
title: セキュリティ センターでMicrosoft 365 Defender データへのアクセスMicrosoft 365管理する
description: Defender でデータへのアクセス許可を管理するMicrosoft 365する
keywords: Access, permissions, Microsoft 365 Defender, M365, security, MCAS, Cloud App Security, Microsoft Defender for Endpoint, scope, scoping, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 52e4e9fc8c73d1adca0c24c5bebb50f9dcf7ac6f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935631"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a><span data-ttu-id="cbfd5-104">グローバル ロールを使用Microsoft 365 Defender へのAzure Active Directory管理する</span><span class="sxs-lookup"><span data-stu-id="cbfd5-104">Manage access to Microsoft 365 Defender with Azure Active Directory global roles</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="cbfd5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="cbfd5-105">**Applies to:**</span></span>
- <span data-ttu-id="cbfd5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cbfd5-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="cbfd5-107">Defender へのアクセスを管理するには、2 Microsoft 365があります。</span><span class="sxs-lookup"><span data-stu-id="cbfd5-107">There are two ways to manage access to Microsoft 365 Defender</span></span>
- <span data-ttu-id="cbfd5-108">**グローバル Azure Active Directory (AD) の役割**</span><span class="sxs-lookup"><span data-stu-id="cbfd5-108">**Global Azure Active Directory (AD) roles**</span></span>
- <span data-ttu-id="cbfd5-109">**カスタム ロール アクセス**</span><span class="sxs-lookup"><span data-stu-id="cbfd5-109">**Custom role access**</span></span>

<span data-ttu-id="cbfd5-110">次のグローバル ユーザー **(Azure Active Directory) AD割** り当てられたアカウントは、Defender のMicrosoft 365データにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cbfd5-110">Accounts assigned the following **Global Azure Active Directory (AD) roles** can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="cbfd5-111">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="cbfd5-111">Global administrator</span></span>
- <span data-ttu-id="cbfd5-112">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="cbfd5-112">Security administrator</span></span>
- <span data-ttu-id="cbfd5-113">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="cbfd5-113">Security Operator</span></span>
- <span data-ttu-id="cbfd5-114">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="cbfd5-114">Global Reader</span></span>
- <span data-ttu-id="cbfd5-115">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="cbfd5-115">Security Reader</span></span>

<span data-ttu-id="cbfd5-116">これらのロールを持つアカウントを確認するには、[Microsoft 365 セキュリティ センターで権限を表示](https://security.microsoft.com/permissions)します。</span><span class="sxs-lookup"><span data-stu-id="cbfd5-116">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

<span data-ttu-id="cbfd5-117">**カスタム ロール アクセス** は、Microsoft 365 Defender の新機能であり、Microsoft Defender 365 の特定のデータ、タスク、および機能へのアクセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="cbfd5-117">**Custom role** access is a new capability in Microsoft 365 Defender and allows you to manage access to specific data, tasks, and capabilities in Microsoft Defender 365.</span></span> <span data-ttu-id="cbfd5-118">カスタム ロールは、グローバル Azure ADロールよりも多くの制御を提供し、必要な最小限の役割で必要なアクセスのみをユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="cbfd5-118">Custom roles offer more control than global Azure AD roles, providing users only the access they need with the least-permissive roles necessary.</span></span>  <span data-ttu-id="cbfd5-119">カスタム ロールは、グローバル Azure ロールとカスタム ロールにADできます。</span><span class="sxs-lookup"><span data-stu-id="cbfd5-119">Custom roles can be created in addition to global Azure AD roles.</span></span> <span data-ttu-id="cbfd5-120">[カスタム ロールの詳細を参照してください](custom-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="cbfd5-120">[Learn more about custom roles](custom-roles.md).</span></span>

> <span data-ttu-id="cbfd5-121">![メモ]この記事は、グローバル ロールの管理にのみAzure Active Directoryします。</span><span class="sxs-lookup"><span data-stu-id="cbfd5-121">![NOTE] This article applies only to managing global Azure Active Directory roles.</span></span> <span data-ttu-id="cbfd5-122">カスタムの役割ベースのアクセス制御の使用の詳細については、「役割ベースのアクセス制御のカスタム [ロール」を参照してください。](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="cbfd5-122">For more information about using custom role-based access control, see [Custom roles for role-based access control](custom-roles.md)</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="cbfd5-123">機能へのアクセス</span><span class="sxs-lookup"><span data-stu-id="cbfd5-123">Access to functionality</span></span>
<span data-ttu-id="cbfd5-124">特定の機能へのアクセスは、[Azure AD でのロール](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)によって決まります。</span><span class="sxs-lookup"><span data-stu-id="cbfd5-124">Access to specific functionality is determined by your [Azure AD role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="cbfd5-125">ユーザーまたはユーザー グループに新しい役割を割り当てる必要がある場合は、グローバル管理者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="cbfd5-125">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="cbfd5-126">保留中の自動化タスクを承認する</span><span class="sxs-lookup"><span data-stu-id="cbfd5-126">Approve pending automated tasks</span></span>
<span data-ttu-id="cbfd5-127">「[調査と修復の自動化](m365d-autoir-actions.md)」 は、調査中に見つかったメール、転送ルール、ファイル、持続性機構など、その他の成果物に対処できます。</span><span class="sxs-lookup"><span data-stu-id="cbfd5-127">[Automated investigation and remediation](m365d-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="cbfd5-128">明示的な承認が必要な保留中のアクションを承認または拒否するには、Microsoft 365 に特定の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbfd5-128">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="cbfd5-129">詳細については、「[アクションセンターの権限](m365d-action-center.md#required-permissions-for-action-center-tasks)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cbfd5-129">To learn more, see [Action center permissions](m365d-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="cbfd5-130">データへのアクセス</span><span class="sxs-lookup"><span data-stu-id="cbfd5-130">Access to data</span></span>
<span data-ttu-id="cbfd5-131">Defender データMicrosoft 365へのアクセスは、Microsoft Defender for Endpoint の役割ベースのアクセス制御 (RBAC) のユーザー グループに割り当てられたスコープを使用して制御できます。</span><span class="sxs-lookup"><span data-stu-id="cbfd5-131">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="cbfd5-132">Defender for Endpoint の特定のデバイス セットにアクセスの範囲が設定されていない場合は、Defender のデータにフル アクセスMicrosoft 365されます。</span><span class="sxs-lookup"><span data-stu-id="cbfd5-132">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="cbfd5-133">ただし、アカウントのスコープを指定すると、対象のデバイスに関するデータのみが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="cbfd5-133">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="cbfd5-134">たとえば、Microsoft Defender for Endpoint の役割を持つ 1 つのユーザー グループにのみ属し、そのユーザー グループに販売デバイスへのアクセス権が与えられた場合、Microsoft 365 Defender の販売デバイスに関するデータだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cbfd5-134">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="cbfd5-135">Microsoft Defender for Endpoint の RBAC 設定の詳細</span><span class="sxs-lookup"><span data-stu-id="cbfd5-135">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="cbfd5-136">Microsoft Cloud App Security のアクセス制御</span><span class="sxs-lookup"><span data-stu-id="cbfd5-136">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="cbfd5-137">プレビュー中に、Microsoft 365設定に基づいてアクセス制御が適用Cloud App Securityされます。</span><span class="sxs-lookup"><span data-stu-id="cbfd5-137">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="cbfd5-138">Defender データMicrosoft 365へのアクセスは、これらの設定の影響を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbfd5-138">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cbfd5-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbfd5-139">Related topics</span></span>
- [<span data-ttu-id="cbfd5-140">Defender の役割ベースのアクセス制御のカスタム ロールMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="cbfd5-140">Custom roles in role-based access control for Microsoft 365 Defender</span></span>](custom-roles.md)
- [<span data-ttu-id="cbfd5-141">Azure AD ロール</span><span class="sxs-lookup"><span data-stu-id="cbfd5-141">Azure AD roles</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="cbfd5-142">エンドポイント RBAC 用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cbfd5-142">Microsoft Defender for Endpoint RBAC</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="cbfd5-143">Cloud App Security roles</span><span class="sxs-lookup"><span data-stu-id="cbfd5-143">Cloud App Security roles</span></span>](/cloud-app-security/manage-admins)