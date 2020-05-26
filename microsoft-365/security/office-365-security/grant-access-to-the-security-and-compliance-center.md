---
title: ユーザーにセキュリティ/コンプライアンス センターへのアクセス権を付与する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: ユーザーがセキュリティまたはコンプライアンス機能を管理する前に、Microsoft 365 セキュリティ & コンプライアンスセンターでアクセス許可を割り当てる必要があります。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 19358e3cca0c4d47338fe5fc72b671e36477ce7e
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351953"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="a1ce9-103">ユーザーにセキュリティ/コンプライアンス センターへのアクセス権を付与する</span><span class="sxs-lookup"><span data-stu-id="a1ce9-103">Give users access to the Security & Compliance Center</span></span>

<span data-ttu-id="a1ce9-104">ユーザーがセキュリティまたはコンプライアンス機能を管理する前に、セキュリティ & コンプライアンスセンターでアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-104">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="a1ce9-105">セキュリティ & コンプライアンスセンターでは、組織の全体管理者または組織のメンバーとして、これらのアクセス許可をユーザーに与えることができます。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-105">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="a1ce9-106">ユーザーが管理できるのは、アクセス権が付与されたセキュリティまたはコンプライアンスの機能のみです。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="a1ce9-107">セキュリティ & コンプライアンスセンターでユーザーに付与できるさまざまなアクセス許可の詳細については、「[セキュリティ & コンプライアンスセンターでアクセス許可](permissions-in-the-security-and-compliance-center.md)を確認する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a1ce9-108">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="a1ce9-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a1ce9-109">この記事に記載されている手順を完了するには、グローバル管理者であるか、またはセキュリティ & コンプライアンスセンターの組織の組織の管理役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-109">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="a1ce9-110">セキュリティ & コンプライアンスセンターの役割グループには、Exchange Online の役割グループと同じような名前が付いている場合がありますが、これらは同じではありません。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="a1ce9-111">役割グループのメンバーシップは、Exchange Online とセキュリティ & コンプライアンスセンターとの間で共有されません。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="a1ce9-112">(AOBO) 権限を持つ代理アクセス許可 (DAP) パートナーは、セキュリティ & コンプライアンスセンターにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="a1ce9-113">管理センターを使用して、別のユーザーにセキュリティ & コンプライアンスセンターへのアクセス権を付与する</span><span class="sxs-lookup"><span data-stu-id="a1ce9-113">Use the admin center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="a1ce9-114">[サインインして、管理センターに移動](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)します。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-114">[Sign in and go to the admin center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span>

2. <span data-ttu-id="a1ce9-115">Microsoft 365 管理センターで、**管理センター**を開き、[**セキュリティ & コンプライアンス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-115">In the Microsoft 365 admin center, open **Admin centers** and then click **Security & Compliance**.</span></span>

3. <span data-ttu-id="a1ce9-116">[セキュリティ & コンプライアンスセンター] で、[**アクセス許可**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-116">In the Security & Compliance Center, go to **Permissions**.</span></span>

4. <span data-ttu-id="a1ce9-117">リストからユーザーを追加する役割グループを選択し、 \*\*[編集\*\* ![ ] [編集] アイコンをクリックし ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) ます。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-117">From the list, choose the role group that you want to add the user to and click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

5. <span data-ttu-id="a1ce9-118">役割グループのプロパティページの [**メンバー**] で、 \*\*[追加\*\* ![ ] アイコンをクリックし、 ](../../media/ITPro-EAC-AddIcon.gif) 追加するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-118">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

6. <span data-ttu-id="a1ce9-119">役割グループに追加するすべてのユーザーを選択したら、[ \*\* \> 追加\*\*] をクリックし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-119">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

7. <span data-ttu-id="a1ce9-120">**[保存]** をクリックして、役割グループに加えた変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-120">Click **Save** to save the changes to the role group.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="a1ce9-121">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="a1ce9-121">How do you know this worked?</span></span>

1. <span data-ttu-id="a1ce9-122">[セキュリティ & コンプライアンスセンター] で、[**アクセス許可**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-122">In the Security & Compliance Center, go to **Permissions**.</span></span>

2. <span data-ttu-id="a1ce9-123">リストから、メンバーを表示する役割グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-123">From the list, select the role group to view the members.</span></span>

3. <span data-ttu-id="a1ce9-124">右側の役割グループの詳細では、役割グループのメンバーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-124">On the right, in the role group details, you can view the members of the role group.</span></span>

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="a1ce9-125">PowerShell を使用して、別のユーザーにセキュリティ & コンプライアンスセンターへのアクセス権を付与する</span><span class="sxs-lookup"><span data-stu-id="a1ce9-125">Use PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="a1ce9-126">[セキュリティ/コンプライアンス センター PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-126">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="a1ce9-127">次の例で示すように、**Add-RoleGroupMember** コマンドを使用して、ユーザーを Organization Management の役割に追加できます。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-127">Use the **Add-RoleGroupMember** command to add a user to the Organization Management Role, as shown in the following example.</span></span>

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   <span data-ttu-id="a1ce9-128">**パラメーター**:</span><span class="sxs-lookup"><span data-stu-id="a1ce9-128">**Parameters**:</span></span>

   - <span data-ttu-id="a1ce9-129">_Identity_は、メンバーを追加する役割グループです。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-129">_Identity_ is the role group to add a member to.</span></span>

   - <span data-ttu-id="a1ce9-130">_Member_は、役割グループに追加するメールボックス、ユニバーサルセキュリティグループ (USG)、またはコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-130">_Member_ is the mailbox, universal security group (USG), or computer to add to the role group.</span></span> <span data-ttu-id="a1ce9-131">一度に 1 メンバーしか指定できません。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-131">You can specify only one member at a time.</span></span>

<span data-ttu-id="a1ce9-132">構文とパラメーターの詳細については、「 [add-rolegroupmember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-132">For detailed information on syntax and parameters, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="a1ce9-133">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="a1ce9-133">How do you know this worked?</span></span>

<span data-ttu-id="a1ce9-134">ユーザーにセキュリティ & コンプライアンスセンターへのアクセス権が与えられたことを確認するには、次の例に示すように、 **add-rolegroupmember**コマンドレットを使用して組織の管理役割グループのメンバーを表示します。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-134">To verify that you've given users access to the Security & Compliance Center, use the **Get-RoleGroupMember** cmdlet to view the members in the Organization Management role group, as shown in the following example.</span></span>

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

<span data-ttu-id="a1ce9-135">構文とパラメーターの詳細については、「 [add-rolegroupmember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-135">For detailed information on syntax and parameters, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
