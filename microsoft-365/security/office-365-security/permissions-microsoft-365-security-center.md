---
title: Microsoft 365 Defender ポータルのアクセス許可
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
ms.audience: Admin
ms.topic: article
audience: Admin
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 管理者は、セキュリティに関連するすべてのタスクについて、Microsoft 365 Defender ポータルでアクセス許可を管理する方法を学習できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e810b0146803d22246db6d4248d7d4a6a203834b
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879026"
---
# <a name="permissions-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="cbbf1-103">Microsoft 365 Defender ポータルのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="cbbf1-103">Permissions in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cbbf1-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="cbbf1-104">**Applies to**</span></span>
- [<span data-ttu-id="cbbf1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="cbbf1-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="cbbf1-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="cbbf1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="cbbf1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cbbf1-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="cbbf1-108">すべての Microsoft 365 サービスに関するセキュリティのシナリオを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-108">You need to manage security scenarios that span all the Microsoft 365 services.</span></span> <span data-ttu-id="cbbf1-109">また、組織内の適切なユーザーに適切な管理者権限を付与する柔軟性も必要です。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-109">And you need the flexibility to give the right admin permissions to the right people in your organization.</span></span>

<span data-ttu-id="cbbf1-110">Microsoft 365 Defender ポータルは <https://security.microsoft.com> からアクセスできます。これは、Microsoft 365 でセキュリティ タスクを実行するユーザーのアクセス許可の直接的な管理をサポートします。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-110">The Microsoft 365 Defender portal at <https://security.microsoft.com> supports directly managing permissions for users who perform security tasks in Microsoft 365.</span></span> <span data-ttu-id="cbbf1-111">Microsoft 365 Defender ポータルを使用してアクセス許可を管理することで、セキュリティに関連するすべてのタスクについて、アクセス許可を一元的に管理できます。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-111">By using the Microsoft 365 Defender portal to manage permissions, you can manage permissions centrally for all tasks related to security.</span></span>

<span data-ttu-id="cbbf1-112">Microsoft 365 Defender ポータルでアクセス許可を管理するには、**[アクセス許可と役割]** または <https://security.microsoft.com/securitypermissions> に移動します。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-112">To manage permissions in the Microsoft 365 Defender portal, go to **Permissions & roles** or <https://security.microsoft.com/securitypermissions>.</span></span> <span data-ttu-id="cbbf1-113">Microsoft 365 Defender ポータルで、**グローバル管理者** または **組織管理** 役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-113">You need to be a **global administrator** or a member of the **Organization Management** role group in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="cbbf1-114">具体的には、**"役割の管理"** 役割を使用すると、ユーザーは Microsoft 365 Defender ポータルで役割グループの表示、作成、および変更をすることができます。また、この役割は既定で **"組織管理"** 役割グループにのみ割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-114">Specifically, the **Role Management** role allows users to view, create, and modify role groups in the Microsoft 365 Defender portal, and by default, that role is assigned only to the **Organization Management** role group.</span></span>

> [!NOTE]
> <span data-ttu-id="cbbf1-115">Microsoft 365 コンプライアンス センターのアクセス許可については、「[Microsoft 365 コンプライアンス センターのアクセス許可](../../compliance/microsoft-365-compliance-center-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-115">For information about permissions in the Microsoft 365 compliance center, see [Permissions in the Microsoft 365 compliance center](../../compliance/microsoft-365-compliance-center-permissions.md).</span></span>

## <a name="relationship-of-members-roles-and-role-groups"></a><span data-ttu-id="cbbf1-116">メンバー、役割、役割グループの関係</span><span class="sxs-lookup"><span data-stu-id="cbbf1-116">Relationship of members, roles, and role groups</span></span>

<span data-ttu-id="cbbf1-117">Microsoft 365 Defender ポータルのアクセス許可は、役割ベースのアクセス制御 (RBAC) の権限モデルに基づきます。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-117">Permissions in the Microsoft 365 Defender portal are based on the role-based access control (RBAC) permissions model.</span></span> <span data-ttu-id="cbbf1-118">RBAC は、Microsoft 365 のほとんどのサービスで使用されているのと同じアクセス許可モデルです。そのため、これらのサービスのアクセス許可構造に慣れている場合、Microsoft 365 Defender ポータルでのアクセス許可の付与が非常によく似ていることに気づくでしょう。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-118">RBAC is the same permissions model that's used by most Microsoft 365 services, so if you're familiar with the permission structure in these services, granting permissions in the Microsoft 365 Defender portal will be very familiar.</span></span>

<span data-ttu-id="cbbf1-119">**役割** は、一連のタスクを実行するアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-119">A **role** grants the permissions to do a set of tasks.</span></span>

<span data-ttu-id="cbbf1-120">**役割グループ** は、ユーザーが Microsoft 365 Defender ポータルで仕事を行えるようにする一連の役割です。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-120">A **role group** is a set of roles that lets people do their jobs in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="cbbf1-121">たとえば、"攻撃シミュレーター管理者" 役割グループには、攻撃シミュレーション トレーニングのあらゆる側面を作成および管理するための "攻撃シミュレーター管理者" 役割が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-121">For example, the Attack Simulator Administrators role group includes the Attack Simulator Admin role to create and manage all aspects of attack simulation training.</span></span>

<span data-ttu-id="cbbf1-122">Microsoft 365 Defender ポータルには、割り当てる必要がある最も一般的なタスクと機能に対する既定の役割グループが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-122">The Microsoft 365 Defender portal includes default role groups for the most common tasks and functions that you'll need to assign.</span></span> <span data-ttu-id="cbbf1-123">通常、個々のユーザーを既定の役割グループの **メンバー** として追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-123">Generally, we recommend simply adding individual users as **members** to the default role groups.</span></span>

![役割グループと、ロールおよびメンバーとの関係を示す図](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="roles-and-role-groups-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="cbbf1-125">Microsoft 365 Defender ポータルの役割と役割グループ</span><span class="sxs-lookup"><span data-stu-id="cbbf1-125">Roles and role groups in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="cbbf1-126">Microsoft 365 Defender ポータルの **[アクセス許可と役割]** では、次の種類の役割と役割グループを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-126">The following types of roles and role groups are available in **Permissions & roles** in the Microsoft 365 Defender portalr:</span></span>

- <span data-ttu-id="cbbf1-127">**Azure AD ロール**: 役割と割り当てられたユーザーを表示できますが、Microsoft 365 Defender ポータルで直接管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-127">**Azure AD roles**: You can view the roles and assigned users, but you can't manage them directly in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="cbbf1-128">Azure AD ロールは、**すべての** Microsoft 365 サービスでアクセス許可を割り当てる中心的な役割です。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-128">Azure AD roles are central roles that assign permissions for **all** Microsoft 365 services.</span></span>

- <span data-ttu-id="cbbf1-129">**メールと共同作業の役割**: セキュリティ/コンプライアンス センターで使用できるのと同じ役割グループですが、Microsoft 365 Defender ポータルから直接管理できます。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-129">**Email & collaboration roles**: These are the same role groups that are available in the Security & Compliance Center, but you can manage them directly in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="cbbf1-130">ここで割り当てるアクセス許可は Microsoft 365 Defender ポータル、Microsoft 365 コンプライアンス センター、およびセキュリティ/コンプライアンス センターに固有のものであり、他の Microsoft 365 ワークロードで必要なすべてのアクセス許可をカバーするものではありません。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-130">The permissions that you assign here are specific to the Microsoft 365 Defender portal, the Microsoft 365 compliance center, and the Security & Compliance Center, and don't cover all of the permissions that are needed in other Microsoft 365 workloads.</span></span>

![Microsoft 365 Defender ポータルのアクセス許可と役割のページ](../../media/m365-sc-permissions-and-roles-page.png)

### <a name="azure-ad-roles-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="cbbf1-132">Microsoft 365 Defender ポータルの Azure AD ロール</span><span class="sxs-lookup"><span data-stu-id="cbbf1-132">Azure AD roles in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="cbbf1-133">**[メールと共同作業の役割]** \> **[アクセス許可と役割]** \> **[Azure AD ロール]** \> **[役割]** (または直接 <https://security.microsoft.com/aadpermissions>) に移動すると、このセクションで説明されている Azure AD ロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-133">When you go **Email & collaboration roles** \> **Permissions & roles** \> **Azure AD roles** \> **Roles** (or directly to <https://security.microsoft.com/aadpermissions>) you'll see the Azure AD roles that are described in this section.</span></span>

<span data-ttu-id="cbbf1-134">役割を選択すると、役割の説明とユーザーの割り当てを含む詳細ポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-134">When you select a role, a details flyout that contains the description of the role and the user assignments appears.</span></span> <span data-ttu-id="cbbf1-135">ただし、それらの割り当てを管理するには、詳細ポップアップで **[Azure AD でメンバーを管理する]** をクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-135">But to manage those assignments, you need to click **Manage members in Azure AD** in the details flyout.</span></span>

![Azure Active Directory のアクセス許可管理へのリンク](../../media/permissions-manage-in-azure-ad-link.png)

<span data-ttu-id="cbbf1-137">詳細については、「[Azure Active Directory で管理者ロールを表示して割り当てる](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-137">For more information, see [View and assign administrator roles in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<br>

****

|<span data-ttu-id="cbbf1-138">役割</span><span class="sxs-lookup"><span data-stu-id="cbbf1-138">Role</span></span>|<span data-ttu-id="cbbf1-139">内容</span><span class="sxs-lookup"><span data-stu-id="cbbf1-139">Description</span></span>|
|---|---|
|<span data-ttu-id="cbbf1-140">**全体管理者**</span><span class="sxs-lookup"><span data-stu-id="cbbf1-140">**Global administrator**</span></span>|<span data-ttu-id="cbbf1-141">Microsoft 365 サービスのすべての管理機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-141">Access to all administrative features in all Microsoft 365 services.</span></span> <span data-ttu-id="cbbf1-142">他の管理者ロールを割り当てることができるのは全体管理者だけです。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-142">Only global administrators can assign other administrator roles.</span></span> <span data-ttu-id="cbbf1-143">詳細については、「[グローバル管理者または会社の管理者](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-143">For more information, see [Global Administrator / Company Administrator](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator).</span></span>|
|<span data-ttu-id="cbbf1-144">**コンプライアンス データ管理者**</span><span class="sxs-lookup"><span data-stu-id="cbbf1-144">**Compliance data administrator**</span></span>|<span data-ttu-id="cbbf1-145">Microsoft 365 全体の組織のデータを追跡し、保護されていることを確認し、あらゆる問題を把握して分析しリスクを軽減する手伝いをします。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-145">Keep track of your organization's data across Microsoft 365, make sure it's protected, and get insights into any issues to help mitigate risks.</span></span> <span data-ttu-id="cbbf1-146">詳細については、「[コンプライアンス データ管理者](/azure/active-directory/roles/permissions-reference#compliance-data-administrator)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-146">For more information, see [Compliance Data Administrator](/azure/active-directory/roles/permissions-reference#compliance-data-administrator).</span></span>|
|<span data-ttu-id="cbbf1-147">**コンプライアンス管理者**</span><span class="sxs-lookup"><span data-stu-id="cbbf1-147">**Compliance administrator**</span></span>|<span data-ttu-id="cbbf1-148">組織が規制要件を遵守し続けること、電子情報開示ケースを管理すること、および Microsoft 365 の使用場所、ID、アプリ全体のデータ ガバナンス ポリシーを維持します。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-148">Help your organization stay compliant with any regulatory requirements, manage eDiscovery cases, and maintain data governance policies across Microsoft 365 locations, identities, and apps.</span></span> <span data-ttu-id="cbbf1-149">詳細については、「[コンプライアンス管理者](/azure/active-directory/roles/permissions-reference#compliance-administrator)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-149">For more information, see [Compliance Administrator](/azure/active-directory/roles/permissions-reference#compliance-administrator).</span></span>|
|<span data-ttu-id="cbbf1-150">**セキュリティ オペレーター**</span><span class="sxs-lookup"><span data-stu-id="cbbf1-150">**Security operator**</span></span>|<span data-ttu-id="cbbf1-151">このロールを持つユーザーは、Microsoft 365 のユーザー、デバイス、コンテンツに対するアクティブな脅威を表示、調査、および対処します。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-151">View, investigate, and respond to active threats to your Microsoft 365 users, devices, and content.</span></span> <span data-ttu-id="cbbf1-152">詳細については、「[セキュリティ オペレーター](/azure/active-directory/roles/permissions-reference#security-operator)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-152">For more information, see [Security Operator](/azure/active-directory/roles/permissions-reference#security-operator).</span></span>|
|<span data-ttu-id="cbbf1-153">**セキュリティ閲覧者**</span><span class="sxs-lookup"><span data-stu-id="cbbf1-153">**Security reader**</span></span>|<span data-ttu-id="cbbf1-154">このロールを持つユーザーは、Microsoft 365 のユーザー、デバイス、コンテンツに対するアクティブな脅威を表示、調査ができますが、セキュリティ オペレーターとは異なり、アクションを実行するアクセス許可はありません。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-154">View and investigate active threats to your Microsoft 365 users, devices, and content, but (unlike the Security operator) they do not have permissions to respond by taking action.</span></span> <span data-ttu-id="cbbf1-155">詳細については、「[セキュリティ 閲覧者](/azure/active-directory/roles/permissions-reference#security-reader)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-155">For more information, see [Security Reader](/azure/active-directory/roles/permissions-reference#security-reader).</span></span>|
|<span data-ttu-id="cbbf1-156">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="cbbf1-156">**Security administrator**</span></span>|<span data-ttu-id="cbbf1-157">このロールを持つユーザーは、セキュリティ ポリシーを管理し、Microsoft 365 製品全体のセキュリティ分析とレポートを確認し、脅威の情勢を十分に把握し迅速に対処して、組織の全体的なセキュリティを制御します。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-157">Control your organization's overall security by managing security policies, reviewing security analytics and reports across Microsoft 365 products, and staying up-to-speed on the threat landscape.</span></span> <span data-ttu-id="cbbf1-158">詳細については、「[セキュリティ 管理者](/azure/active-directory/roles/permissions-reference#security-administrator)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-158">For more information, see [Security Administrator](/azure/active-directory/roles/permissions-reference#security-administrator).</span></span>|
|<span data-ttu-id="cbbf1-159">**グローバル閲覧者**</span><span class="sxs-lookup"><span data-stu-id="cbbf1-159">**Global reader**</span></span>|<span data-ttu-id="cbbf1-160">読み取り専用バージョンの **グローバル閲覧者** のロール。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-160">The read-only version of the **Global administrator** role.</span></span> <span data-ttu-id="cbbf1-161">Microsoft 365 のすべての設定と管理情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-161">View all settings and administrative information across Microsoft 365.</span></span> <span data-ttu-id="cbbf1-162">詳細については、「[グローバル閲覧者](/azure/active-directory/roles/permissions-reference#global-reader)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-162">For more information, see [Global Reader](/azure/active-directory/roles/permissions-reference#global-reader).</span></span>|
|<span data-ttu-id="cbbf1-163">**攻撃のシミュレーションの管理者**</span><span class="sxs-lookup"><span data-stu-id="cbbf1-163">**Attack simulation administrator**</span></span>|<span data-ttu-id="cbbf1-164">[攻撃シミュレーション](attack-simulation-training.md)の作成、シミュレーションの開始/スケジューリング、シミュレーション結果の確認のすべての側面を作成および管理します。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-164">Create and manage all aspects of [attack simulation](attack-simulation-training.md) creation, launch/scheduling of a simulation, and the review of simulation results.</span></span> <span data-ttu-id="cbbf1-165">詳細については、「[攻撃のシミュレーションの管理者](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-165">For more information, see [Attack Simulation Administrator](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator).</span></span>|
|<span data-ttu-id="cbbf1-166">**攻撃のペイロードの作成者**</span><span class="sxs-lookup"><span data-stu-id="cbbf1-166">**Attack payload author**</span></span>|<span data-ttu-id="cbbf1-167">攻撃のペイロードを作成しますが、実際に起動することやスケジュールすることはしません。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-167">Create attack payloads but not actually launch or schedule them.</span></span> <span data-ttu-id="cbbf1-168">詳細については、「[攻撃のペイロードの作成者](/azure/active-directory/roles/permissions-reference#attack-payload-author)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-168">For more information, see [Attack Payload Author](/azure/active-directory/roles/permissions-reference#attack-payload-author).</span></span>|
|

### <a name="email--collaboration-roles-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="cbbf1-169">Microsoft 365 Defender ポータルのメールと共同作業の役割</span><span class="sxs-lookup"><span data-stu-id="cbbf1-169">Email & collaboration roles in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="cbbf1-170">**[メールと共同作業の役割]** \> **[アクセス許可と役割]** \> **[メールと共同作業の役割]** \> **[役割]** (または直接 <https://security.microsoft.com/emailandcollabpermissions>) に移動すると、セキュリティ/コンプライアンス センターで使用できるのと同じ役割グループが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-170">When you go to **Email & collaboration roles** \> **Permissions & roles** \> **Email & collaboration roles** \> **Roles** (or directly to <https://security.microsoft.com/emailandcollabpermissions>) you'll see the same role groups that are available in the Security & Compliance Center.</span></span>

<span data-ttu-id="cbbf1-171">これらの役割グループの詳細については、「[セキュリティ/コンプライアンス センターの権限](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-171">For complete information about these role groups, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)</span></span>

#### <a name="modify-email--collaboration-role-membership-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="cbbf1-172">Microsoft 365 Defender ポータルのメールと共同作業の役割メンバーシップを変更する</span><span class="sxs-lookup"><span data-stu-id="cbbf1-172">Modify Email & collaboration role membership in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="cbbf1-173">Microsoft 365 Defender ポータルで、**[メールと共同作業の役割]** \> **[アクセス許可と役割]** \> **[メールと共同作業の役割]** \> **[役割]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-173">In the Microsoft 365 Defender portal, go to **Email & collaboration roles** \> **Permissions & roles** \> **Email & collaboration roles** \> **Roles**.</span></span>

2. <span data-ttu-id="cbbf1-174">**[アクセス許可]** ページが開いたら、変更する役割グループをリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-174">In the **Permissions** page that opens, select the role group that you want to modify from the list.</span></span> <span data-ttu-id="cbbf1-175">**[名前]** の列見出しをクリックしてリストを名前で並べ替えることができます。または、**[検索]** ![[検索] アイコン](../../media/m365-cc-sc-search-icon.png) をクリックして役割グループを探すこともできます。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-175">You can click on the **Name** column header to sort the list by name, or you can click **Search** ![Search icon](../../media/m365-cc-sc-search-icon.png) to find the role group.</span></span>

3. <span data-ttu-id="cbbf1-176">役割グループの詳細ポップアップが表示されたら、**[メンバー]** セクションで **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-176">In the role group details flyout that appears, click **Edit** in the **Members** section.</span></span>

4. <span data-ttu-id="cbbf1-177">**[メンバーの選択の編集]** ページが開いたら、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-177">In the **Editing choose members** page that appears, do one of the following steps:</span></span>
   - <span data-ttu-id="cbbf1-178">役割グループのメンバーが存在しない場合、**[メンバーの選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-178">If there are no role group members, click **Choose members**.</span></span>
   - <span data-ttu-id="cbbf1-179">役割グループのメンバーが存在する場合、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-179">If there are existing role group members, click **Edit**</span></span>

5. <span data-ttu-id="cbbf1-180">**[メンバーの選択]** ポップアップが表示されたら、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-180">In the **Choose members** flyout that appears, do one of the following steps:</span></span>

   - <span data-ttu-id="cbbf1-181">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-181">Click **Add**.</span></span> <span data-ttu-id="cbbf1-182">ユーザーの一覧が表示されたら、1 人以上のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-182">In the list of users that appears, select one or more users.</span></span> <span data-ttu-id="cbbf1-183">または、**[検索]** ![[検索] アイコン](../../media/m365-cc-sc-search-icon.png) をクリックして、ユーザーを探して選択します。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-183">Or, you can click **Search** ![Search icon](../../media/m365-cc-sc-search-icon.png) to find and select users.</span></span>

     <span data-ttu-id="cbbf1-184">追加するユーザーを選択したら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-184">When you've selected the users that you want to add, click **Add**.</span></span>

   - <span data-ttu-id="cbbf1-185">**[削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-185">Click **Remove**.</span></span> <span data-ttu-id="cbbf1-186">存在するメンバーを 1 人以上選択します。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-186">Select one or more of the existing members.</span></span> <span data-ttu-id="cbbf1-187">または、**[検索]** ![[検索] アイコン](../../media/m365-cc-sc-search-icon.png) をクリックして、メンバーを見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-187">Or, you can click **Search** ![Search icon](../../media/m365-cc-sc-search-icon.png) to find and select members.</span></span>

     <span data-ttu-id="cbbf1-188">削除するユーザーを選択したら、**[削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-188">When you've selected the users that you want to remove, click **Remove**.</span></span>

6. <span data-ttu-id="cbbf1-189">**[メンバーの選択]** ポップアップに戻り、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-189">Back on the **Choose members** flyout, click **Done**.</span></span>

7. <span data-ttu-id="cbbf1-190">**[メンバーの選択の編集]** ページに戻り、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-190">Back on the **Editing choose members** page, click **Save**.</span></span>

8. <span data-ttu-id="cbbf1-191">役割グループの詳細ポップアップに戻り、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cbbf1-191">Back on the role group details flyout, click **Done**.</span></span>
