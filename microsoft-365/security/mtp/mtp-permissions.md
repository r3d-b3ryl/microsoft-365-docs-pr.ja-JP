---
title: Microsoft 365 セキュリティ センターで Microsoft 365 Defender データへのアクセスを管理する
description: Microsoft 365 Defender でデータへのアクセス許可を管理する方法について説明します。
keywords: アクセス、アクセス許可、MTP、Microsoft Threat Protection、M365、セキュリティ、MCAS、MDATP、Cloud App Security、Microsoft Defender Advanced Threat Protection、スコープ、スコーピング、RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6f042b0c6314e8e5f80d40d76159712bc817a01c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930140"
---
# <a name="manage-access-to-microsoft-365-defender"></a><span data-ttu-id="925f1-104">Microsoft 365 Defender へのアクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="925f1-104">Manage access to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="925f1-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="925f1-105">**Applies to:**</span></span>
- <span data-ttu-id="925f1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="925f1-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="925f1-107">次の Azure Active Directory (AD) ロールが割り当てられているアカウントは、Microsoft 365 Defender の機能とデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="925f1-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="925f1-108">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="925f1-108">Global administrator</span></span>
- <span data-ttu-id="925f1-109">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="925f1-109">Security administrator</span></span>
- <span data-ttu-id="925f1-110">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="925f1-110">Security Operator</span></span>
- <span data-ttu-id="925f1-111">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="925f1-111">Global Reader</span></span>
- <span data-ttu-id="925f1-112">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="925f1-112">Security Reader</span></span>

<span data-ttu-id="925f1-113">これらのロールを持つアカウントを確認するには、[Microsoft 365 セキュリティ センターで権限を表示](https://security.microsoft.com/permissions)します。</span><span class="sxs-lookup"><span data-stu-id="925f1-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="925f1-114">機能へのアクセス</span><span class="sxs-lookup"><span data-stu-id="925f1-114">Access to functionality</span></span>
<span data-ttu-id="925f1-115">特定の機能へのアクセスは、[Azure AD でのロール](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)によって決まります。</span><span class="sxs-lookup"><span data-stu-id="925f1-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="925f1-116">ユーザーまたはユーザー グループに新しい役割を割り当てる必要がある場合は、グローバル管理者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="925f1-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="925f1-117">保留中の自動化タスクを承認する</span><span class="sxs-lookup"><span data-stu-id="925f1-117">Approve pending automated tasks</span></span>
<span data-ttu-id="925f1-118">「[調査と修復の自動化](mtp-autoir-actions.md)」 は、調査中に見つかったメール、転送ルール、ファイル、持続性機構など、その他の成果物に対処できます。</span><span class="sxs-lookup"><span data-stu-id="925f1-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="925f1-119">明示的な承認が必要な保留中のアクションを承認または拒否するには、Microsoft 365 に特定の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="925f1-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="925f1-120">詳細については、「[アクションセンターの権限](mtp-action-center.md#required-permissions-for-action-center-tasks)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="925f1-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="925f1-121">データへのアクセス</span><span class="sxs-lookup"><span data-stu-id="925f1-121">Access to data</span></span>
<span data-ttu-id="925f1-122">Microsoft 365 Defender データへのアクセスは、Microsoft Defender for Endpoint の役割ベースのアクセス制御 (RBAC) のユーザー グループに割り当てられたスコープを使用して制御できます。</span><span class="sxs-lookup"><span data-stu-id="925f1-122">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="925f1-123">エンドポイント用 Defender の特定のデバイス セットにアクセスのスコープが設定されていない場合は、Microsoft 365 Defender のデータにフル アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="925f1-123">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="925f1-124">ただし、アカウントのスコープを指定すると、対象のデバイスに関するデータのみが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="925f1-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="925f1-125">たとえば、Microsoft Defender for Endpoint の役割を持つ 1 つのユーザー グループにのみ属し、そのユーザー グループに販売デバイスへのアクセス権だけが与えられた場合、Microsoft 365 Defender の販売デバイスに関するデータだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="925f1-125">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="925f1-126">Microsoft Defender for Endpoint の RBAC 設定の詳細</span><span class="sxs-lookup"><span data-stu-id="925f1-126">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="925f1-127">Microsoft Cloud App Security のアクセス制御</span><span class="sxs-lookup"><span data-stu-id="925f1-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="925f1-128">プレビュー中、Microsoft 365 Defender は Cloud App Security の設定に基づいてアクセス制御を適用します。</span><span class="sxs-lookup"><span data-stu-id="925f1-128">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="925f1-129">Microsoft 365 Defender データへのアクセスは、これらの設定の影響を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="925f1-129">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="925f1-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="925f1-130">Related topics</span></span>

- [<span data-ttu-id="925f1-131">Azure AD ロール</span><span class="sxs-lookup"><span data-stu-id="925f1-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="925f1-132">Microsoft Defender for Endpoint RBAC</span><span class="sxs-lookup"><span data-stu-id="925f1-132">Microsoft Defender for Endpoint RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="925f1-133">Cloud App Security roles</span><span class="sxs-lookup"><span data-stu-id="925f1-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
