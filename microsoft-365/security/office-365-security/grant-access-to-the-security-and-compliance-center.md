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
description: ユーザーがセキュリティまたはコンプライアンス機能を管理する前に、Microsoft 365 セキュリティ & コンプライアンスセンターでアクセス許可を割り当てる必要があります。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5d586684d44545f7aea94c30f5474b1fe5fa4651
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202809"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="e64a2-103">ユーザーにセキュリティ/コンプライアンス センターへのアクセス権を付与する</span><span class="sxs-lookup"><span data-stu-id="e64a2-103">Give users access to the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e64a2-104">ユーザーがセキュリティまたはコンプライアンス機能を管理する前に、セキュリティ & コンプライアンスセンターでアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e64a2-104">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="e64a2-105">セキュリティ & コンプライアンスセンターでは、組織の全体管理者または組織のメンバーとして、これらのアクセス許可をユーザーに与えることができます。</span><span class="sxs-lookup"><span data-stu-id="e64a2-105">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="e64a2-106">ユーザーが管理できるのは、アクセス権が付与されたセキュリティまたはコンプライアンスの機能のみです。</span><span class="sxs-lookup"><span data-stu-id="e64a2-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="e64a2-107">セキュリティ & コンプライアンスセンターでユーザーに付与できるさまざまなアクセス許可の詳細については、「 [セキュリティ & コンプライアンスセンターでアクセス許可](permissions-in-the-security-and-compliance-center.md)を確認する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e64a2-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e64a2-108">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="e64a2-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e64a2-109">この記事に記載されている手順を完了するには、グローバル管理者であるか、またはセキュリティ & コンプライアンスセンターの組織の組織の管理役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e64a2-109">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="e64a2-110">セキュリティ & コンプライアンスセンターの役割グループには、Exchange Online の役割グループと同じような名前が付いている場合がありますが、これらは同じではありません。</span><span class="sxs-lookup"><span data-stu-id="e64a2-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="e64a2-111">役割グループのメンバーシップは、Exchange Online とセキュリティ & コンプライアンスセンターとの間で共有されません。</span><span class="sxs-lookup"><span data-stu-id="e64a2-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="e64a2-112">(AOBO) 権限を持つ代理アクセス許可 (DAP) パートナーは、セキュリティ & コンプライアンスセンターにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="e64a2-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="e64a2-113">セキュリティ & コンプライアンスセンターを使用して、別のユーザーにセキュリティ & コンプライアンスセンターへのアクセス権を付与する</span><span class="sxs-lookup"><span data-stu-id="e64a2-113">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="e64a2-114">[セキュリティ & コンプライアンスセンター] を開き、 <https://protection.office.com> [ **アクセス許可**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e64a2-114">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="e64a2-115">[ **アクセス許可** ] タブに直接移動するには、を開き <https://protection.office.com/permissions> ます。</span><span class="sxs-lookup"><span data-stu-id="e64a2-115">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="e64a2-116">役割グループの一覧から役割グループを選択し、[編集] 編集アイコン **をクリックし** ![ ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) ます。</span><span class="sxs-lookup"><span data-stu-id="e64a2-116">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="e64a2-117">役割グループのプロパティページの [**メンバー**] で、 \*\*[追加\*\* ![ ] アイコンをクリックし、 ](../../media/ITPro-EAC-AddIcon.gif) 追加するユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="e64a2-117">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="e64a2-118">役割グループに追加するすべてのユーザーを選択したら、[ \*\* \> 追加\*\*] をクリックし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e64a2-118">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="e64a2-119">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e64a2-119">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="e64a2-120">セキュリティ & コンプライアンスセンターの PowerShell を使用して、別のユーザーがセキュリティ & コンプライアンスセンターにアクセスできるようにする</span><span class="sxs-lookup"><span data-stu-id="e64a2-120">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="e64a2-121">[セキュリティ/コンプライアンス センター PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e64a2-121">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="e64a2-122">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="e64a2-122">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="e64a2-123">構文およびパラメーターの詳細については、「 [add-rolegroupmember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e64a2-123">For detailed syntax and parameter issues, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e64a2-124">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="e64a2-124">How do you know this worked?</span></span>

<span data-ttu-id="e64a2-125">セキュリティ & コンプライアンスセンターへのアクセスが正常に付与されたことを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e64a2-125">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="e64a2-126">[セキュリティ & コンプライアンスセンター] で、[ **アクセス許可** ] に移動して役割グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="e64a2-126">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="e64a2-127">表示される詳細ポップアップで、役割グループのメンバーを確認します。</span><span class="sxs-lookup"><span data-stu-id="e64a2-127">In the details flyout that opens, verify the members of the role group.</span></span> 

- <span data-ttu-id="e64a2-128">セキュリティ & コンプライアンスセンターの PowerShell で、を \<RoleGroupName\> 役割グループの名前に置き換えて、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e64a2-128">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="e64a2-129">構文およびパラメーターの詳細については、「 [add-rolegroupmember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e64a2-129">For detailed syntax and parameter information, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
