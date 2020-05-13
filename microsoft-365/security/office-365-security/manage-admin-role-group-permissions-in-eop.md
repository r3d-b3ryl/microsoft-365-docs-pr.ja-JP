---
title: EOP で役割グループを管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 管理者は、exchange Online Protection の Exchange 管理センター (EAC) でアクセス許可を割り当てる、または削除する方法を学習できます。
ms.openlocfilehash: 3d7b709304f901c4adc41c67b0d6fe9c6ff382bf
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209685"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="4e70c-103">スタンドアロン EOP で役割グループを管理する</span><span class="sxs-lookup"><span data-stu-id="4e70c-103">Manage role groups in standalone EOP</span></span>

<span data-ttu-id="4e70c-104">Exchange Online メールボックスを持たないスタンドアロンの Exchange Online Protection (EOP) 組織では、Exchange 管理センター (EAC) を使用してユーザーを役割グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="4e70c-105">ユーザーを役割グループに追加すると、特定の管理タスクを実行するためのアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-105">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="4e70c-106">役割グループからユーザーを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-106">You can also remove users from role groups.</span></span>

<span data-ttu-id="4e70c-107">役割と役割グループの詳細については、「 [Permissions in STANDALONE EOP](feature-permissions-in-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e70c-107">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4e70c-108">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="4e70c-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4e70c-109">Exchange 管理センター (EAC) を開くには、「 [exchange admin center in STANDALONE EOP](exchange-admin-center-in-exchange-online-protection-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e70c-109">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="4e70c-110">スタンドアロン EOP PowerShell を開くには、「 [Exchange Online Protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e70c-110">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="4e70c-111">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e70c-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="4e70c-112">具体的には、役割管理役割が必要です。これは、既定では、組織の管理 (グローバル管理者) 役割グループに割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="4e70c-112">Specifically, you need the Role Management role, which is assigned to the OrganizationManagement (global admins) role group by default.</span></span> <span data-ttu-id="4e70c-113">詳細については、「 [Permissions in STANDALONE EOP](feature-permissions-in-eop.md) 」を参照して、EAC を使用して、[役割グループのメンバーの一覧を変更](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="4e70c-114">このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e70c-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="4e70c-115">問題がある場合は、</span><span class="sxs-lookup"><span data-stu-id="4e70c-115">Having problems?</span></span> <span data-ttu-id="4e70c-116">[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)フォーラムでヘルプを要求します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="4e70c-117">EAC を使用して役割グループを管理する</span><span class="sxs-lookup"><span data-stu-id="4e70c-117">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="4e70c-118">EAC を使用して役割グループを表示する</span><span class="sxs-lookup"><span data-stu-id="4e70c-118">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="4e70c-119">EAC で、[**アクセス許可** \> **管理者の役割**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-119">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="4e70c-120">組織の役割グループのすべてが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-120">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="4e70c-121">役割グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-121">Select a role group.</span></span> <span data-ttu-id="4e70c-122">詳細ウィンドウには、役割グループの**名前**、**説明**、**割り当てられた役割**、および**管理者**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-122">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="4e70c-123">この情報は **、[編集**] 編集アイコンをクリックして確認することもでき ![ ](../../media/ITPro-EAC-EditIcon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-123">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="4e70c-124">EAC を使用して役割グループを作成する</span><span class="sxs-lookup"><span data-stu-id="4e70c-124">Use the EAC to create role groups</span></span>

<span data-ttu-id="4e70c-125">新しい役割グループを作成する場合、すべての設定を (グループの作成時または実行後に) 自分で構成できます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-125">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="4e70c-126">または、既存の役割グループをコピーして変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-126">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="4e70c-127">EAC で、[**アクセス許可** \> **管理者の役割**] に移動し、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-127">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="4e70c-128">**新しい役割グループを手動で作成**します \*\*。 [追加\*\* ![ ] アイコンをクリックし ](../../media/ITPro-EAC-AddIcon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-128">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="4e70c-129">**既存の役割グループをコピー**する: コピーする役割グループを選択し、[コピー**のコピー** ![ ] アイコンをクリックし ](../../media/ITPro-EAC-CopyIcon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-129">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="4e70c-130">表示される [**役割グループの新規作成**] ウィンドウで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-130">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="4e70c-131">[**名前**]: 役割グループの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-131">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="4e70c-132">[**説明**]: 役割グループの説明 (オプション) を入力します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-132">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="4e70c-133">[**役割**] **Add** : [ ![ 追加] アイコンをクリック ](../../media/ITPro-EAC-AddIcon.png) するか**Remove** ![ 、ITPro-EAC-RemoveIcon を削除して ](../../media/ITPro-EAC-RemoveIcon.gif) 、役割グループに割り当てられている役割を選択または変更します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-133">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="4e70c-134">**メンバー** **: [追加\*\* ![ ] アイコン ](../../media/ITPro-EAC-AddIcon.png) を**Remove\*\*クリック ![ するか、ITPro-EAC-RemoveIcon を削除し ](../../media/ITPro-EAC-RemoveIcon.gif) て役割グループのメンバーシップを変更します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-134">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="4e70c-135">完了したら、[**保存**] をクリックして役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-135">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="4e70c-136">EAC を使用して役割グループを変更する</span><span class="sxs-lookup"><span data-stu-id="4e70c-136">Use the EAC to modify role groups</span></span>

<span data-ttu-id="4e70c-137">EAC で、[**アクセス許可** \> **管理者の役割**] に移動し、変更する役割グループを選択し**Edit**てから、[編集 ![ ] 編集アイコンをクリックし ](../../media/ITPro-EAC-EditIcon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-137">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="4e70c-138">役割グループの作成時に役割グループを変更する場合も、同じオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-138">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="4e70c-139">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-139">You can:</span></span>

- <span data-ttu-id="4e70c-140">名前と説明を変更します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-140">Change the name and description.</span></span>

- <span data-ttu-id="4e70c-141">管理役割を追加および削除する (役割の割り当てを作成または削除する)。</span><span class="sxs-lookup"><span data-stu-id="4e70c-141">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="4e70c-142">メンバーを追加および削除します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-142">Add and remove members.</span></span>

<span data-ttu-id="4e70c-143">**注**: 一部の役割グループ (たとえば、組織管理) は、グループから削除できる役割を制限します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-143">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="4e70c-144">EAC を使用して役割グループのメンバーの一覧を変更する</span><span class="sxs-lookup"><span data-stu-id="4e70c-144">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="4e70c-145">EAC で、[**アクセス許可** \> **管理者の役割**] に移動し、変更する役割グループを選択して**Edit**から、[編集 ![ ] 編集アイコンをクリックし ](../../media/ITPro-EAC-EditIcon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-145">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="4e70c-146">開いている役割グループのプロパティページの [ **Memebers** ] セクションで、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-146">In the role group properties page that opens, in the **Memebers** section, do either of the following steps:</span></span>

   - <span data-ttu-id="4e70c-147">[**追加** ![ ] アイコン ](../../media/ITPro-EAC-AddIcon.png) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e70c-147">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="4e70c-148">表示されるページで、wou を追加するユーザーを見つけ、[**追加->**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e70c-148">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="4e70c-149">[ユーザー] を選択し、必要に応じて [ **>** ] を繰り返しクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e70c-149">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="4e70c-150">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e70c-150">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="4e70c-151">削除するユーザーを選択し、[削除] [削除] アイコン**をクリックし** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) ます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-151">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="4e70c-152">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e70c-152">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4e70c-153">役割グループに対してメンバーを追加または削除した後、ユーザーは自身の管理者権限の変更を確認するためにサインアウトしてから、再度サインインしなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="4e70c-153">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="4e70c-154">EAC を使用して役割グループを削除する</span><span class="sxs-lookup"><span data-stu-id="4e70c-154">Use the EAC to remove role groups</span></span>

<span data-ttu-id="4e70c-155">組み込みの役割グループを削除することはできませんが、作成したカスタム役割グループを削除することはできます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-155">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="4e70c-156">EAC で、[**アクセス許可** \> **管理者の役割**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-156">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="4e70c-157">削除する役割グループを選択し、[削除] **[削除] アイコンをクリックし** ![ ](../../media/ITPro-EAC-DeleteIcon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-157">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="4e70c-158">確認ウィンドウが表示されたら、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e70c-158">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="4e70c-159">PowerShell を使用して役割グループを管理する</span><span class="sxs-lookup"><span data-stu-id="4e70c-159">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="4e70c-160">スタンドアロンの EOP PowerShell を使用して役割グループを表示する</span><span class="sxs-lookup"><span data-stu-id="4e70c-160">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="4e70c-161">役割グループを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-161">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="4e70c-162">この例では、すべての役割グループの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-162">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="4e70c-163">この例では、"受信者管理者" という名前の役割グループの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-163">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="4e70c-164">この例では、ユーザージュリアがメンバーであるすべての役割グループを返します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-164">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="4e70c-165">次のコマンドを実行すると、ジュリアの DistinguishedName (DN) 値を使用する必要があります `Get-User -Identity Julia | Format-List DistinguishedName` 。</span><span class="sxs-lookup"><span data-stu-id="4e70c-165">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="4e70c-166">構文およびパラメーターの詳細については、「[Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/Get-RoleGroup)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e70c-166">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="4e70c-167">スタンドアロンの EOP PowerShell を使用して役割グループを作成する</span><span class="sxs-lookup"><span data-stu-id="4e70c-167">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="4e70c-168">新しい役割グループを作成する場合、すべての設定を手動で構成できます (グループの作成時または実行後)。</span><span class="sxs-lookup"><span data-stu-id="4e70c-168">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="4e70c-169">または、既存の役割グループをコピーして変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-169">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="4e70c-170">新しい役割グループを手動で作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-170">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="4e70c-171">_Roles_パラメーターは、次の構文を使用して、役割グループに割り当てる管理役割を指定し `"Role1","Role1",..."RoleN"` ます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-171">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="4e70c-172">利用可能な役割を確認するには、管理者の**役割**のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-172">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="4e70c-173">_Members_パラメーターは、次の構文を使用して、役割グループのメンバーを指定し `"Member1","Member2",..."MemberN"` ます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-173">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="4e70c-174">ユーザー、メールが有効なユニバーサルセキュリティグループ (Usg)、またはその他の役割グループ (セキュリティプリンシパル) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-174">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="4e70c-175">この例では、次の設定を使用して "制限付き受信者管理" という名前の新しい役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-175">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="4e70c-176">"Mail Recipients/メール受信者" 役割は、役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-176">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="4e70c-177">Kim と Martin のユーザーは、メンバーとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-177">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="4e70c-178">既存の役割グループをコピーするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-178">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="4e70c-179">以下の構文を使用して、変数にコピーする役割グループを格納します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-179">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="4e70c-180">次の構文を使用して、新しい役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-180">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="4e70c-181">_Members_パラメーターは、次の構文を使用して、役割グループのメンバーを指定し `"Member1","Member2",..."MemberN"` ます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-181">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="4e70c-182">ユーザー、メールが有効なユニバーサルセキュリティグループ (Usg)、またはその他の役割グループ (セキュリティプリンシパル) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-182">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="4e70c-183">この例では、組織の管理役割グループを "制限された組織の管理" という名前の新しい役割グループにコピーします。</span><span class="sxs-lookup"><span data-stu-id="4e70c-183">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="4e70c-184">役割グループのメンバーは、Isabelle、Carter、Lukas です。</span><span class="sxs-lookup"><span data-stu-id="4e70c-184">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="4e70c-185">構文およびパラメーターの詳細については、「[新しい-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/New-RoleGroup)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e70c-185">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="4e70c-186">スタンドアロンの EOP PowerShell を使用する役割グループのメンバーの一覧を変更する</span><span class="sxs-lookup"><span data-stu-id="4e70c-186">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="4e70c-187">**Add-rolegroupmember**および**add-rolegroupmember**コマンドレットは、個々のメンバーを一度に1つずつ追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-187">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="4e70c-188">**Add-rolegroupmember**コマンドレットでは、既存のメンバーの一覧を置き換えたり変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-188">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="4e70c-189">役割グループのメンバーは、ユーザー、メールが有効なユニバーサルセキュリティグループ (Usg)、またはその他の役割グループ (セキュリティプリンシパル) にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-189">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="4e70c-190">役割グループのメンバーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-190">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="4e70c-191">既存のメンバーリストを指定した値に_置き換える_には、次の構文を使用し `"Member1","Member2",..."MemberN"` ます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-191">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="4e70c-192">既存のメンバーリストを_選択的に変更_するには、次の構文を使用し `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` ます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-192">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="4e70c-193">この例では、ヘルプデスク役割グループの現在のすべてのメンバーを指定されたユーザーに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-193">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="4e70c-194">この例では、Daigoro Akai を追加し、ヘルプデスク役割グループのメンバーの一覧から Valeria Barrio を削除します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-194">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="4e70c-195">構文およびパラメーターの詳細については、「 [add-rolegroupmember](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/Update-RoleGroupMember)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e70c-195">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="4e70c-196">スタンドアロンの EOP PowerShell を使用して役割グループを削除する</span><span class="sxs-lookup"><span data-stu-id="4e70c-196">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="4e70c-197">組み込みの役割グループを削除することはできませんが、作成したカスタム役割グループを削除することはできます。</span><span class="sxs-lookup"><span data-stu-id="4e70c-197">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="4e70c-198">カスタム役割グループを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-198">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="4e70c-199">この例では、Training Administrators 役割グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-199">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="4e70c-200">構文およびパラメーターの詳細については、「[Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/Remove-RoleGroup)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e70c-200">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="4e70c-201">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="4e70c-201">How do you know these procedures worked?</span></span>

<span data-ttu-id="4e70c-202">役割グループが正常にコピーされたことを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-202">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="4e70c-203">EAC で、[**アクセス許可** \> **管理者の役割**] に移動し、役割グループが表示されている (または一覧に表示されていない) ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-203">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="4e70c-204">役割グループを選択して、詳細ウィンドウで設定を確認するか \*\*、[編集\*\* ![ ] 編集アイコンをクリックし ](../../media/ITPro-EAC-EditIcon.png) て設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-204">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="4e70c-205">Exchange Online PowerShell で、役割 \< グループ名を \> 役割グループの名前に置き換え、次のコマンドを実行して役割グループが存在する (または存在しない) ことを確認し、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="4e70c-205">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
