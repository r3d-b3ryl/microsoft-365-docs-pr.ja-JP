---
title: Microsoft 365 セキュリティ センターのアクセス許可
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
description: 管理者が Microsoft 365 セキュリティ センターでセキュリティに関連するすべてのタスクのアクセス許可を管理する方法を説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9c2d28510c25290921084e6a238fa8c781c35624
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772525"
---
# <a name="permissions-in-the-microsoft-365-security-center"></a><span data-ttu-id="34ec1-103">Microsoft 365 セキュリティ センターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="34ec1-103">Permissions in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="34ec1-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="34ec1-104">**Applies to**</span></span>
- [<span data-ttu-id="34ec1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="34ec1-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="34ec1-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="34ec1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="34ec1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34ec1-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="34ec1-108">すべての Microsoft 365 サービスに関するセキュリティのシナリオを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ec1-108">You need to manage security scenarios that span all the Microsoft 365 services.</span></span> <span data-ttu-id="34ec1-109">また、組織内の適切なユーザーに適切な管理者権限を付与する柔軟性も必要です。</span><span class="sxs-lookup"><span data-stu-id="34ec1-109">And you need the flexibility to give the right admin permissions to the right people in your organization.</span></span>

<span data-ttu-id="34ec1-110">Microsoft 365 セキュリティ センターは <https://security.microsoft.com> からアクセスできます。これは、Microsoft 365 でセキュリティ タスクを実行するユーザーのアクセス許可の直接的な管理をサポートします。</span><span class="sxs-lookup"><span data-stu-id="34ec1-110">The Microsoft 365 security center at <https://security.microsoft.com> supports directly managing permissions for users who perform security tasks in Microsoft 365.</span></span> <span data-ttu-id="34ec1-111">セキュリティ センターを使用してアクセス許可を管理することで、セキュリティに関連するすべてのタスクについて、アクセス許可を一元的に管理できます。</span><span class="sxs-lookup"><span data-stu-id="34ec1-111">By using the security center to manage permissions, you can manage permissions centrally for all tasks related to security.</span></span>

<span data-ttu-id="34ec1-112">セキュリティ センターでアクセス許可を管理するには、**[アクセス許可と役割]** または <https://security.microsoft.com/securitypermissions> に移動します。</span><span class="sxs-lookup"><span data-stu-id="34ec1-112">To manage permissions in the security center, go to **Permissions & roles** or <https://security.microsoft.com/securitypermissions>.</span></span> <span data-ttu-id="34ec1-113">セキュリティ センターで、**グローバル管理者** または **組織管理** 役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ec1-113">You need to be a **global administrator** or a member of the **Organization Management** role group in the security center.</span></span> <span data-ttu-id="34ec1-114">具体的には、**"役割の管理"** 役割を使用すると、ユーザーはセキュリティ センターで役割グループの表示、作成、および変更をすることができます。また、この役割は既定で **"組織管理"** 役割グループにのみ割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="34ec1-114">Specifically, the **Role Management** role allows users to view, create, and modify role groups in the security center, and by default, that role is assigned only to the **Organization Management** role group.</span></span>

## <a name="relationship-of-members-roles-and-role-groups"></a><span data-ttu-id="34ec1-115">メンバー、役割、役割グループの関係</span><span class="sxs-lookup"><span data-stu-id="34ec1-115">Relationship of members, roles, and role groups</span></span>

<span data-ttu-id="34ec1-116">セキュリティ センターのアクセス許可は、役割ベースのアクセス制御 (RBAC) の権限モデルに基づきます。</span><span class="sxs-lookup"><span data-stu-id="34ec1-116">Permissions in the security center are based on the role-based access control (RBAC) permissions model.</span></span> <span data-ttu-id="34ec1-117">RBAC は、Microsoft 365 のほとんどのサービスで使用されているのと同じアクセス許可モデルです。そのため、これらのサービスのアクセス許可構造に慣れている場合、セキュリティ センターでのアクセス許可の付与が非常によく似ていることに気づくでしょう。</span><span class="sxs-lookup"><span data-stu-id="34ec1-117">RBAC is the same permissions model that's used by most Microsoft 365 services, so if you're familiar with the permission structure in these services, granting permissions in the security center will be very familiar.</span></span>

<span data-ttu-id="34ec1-118">**役割** は、一連のタスクを実行するアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="34ec1-118">A **role** grants the permissions to do a set of tasks.</span></span>

<span data-ttu-id="34ec1-119">**役割グループ** は、ユーザーがセキュリティ センターで仕事を行えるようにする一連の役割です。</span><span class="sxs-lookup"><span data-stu-id="34ec1-119">A **role group** is a set of roles that lets people do their jobs in the security center.</span></span> <span data-ttu-id="34ec1-120">たとえば、"攻撃シミュレーター管理者" 役割グループには、攻撃シミュレーション トレーニングのあらゆる側面を作成および管理するための "攻撃シミュレーター管理者" 役割が含まれます。</span><span class="sxs-lookup"><span data-stu-id="34ec1-120">For example, the Attack Simulator Administrators role group includes the Attack Simulator Admin role to create and manage all aspects of attack simulation training.</span></span>

<span data-ttu-id="34ec1-121">セキュリティ センターには、割り当てる必要がある最も一般的なタスクと機能に対する既定の役割グループが含まれます。</span><span class="sxs-lookup"><span data-stu-id="34ec1-121">The security center includes default role groups for the most common tasks and functions that you'll need to assign.</span></span> <span data-ttu-id="34ec1-122">通常、個々のユーザーを既定の役割グループの **メンバー** として追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="34ec1-122">Generally, we recommend simply adding individual users as **members** to the default role groups.</span></span>

![役割グループと、ロールおよびメンバーとの関係を示す図](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="roles-and-role-groups-in-the-security-center"></a><span data-ttu-id="34ec1-124">セキュリティ センターの役割と役割グループ</span><span class="sxs-lookup"><span data-stu-id="34ec1-124">Roles and role groups in the security center</span></span>

<span data-ttu-id="34ec1-125">セキュリティ センターの **[アクセス許可と役割]** では、次の種類の役割と役割グループを使用できます。</span><span class="sxs-lookup"><span data-stu-id="34ec1-125">The following types of roles and role groups are available in **Permissions & roles** in the security center:</span></span>

- <span data-ttu-id="34ec1-126">**Azure AD ロール**: 役割と割り当てられたユーザーを表示できますが、セキュリティ センターで直接管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="34ec1-126">**Azure AD roles**: You can view the roles and assigned users, but you can't manage them directly in the security center.</span></span> <span data-ttu-id="34ec1-127">Azure AD ロールは、**すべての** Microsoft 365 サービスでアクセス許可を割り当てる中心的な役割です。</span><span class="sxs-lookup"><span data-stu-id="34ec1-127">Azure AD roles are central roles that assign permissions for **all** Microsoft 365 services.</span></span>

- <span data-ttu-id="34ec1-128">**メールと共同作業の役割**: セキュリティ/コンプライアンス センターで使用できるのと同じ役割グループですが、セキュリティ センターから直接管理できます。</span><span class="sxs-lookup"><span data-stu-id="34ec1-128">**Email & collaboration roles**: These are the same role groups that are available in the Security & Compliance Center, but you can manage them directly in the security center.</span></span> <span data-ttu-id="34ec1-129">ここで割り当てるアクセス許可は Microsoft 365 セキュリティ センター、Microsoft 365 コンプライアンス センターおよびセキュリティ/コンプライアンス センターに固有のものであり、他の Microsoft 365 ワークロードで必要なすべてのアクセス許可をカバーするものではありません。</span><span class="sxs-lookup"><span data-stu-id="34ec1-129">The permissions that you assign here are specific to the Microsoft 365 security center, the Microsoft 365 compliance center, and the Security & Compliance Center, and don't cover all of the permissions that are needed in other Microsoft 365 workloads.</span></span>

![Microsoft 365 セキュリティ センターのアクセス許可と役割のページ](../../media/m365-sc-permissions-and-roles-page.png)

### <a name="azure-ad-roles-in-the-security-center"></a><span data-ttu-id="34ec1-131">セキュリティ センターの Azure AD ロール</span><span class="sxs-lookup"><span data-stu-id="34ec1-131">Azure AD roles in the security center</span></span>

<span data-ttu-id="34ec1-132">**[メールと共同作業の役割]** \> **[アクセス許可と役割]** \> **[Azure AD ロール]** \> **[役割]** (または直接 <https://security.microsoft.com/aadpermissions>) に移動すると、このセクションで説明されている Azure AD ロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="34ec1-132">When you go **Email & collaboration roles** \> **Permissions & roles** \> **Azure AD roles** \> **Roles** (or directly to <https://security.microsoft.com/aadpermissions>) you'll see the Azure AD roles that are described in this section.</span></span>

<span data-ttu-id="34ec1-133">役割を選択すると、役割の説明とユーザーの割り当てを含む詳細ポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="34ec1-133">When you select a role, a details flyout that contains the description of the role and the user assignments appears.</span></span> <span data-ttu-id="34ec1-134">ただし、それらの割り当てを管理するには、詳細ポップアップで **[Azure AD でメンバーを管理する]** をクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ec1-134">But to manage those assignments, you need to click **Manage members in Azure AD** in the details flyout.</span></span>

![Azure Active Directory のアクセス許可管理へのリンク](../../media/permissions-manage-in-azure-ad-link.png)

<span data-ttu-id="34ec1-136">詳細については、「[Azure Active Directory で管理者ロールを表示して割り当てる](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34ec1-136">For more information, see [View and assign administrator roles in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<br>

****

|<span data-ttu-id="34ec1-137">役割</span><span class="sxs-lookup"><span data-stu-id="34ec1-137">Role</span></span>|<span data-ttu-id="34ec1-138">内容</span><span class="sxs-lookup"><span data-stu-id="34ec1-138">Description</span></span>|
|---|---|
|<span data-ttu-id="34ec1-139">**全体管理者**</span><span class="sxs-lookup"><span data-stu-id="34ec1-139">**Global administrator**</span></span>|<span data-ttu-id="34ec1-140">Microsoft 365 サービスのすべての管理機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="34ec1-140">Access to all administrative features in all Microsoft 365 services.</span></span> <span data-ttu-id="34ec1-141">他の管理者ロールを割り当てることができるのは全体管理者だけです。</span><span class="sxs-lookup"><span data-stu-id="34ec1-141">Only global administrators can assign other administrator roles.</span></span> <span data-ttu-id="34ec1-142">詳細については、「[グローバル管理者または会社の管理者](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34ec1-142">For more information, see [Global Administrator / Company Administrator](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator).</span></span>|
|<span data-ttu-id="34ec1-143">**コンプライアンス データ管理者**</span><span class="sxs-lookup"><span data-stu-id="34ec1-143">**Compliance data administrator**</span></span>|<span data-ttu-id="34ec1-144">Microsoft 365 全体の組織のデータを追跡し、保護されていることを確認し、あらゆる問題を把握して分析しリスクを軽減する手伝いをします。</span><span class="sxs-lookup"><span data-stu-id="34ec1-144">Keep track of your organization's data across Microsoft 365, make sure it's protected, and get insights into any issues to help mitigate risks.</span></span> <span data-ttu-id="34ec1-145">詳細については、「[コンプライアンス データ管理者](/azure/active-directory/roles/permissions-reference#compliance-data-administrator)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34ec1-145">For more information, see [Compliance Data Administrator](/azure/active-directory/roles/permissions-reference#compliance-data-administrator).</span></span>|
|<span data-ttu-id="34ec1-146">**コンプライアンス管理者**</span><span class="sxs-lookup"><span data-stu-id="34ec1-146">**Compliance administrator**</span></span>|<span data-ttu-id="34ec1-147">組織が規制要件を遵守し続けること、電子情報開示ケースを管理すること、および Microsoft 365 の使用場所、ID、アプリ全体のデータ ガバナンス ポリシーを維持します。</span><span class="sxs-lookup"><span data-stu-id="34ec1-147">Help your organization stay compliant with any regulatory requirements, manage eDiscovery cases, and maintain data governance policies across Microsoft 365 locations, identities, and apps.</span></span> <span data-ttu-id="34ec1-148">詳細については、「[コンプライアンス管理者](/azure/active-directory/roles/permissions-reference#compliance-administrator)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34ec1-148">For more information, see [Compliance Administrator](/azure/active-directory/roles/permissions-reference#compliance-administrator).</span></span>|
|<span data-ttu-id="34ec1-149">**セキュリティ オペレーター**</span><span class="sxs-lookup"><span data-stu-id="34ec1-149">**Security operator**</span></span>|<span data-ttu-id="34ec1-150">このロールを持つユーザーは、Microsoft 365 のユーザー、デバイス、コンテンツに対するアクティブな脅威を表示、調査、および対処します。</span><span class="sxs-lookup"><span data-stu-id="34ec1-150">View, investigate, and respond to active threats to your Microsoft 365 users, devices, and content.</span></span> <span data-ttu-id="34ec1-151">詳細については、「[セキュリティ オペレーター](/azure/active-directory/roles/permissions-reference#security-operator)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34ec1-151">For more information, see [Security Operator](/azure/active-directory/roles/permissions-reference#security-operator).</span></span>|
|<span data-ttu-id="34ec1-152">**セキュリティ閲覧者**</span><span class="sxs-lookup"><span data-stu-id="34ec1-152">**Security reader**</span></span>|<span data-ttu-id="34ec1-153">このロールを持つユーザーは、Microsoft 365 のユーザー、デバイス、コンテンツに対するアクティブな脅威を表示、調査ができますが、セキュリティ オペレーターとは異なり、アクションを実行するアクセス許可はありません。</span><span class="sxs-lookup"><span data-stu-id="34ec1-153">View and investigate active threats to your Microsoft 365 users, devices, and content, but (unlike the Security operator) they do not have permissions to respond by taking action.</span></span> <span data-ttu-id="34ec1-154">詳細については、「[セキュリティ 閲覧者](/azure/active-directory/roles/permissions-reference#security-reader)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34ec1-154">For more information, see [Security Reader](/azure/active-directory/roles/permissions-reference#security-reader).</span></span>|
|<span data-ttu-id="34ec1-155">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="34ec1-155">**Security administrator**</span></span>|<span data-ttu-id="34ec1-156">このロールを持つユーザーは、セキュリティ ポリシーを管理し、Microsoft 365 製品全体のセキュリティ分析とレポートを確認し、脅威の情勢を十分に把握し迅速に対処して、組織の全体的なセキュリティを制御します。</span><span class="sxs-lookup"><span data-stu-id="34ec1-156">Control your organization's overall security by managing security policies, reviewing security analytics and reports across Microsoft 365 products, and staying up-to-speed on the threat landscape.</span></span> <span data-ttu-id="34ec1-157">詳細については、「[セキュリティ 管理者](/azure/active-directory/roles/permissions-reference#security-administrator)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34ec1-157">For more information, see [Security Administrator](/azure/active-directory/roles/permissions-reference#security-administrator).</span></span>|
|<span data-ttu-id="34ec1-158">**グローバル閲覧者**</span><span class="sxs-lookup"><span data-stu-id="34ec1-158">**Global reader**</span></span>|<span data-ttu-id="34ec1-159">読み取り専用バージョンの **グローバル閲覧者** のロール。</span><span class="sxs-lookup"><span data-stu-id="34ec1-159">The read-only version of the **Global administrator** role.</span></span> <span data-ttu-id="34ec1-160">Microsoft 365 のすべての設定と管理情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="34ec1-160">View all settings and administrative information across Microsoft 365.</span></span> <span data-ttu-id="34ec1-161">詳細については、「[グローバル閲覧者](/azure/active-directory/roles/permissions-reference#global-reader)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34ec1-161">For more information, see [Global Reader](/azure/active-directory/roles/permissions-reference#global-reader).</span></span>|
|<span data-ttu-id="34ec1-162">**攻撃のシミュレーションの管理者**</span><span class="sxs-lookup"><span data-stu-id="34ec1-162">**Attack simulation administrator**</span></span>|<span data-ttu-id="34ec1-163">[攻撃シミュレーション](attack-simulation-training.md)の作成、シミュレーションの開始/スケジューリング、シミュレーション結果の確認のすべての側面を作成および管理します。</span><span class="sxs-lookup"><span data-stu-id="34ec1-163">Create and manage all aspects of [attack simulation](attack-simulation-training.md) creation, launch/scheduling of a simulation, and the review of simulation results.</span></span> <span data-ttu-id="34ec1-164">詳細については、「[攻撃のシミュレーションの管理者](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34ec1-164">For more information, see [Attack Simulation Administrator](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator).</span></span>|
|<span data-ttu-id="34ec1-165">**攻撃のペイロードの作成者**</span><span class="sxs-lookup"><span data-stu-id="34ec1-165">**Attack payload author**</span></span>|<span data-ttu-id="34ec1-166">攻撃のペイロードを作成しますが、実際に起動することやスケジュールすることはしません。</span><span class="sxs-lookup"><span data-stu-id="34ec1-166">Create attack payloads but not actually launch or schedule them.</span></span> <span data-ttu-id="34ec1-167">詳細については、「[攻撃のペイロードの作成者](/azure/active-directory/roles/permissions-reference#attack-payload-author)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34ec1-167">For more information, see [Attack Payload Author](/azure/active-directory/roles/permissions-reference#attack-payload-author).</span></span>|
|

### <a name="email--collaboration-roles-in-the-security-center"></a><span data-ttu-id="34ec1-168">セキュリティ センターのメールと共同作業の役割</span><span class="sxs-lookup"><span data-stu-id="34ec1-168">Email & collaboration roles in the security center</span></span>

<span data-ttu-id="34ec1-169">**[メールと共同作業の役割]** \> **[アクセス許可と役割]** \> **[メールと共同作業の役割]** \> **[役割]** (または直接 <https://security.microsoft.com/emailandcollabpermissions>) に移動すると、セキュリティ/コンプライアンス センターで使用できるのと同じ役割グループが表示されます。</span><span class="sxs-lookup"><span data-stu-id="34ec1-169">When you go to **Email & collaboration roles** \> **Permissions & roles** \> **Email & collaboration roles** \> **Roles** (or directly to <https://security.microsoft.com/emailandcollabpermissions>) you'll see the same role groups that are available in the Security & Compliance Center.</span></span>

<span data-ttu-id="34ec1-170">これらの役割グループの詳細については、「[セキュリティ/コンプライアンス センターの権限](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34ec1-170">For complete information about these role groups, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)</span></span>

#### <a name="modify-email--collaboration-role-membership-in-the-security-center"></a><span data-ttu-id="34ec1-171">セキュリティ センターでメールと共同作業の役割のメンバーシップを変更する</span><span class="sxs-lookup"><span data-stu-id="34ec1-171">Modify Email & collaboration role membership in the security center</span></span>

1. <span data-ttu-id="34ec1-172">セキュリティ センターで、**[メールと共同作業の役割]** \> **[アクセス許可と役割]** \> **[メールと共同作業の役割]** \> **[役割]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="34ec1-172">In the security center, go to **Email & collaboration roles** \> **Permissions & roles** \> **Email & collaboration roles** \> **Roles**.</span></span>

2. <span data-ttu-id="34ec1-173">**[アクセス許可]** ページが開いたら、変更する役割グループをリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="34ec1-173">In the **Permissions** page that opens, select the role group that you want to modify from the list.</span></span> <span data-ttu-id="34ec1-174">**[名前]** の列見出しをクリックしてリストを名前で並べ替えることができます。または、**[検索]** ![[検索] アイコン](../../media/m365-cc-sc-search-icon.png) をクリックして役割グループを探すこともできます。</span><span class="sxs-lookup"><span data-stu-id="34ec1-174">You can click on the **Name** column header to sort the list by name, or you can click **Search** ![Search icon](../../media/m365-cc-sc-search-icon.png) to find the role group.</span></span>

3. <span data-ttu-id="34ec1-175">役割グループの詳細ポップアップが表示されたら、**[メンバー]** セクションで **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ec1-175">In the role group details flyout that appears, click **Edit** in the **Members** section.</span></span>

4. <span data-ttu-id="34ec1-176">**[メンバーの選択の編集]** ページが開いたら、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="34ec1-176">In the **Editing choose members** page that appears, do one of the following steps:</span></span>
   - <span data-ttu-id="34ec1-177">役割グループのメンバーが存在しない場合、**[メンバーの選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ec1-177">If there are no role group members, click **Choose members**.</span></span>
   - <span data-ttu-id="34ec1-178">役割グループのメンバーが存在する場合、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ec1-178">If there are existing role group members, click **Edit**</span></span>

5. <span data-ttu-id="34ec1-179">**[メンバーの選択]** ポップアップが表示されたら、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="34ec1-179">In the **Choose members** flyout that appears, do one of the following steps:</span></span>

   - <span data-ttu-id="34ec1-180">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ec1-180">Click **Add**.</span></span> <span data-ttu-id="34ec1-181">ユーザーの一覧が表示されたら、1 人以上のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="34ec1-181">In the list of users that appears, select one or more users.</span></span> <span data-ttu-id="34ec1-182">または、**[検索]** ![[検索] アイコン](../../media/m365-cc-sc-search-icon.png) をクリックして、ユーザーを探して選択します。</span><span class="sxs-lookup"><span data-stu-id="34ec1-182">Or, you can click **Search** ![Search icon](../../media/m365-cc-sc-search-icon.png) to find and select users.</span></span>

     <span data-ttu-id="34ec1-183">追加するユーザーを選択したら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ec1-183">When you've selected the users that you want to add, click **Add**.</span></span>

   - <span data-ttu-id="34ec1-184">**[削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ec1-184">Click **Remove**.</span></span> <span data-ttu-id="34ec1-185">存在するメンバーを 1 人以上選択します。</span><span class="sxs-lookup"><span data-stu-id="34ec1-185">Select one or more of the existing members.</span></span> <span data-ttu-id="34ec1-186">または、**[検索]** ![[検索] アイコン](../../media/m365-cc-sc-search-icon.png) をクリックして、メンバーを見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="34ec1-186">Or, you can click **Search** ![Search icon](../../media/m365-cc-sc-search-icon.png) to find and select members.</span></span>

     <span data-ttu-id="34ec1-187">削除するユーザーを選択したら、**[削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ec1-187">When you've selected the users that you want to remove, click **Remove**.</span></span>

6. <span data-ttu-id="34ec1-188">**[メンバーの選択]** ポップアップに戻り、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ec1-188">Back on the **Choose members** flyout, click **Done**.</span></span>

7. <span data-ttu-id="34ec1-189">**[メンバーの選択の編集]** ページに戻り、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ec1-189">Back on the **Editing choose members** page, click **Save**.</span></span>

8. <span data-ttu-id="34ec1-190">役割グループの詳細ポップアップに戻り、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ec1-190">Back on the role group details flyout, click **Done**.</span></span>
