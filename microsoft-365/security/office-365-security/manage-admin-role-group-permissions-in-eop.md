---
title: EOP で役割グループを管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 管理者は、Exchange Online Protection の Exchange 管理センター (EAC) でアクセス許可を割り当てるまたは削除する方法について学習できます。
ms.openlocfilehash: 4a1353963e5e3eadc1a07f8b4aa3a765b06c86ec
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659299"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="039b6-103">スタンドアロン EOP で役割グループを管理する</span><span class="sxs-lookup"><span data-stu-id="039b6-103">Manage role groups in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="039b6-104">Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織では、Exchange 管理センター (EAC) を使用してユーザーを役割グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="039b6-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="039b6-105">役割グループにユーザーを追加すると、特定の管理タスクを実行するためのアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="039b6-105">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="039b6-106">役割グループからユーザーを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="039b6-106">You can also remove users from role groups.</span></span>

<span data-ttu-id="039b6-107">役割と役割グループの詳細については、「スタンドアロン [EOP のアクセス許可」を参照してください](feature-permissions-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="039b6-107">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="039b6-108">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="039b6-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="039b6-109">Exchange 管理センター (EAC) を開く方法については、スタンドアロン EOP の [Exchange 管理センターを参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="039b6-109">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="039b6-110">スタンドアロンの EOP PowerShell を開く方法については [、「Exchange Online Protection PowerShell への接続」を参照してください](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="039b6-110">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="039b6-111">この記事の手順を実行する前に、Exchange Online Protection でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="039b6-111">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="039b6-112">具体的には、既定で **"Organization Management/** 組織の管理" 役割グループに割り当てられる **"Role Management/** 役割管理" 役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="039b6-112">Specifically, you need the **Role Management** role, which is assigned to the **Organization Management** role group by default.</span></span> <span data-ttu-id="039b6-113">詳細については、「スタンドアロン [EOP のアクセス](feature-permissions-in-eop.md) 許可」および「EAC を使用して役割グループのメンバーの一覧 [を変更する」を参照してください](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="039b6-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="039b6-114">この記事の手順に適用できるキーボード ショートカットの詳細については [、Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)の Exchange 管理センターのキーボード ショートカットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="039b6-114">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="039b6-115">問題が発生する場合</span><span class="sxs-lookup"><span data-stu-id="039b6-115">Having problems?</span></span> <span data-ttu-id="039b6-116">[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) フォーラムでサポートをご依頼ください。</span><span class="sxs-lookup"><span data-stu-id="039b6-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="039b6-117">EAC を使用して役割グループを管理する</span><span class="sxs-lookup"><span data-stu-id="039b6-117">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="039b6-118">EAC を使用して役割グループを表示する</span><span class="sxs-lookup"><span data-stu-id="039b6-118">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="039b6-119">EAC で、アクセス許可管理者 **の役割に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="039b6-119">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="039b6-120">組織の役割グループのすべてが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="039b6-120">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="039b6-121">役割グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="039b6-121">Select a role group.</span></span> <span data-ttu-id="039b6-122">[詳細] ウィンドウには、 **名前**、 **説明**、 **割** り当てられた役割、 **および役割グループ** の管理が表示されます。</span><span class="sxs-lookup"><span data-stu-id="039b6-122">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="039b6-123">この情報は、[編集] アイコンをクリック **して** ![ 表示することもできます ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="039b6-123">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="039b6-124">EAC を使用して役割グループを作成する</span><span class="sxs-lookup"><span data-stu-id="039b6-124">Use the EAC to create role groups</span></span>

<span data-ttu-id="039b6-125">新しい役割グループを作成する場合は、(グループの作成時または作成後に) すべての設定を自分で構成できます。</span><span class="sxs-lookup"><span data-stu-id="039b6-125">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="039b6-126">または、既存の役割グループをコピーして変更できます。</span><span class="sxs-lookup"><span data-stu-id="039b6-126">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="039b6-127">EAC で、アクセス許可管理者 **の役割に** \> **移動** し、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="039b6-127">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="039b6-128">**新しい役割グループを手動で作成する**: [追加 **] アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="039b6-128">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="039b6-129">**既存の役割グループをコピー** する : コピーする役割グループを選択し、[コピー  ] アイコン ![ をクリックします ](../../media/ITPro-EAC-CopyIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="039b6-129">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="039b6-130">表示される **[新しい役割グループ** ] ウィンドウで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="039b6-130">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="039b6-131">**Name**: 役割グループの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="039b6-131">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="039b6-132">**説明**: 役割グループのオプションの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="039b6-132">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="039b6-133">**役割**: [追加 **] アイコン** または [削除] アイコンをクリックして、役割グループに割り当てられている役割を ![ ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 選択または変更します。</span><span class="sxs-lookup"><span data-stu-id="039b6-133">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="039b6-134">**メンバー**: [追加 **] アイコンまたは**[削除] アイコンをクリック ![ して、 ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 役割グループのメンバーシップを変更します。</span><span class="sxs-lookup"><span data-stu-id="039b6-134">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="039b6-135">完了したら、[保存] をクリック **して** 役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="039b6-135">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="039b6-136">EAC を使用して役割グループを変更する</span><span class="sxs-lookup"><span data-stu-id="039b6-136">Use the EAC to modify role groups</span></span>

<span data-ttu-id="039b6-137">EAC で、アクセス許可の管理役割に移動し、変更する役割グループを選択して、[編集] アイコン \> **を** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="039b6-137">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="039b6-138">役割グループを変更する場合と役割グループを作成する場合と同じオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="039b6-138">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="039b6-139">以下のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="039b6-139">You can:</span></span>

- <span data-ttu-id="039b6-140">名前と説明を変更します。</span><span class="sxs-lookup"><span data-stu-id="039b6-140">Change the name and description.</span></span>

- <span data-ttu-id="039b6-141">管理役割を追加および削除する (役割の割り当てを作成または削除する)。</span><span class="sxs-lookup"><span data-stu-id="039b6-141">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="039b6-142">メンバーを追加および削除します。</span><span class="sxs-lookup"><span data-stu-id="039b6-142">Add and remove members.</span></span>

<span data-ttu-id="039b6-143">**注**: 一部の役割グループ (組織の管理など) では、グループから削除できる役割が制限されます。</span><span class="sxs-lookup"><span data-stu-id="039b6-143">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="039b6-144">EAC を使用して役割グループのメンバーの一覧を変更する</span><span class="sxs-lookup"><span data-stu-id="039b6-144">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="039b6-145">EAC で、[アクセス許可の管理 **]** 役割に移動し、変更する役割グループを選択して、[編集] アイコン \>  ![ をクリックします ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="039b6-145">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="039b6-146">開く役割グループのプロパティ ページの [ **メンバー** ] セクションで、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="039b6-146">In the role group properties page that opens, in the **Members** section, do either of the following steps:</span></span>

   - <span data-ttu-id="039b6-147">[追加 **] アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="039b6-147">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="039b6-148">表示されるページで、追加するユーザーを見つけ、[追加] **->。**</span><span class="sxs-lookup"><span data-stu-id="039b6-148">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="039b6-149">ユーザーを選択し、[ **追加] ->** 何度もクリックします。</span><span class="sxs-lookup"><span data-stu-id="039b6-149">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="039b6-150">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="039b6-150">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="039b6-151">削除するユーザーを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="039b6-151">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="039b6-152">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="039b6-152">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="039b6-153">役割グループに対してメンバーを追加または削除した後、ユーザーは自身の管理者権限の変更を確認するためにサインアウトしてから、再度サインインしなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="039b6-153">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="039b6-154">EAC を使用して役割グループを削除する</span><span class="sxs-lookup"><span data-stu-id="039b6-154">Use the EAC to remove role groups</span></span>

<span data-ttu-id="039b6-155">組み込みの役割グループは削除できませんが、作成したカスタム役割グループは削除できます。</span><span class="sxs-lookup"><span data-stu-id="039b6-155">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="039b6-156">EAC で、アクセス許可管理者 **の役割に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="039b6-156">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="039b6-157">削除する役割グループを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="039b6-157">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="039b6-158">表示 **される確認** ウィンドウで [はい] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="039b6-158">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="039b6-159">PowerShell を使用して役割グループを管理する</span><span class="sxs-lookup"><span data-stu-id="039b6-159">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="039b6-160">スタンドアロンの EOP PowerShell を使用して役割グループを表示する</span><span class="sxs-lookup"><span data-stu-id="039b6-160">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="039b6-161">役割グループを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="039b6-161">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="039b6-162">この例では、すべての役割グループの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="039b6-162">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="039b6-163">この例では、Recipient Administrators という名前の役割グループの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="039b6-163">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="039b6-164">この例では、ユーザー Julia がメンバーであるすべての役割グループを返します。</span><span class="sxs-lookup"><span data-stu-id="039b6-164">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="039b6-165">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the `Get-User -Identity Julia | Format-List DistinguishedName` command:</span><span class="sxs-lookup"><span data-stu-id="039b6-165">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="039b6-166">構文およびパラメーターの詳細については、「[Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="039b6-166">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="039b6-167">スタンドアロンの EOP PowerShell を使用して役割グループを作成する</span><span class="sxs-lookup"><span data-stu-id="039b6-167">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="039b6-168">新しい役割グループを作成する場合、すべての設定を手動で構成できます (グループの作成中または作成後)。</span><span class="sxs-lookup"><span data-stu-id="039b6-168">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="039b6-169">または、既存の役割グループをコピーして変更できます。</span><span class="sxs-lookup"><span data-stu-id="039b6-169">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="039b6-170">新しい役割グループを手動で作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="039b6-170">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="039b6-171">_Roles パラメーター_ は、次の構文を使用して、役割グループに割り当てる管理役割を指定します `"Role1","Role1",..."RoleN"` 。</span><span class="sxs-lookup"><span data-stu-id="039b6-171">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="039b6-172">**Get-ManagementRole** コマンドレットを使用して、使用できる役割を確認できます。</span><span class="sxs-lookup"><span data-stu-id="039b6-172">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="039b6-173">_Members パラメーター_ は、次の構文を使用して役割グループのメンバーを指定します `"Member1","Member2",..."MemberN"` 。</span><span class="sxs-lookup"><span data-stu-id="039b6-173">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="039b6-174">ユーザー、メールが有効なユニバーサル セキュリティ グループ (USG)、またはその他の役割グループ (セキュリティ プリンシパル) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="039b6-174">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="039b6-175">この例では、次の設定を使用して、"Limited Recipient Management" という名前の新しい役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="039b6-175">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="039b6-176">"Mail Recipients/メール受信者" 役割は、役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="039b6-176">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="039b6-177">ユーザー Kim と Martin がメンバーとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="039b6-177">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="039b6-178">既存の役割グループをコピーするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="039b6-178">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="039b6-179">以下の構文を使用して、変数にコピーする役割グループを格納します。</span><span class="sxs-lookup"><span data-stu-id="039b6-179">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="039b6-180">次の構文を使用して、新しい役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="039b6-180">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="039b6-181">_Members パラメーター_ は、次の構文を使用して役割グループのメンバーを指定します `"Member1","Member2",..."MemberN"` 。</span><span class="sxs-lookup"><span data-stu-id="039b6-181">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="039b6-182">ユーザー、メールが有効なユニバーサル セキュリティ グループ (USG)、またはその他の役割グループ (セキュリティ プリンシパル) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="039b6-182">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="039b6-183">この例では、Organization Management 役割グループを "Limited Organization Management" という名前の新しい役割グループにコピーします。</span><span class="sxs-lookup"><span data-stu-id="039b6-183">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="039b6-184">役割グループのメンバーは、Isabelle、Carter、Lukas です。</span><span class="sxs-lookup"><span data-stu-id="039b6-184">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="039b6-185">構文およびパラメーターの詳細については [、New-RoleGroup を参照してください](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)。</span><span class="sxs-lookup"><span data-stu-id="039b6-185">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="039b6-186">スタンドアロンの EOP PowerShell を使用して役割グループのメンバーの一覧を変更する</span><span class="sxs-lookup"><span data-stu-id="039b6-186">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="039b6-187">**Add-RoleGroupMember** コマンドレットと **Remove-RoleGroupMember** コマンドレットは、個々のメンバーを一度に 1 人追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="039b6-187">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="039b6-188">**Update-RoleGroupMember コマンドレットは、メンバー** の既存のリストを置き換えまたは変更できます。</span><span class="sxs-lookup"><span data-stu-id="039b6-188">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="039b6-189">役割グループのメンバーには、ユーザー、メールが有効なユニバーサル セキュリティ グループ (USG)、または他の役割グループ (セキュリティ プリンシパル) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="039b6-189">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="039b6-190">役割グループのメンバーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="039b6-190">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="039b6-191">既存 _の_ メンバーの一覧を指定した値に置き換える場合は、次の構文を使用します `"Member1","Member2",..."MemberN"` 。</span><span class="sxs-lookup"><span data-stu-id="039b6-191">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="039b6-192">メンバー _の既存の_ 一覧を選択的に変更するには、次の構文を使用します `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` 。</span><span class="sxs-lookup"><span data-stu-id="039b6-192">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="039b6-193">この例では、Help Desk 役割グループのすべての現在のメンバーを、指定されたユーザーに置き換えています。</span><span class="sxs-lookup"><span data-stu-id="039b6-193">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="039b6-194">次の使用例は、"Help Desk/ヘルプ デスク" 役割グループのメンバーの一覧から Valeria Barrio を追加し、Valeria Barrio を削除します。</span><span class="sxs-lookup"><span data-stu-id="039b6-194">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="039b6-195">構文およびパラメーターの詳細については [、「Update-RoleGroupMember」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)。</span><span class="sxs-lookup"><span data-stu-id="039b6-195">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="039b6-196">スタンドアロンの EOP PowerShell を使用して役割グループを削除する</span><span class="sxs-lookup"><span data-stu-id="039b6-196">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="039b6-197">組み込みの役割グループは削除できませんが、作成したカスタム役割グループは削除できます。</span><span class="sxs-lookup"><span data-stu-id="039b6-197">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="039b6-198">カスタム役割グループを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="039b6-198">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="039b6-199">この例では、Training Administrators 役割グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="039b6-199">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="039b6-200">構文およびパラメーターの詳細については、「[Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="039b6-200">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="039b6-201">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="039b6-201">How do you know these procedures worked?</span></span>

<span data-ttu-id="039b6-202">役割グループが正常にコピーされたことを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="039b6-202">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="039b6-203">EAC で、アクセス許可管理者の **役割** に移動し、役割グループが一覧に表示 (または一覧に表示されていない \> ) を確認します。</span><span class="sxs-lookup"><span data-stu-id="039b6-203">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="039b6-204">役割グループを選択し、[詳細] ウィンドウで設定を確認するか、[編集] アイコンをクリックして設定 ![ ](../../media/ITPro-EAC-EditIcon.png) を確認します。</span><span class="sxs-lookup"><span data-stu-id="039b6-204">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="039b6-205">Exchange Online PowerShell で、役割グループの名前に置き換え、次のコマンドを実行して役割グループが存在する (または存在しない) か確認し、設定を \<Role Group Name\> 確認します。</span><span class="sxs-lookup"><span data-stu-id="039b6-205">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
