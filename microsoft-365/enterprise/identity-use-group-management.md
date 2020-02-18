---
title: '手順 5: 管理にグループを使用する'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: グループを使って、管理タスクの一部を自動的に管理することができます。
ms.openlocfilehash: 215bb84cbb0cedc2f1320372ba8239cd51d07c98
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067274"
---
# <a name="step-5-use-groups-for-management"></a><span data-ttu-id="bff49-103">手順 5: 管理にグループを使用する</span><span class="sxs-lookup"><span data-stu-id="bff49-103">Step 5: Use groups for management</span></span>

![フェーズ 2 - ID](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="bff49-105">ユーザーが各自のグループを作成および管理できるようにする</span><span class="sxs-lookup"><span data-stu-id="bff49-105">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="bff49-106">*この手順はオプションであり、Microsoft 365 のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="bff49-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="bff49-107">このセクションでは、IT 管理者ではなくグループの所有者が管理できる Azure Active Directory (Azure AD) グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="bff49-107">In this section, you'll identify Azure Active Directory (Azure AD) groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="bff49-108">*セルフ サービスによるグループ管理*と呼ばれるこの機能では、管理者ロールが割り当てられていないグループ所有者がセキュリティ グループを作成および管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bff49-108">Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="bff49-p102">ユーザーがセキュリティ グループのメンバーシップを要求できます。この要求は IT 管理者ではなくグループ所有者に送られます。これにより、グループ メンバーシップの日常的な管理が、業務でのグループの用途を理解してグループのメンバーシップを管理できるチーム所有者、プロジェクト所有者、またはビジネス所有者に委任されます。</span><span class="sxs-lookup"><span data-stu-id="bff49-p102">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="bff49-111">セルフサービスによるグループ管理は Azure AD セキュリティと Office 365 グループに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="bff49-111">Self-service group management is available only for Azure AD security and Office 365 groups.</span></span> <span data-ttu-id="bff49-112">メールが有効なグループ、配布リスト、またはオンプレミスの Active Directory ドメイン サービス (AD DS) から同期されたことがあるグループではできません。</span><span class="sxs-lookup"><span data-stu-id="bff49-112">It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Active Directory Domain Services (AD DS).</span></span>
>

<span data-ttu-id="bff49-113">詳細については、「[セルフサービス グループ管理に必要な Azure Active Directory の設定](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bff49-113">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="bff49-114">中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-self-service-groups)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="bff49-114">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this section.</span></span>

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="bff49-115">動的グループ メンバーシップをセットアップする</span><span class="sxs-lookup"><span data-stu-id="bff49-115">Set up dynamic group membership</span></span>

<span data-ttu-id="bff49-116">*この手順はオプションであり、Microsoft 365 のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="bff49-116">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="bff49-117">このセクションでは、ユーザー アカウントを Azure AD グループのメンバーとして自動的に追加または削除するための一連のルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="bff49-117">In this section, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="bff49-118">これは*動的グループ メンバーシップ*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="bff49-118">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="bff49-119">ルールはユーザー アカウントの属性 (部門や国など) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="bff49-119">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="bff49-120">ルールの適用方法を次に説明します。</span><span class="sxs-lookup"><span data-stu-id="bff49-120">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="bff49-121">新しいユーザー アカウントがグループのすべてのルールに一致すると、そのアカウントはメンバーになります。</span><span class="sxs-lookup"><span data-stu-id="bff49-121">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="bff49-122">ユーザー アカウントがグループのメンバーではないものの、その属性が変更されグループのすべてのルールに一致した場合は、そのグループのメンバーになります。</span><span class="sxs-lookup"><span data-stu-id="bff49-122">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="bff49-123">ユーザー アカウントがグループのすべてのルールに一致しない場合、そのアカウントはグループに追加されません。</span><span class="sxs-lookup"><span data-stu-id="bff49-123">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="bff49-124">ユーザー アカウントがグループのメンバーであるものの、その属性が変更されそのグループのすべてのルールに一致しなくなると、グループのメンバーではなくなります。</span><span class="sxs-lookup"><span data-stu-id="bff49-124">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="bff49-p105">動的メンバーシップを使用するには、最初に共通のユーザー アカウント属性セットを持つ一連のグループを判別します。たとえば、Sales 部門のすべてのメンバーは、ユーザー アカウントの Department 属性が「Sales」に設定されていることに基づき、Sales Azure AD グループに入れます。</span><span class="sxs-lookup"><span data-stu-id="bff49-p105">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="bff49-127">「[Azure Active Directory で動的グループ メンバーシップの属性ベースのルールを作成する](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bff49-127">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="bff49-128">このセクションの手順を実行すると次のような結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="bff49-128">The results of this section are:</span></span>

- <span data-ttu-id="bff49-129">動的メンバーシップを構成できる Azure AD グループのセット</span><span class="sxs-lookup"><span data-stu-id="bff49-129">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="bff49-130">各動的グループのルール セット</span><span class="sxs-lookup"><span data-stu-id="bff49-130">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="bff49-132">テスト ラボ ガイド: ライセンスとグループのメンバーシップの自動化</span><span class="sxs-lookup"><span data-stu-id="bff49-132">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="bff49-133">中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-dyn-groups)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="bff49-133">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this section.</span></span>

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a><span data-ttu-id="bff49-134">自動ライセンスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="bff49-134">Set up automatic licensing</span></span>

<span data-ttu-id="bff49-135">*この手順はオプションであり、Microsoft 365 のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="bff49-135">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="bff49-136">このセクションでは、一連のサブスクリプションのライセンスをグループのすべてのメンバーに自動的に割り当てるため、Azure AD でセキュリティ グループを構成します。</span><span class="sxs-lookup"><span data-stu-id="bff49-136">In this section, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="bff49-137">これは*グループベースのライセンス*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="bff49-137">This is known as *group-based licensing*.</span></span> <span data-ttu-id="bff49-138">グループでユーザー アカウントを追加または削除すると、そのグループのサブスクリプションのライセンスが自動的にユーザー アカウントに追加または削除されます。</span><span class="sxs-lookup"><span data-stu-id="bff49-138">If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="bff49-139">Microsoft 365 Enterprise では、適切な MIcrosoft 365 Enterprise ライセンスを割り当てる Azure AD セキュリティ グループを構成します。</span><span class="sxs-lookup"><span data-stu-id="bff49-139">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign the appropriate Microsoft 365 Enterprise license.</span></span>

<span data-ttu-id="bff49-140">すべてのグループ メンバーに十分なライセンスがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bff49-140">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="bff49-141">ライセンスが不足している場合、ライセンスが使用可能になるまで、新しいユーザーにはライセンスが割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="bff49-141">If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="bff49-142">Azure B2B (企業間) アカウントが含まれているグループに対しては*グループベースのライセンス*を構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="bff49-142">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="bff49-143">「[Azure Active Directory のグループベースのライセンスの基礎](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)」にある追加情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bff49-143">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="bff49-144">「[Azure Active Directory でのグループ メンバーシップによるユーザーへのライセンスの割り当て](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bff49-144">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="bff49-145">このセクションの手順を実行すると次のような結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="bff49-145">The results of this section are:</span></span>

- <span data-ttu-id="bff49-146">グループベースのライセンスに適したセキュリティ グループを特定している。</span><span class="sxs-lookup"><span data-stu-id="bff49-146">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="bff49-147">グループベースのライセンスに対応してこれらのグループを構成している。</span><span class="sxs-lookup"><span data-stu-id="bff49-147">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Microsoft クラウド のテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="bff49-149">テスト ラボ ガイド: ライセンスとグループのメンバーシップの自動化</span><span class="sxs-lookup"><span data-stu-id="bff49-149">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="bff49-150">中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-group-license)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="bff49-150">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this section.</span></span>

|||
|:-------|:-----|
|![手順 6](../media/stepnumbers/Step6.png)| [<span data-ttu-id="bff49-152">Identity Governance を設定する</span><span class="sxs-lookup"><span data-stu-id="bff49-152">Configure identity governance</span></span>](identity-configure-identity-governance.md) |
