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
description: 管理者は、exchange Online Protection の Exchange 管理センター (EAC) でアクセス許可を割り当てる、または削除する方法を学習できます。
ms.openlocfilehash: fb1e0979b77c38d852f35817e01135af888eac68
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201903"
---
# <a name="manage-role-groups-in-standalone-eop"></a>スタンドアロン EOP で役割グループを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online メールボックスを持たないスタンドアロンの Exchange Online Protection (EOP) 組織では、Exchange 管理センター (EAC) を使用してユーザーを役割グループに追加できます。 ユーザーを役割グループに追加すると、特定の管理タスクを実行するためのアクセス許可が付与されます。 役割グループからユーザーを削除することもできます。

役割と役割グループの詳細については、「 [Permissions in STANDALONE EOP](feature-permissions-in-eop.md)」を参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- Exchange 管理センター (EAC) を開くには、「 [exchange admin center in STANDALONE EOP](exchange-admin-center-in-exchange-online-protection-eop.md)」を参照してください。

- スタンドアロン EOP PowerShell を開くには、「 [Exchange Online Protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 具体的には、役割管理役割が必要です。これは、既定では、組織の管理 (グローバル管理者) 役割グループに割り当てられています。 詳細については、「 [Permissions in STANDALONE EOP](feature-permissions-in-eop.md) 」を参照して、EAC を使用して、 [役割グループのメンバーの一覧を変更](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)します。

- このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。

> [!TIP]
> 問題が発生する場合 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) フォーラムでサポートをご依頼ください。

## <a name="use-the-eac-to-manage-role-groups"></a>EAC を使用して役割グループを管理する

### <a name="use-the-eac-to-view-role-groups"></a>EAC を使用して役割グループを表示する

1. EAC で、[ **アクセス許可** \> **管理者の役割**] に移動します。 組織の役割グループのすべてが一覧表示されます。

2. 役割グループを選択します。 詳細ウィンドウには、役割グループの **名前**、 **説明**、 **割り当てられた役割**、および **管理者** が表示されます。 この情報は **、[編集**] 編集アイコンをクリックして確認することもでき ![ ](../../media/ITPro-EAC-EditIcon.png) ます。

### <a name="use-the-eac-to-create-role-groups"></a>EAC を使用して役割グループを作成する

新しい役割グループを作成する場合、すべての設定を (グループの作成時または実行後に) 自分で構成できます。 または、既存の役割グループをコピーして変更することもできます。

1. EAC で、[ **アクセス許可** \> **管理者の役割**] に移動し、次のいずれかの手順を実行します。

   - **新しい役割グループを手動で作成**します **。 [追加** ![ ] アイコンをクリックし ](../../media/ITPro-EAC-AddIcon.png) ます。

   - **既存の役割グループをコピー**する: コピーする役割グループを選択し、[コピー **のコピー** ![ ] アイコンをクリックし ](../../media/ITPro-EAC-CopyIcon.png) ます。

2. 表示される [ **役割グループの新規作成** ] ウィンドウで、次の設定を構成します。

    - [**名前**]: 役割グループの一意の名前を入力します。

    - [**説明**]: 役割グループの説明 (オプション) を入力します。

    - **役割**: **Add** ![ ](../../media/ITPro-EAC-AddIcon.png) **Remove** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 役割グループに割り当てられている役割を選択または変更するには、[追加] アイコンまたは [削除ITPro-EAC-RemoveIcon.gifをクリックします。

    - **メンバー**: **Add** ![ ](../../media/ITPro-EAC-AddIcon.png) **Remove** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 役割グループのメンバーシップを変更するには、[追加] アイコンをクリックするかITPro-EAC-RemoveIcon.gifを削除します。

3. 完了したら、[ **保存** ] をクリックして役割グループを作成します。

### <a name="use-the-eac-to-modify-role-groups"></a>EAC を使用して役割グループを変更する

EAC で、[**アクセス許可** \> **管理者の役割**] に移動し、変更する役割グループを選択し**Edit**てから、[編集 ![ ] 編集アイコンをクリックし ](../../media/ITPro-EAC-EditIcon.png) ます。

役割グループの作成時に役割グループを変更する場合も、同じオプションを使用できます。 以下のことを実行できます。

- 名前と説明を変更します。

- 管理役割を追加および削除する (役割の割り当てを作成または削除する)。

- メンバーを追加および削除します。

**注**: 一部の役割グループ (たとえば、組織管理) は、グループから削除できる役割を制限します。

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>EAC を使用して役割グループのメンバーの一覧を変更する

1. EAC で、[**アクセス許可** \> **管理者の役割**] に移動し、変更する役割グループを選択して**Edit**から、[編集 ![ ] 編集アイコンをクリックし ](../../media/ITPro-EAC-EditIcon.png) ます。

2. 開いている役割グループのプロパティページの [ **メンバー** ] セクションで、次のいずれかの手順を実行します。

   - [ **追加** ![ ] アイコン ](../../media/ITPro-EAC-AddIcon.png) をクリックします。 表示されるページで、wou を追加するユーザーを見つけ、[ **追加->**] をクリックします。 [ユーザー] を選択し、必要に応じて [ **>** ] を繰り返しクリックします。 完了したら、 **[OK]** をクリックします。

   - 削除するユーザーを選択し、[削除] [削除] アイコン **をクリックし** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) ます。

3. 完了したら、**[保存]** をクリックします。

   > [!NOTE]
   > 役割グループに対してメンバーを追加または削除した後、ユーザーは自身の管理者権限の変更を確認するためにサインアウトしてから、再度サインインしなければならない場合があります。

### <a name="use-the-eac-to-remove-role-groups"></a>EAC を使用して役割グループを削除する

組み込みの役割グループを削除することはできませんが、作成したカスタム役割グループを削除することはできます。

1. EAC で、[ **アクセス許可** \> **管理者の役割**] に移動します。

2. 削除する役割グループを選択し、[削除] **[削除] アイコンをクリックし** ![ ](../../media/ITPro-EAC-DeleteIcon.png) ます。

3. 確認ウィンドウが表示されたら、[ **はい** ] をクリックします。

## <a name="use-powershell-to-manage-role-groups"></a>PowerShell を使用して役割グループを管理する

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>スタンドアロンの EOP PowerShell を使用して役割グループを表示する

役割グループを表示するには、次の構文を使用します。

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

この例では、すべての役割グループの要約リストを返します。

```PowerShell
Get-RoleGroup
```

この例では、"受信者管理者" という名前の役割グループの詳細情報を返します。

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

この例では、ユーザージュリアがメンバーであるすべての役割グループを返します。 次のコマンドを実行すると、ジュリアの DistinguishedName (DN) 値を使用する必要があります `Get-User -Identity Julia | Format-List DistinguishedName` 。

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

構文およびパラメーターの詳細については、「[Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)」を参照してください。

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>スタンドアロンの EOP PowerShell を使用して役割グループを作成する

新しい役割グループを作成する場合、すべての設定を手動で構成できます (グループの作成時または実行後)。 または、既存の役割グループをコピーして変更することもできます。

- 新しい役割グループを手動で作成するには、次の構文を使用します。

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - _Roles_パラメーターは、次の構文を使用して、役割グループに割り当てる管理役割を指定し `"Role1","Role1",..."RoleN"` ます。 **Get-ManagementRole** コマンドレットを使用して、使用できる役割を確認できます。

  - _Members_パラメーターは、次の構文を使用して、役割グループのメンバーを指定し `"Member1","Member2",..."MemberN"` ます。 ユーザー、メールが有効なユニバーサル セキュリティ グループ (USG)、またはその他の役割グループ (セキュリティ プリンシパル) を指定できます。

  この例では、次の設定を使用して "制限付き受信者管理" という名前の新しい役割グループを作成します。

  - "Mail Recipients/メール受信者" 役割は、役割グループに割り当てられます。

  - Kim と Martin のユーザーは、メンバーとして追加されます。

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- 既存の役割グループをコピーするには、次の手順を実行します。

  1. 以下の構文を使用して、変数にコピーする役割グループを格納します。

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. 次の構文を使用して、新しい役割グループを作成します。

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     _Members_パラメーターは、次の構文を使用して、役割グループのメンバーを指定し `"Member1","Member2",..."MemberN"` ます。 ユーザー、メールが有効なユニバーサル セキュリティ グループ (USG)、またはその他の役割グループ (セキュリティ プリンシパル) を指定できます。

     この例では、組織の管理役割グループを "制限された組織の管理" という名前の新しい役割グループにコピーします。 役割グループのメンバーは、Isabelle、Carter、Lukas です。

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

構文およびパラメーターの詳細については、「 [新しい-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)」を参照してください。

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>スタンドアロンの EOP PowerShell を使用する役割グループのメンバーの一覧を変更する

- **Add-rolegroupmember**および**add-rolegroupmember**コマンドレットは、個々のメンバーを一度に1つずつ追加または削除します。 **Add-rolegroupmember**コマンドレットでは、既存のメンバーの一覧を置き換えたり変更したりできます。

- 役割グループのメンバーは、ユーザー、メールが有効なユニバーサルセキュリティグループ (Usg)、またはその他の役割グループ (セキュリティプリンシパル) にすることができます。

役割グループのメンバーを変更するには、次の構文を使用します。

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- 既存のメンバーリストを指定した値に _置き換える_ には、次の構文を使用し `"Member1","Member2",..."MemberN"` ます。

- 既存のメンバーリストを _選択的に変更_ するには、次の構文を使用し `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` ます。

この例では、ヘルプデスク役割グループの現在のすべてのメンバーを指定されたユーザーに置き換えます。

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

この例では、Daigoro Akai を追加し、ヘルプデスク役割グループのメンバーの一覧から Valeria Barrio を削除します。

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

構文およびパラメーターの詳細については、「 [add-rolegroupmember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)」を参照してください。

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>スタンドアロンの EOP PowerShell を使用して役割グループを削除する

組み込みの役割グループを削除することはできませんが、作成したカスタム役割グループを削除することはできます。

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

役割グループが正常にコピーされたことを確認するには、次のいずれかの手順を実行します。

- EAC で、[ **アクセス許可** \> **管理者の役割**] に移動し、役割グループが表示されている (または一覧に表示されていない) ことを確認します。 役割グループを選択して、詳細ウィンドウで設定を確認するか **、[編集** ![ ] 編集アイコンをクリックし ](../../media/ITPro-EAC-EditIcon.png) て設定を確認します。

- Exchange Online PowerShell で、を \<Role Group Name\> 役割グループの名前に置き換え、次のコマンドを実行して役割グループが存在する (または存在しない) ことを確認し、設定を確認します。

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
