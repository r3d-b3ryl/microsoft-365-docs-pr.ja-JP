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
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 管理者は、Exchange Online Protection の Exchange 管理センター (EAC) でアクセス許可を割り当てる方法または削除する方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e712c47d49508934ec7dd2438beff00eb6e1a20
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926882"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="522b2-103">スタンドアロン EOP で役割グループを管理する</span><span class="sxs-lookup"><span data-stu-id="522b2-103">Manage role groups in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="522b2-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="522b2-104">**Applies to**</span></span>
-  [<span data-ttu-id="522b2-105">Exchange Online Protection スタンドアロン</span><span class="sxs-lookup"><span data-stu-id="522b2-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="522b2-106">Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織では、Exchange 管理センター (EAC) を使用してユーザーを役割グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="522b2-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="522b2-107">役割グループにユーザーを追加すると、特定の管理タスクを実行するためのアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="522b2-107">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="522b2-108">役割グループからユーザーを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="522b2-108">You can also remove users from role groups.</span></span>

<span data-ttu-id="522b2-109">役割と役割グループの詳細については、「スタンドアロン [EOP のアクセス許可」を参照してください](feature-permissions-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="522b2-109">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="522b2-110">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="522b2-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="522b2-111">Exchange 管理センター (EAC) を開く場合は、「 [スタンドアロン EOP の Exchange 管理センター」を参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="522b2-111">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="522b2-112">スタンドアロン EOP PowerShell を開く方法については [、「Connect to Exchange Online Protection PowerShell」を参照してください](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="522b2-112">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="522b2-113">この記事の手順を実行するには、Exchange Online Protection でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="522b2-113">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="522b2-114">具体的には、既定で組織 **の管理** 役割グループに割り当てられている役割 **の管理** 役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="522b2-114">Specifically, you need the **Role Management** role, which is assigned to the **Organization Management** role group by default.</span></span> <span data-ttu-id="522b2-115">詳細については、「スタンドアロン [EOP のアクセス](feature-permissions-in-eop.md) 許可」および「役割グループのメンバーの一覧を [変更する EAC](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)を使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="522b2-115">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="522b2-116">この記事の手順に適用されるキーボード ショートカットの詳細については、「Exchange Online の Exchange 管理センターのキーボード ショートカット」 [を参照してください](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="522b2-116">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="522b2-117">問題が発生する場合</span><span class="sxs-lookup"><span data-stu-id="522b2-117">Having problems?</span></span> <span data-ttu-id="522b2-118">[Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) フォーラムでサポートをご依頼ください。</span><span class="sxs-lookup"><span data-stu-id="522b2-118">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="522b2-119">EAC を使用して役割グループを管理する</span><span class="sxs-lookup"><span data-stu-id="522b2-119">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="522b2-120">EAC を使用して役割グループを表示する</span><span class="sxs-lookup"><span data-stu-id="522b2-120">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="522b2-121">EAC で、[アクセス許可] **[管理者の役割]** \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="522b2-121">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="522b2-122">組織の役割グループのすべてが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="522b2-122">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="522b2-123">役割グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="522b2-123">Select a role group.</span></span> <span data-ttu-id="522b2-124">[詳細] ウィンドウには、 **役割** グループの [名前] **、[説明**] **、[** 割り当てられた役割]、および **[管理]** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="522b2-124">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="522b2-125">[編集] アイコンをクリックすると、この **情報を** ![ 確認することもできます ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="522b2-125">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="522b2-126">EAC を使用して役割グループを作成する</span><span class="sxs-lookup"><span data-stu-id="522b2-126">Use the EAC to create role groups</span></span>

<span data-ttu-id="522b2-127">新しい役割グループを作成する場合は、(グループの作成中または後に) すべての設定を自分で構成できます。</span><span class="sxs-lookup"><span data-stu-id="522b2-127">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="522b2-128">または、既存の役割グループをコピーして変更できます。</span><span class="sxs-lookup"><span data-stu-id="522b2-128">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="522b2-129">EAC で、[アクセス許可の **管理]** の役割に移動し、 \> 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="522b2-129">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="522b2-130">**新しい役割グループを手動で作成する**: [追加 **] アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="522b2-130">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="522b2-131">**既存の役割グループをコピー** する: コピーする役割グループを選択し、[コピー] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-CopyIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="522b2-131">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="522b2-132">表示される **[新しい役割グループ]** ウィンドウで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="522b2-132">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="522b2-133">**名前**: 役割グループの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="522b2-133">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="522b2-134">**説明**: 役割グループのオプションの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="522b2-134">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="522b2-135">**役割**: [追加 **] アイコン** または [削除] アイコンをクリックして、役割グループに割り当てられている役割 ![ ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) を選択または変更します。</span><span class="sxs-lookup"><span data-stu-id="522b2-135">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="522b2-136">**メンバー**: [追加 **] アイコン** または [削除] アイコンをクリック ![ ](../../media/ITPro-EAC-AddIcon.png)  ![ して ](../../media/ITPro-EAC-RemoveIcon.gif) 、役割グループのメンバーシップを変更します。</span><span class="sxs-lookup"><span data-stu-id="522b2-136">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="522b2-137">完了したら、[保存] をクリック **して** 役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="522b2-137">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="522b2-138">EAC を使用して役割グループを変更する</span><span class="sxs-lookup"><span data-stu-id="522b2-138">Use the EAC to modify role groups</span></span>

<span data-ttu-id="522b2-139">EAC で、[アクセス許可の管理者の役割] に移動し、変更する役割グループを選択し、[編集] アイコン \> **を** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="522b2-139">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="522b2-140">役割グループを作成する場合と同じオプションは、役割グループを変更するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="522b2-140">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="522b2-141">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="522b2-141">You can:</span></span>

- <span data-ttu-id="522b2-142">名前と説明を変更します。</span><span class="sxs-lookup"><span data-stu-id="522b2-142">Change the name and description.</span></span>

- <span data-ttu-id="522b2-143">管理役割を追加および削除します (役割の割り当てを作成または削除します)。</span><span class="sxs-lookup"><span data-stu-id="522b2-143">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="522b2-144">メンバーを追加および削除します。</span><span class="sxs-lookup"><span data-stu-id="522b2-144">Add and remove members.</span></span>

<span data-ttu-id="522b2-145">**注**: 一部の役割グループ (組織の管理など) では、グループから削除できる役割が制限されています。</span><span class="sxs-lookup"><span data-stu-id="522b2-145">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="522b2-146">役割グループ内のメンバーの一覧を変更する EAC を使用する</span><span class="sxs-lookup"><span data-stu-id="522b2-146">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="522b2-147">EAC で、[アクセス許可の管理者の役割] に移動し、変更する役割グループを選択し、[編集] アイコン \> **を** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="522b2-147">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="522b2-148">開く役割グループのプロパティ ページの [メンバー] **セクションで、** 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="522b2-148">In the role group properties page that opens, in the **Members** section, do either of the following steps:</span></span>

   - <span data-ttu-id="522b2-149">[追加 **] アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="522b2-149">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="522b2-150">表示されるページで、追加するユーザーを見つけて、[追加] をクリックして **[->] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="522b2-150">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="522b2-151">ユーザーを選択し、 **必要に応じて [->** 追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="522b2-151">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="522b2-152">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="522b2-152">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="522b2-153">削除するユーザーを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="522b2-153">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="522b2-154">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="522b2-154">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="522b2-155">役割グループに対してメンバーを追加または削除した後、ユーザーは自身の管理者権限の変更を確認するためにサインアウトしてから、再度サインインしなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="522b2-155">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="522b2-156">EAC を使用して役割グループを削除する</span><span class="sxs-lookup"><span data-stu-id="522b2-156">Use the EAC to remove role groups</span></span>

<span data-ttu-id="522b2-157">組み込みの役割グループは削除できませんが、作成したカスタム役割グループは削除できます。</span><span class="sxs-lookup"><span data-stu-id="522b2-157">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="522b2-158">EAC で、[アクセス許可] **[管理者の役割]** \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="522b2-158">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="522b2-159">削除する役割グループを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="522b2-159">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="522b2-160">表示 **される確認** ウィンドウで [はい] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="522b2-160">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="522b2-161">PowerShell を使用して役割グループを管理する</span><span class="sxs-lookup"><span data-stu-id="522b2-161">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="522b2-162">スタンドアロン EOP PowerShell を使用して役割グループを表示する</span><span class="sxs-lookup"><span data-stu-id="522b2-162">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="522b2-163">役割グループを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="522b2-163">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="522b2-164">次の使用例は、すべての役割グループの概要リストを返します。</span><span class="sxs-lookup"><span data-stu-id="522b2-164">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="522b2-165">次の使用例は、Recipient Administrators という名前の役割グループの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="522b2-165">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="522b2-166">この例では、ユーザー Julia がメンバーであるすべての役割グループを返します。</span><span class="sxs-lookup"><span data-stu-id="522b2-166">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="522b2-167">Julia の識別名 (DN) 値を使用する必要があります。これは、次のコマンドを実行して見つける必要があります `Get-User -Identity Julia | Format-List DistinguishedName` 。</span><span class="sxs-lookup"><span data-stu-id="522b2-167">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="522b2-168">構文およびパラメーターの詳細については、「[Get-RoleGroup](/powershell/module/exchange/Get-RoleGroup)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="522b2-168">For detailed syntax and parameter information, see [Get-RoleGroup](/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="522b2-169">スタンドアロン EOP PowerShell を使用して役割グループを作成する</span><span class="sxs-lookup"><span data-stu-id="522b2-169">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="522b2-170">新しい役割グループを作成する場合は、(グループの作成中または後に) すべての設定を手動で構成できます。</span><span class="sxs-lookup"><span data-stu-id="522b2-170">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="522b2-171">または、既存の役割グループをコピーして変更できます。</span><span class="sxs-lookup"><span data-stu-id="522b2-171">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="522b2-172">新しい役割グループを手動で作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="522b2-172">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="522b2-173">_Roles パラメーターは_、次の構文を使用して役割グループに割り当てる管理役割を指定します `"Role1","Role1",..."RoleN"` 。</span><span class="sxs-lookup"><span data-stu-id="522b2-173">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="522b2-174">**Get-ManagementRole** コマンドレットを使用して、使用できる役割を確認できます。</span><span class="sxs-lookup"><span data-stu-id="522b2-174">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="522b2-175">_Members パラメーター_ は、次の構文を使用して役割グループのメンバーを指定します `"Member1","Member2",..."MemberN"` 。</span><span class="sxs-lookup"><span data-stu-id="522b2-175">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="522b2-176">ユーザー、メールが有効なユニバーサル セキュリティ グループ (USG)、またはその他の役割グループ (セキュリティ プリンシパル) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="522b2-176">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="522b2-177">この例では、次の設定を使用して、"制限付き受信者管理" という名前の新しい役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="522b2-177">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="522b2-178">[メール受信者] 役割は、役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="522b2-178">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="522b2-179">Kim と Martin のユーザーはメンバーとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="522b2-179">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="522b2-180">既存の役割グループをコピーするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="522b2-180">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="522b2-181">以下の構文を使用して、変数にコピーする役割グループを格納します。</span><span class="sxs-lookup"><span data-stu-id="522b2-181">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="522b2-182">次の構文を使用して、新しい役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="522b2-182">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="522b2-183">_Members パラメーター_ は、次の構文を使用して役割グループのメンバーを指定します `"Member1","Member2",..."MemberN"` 。</span><span class="sxs-lookup"><span data-stu-id="522b2-183">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="522b2-184">ユーザー、メールが有効なユニバーサル セキュリティ グループ (USG)、またはその他の役割グループ (セキュリティ プリンシパル) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="522b2-184">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="522b2-185">次の使用例は、組織の管理役割グループを "Limited Organization Management" という名前の新しい役割グループにコピーします。</span><span class="sxs-lookup"><span data-stu-id="522b2-185">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="522b2-186">役割グループのメンバーは、イザベル、カーター、および Lukas です。</span><span class="sxs-lookup"><span data-stu-id="522b2-186">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="522b2-187">構文とパラメーターの詳細については [、New-RoleGroup を参照してください](/powershell/module/exchange/New-RoleGroup)。</span><span class="sxs-lookup"><span data-stu-id="522b2-187">For detailed syntax and parameter information, [New-RoleGroup](/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="522b2-188">スタンドアロンの EOP PowerShell を使用して、役割グループ内のメンバーの一覧を変更する</span><span class="sxs-lookup"><span data-stu-id="522b2-188">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="522b2-189">**Add-RoleGroupMember** コマンドレットと **Remove-RoleGroupMember** コマンドレットは、個々のメンバーを一度に 1 つ追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="522b2-189">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="522b2-190">**Update-RoleGroupMember** コマンドレットは、メンバーの既存のリストを置き換えるまたは変更できます。</span><span class="sxs-lookup"><span data-stu-id="522b2-190">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="522b2-191">役割グループのメンバーには、ユーザー、メールが有効なユニバーサル セキュリティ グループ (USG)、または他の役割グループ (セキュリティ プリンシパル) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="522b2-191">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="522b2-192">役割グループのメンバーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="522b2-192">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="522b2-193">メンバー _の_ 既存のリストを指定した値に置き換える場合は、次の構文を使用します `"Member1","Member2",..."MemberN"` 。</span><span class="sxs-lookup"><span data-stu-id="522b2-193">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="522b2-194">メンバー _の既存のリスト_ を選択的に変更するには、次の構文を使用します `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` 。</span><span class="sxs-lookup"><span data-stu-id="522b2-194">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="522b2-195">この例では、ヘルプ デスク役割グループのすべての現在のメンバーを指定したユーザーに置き換えています。</span><span class="sxs-lookup"><span data-stu-id="522b2-195">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="522b2-196">この例では、Daigoro Akai を追加し、ヘルプ デスク役割グループのメンバーの一覧から Valeria Barrio を削除します。</span><span class="sxs-lookup"><span data-stu-id="522b2-196">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="522b2-197">構文とパラメーターの詳細については [、「Update-RoleGroupMember」を参照してください](/powershell/module/exchange/Update-RoleGroupMember)。</span><span class="sxs-lookup"><span data-stu-id="522b2-197">For detailed syntax and parameter information, see [Update-RoleGroupMember](/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="522b2-198">スタンドアロン EOP PowerShell を使用して役割グループを削除する</span><span class="sxs-lookup"><span data-stu-id="522b2-198">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="522b2-199">組み込みの役割グループは削除できませんが、作成したカスタム役割グループは削除できます。</span><span class="sxs-lookup"><span data-stu-id="522b2-199">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="522b2-200">カスタム役割グループを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="522b2-200">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="522b2-201">この例では、Training Administrators 役割グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="522b2-201">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="522b2-202">構文およびパラメーターの詳細については、「[Remove-RoleGroup](/powershell/module/exchange/Remove-RoleGroup)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="522b2-202">For detailed syntax and parameter information, see [Remove-RoleGroup](/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="522b2-203">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="522b2-203">How do you know these procedures worked?</span></span>

<span data-ttu-id="522b2-204">役割グループが正常にコピーされたことを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="522b2-204">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="522b2-205">EAC で、[アクセス許可の管理者 **の** 役割] に移動し、役割グループが一覧表示 (または一覧に表示されていない \> ) を確認します。</span><span class="sxs-lookup"><span data-stu-id="522b2-205">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="522b2-206">役割グループを選択し、[詳細] ウィンドウで設定を確認するか、[編集] アイコンをクリックして設定 ![ ](../../media/ITPro-EAC-EditIcon.png) を確認します。</span><span class="sxs-lookup"><span data-stu-id="522b2-206">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="522b2-207">Exchange Online PowerShell で、役割グループの名前に置き換え、次のコマンドを実行して役割グループが存在する (または存在しない) か確認し、設定 \<Role Group Name\> を確認します。</span><span class="sxs-lookup"><span data-stu-id="522b2-207">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```