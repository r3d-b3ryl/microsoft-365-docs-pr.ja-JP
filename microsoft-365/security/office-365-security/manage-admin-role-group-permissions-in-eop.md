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
description: 管理者は、Exchange Online Protection の Exchange 管理センター (EAC) でアクセス許可を割り当てたり、削除したりする方法について学習できます。
ms.openlocfilehash: 8d452eb85d59bbe82cc6685d652617bc857c1ddf
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825691"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="64b58-103">スタンドアロン EOP で役割グループを管理する</span><span class="sxs-lookup"><span data-stu-id="64b58-103">Manage role groups in standalone EOP</span></span>

<span data-ttu-id="64b58-104">Exchange Online メールボックスを使用しているスタンドアロン Exchange Online Protection (EOP) 組織では、Exchange 管理センター (EAC) を使用して、ユーザーを役割グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="64b58-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="64b58-105">ユーザーを役割グループに追加すると、そのユーザーに特定の管理タスクを実行するアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="64b58-105">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="64b58-106">役割グループからユーザーを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="64b58-106">You can also remove users from role groups.</span></span>

<span data-ttu-id="64b58-107">役割と役割グループの詳細については、「スタンドアロン [EOP のアクセス許可」を参照してください](feature-permissions-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="64b58-107">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="64b58-108">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="64b58-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="64b58-109">Exchange 管理センター (EAC) を開くには、スタンドアロン [EOP の Exchange 管理センターを参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="64b58-109">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="64b58-110">スタンドアロン EOP PowerShell を開くには、「Exchange [Online Protection の PowerShell に接続してください。」を参照してください](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="64b58-110">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="64b58-111">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="64b58-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="64b58-112">具体的には、既定で OrganizationManagement (グローバル管理者) 役割グループに割り当てられている、"Role Management/役割管理" 役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="64b58-112">Specifically, you need the Role Management role, which is assigned to the OrganizationManagement (global admins) role group by default.</span></span> <span data-ttu-id="64b58-113">詳細については、「スタンドアロン [EOP のアクセス許可」を参照し、EAC](feature-permissions-in-eop.md) [を使用して役割グループ内のメンバーの一覧を変更します](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="64b58-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="64b58-114">このトピックの手順で使用可能なキーボード ショートカットについては [、Exchange Online の Exchange 管理センターのキーボード ショートカットを参照してください](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="64b58-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="64b58-115">問題が発生する場合</span><span class="sxs-lookup"><span data-stu-id="64b58-115">Having problems?</span></span> <span data-ttu-id="64b58-116">[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) フォーラムでサポートをご依頼ください。</span><span class="sxs-lookup"><span data-stu-id="64b58-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="64b58-117">EAC を使用して役割グループを管理する</span><span class="sxs-lookup"><span data-stu-id="64b58-117">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="64b58-118">EAC を使用して役割グループを表示する</span><span class="sxs-lookup"><span data-stu-id="64b58-118">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="64b58-119">EAC でアクセス許可管理者役割 **に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="64b58-119">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="64b58-120">組織の役割グループのすべてが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="64b58-120">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="64b58-121">役割グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="64b58-121">Select a role group.</span></span> <span data-ttu-id="64b58-122">詳細ウィンドウには、その役割**グループによって** **[名前、説明\*\*\*\*、割り**当てられた**役割、管理]** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="64b58-122">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="64b58-123">この情報は、[編集] アイコンをクリック **して確認** ![ できます ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="64b58-123">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="64b58-124">EAC を使用して役割グループを作成する</span><span class="sxs-lookup"><span data-stu-id="64b58-124">Use the EAC to create role groups</span></span>

<span data-ttu-id="64b58-125">新しい役割グループを作成する場合、(グループの作成中またはその後) すべての設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="64b58-125">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="64b58-126">また、既存の役割グループをコピーして変更できます。</span><span class="sxs-lookup"><span data-stu-id="64b58-126">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="64b58-127">EAC で、アクセス許可**Permissions**管理者 \> **の役割に移動**し、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="64b58-127">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="64b58-128">**新しい役割グループを手動で作成する**: [ **追加]** ![ アイコンをクリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="64b58-128">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="64b58-129">**Copy an existing role group:** Select the role group **Copy** that you want to copy ![ copy icon ](../../media/ITPro-EAC-CopyIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="64b58-129">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="64b58-130">表示される **[役割グループの新規** 作成] ウィンドウで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="64b58-130">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="64b58-131">**Name:** 役割グループの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="64b58-131">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="64b58-132">**Description**:役割グループの説明 (省略可能) を入力します。</span><span class="sxs-lookup"><span data-stu-id="64b58-132">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="64b58-133">**[Role:** 追加 **] アイコン** ![ または [ ](../../media/ITPro-EAC-AddIcon.png) 削除 **]** ![ をクリック ](../../media/ITPro-EAC-RemoveIcon.gif)ITPro-EAC-RemoveIcon.gif、役割グループに割り当てられている役割を選択または変更できます。</span><span class="sxs-lookup"><span data-stu-id="64b58-133">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="64b58-134">**Members**: [追加] **アイコンまたは** ![ [ ](../../media/ITPro-EAC-AddIcon.png) 追加] **を** ![ クリックITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) 役割グループのメンバーシップを変更します。</span><span class="sxs-lookup"><span data-stu-id="64b58-134">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="64b58-135">完了したら、[保存] **をクリックして** 役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="64b58-135">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="64b58-136">EAC を使用して役割グループを変更する</span><span class="sxs-lookup"><span data-stu-id="64b58-136">Use the EAC to modify role groups</span></span>

<span data-ttu-id="64b58-137">EAC で、[アクセス許可の管理 **役割** \> **] に**移動し、変更する役割グループを選択してから、[編集] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="64b58-137">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="64b58-138">役割グループを変更する場合と同じオプションは、役割グループの作成時と同じオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="64b58-138">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="64b58-139">以下のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="64b58-139">You can:</span></span>

- <span data-ttu-id="64b58-140">名前と説明を変更します。</span><span class="sxs-lookup"><span data-stu-id="64b58-140">Change the name and description.</span></span>

- <span data-ttu-id="64b58-141">管理役割の追加と削除 (役割の割り当ての作成または削除)。</span><span class="sxs-lookup"><span data-stu-id="64b58-141">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="64b58-142">メンバーを追加および削除します。</span><span class="sxs-lookup"><span data-stu-id="64b58-142">Add and remove members.</span></span>

<span data-ttu-id="64b58-143">**注**: 一部の役割グループ (組織の管理など) では、グループから削除できる役割を制限します。</span><span class="sxs-lookup"><span data-stu-id="64b58-143">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="64b58-144">EAC を使用して役割グループのメンバー一覧を変更する</span><span class="sxs-lookup"><span data-stu-id="64b58-144">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="64b58-145">EAC で、[アクセス許可の管理 **役割** \> **] に**移動し、変更する役割グループを選択してから、[編集] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="64b58-145">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="64b58-146">開いた役割グループのプロパティ ページが表示された [ **メンバー]** セクションで、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="64b58-146">In the role group properties page that opens, in the **Members** section, do either of the following steps:</span></span>

   - <span data-ttu-id="64b58-147">[追加 **]** ![ アイコンをクリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="64b58-147">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="64b58-148">表示されたページで、追加したいユーザーを見つけ **、add->**。</span><span class="sxs-lookup"><span data-stu-id="64b58-148">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="64b58-149">ユーザーを選択し **、add ->** 必要に応じて 、数回だけをクリックします。</span><span class="sxs-lookup"><span data-stu-id="64b58-149">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="64b58-150">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64b58-150">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="64b58-151">削除するユーザーを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="64b58-151">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="64b58-152">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64b58-152">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="64b58-153">役割グループに対してメンバーを追加または削除した後、ユーザーは自身の管理者権限の変更を確認するためにサインアウトしてから、再度サインインしなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="64b58-153">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="64b58-154">EAC を使用して役割グループを削除する</span><span class="sxs-lookup"><span data-stu-id="64b58-154">Use the EAC to remove role groups</span></span>

<span data-ttu-id="64b58-155">組み込みの役割グループを削除することはできませんが、作成したカスタム役割グループを削除できます。</span><span class="sxs-lookup"><span data-stu-id="64b58-155">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="64b58-156">EAC でアクセス許可管理者役割 **に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="64b58-156">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="64b58-157">削除する役割グループを選択し、[削除] アイコン **をクリック** ![ します ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="64b58-157">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="64b58-158">表示 **された確認** ウィンドウで [はい] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64b58-158">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="64b58-159">PowerShell を使用して役割グループを管理する</span><span class="sxs-lookup"><span data-stu-id="64b58-159">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="64b58-160">スタンドアロン EOP PowerShell を使用して役割グループを表示する</span><span class="sxs-lookup"><span data-stu-id="64b58-160">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="64b58-161">役割グループを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="64b58-161">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="64b58-162">この例では、すべての役割グループの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="64b58-162">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="64b58-163">この例では、Recipient Administrators という名前の役割グループの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="64b58-163">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="64b58-164">この例では、ユーザー Julia がメンバーになっているすべての役割グループを返します。</span><span class="sxs-lookup"><span data-stu-id="64b58-164">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="64b58-165">Julia の DistinguishedName (DN) 値を使用する必要があります。コマンドを実行して確認 `Get-User -Identity Julia | Format-List DistinguishedName` できます。</span><span class="sxs-lookup"><span data-stu-id="64b58-165">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="64b58-166">構文およびパラメーターの詳細については、「[Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64b58-166">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="64b58-167">スタンドアロン EOP PowerShell を使用して役割グループを作成する</span><span class="sxs-lookup"><span data-stu-id="64b58-167">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="64b58-168">新しい役割グループを作成すると、設定をすべて手動で構成できます (グループの作成中またはその後)。</span><span class="sxs-lookup"><span data-stu-id="64b58-168">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="64b58-169">また、既存の役割グループをコピーして変更できます。</span><span class="sxs-lookup"><span data-stu-id="64b58-169">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="64b58-170">新しい役割グループを手動で作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="64b58-170">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="64b58-171">_Role パラメーターは_、以下の構文を使用して役割グループに割り当てる管理役割を指定します `"Role1","Role1",..."RoleN"` 。</span><span class="sxs-lookup"><span data-stu-id="64b58-171">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="64b58-172">**Get-ManagementRole** コマンドレットを使用して、使用できる役割を確認できます。</span><span class="sxs-lookup"><span data-stu-id="64b58-172">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="64b58-173">_Members パラメーターは_、以下の構文を使用して、役割グループのメンバーを指定します `"Member1","Member2",..."MemberN"` 。</span><span class="sxs-lookup"><span data-stu-id="64b58-173">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="64b58-174">ユーザー、メールが有効なユニバーサル セキュリティ グループ (USG)、またはその他の役割グループ (セキュリティ プリンシパル) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="64b58-174">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="64b58-175">この例では、次の設定を使用して「Limited Recipient Management」という名前の新しい役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="64b58-175">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="64b58-176">メール受信者の役割が、役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="64b58-176">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="64b58-177">ユーザーの Kim と Martin がメンバーとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="64b58-177">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="64b58-178">既存の役割グループをコピーするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="64b58-178">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="64b58-179">以下の構文を使用して、変数にコピーする役割グループを格納します。</span><span class="sxs-lookup"><span data-stu-id="64b58-179">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="64b58-180">以下の構文を使用して、新しい役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="64b58-180">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="64b58-181">_Members パラメーターは_、以下の構文を使用して、役割グループのメンバーを指定します `"Member1","Member2",..."MemberN"` 。</span><span class="sxs-lookup"><span data-stu-id="64b58-181">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="64b58-182">ユーザー、メールが有効なユニバーサル セキュリティ グループ (USG)、またはその他の役割グループ (セキュリティ プリンシパル) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="64b58-182">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="64b58-183">この例では、"Organization Management/組織の管理" 役割グループを"Limited Organization Management"という名前の新しい役割グループにコピーします。</span><span class="sxs-lookup"><span data-stu-id="64b58-183">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="64b58-184">役割グループのメンバーは、Isabelle、Carter、Lukas です。</span><span class="sxs-lookup"><span data-stu-id="64b58-184">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="64b58-185">構文およびパラメーターの詳細については [、「New-RoleGroup」を参照してください](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)。</span><span class="sxs-lookup"><span data-stu-id="64b58-185">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="64b58-186">スタンドアロン EOP PowerShell を使用して、役割グループのメンバーリストを変更する</span><span class="sxs-lookup"><span data-stu-id="64b58-186">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="64b58-187">**Add-RoleGroupMember コマンドレットと** **Remove-RoleGroupMember コマンドレットは、** 一度に 1 人のメンバーを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="64b58-187">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="64b58-188">**Update-RoleGroupMember コマンドレットは、** 既存のメンバー一覧を置き換えまたは変更できます。</span><span class="sxs-lookup"><span data-stu-id="64b58-188">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="64b58-189">役割グループのメンバーは、ユーザー、メールが有効なユニバーサル セキュリティ グループ (USG)、またはその他の役割グループ (セキュリティ プリンシパル) の場合があります。</span><span class="sxs-lookup"><span data-stu-id="64b58-189">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="64b58-190">役割グループのメンバーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="64b58-190">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="64b58-191">既存 _のメンバー_ の一覧を指定した値に置き換えるには、次の構文を使用します `"Member1","Member2",..."MemberN"` 。</span><span class="sxs-lookup"><span data-stu-id="64b58-191">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="64b58-192">メンバー _の既存のリストを_ 選択的に変更するには、次の構文を使用します `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` 。</span><span class="sxs-lookup"><span data-stu-id="64b58-192">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="64b58-193">この例では、"Help Desk/ヘルプ デスク" 役割グループの現在のすべてのメンバーを、指定したユーザーに置き換えました。</span><span class="sxs-lookup"><span data-stu-id="64b58-193">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="64b58-194">この例では、Daigoro Akai を追加し、"Help Desk/ヘルプ デスク" 役割グループのメンバー リストから Valeria Barrio を削除します。</span><span class="sxs-lookup"><span data-stu-id="64b58-194">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="64b58-195">構文およびパラメーターの詳細については [、Update-RoleGroupMember を参照してください](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)。</span><span class="sxs-lookup"><span data-stu-id="64b58-195">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="64b58-196">スタンドアロン EOP PowerShell を使用して役割グループを削除する</span><span class="sxs-lookup"><span data-stu-id="64b58-196">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="64b58-197">組み込みの役割グループを削除することはできませんが、作成したカスタム役割グループを削除できます。</span><span class="sxs-lookup"><span data-stu-id="64b58-197">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="64b58-198">カスタム役割グループを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="64b58-198">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="64b58-199">この例では、Training Administrators 役割グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="64b58-199">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="64b58-200">構文およびパラメーターの詳細については、「[Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64b58-200">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="64b58-201">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="64b58-201">How do you know these procedures worked?</span></span>

<span data-ttu-id="64b58-202">役割グループが正常にコピーされたことを確認するには、次の手順のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="64b58-202">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="64b58-203">EAC で、[アクセス許可の管理役割 **]** \> **に移動し**、役割グループが一覧に表示されている (または一覧にない) ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="64b58-203">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="64b58-204">役割グループを選択し、[詳細] ウィンドウで設定を確認するか、[編集] **アイコンをクリック** ![ ](../../media/ITPro-EAC-EditIcon.png) して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="64b58-204">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="64b58-205">Exchange Online PowerShell で、役割 \<Role Group Name\> グループの名前に置き換え、次のコマンドを実行して、役割グループが存在するかどうかを確認 (存在しない) ため、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="64b58-205">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
