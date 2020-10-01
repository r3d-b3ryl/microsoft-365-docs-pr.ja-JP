---
title: Microsoft 365 グループを管理する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Microsoft 365 グループを管理する方法について説明します。
ms.openlocfilehash: a01bf5dcc0b87cbdce8d7044b666cfb3a16a5aa9
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328520"
---
# <a name="manage-microsoft-365-groups"></a><span data-ttu-id="bc8ab-103">Microsoft 365 グループを管理する</span><span class="sxs-lookup"><span data-stu-id="bc8ab-103">Manage Microsoft 365 groups</span></span>

<span data-ttu-id="bc8ab-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="bc8ab-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="bc8ab-105">構成に応じて、Microsoft 365 グループをさまざまな方法で管理できます。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-105">You can manage Microsoft 365 groups in several different ways, depending on your configuration.</span></span> <span data-ttu-id="bc8ab-106">ユーザーアカウントは、 [Microsoft 365 管理センター](https://docs.microsoft.com/microsoft-365/admin/add-users/)、PowerShell、Active Directory ドメインサービス (AD DS)、または [azure Active DIRECTORY (azure AD) 管理センター](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)で管理できます。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-106">You can manage user accounts in the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/), PowerShell, in Active Directory Domain Services (AD DS), or in the [Azure Active Directory (Azure AD) admin center](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span></span> 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a><span data-ttu-id="bc8ab-107">グループを管理する場所と方法を計画します。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-107">Plan for where and how you will manage your groups</span></span>

<span data-ttu-id="bc8ab-108">ユーザーアカウントを管理する場所と方法は、Microsoft 365 で使用する id モデルによって異なります。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="bc8ab-109">これらのモデル全体は、クラウド専用でハイブリッドです。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-109">The two overall models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="bc8ab-110">クラウド専用</span><span class="sxs-lookup"><span data-stu-id="bc8ab-110">Cloud-only</span></span>

<span data-ttu-id="bc8ab-111">以下を使用して、グループを作成して管理します。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-111">You create and manage groups with:</span></span>

- [<span data-ttu-id="bc8ab-112">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="bc8ab-112">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [<span data-ttu-id="bc8ab-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc8ab-113">PowerShell</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="bc8ab-114">Azure AD 管理センター</span><span class="sxs-lookup"><span data-stu-id="bc8ab-114">Azure AD admin center</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a><span data-ttu-id="bc8ab-115">ハイブリッド</span><span class="sxs-lookup"><span data-stu-id="bc8ab-115">Hybrid</span></span>

<span data-ttu-id="bc8ab-116">AD DS グループは AD DS から Microsoft 365 と同期されるので、オンプレミスの AD DS ツールを使用してこれらのグループを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-116">AD DS groups are synchronized with Microsoft 365 from AD DS, so you must use on-premises AD DS tools to manage these groups.</span></span>

<span data-ttu-id="bc8ab-117">Ad DS グループとは別の Azure AD グループを作成して管理することもできますが、AD DS からユーザーとグループを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-117">You can also create and manage Azure AD groups that are separate from AD DS groups but can contain users and groups from AD DS.</span></span> <span data-ttu-id="bc8ab-118">この場合は、次のものを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-118">In this case, you can use:</span></span>

- [<span data-ttu-id="bc8ab-119">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="bc8ab-119">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [<span data-ttu-id="bc8ab-120">PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc8ab-120">PowerShell</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="bc8ab-121">Azure AD 管理センター</span><span class="sxs-lookup"><span data-stu-id="bc8ab-121">Azure AD admin center</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="bc8ab-122">ユーザーが各自のグループを作成および管理できるようにする</span><span class="sxs-lookup"><span data-stu-id="bc8ab-122">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="bc8ab-123">Azure AD では、IT 管理者ではなくグループ所有者が管理できるグループを許可します。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-123">Azure AD allows groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="bc8ab-124">*セルフ サービスによるグループ管理*と呼ばれるこの機能では、管理者ロールが割り当てられていないグループ所有者がセキュリティ グループを作成および管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-124">Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="bc8ab-p105">ユーザーがセキュリティ グループのメンバーシップを要求できます。この要求は IT 管理者ではなくグループ所有者に送られます。これにより、グループ メンバーシップの日常的な管理が、業務でのグループの用途を理解してグループのメンバーシップを管理できるチーム所有者、プロジェクト所有者、またはビジネス所有者に委任されます。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-p105">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="bc8ab-127">セルフサービスによるグループ管理は Azure AD セキュリティと Microsoft 365 グループに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-127">Self-service group management is available only for Azure AD security and Microsoft 365 groups.</span></span> <span data-ttu-id="bc8ab-128">メールが有効なグループ、配布リスト、または AD DS から同期された任意のグループに対しては使用できません。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-128">It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from AD DS.</span></span>
>

<span data-ttu-id="bc8ab-129">詳細については、「[セルフサービス グループ管理に必要な Azure Active Directory の設定](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-129">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="bc8ab-130">動的グループ メンバーシップをセットアップする</span><span class="sxs-lookup"><span data-stu-id="bc8ab-130">Set up dynamic group membership</span></span>

<span data-ttu-id="bc8ab-131">Azure AD では、ユーザーアカウントを Azure AD グループのメンバーとして自動的に追加または削除する一連のルールの構成をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-131">Azure AD supports configuring a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="bc8ab-132">これは*動的グループ メンバーシップ*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-132">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="bc8ab-133">ルールはユーザー アカウントの属性 (部門や国など) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-133">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="bc8ab-134">ルールの適用方法を次に説明します。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-134">Here's how the rules are applied:</span></span>

- <span data-ttu-id="bc8ab-135">新しいユーザー アカウントがグループのすべてのルールに一致すると、そのアカウントはメンバーになります。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-135">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="bc8ab-136">ユーザー アカウントがグループのメンバーではないものの、その属性が変更されグループのすべてのルールに一致した場合は、そのユーザーアカウントはグループのメンバーになります。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-136">If a user account isn't a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="bc8ab-137">ユーザー アカウントがグループのすべてのルールに一致しない場合、そのアカウントはグループに追加されません。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-137">If a user account doesn't match all the rules for the group, it isn't added to the group.</span></span>
- <span data-ttu-id="bc8ab-138">ユーザー アカウントがグループのメンバーであるものの、その属性が変更されそのグループのすべてのルールに一致しなくなると、グループのメンバーではなくなります。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-138">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="bc8ab-p108">動的メンバーシップを使用するには、最初に共通のユーザー アカウント属性セットを持つ一連のグループを判別します。たとえば、Sales 部門のすべてのメンバーは、ユーザー アカウントの Department 属性が「Sales」に設定されていることに基づき、Sales Azure AD グループに入れます。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-p108">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to "Sales".</span></span>

<span data-ttu-id="bc8ab-141">「[Azure Active Directory で動的グループ メンバーシップの属性ベースのルールを作成する](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-141">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

## <a name="set-up-automatic-licensing"></a><span data-ttu-id="bc8ab-142">自動ライセンスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="bc8ab-142">Set up automatic licensing</span></span>

<span data-ttu-id="bc8ab-143">Azure AD のセキュリティグループを構成して、サブスクリプションのセットからグループのすべてのメンバーにライセンスを自動的に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-143">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="bc8ab-144">これは*グループベースのライセンス*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-144">This is known as *group-based licensing*.</span></span> <span data-ttu-id="bc8ab-145">グループでユーザー アカウントを追加または削除すると、そのグループのサブスクリプションのライセンスが自動的にユーザー アカウントに追加または削除されます。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-145">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="bc8ab-146">Microsoft 365 Enterprise では、適切な MIcrosoft 365 Enterprise ライセンスを割り当てる Azure AD セキュリティ グループを構成します。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-146">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign the appropriate Microsoft 365 Enterprise license.</span></span>

<span data-ttu-id="bc8ab-147">すべてのグループ メンバーに十分なライセンスがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-147">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="bc8ab-148">ライセンスが不足している場合、ライセンスが使用可能になるまで、新しいユーザーにはライセンスが割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-148">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="bc8ab-149">Azure B2B (企業間) アカウントが含まれているグループに対してはグループベースのライセンスを構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-149">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="bc8ab-150">詳細については、「 [AZURE AD のグループベースのライセンスの基礎](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-150">For more information, see [Group-based licensing basics in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="bc8ab-151">「 [Azure セキュリティグループのグループベースのライセンスを構成するに](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)は」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc8ab-151">See the [instructions to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>
