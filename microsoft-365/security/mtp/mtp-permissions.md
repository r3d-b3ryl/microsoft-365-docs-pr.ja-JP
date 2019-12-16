---
title: Microsoft 365 セキュリティ センターで Microsoft Threat Protection データへのアクセスを管理する
description: Microsoft Threat Protection でデータへのアクセス許可を管理する方法について説明します。
keywords: アクセス、アクセス許可、MTP、Microsoft Threat Protection、M365、セキュリティ、MCAS、MDATP、Cloud App Security、Microsoft Defender Advanced Threat Protection、スコープ、スコーピング、RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: df4450271b7cbbd1862b86cbed295c88c168d66d
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911365"
---
# <a name="manage-access-to-microsoft-threat-protection"></a><span data-ttu-id="7a59c-104">Microsoft Threat Protection へのアクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="7a59c-104">Manage access to Microsoft Threat Protection</span></span>

<span data-ttu-id="7a59c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="7a59c-105">**Applies to:**</span></span>
- <span data-ttu-id="7a59c-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7a59c-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="7a59c-107">次の Azure Active Directory (AD) のロールが割り当てられているアカウントは、Microsoft Threat Protection の機能とデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7a59c-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>
- <span data-ttu-id="7a59c-108">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="7a59c-108">Global administrator</span></span>
- <span data-ttu-id="7a59c-109">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="7a59c-109">Security administrator</span></span>
- <span data-ttu-id="7a59c-110">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="7a59c-110">Security operator</span></span>
- <span data-ttu-id="7a59c-111">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="7a59c-111">Global Reader</span></span>
- <span data-ttu-id="7a59c-112">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="7a59c-112">Security reader</span></span>

<span data-ttu-id="7a59c-113">これらのロールを持つアカウントを確認するには、[Microsoft 365 セキュリティ センターで権限を表示](https://security.microsoft.com/permissions)します。</span><span class="sxs-lookup"><span data-stu-id="7a59c-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="7a59c-114">機能へのアクセス</span><span class="sxs-lookup"><span data-stu-id="7a59c-114">Access to SharePoint data and functionality</span></span>
<span data-ttu-id="7a59c-115">特定の機能へのアクセスは、[Azure AD でのロール](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)によって決まります。</span><span class="sxs-lookup"><span data-stu-id="7a59c-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="7a59c-116">ユーザーまたはユーザー グループに新しい役割を割り当てる必要がある場合は、グローバル管理者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="7a59c-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="7a59c-117">保留中の自動化タスクを承認する</span><span class="sxs-lookup"><span data-stu-id="7a59c-117">Approve pending automated tasks</span></span>
<span data-ttu-id="7a59c-118">「[調査と修復の自動化](mtp-autoir-actions.md)」 は、調査中に見つかったメール、転送ルール、ファイル、持続性機構など、その他の成果物に対処できます。</span><span class="sxs-lookup"><span data-stu-id="7a59c-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="7a59c-119">明示的な承認が必要な保留中のアクションを承認または拒否するには、Microsoft 365 に特定の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a59c-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="7a59c-120">詳細については、「[アクションセンターの権限](mtp-action-center.md#required-permissions-for-action-center-tasks)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7a59c-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="7a59c-121">データへのアクセス</span><span class="sxs-lookup"><span data-stu-id="7a59c-121">Access to non-Microsoft data sources</span></span>
<span data-ttu-id="7a59c-122">Microsoft Threat Protection のデータへのアクセスは、Microsoft Defender ATP の役割ベースのアクセス制御 (RBAC) でユーザーグループに割り当てらているスコープを使用して制御できます。</span><span class="sxs-lookup"><span data-stu-id="7a59c-122">Access to Microsoft Threat Protection data can be controlled using the scope assigned to user groups in Microsoft Defender ATP role-based access control (RBAC).</span></span> <span data-ttu-id="7a59c-123">アクセスが Microsoft Defender ATP の特定のデバイス セットに限定されていない場合は、Microsoft Threat Protection のデータにフル アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7a59c-123">If your access has not been scoped to a specific set of devices in the Microsoft Defender ATP, you will have full access to data in Microsoft Threat Protection.</span></span> <span data-ttu-id="7a59c-124">ただし、アカウントのスコープを指定すると、対象のデバイスに関するデータのみが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="7a59c-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="7a59c-125">たとえば、Microsoft Defender ATP ロールが割り当てられている 1 つのユーザー グループのみに属していて、そのユーザーグループに販売デバイスのみへのアクセス権が付与されている場合は、Microsoft Threat Protection には販売デバイスに関するデータのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a59c-125">For example, if you belong to only one user group with a Microsoft Defender ATP role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft Threat Protection.</span></span> [<span data-ttu-id="7a59c-126">Microsoft Defender ATP の RBAC 設定についての詳細情報を参照します</span><span class="sxs-lookup"><span data-stu-id="7a59c-126">Learn more about RBAC settings in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="7a59c-127">Microsoft Cloud App Security のアクセス制御</span><span class="sxs-lookup"><span data-stu-id="7a59c-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="7a59c-128">プレビュー中、Microsoft Threat Protection は、クラウド アプリのセキュリティ設定に基づくアクセス制御を適用しません。</span><span class="sxs-lookup"><span data-stu-id="7a59c-128">During the preview, Microsoft Threat Protection does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="7a59c-129">これらの設定は、Microsoft Threat Protection のデータへのアクセスに影響しません。</span><span class="sxs-lookup"><span data-stu-id="7a59c-129">Access to Microsoft Threat Protection data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7a59c-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a59c-130">Related topics</span></span>

- [<span data-ttu-id="7a59c-131">Azure AD ロール</span><span class="sxs-lookup"><span data-stu-id="7a59c-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="7a59c-132">Microsoft Defender ATP RBAC</span><span class="sxs-lookup"><span data-stu-id="7a59c-132">Microsoft Defender ATP RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="7a59c-133">Cloud App Security roles</span><span class="sxs-lookup"><span data-stu-id="7a59c-133">Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)