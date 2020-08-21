---
title: ユーザーにセキュリティ/コンプライアンス センターへのアクセス権を付与する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: ユーザーが Microsoft 365 セキュリティ/コンプライアンス センターでのアクセス許可を割り &当てないと、そのセキュリティまたはコンプライアンス機能を管理できません。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d21fef9458c02bd09d6d5ce2129b95571e0f8371
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826603"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="40c2f-103">ユーザーにセキュリティ/コンプライアンス センターへのアクセス権を付与する</span><span class="sxs-lookup"><span data-stu-id="40c2f-103">Give users access to the Security & Compliance Center</span></span>

<span data-ttu-id="40c2f-104">ユーザーは、自分のいずれかのセキュリティまたはコンプライアンス機能を管理&、セキュリティ コンプライアンス センターでアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="40c2f-104">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="40c2f-105">グローバル管理者またはセキュリティ コンプライアンス センターの [組織の管理] 役割グループ &のメンバーは、ユーザーにこれらの許可を付与できます。</span><span class="sxs-lookup"><span data-stu-id="40c2f-105">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="40c2f-106">ユーザーが管理できるのは、アクセス権が付与されたセキュリティまたはコンプライアンスの機能のみです。</span><span class="sxs-lookup"><span data-stu-id="40c2f-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="40c2f-107">ユーザーに付与できるさまざまなアクセス許可の詳細については、セキュリティ/コンプライアンス センター& [&確認してください](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="40c2f-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="40c2f-108">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="40c2f-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="40c2f-109">この記事の手順を実行するには、グローバル管理者か、セキュリティ & コンプライアンス センターの組織の管理役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="40c2f-109">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="40c2f-110">セキュリティ コンプライアンス センターの役割グループ&、Exchange Online の役割グループと名前が似ていますが、同じです。</span><span class="sxs-lookup"><span data-stu-id="40c2f-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="40c2f-111">役割グループのメンバーシップは、Exchange Online とセキュリティ コンプライアンス センターの間&されません。</span><span class="sxs-lookup"><span data-stu-id="40c2f-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="40c2f-112">委任アクセス許可 (AOBO) アクセス許可を持つ委任アクセス許可 (DAP) パートナーは、コンプライアンス センターのセキュリティ &にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="40c2f-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="40c2f-113">管理センターを使用して、セキュリティ センターとコンプライアンス センターへのアクセス&許可する</span><span class="sxs-lookup"><span data-stu-id="40c2f-113">Use the admin center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="40c2f-114">[サインインして管理センターに移動します](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)。</span><span class="sxs-lookup"><span data-stu-id="40c2f-114">[Sign in and go to the admin center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span>

2. <span data-ttu-id="40c2f-115">Microsoft 365 管理センターで、[管理センター **] を開き、[** セキュリティ]、[ **コンプライアンス&します**。</span><span class="sxs-lookup"><span data-stu-id="40c2f-115">In the Microsoft 365 admin center, open **Admin centers** and then click **Security & Compliance**.</span></span>

3. <span data-ttu-id="40c2f-116">セキュリティ/コンプライアンス センター&アクセス許可に移動 **します**。</span><span class="sxs-lookup"><span data-stu-id="40c2f-116">In the Security & Compliance Center, go to **Permissions**.</span></span>

4. <span data-ttu-id="40c2f-117">一覧から、ユーザーを追加する役割グループを選択し、[編集] アイコン **を** ![ クリックします ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="40c2f-117">From the list, choose the role group that you want to add the user to and click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

5. <span data-ttu-id="40c2f-118">[**メンバー**の追加] の役割グループのプロパティ ページで、[**追加** ![ ] アイコン ](../../media/ITPro-EAC-AddIcon.gif) をクリックし、追加するユーザーの名前を 1 つまたは複数選択します。</span><span class="sxs-lookup"><span data-stu-id="40c2f-118">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

6. <span data-ttu-id="40c2f-119">役割グループに追加するユーザーをすべて選択したら、[追加] をクリックしてから **[OK] \> **を**クリックします**。</span><span class="sxs-lookup"><span data-stu-id="40c2f-119">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

7. <span data-ttu-id="40c2f-120">**[保存]** をクリックして、役割グループに加えた変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="40c2f-120">Click **Save** to save the changes to the role group.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="40c2f-121">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="40c2f-121">How do you know this worked?</span></span>

1. <span data-ttu-id="40c2f-122">セキュリティ/コンプライアンス センター&アクセス許可に移動 **します**。</span><span class="sxs-lookup"><span data-stu-id="40c2f-122">In the Security & Compliance Center, go to **Permissions**.</span></span>

2. <span data-ttu-id="40c2f-123">一覧から、メンバーを表示する役割グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="40c2f-123">From the list, select the role group to view the members.</span></span>

3. <span data-ttu-id="40c2f-124">右側の役割グループの詳細に、役割グループのメンバーを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="40c2f-124">On the right, in the role group details, you can view the members of the role group.</span></span>

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="40c2f-125">PowerShell を使用して、セキュリティ/コンプライアンス センターへのアクセス権を別&付与する</span><span class="sxs-lookup"><span data-stu-id="40c2f-125">Use PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="40c2f-126">[セキュリティ/コンプライアンス センター PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="40c2f-126">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="40c2f-127">次の例で示すように、**Add-RoleGroupMember** コマンドを使用して、ユーザーを Organization Management の役割に追加できます。</span><span class="sxs-lookup"><span data-stu-id="40c2f-127">Use the **Add-RoleGroupMember** command to add a user to the Organization Management Role, as shown in the following example.</span></span>

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   <span data-ttu-id="40c2f-128">**パラメーター**:</span><span class="sxs-lookup"><span data-stu-id="40c2f-128">**Parameters**:</span></span>

   - <span data-ttu-id="40c2f-129">_Identity_ は、メンバーを追加する役割グループです。</span><span class="sxs-lookup"><span data-stu-id="40c2f-129">_Identity_ is the role group to add a member to.</span></span>

   - <span data-ttu-id="40c2f-130">_メンバー_ は、役割グループに追加するメールボックス、ユニバーサル セキュリティ グループ (USG)、またはコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="40c2f-130">_Member_ is the mailbox, universal security group (USG), or computer to add to the role group.</span></span> <span data-ttu-id="40c2f-131">一度に 1 メンバーしか指定できません。</span><span class="sxs-lookup"><span data-stu-id="40c2f-131">You can specify only one member at a time.</span></span>

<span data-ttu-id="40c2f-132">構文およびパラメーターの詳細については [、「Add-RoleGroupMember」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember)。</span><span class="sxs-lookup"><span data-stu-id="40c2f-132">For detailed information on syntax and parameters, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="40c2f-133">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="40c2f-133">How do you know this worked?</span></span>

<span data-ttu-id="40c2f-134">ユーザーにセキュリティ & コンプライアンス センターへのアクセス権を付与したことを確認するには、 **次の例のように、Get-RoleGroupMember** コマンドレットを使用して組織管理役割グループのメンバーを表示します。</span><span class="sxs-lookup"><span data-stu-id="40c2f-134">To verify that you've given users access to the Security & Compliance Center, use the **Get-RoleGroupMember** cmdlet to view the members in the Organization Management role group, as shown in the following example.</span></span>

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

<span data-ttu-id="40c2f-135">構文およびパラメーターの詳細については [、「Get-RoleGroupMember」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)。</span><span class="sxs-lookup"><span data-stu-id="40c2f-135">For detailed information on syntax and parameters, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
