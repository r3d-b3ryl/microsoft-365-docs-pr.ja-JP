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
# <a name="manage-role-groups-in-standalone-eop"></a>スタンドアロン EOP で役割グループを管理する

Exchange Online メールボックスを使用しているスタンドアロン Exchange Online Protection (EOP) 組織では、Exchange 管理センター (EAC) を使用して、ユーザーを役割グループに追加できます。 ユーザーを役割グループに追加すると、そのユーザーに特定の管理タスクを実行するアクセス許可が付与されます。 役割グループからユーザーを削除することもできます。

役割と役割グループの詳細については、「スタンドアロン [EOP のアクセス許可」を参照してください](feature-permissions-in-eop.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- Exchange 管理センター (EAC) を開くには、スタンドアロン [EOP の Exchange 管理センターを参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。

- スタンドアロン EOP PowerShell を開くには、「Exchange [Online Protection の PowerShell に接続してください。」を参照してください](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 具体的には、既定で OrganizationManagement (グローバル管理者) 役割グループに割り当てられている、"Role Management/役割管理" 役割が必要です。 詳細については、「スタンドアロン [EOP のアクセス許可」を参照し、EAC](feature-permissions-in-eop.md) [を使用して役割グループ内のメンバーの一覧を変更します](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- このトピックの手順で使用可能なキーボード ショートカットについては [、Exchange Online の Exchange 管理センターのキーボード ショートカットを参照してください](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 問題が発生する場合 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) フォーラムでサポートをご依頼ください。

## <a name="use-the-eac-to-manage-role-groups"></a>EAC を使用して役割グループを管理する

### <a name="use-the-eac-to-view-role-groups"></a>EAC を使用して役割グループを表示する

1. EAC でアクセス許可管理者役割 **に** \> **移動します**。 組織の役割グループのすべてが一覧表示されます。

2. 役割グループを選択します。 詳細ウィンドウには、その役割**グループによって** **[名前、説明****、割り**当てられた**役割、管理]** が表示されます。 この情報は、[編集] アイコンをクリック **して確認** ![ できます ](../../media/ITPro-EAC-EditIcon.png) 。

### <a name="use-the-eac-to-create-role-groups"></a>EAC を使用して役割グループを作成する

新しい役割グループを作成する場合、(グループの作成中またはその後) すべての設定を構成できます。 また、既存の役割グループをコピーして変更できます。

1. EAC で、アクセス許可**Permissions**管理者 \> **の役割に移動**し、次のいずれかの手順を実行します。

   - **新しい役割グループを手動で作成する**: [ **追加]** ![ アイコンをクリックします ](../../media/ITPro-EAC-AddIcon.png) 。

   - **Copy an existing role group:** Select the role group **Copy** that you want to copy ![ copy icon ](../../media/ITPro-EAC-CopyIcon.png) .

2. 表示される **[役割グループの新規** 作成] ウィンドウで、次の設定を構成します。

    - **Name:** 役割グループの一意の名前を入力します。

    - **Description**:役割グループの説明 (省略可能) を入力します。

    - **[Role:** 追加 **] アイコン** ![ または [ ](../../media/ITPro-EAC-AddIcon.png) 削除 **]** ![ をクリック ](../../media/ITPro-EAC-RemoveIcon.gif)ITPro-EAC-RemoveIcon.gif、役割グループに割り当てられている役割を選択または変更できます。

    - **Members**: [追加] **アイコンまたは** ![ [ ](../../media/ITPro-EAC-AddIcon.png) 追加] **を** ![ クリックITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) 役割グループのメンバーシップを変更します。

3. 完了したら、[保存] **をクリックして** 役割グループを作成します。

### <a name="use-the-eac-to-modify-role-groups"></a>EAC を使用して役割グループを変更する

EAC で、[アクセス許可の管理 **役割** \> **] に**移動し、変更する役割グループを選択してから、[編集] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。

役割グループを変更する場合と同じオプションは、役割グループの作成時と同じオプションを使用できます。 以下のことを実行できます。

- 名前と説明を変更します。

- 管理役割の追加と削除 (役割の割り当ての作成または削除)。

- メンバーを追加および削除します。

**注**: 一部の役割グループ (組織の管理など) では、グループから削除できる役割を制限します。

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>EAC を使用して役割グループのメンバー一覧を変更する

1. EAC で、[アクセス許可の管理 **役割** \> **] に**移動し、変更する役割グループを選択してから、[編集] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。

2. 開いた役割グループのプロパティ ページが表示された [ **メンバー]** セクションで、次のいずれかの手順を実行します。

   - [追加 **]** ![ アイコンをクリックします ](../../media/ITPro-EAC-AddIcon.png) 。 表示されたページで、追加したいユーザーを見つけ **、add->**。 ユーザーを選択し **、add ->** 必要に応じて 、数回だけをクリックします。 完了したら、 **[OK]** をクリックします。

   - 削除するユーザーを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。

3. 完了したら、**[保存]** をクリックします。

   > [!NOTE]
   > 役割グループに対してメンバーを追加または削除した後、ユーザーは自身の管理者権限の変更を確認するためにサインアウトしてから、再度サインインしなければならない場合があります。

### <a name="use-the-eac-to-remove-role-groups"></a>EAC を使用して役割グループを削除する

組み込みの役割グループを削除することはできませんが、作成したカスタム役割グループを削除できます。

1. EAC でアクセス許可管理者役割 **に** \> **移動します**。

2. 削除する役割グループを選択し、[削除] アイコン **をクリック** ![ します ](../../media/ITPro-EAC-DeleteIcon.png) 。

3. 表示 **された確認** ウィンドウで [はい] をクリックします。

## <a name="use-powershell-to-manage-role-groups"></a>PowerShell を使用して役割グループを管理する

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>スタンドアロン EOP PowerShell を使用して役割グループを表示する

役割グループを表示するには、次の構文を使用します。

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

この例では、すべての役割グループの要約リストを返します。

```PowerShell
Get-RoleGroup
```

この例では、Recipient Administrators という名前の役割グループの詳細情報を返します。

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

この例では、ユーザー Julia がメンバーになっているすべての役割グループを返します。 Julia の DistinguishedName (DN) 値を使用する必要があります。コマンドを実行して確認 `Get-User -Identity Julia | Format-List DistinguishedName` できます。

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

構文およびパラメーターの詳細については、「[Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)」を参照してください。

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>スタンドアロン EOP PowerShell を使用して役割グループを作成する

新しい役割グループを作成すると、設定をすべて手動で構成できます (グループの作成中またはその後)。 また、既存の役割グループをコピーして変更できます。

- 新しい役割グループを手動で作成するには、次の構文を使用します。

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - _Role パラメーターは_、以下の構文を使用して役割グループに割り当てる管理役割を指定します `"Role1","Role1",..."RoleN"` 。 **Get-ManagementRole** コマンドレットを使用して、使用できる役割を確認できます。

  - _Members パラメーターは_、以下の構文を使用して、役割グループのメンバーを指定します `"Member1","Member2",..."MemberN"` 。 ユーザー、メールが有効なユニバーサル セキュリティ グループ (USG)、またはその他の役割グループ (セキュリティ プリンシパル) を指定できます。

  この例では、次の設定を使用して「Limited Recipient Management」という名前の新しい役割グループを作成します。

  - メール受信者の役割が、役割グループに割り当てられます。

  - ユーザーの Kim と Martin がメンバーとして追加されます。

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- 既存の役割グループをコピーするには、次の手順を実行します。

  1. 以下の構文を使用して、変数にコピーする役割グループを格納します。

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. 以下の構文を使用して、新しい役割グループを作成します。

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     _Members パラメーターは_、以下の構文を使用して、役割グループのメンバーを指定します `"Member1","Member2",..."MemberN"` 。 ユーザー、メールが有効なユニバーサル セキュリティ グループ (USG)、またはその他の役割グループ (セキュリティ プリンシパル) を指定できます。

     この例では、"Organization Management/組織の管理" 役割グループを"Limited Organization Management"という名前の新しい役割グループにコピーします。 役割グループのメンバーは、Isabelle、Carter、Lukas です。

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

構文およびパラメーターの詳細については [、「New-RoleGroup」を参照してください](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)。

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>スタンドアロン EOP PowerShell を使用して、役割グループのメンバーリストを変更する

- **Add-RoleGroupMember コマンドレットと** **Remove-RoleGroupMember コマンドレットは、** 一度に 1 人のメンバーを追加または削除します。 **Update-RoleGroupMember コマンドレットは、** 既存のメンバー一覧を置き換えまたは変更できます。

- 役割グループのメンバーは、ユーザー、メールが有効なユニバーサル セキュリティ グループ (USG)、またはその他の役割グループ (セキュリティ プリンシパル) の場合があります。

役割グループのメンバーを変更するには、次の構文を使用します。

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- 既存 _のメンバー_ の一覧を指定した値に置き換えるには、次の構文を使用します `"Member1","Member2",..."MemberN"` 。

- メンバー _の既存のリストを_ 選択的に変更するには、次の構文を使用します `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` 。

この例では、"Help Desk/ヘルプ デスク" 役割グループの現在のすべてのメンバーを、指定したユーザーに置き換えました。

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

この例では、Daigoro Akai を追加し、"Help Desk/ヘルプ デスク" 役割グループのメンバー リストから Valeria Barrio を削除します。

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

構文およびパラメーターの詳細については [、Update-RoleGroupMember を参照してください](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)。

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>スタンドアロン EOP PowerShell を使用して役割グループを削除する

組み込みの役割グループを削除することはできませんが、作成したカスタム役割グループを削除できます。

カスタム役割グループを削除するには、次の構文を使用します。

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

この例では、Training Administrators 役割グループを削除します。

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

構文およびパラメーターの詳細については、「[Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup)」を参照してください。

### <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

役割グループが正常にコピーされたことを確認するには、次の手順のいずれかを実行します。

- EAC で、[アクセス許可の管理役割 **]** \> **に移動し**、役割グループが一覧に表示されている (または一覧にない) ことを確認します。 役割グループを選択し、[詳細] ウィンドウで設定を確認するか、[編集] **アイコンをクリック** ![ ](../../media/ITPro-EAC-EditIcon.png) して設定を確認します。

- Exchange Online PowerShell で、役割 \<Role Group Name\> グループの名前に置き換え、次のコマンドを実行して、役割グループが存在するかどうかを確認 (存在しない) ため、設定を確認します。

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
