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
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206275"
---
# <a name="manage-role-groups-in-standalone-eop"></a>スタンドアロン EOP で役割グループを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
-  [Exchange Online Protection スタンドアロン](exchange-online-protection-overview.md)

Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織では、Exchange 管理センター (EAC) を使用してユーザーを役割グループに追加できます。 役割グループにユーザーを追加すると、特定の管理タスクを実行するためのアクセス許可がユーザーに付与されます。 役割グループからユーザーを削除することもできます。

役割と役割グループの詳細については、「スタンドアロン [EOP のアクセス許可」を参照してください](feature-permissions-in-eop.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- Exchange 管理センター (EAC) を開く場合は、「 [スタンドアロン EOP の Exchange 管理センター」を参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。

- スタンドアロン EOP PowerShell を開く方法については [、「Connect to Exchange Online Protection PowerShell」を参照してください](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- この記事の手順を実行するには、Exchange Online Protection でアクセス許可を割り当てる必要があります。 具体的には、既定で組織 **の管理** 役割グループに割り当てられている役割 **の管理** 役割が必要です。 詳細については、「スタンドアロン [EOP のアクセス](feature-permissions-in-eop.md) 許可」および「役割グループのメンバーの一覧を [変更する EAC](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)を使用する」を参照してください。

- この記事の手順に適用されるキーボード ショートカットの詳細については、「Exchange Online の Exchange 管理センターのキーボード ショートカット」 [を参照してください](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 問題が発生する場合 [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) フォーラムでサポートをご依頼ください。

## <a name="use-the-eac-to-manage-role-groups"></a>EAC を使用して役割グループを管理する

### <a name="use-the-eac-to-view-role-groups"></a>EAC を使用して役割グループを表示する

1. EAC で、[アクセス許可] **[管理者の役割]** \> **に移動します**。 組織の役割グループのすべてが一覧表示されます。

2. 役割グループを選択します。 [詳細] ウィンドウには、 **役割** グループの [名前] **、[説明**] **、[** 割り当てられた役割]、および **[管理]** が表示されます。 [編集] アイコンをクリックすると、この **情報を** ![ 確認することもできます ](../../media/ITPro-EAC-EditIcon.png) 。

### <a name="use-the-eac-to-create-role-groups"></a>EAC を使用して役割グループを作成する

新しい役割グループを作成する場合は、(グループの作成中または後に) すべての設定を自分で構成できます。 または、既存の役割グループをコピーして変更できます。

1. EAC で、[アクセス許可の **管理]** の役割に移動し、 \> 次のいずれかの手順を実行します。

   - **新しい役割グループを手動で作成する**: [追加 **] アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。

   - **既存の役割グループをコピー** する: コピーする役割グループを選択し、[コピー] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-CopyIcon.png) 。

2. 表示される **[新しい役割グループ]** ウィンドウで、次の設定を構成します。

    - **名前**: 役割グループの一意の名前を入力します。

    - **説明**: 役割グループのオプションの説明を入力します。

    - **役割**: [追加 **] アイコン** または [削除] アイコンをクリックして、役割グループに割り当てられている役割 ![ ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) を選択または変更します。

    - **メンバー**: [追加 **] アイコン** または [削除] アイコンをクリック ![ ](../../media/ITPro-EAC-AddIcon.png)  ![ して ](../../media/ITPro-EAC-RemoveIcon.gif) 、役割グループのメンバーシップを変更します。

3. 完了したら、[保存] をクリック **して** 役割グループを作成します。

### <a name="use-the-eac-to-modify-role-groups"></a>EAC を使用して役割グループを変更する

EAC で、[アクセス許可の管理者の役割] に移動し、変更する役割グループを選択し、[編集] アイコン \> **を** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。

役割グループを作成する場合と同じオプションは、役割グループを変更するときに使用できます。 以下のことを実行できます。

- 名前と説明を変更します。

- 管理役割を追加および削除します (役割の割り当てを作成または削除します)。

- メンバーを追加および削除します。

**注**: 一部の役割グループ (組織の管理など) では、グループから削除できる役割が制限されています。

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>役割グループ内のメンバーの一覧を変更する EAC を使用する

1. EAC で、[アクセス許可の管理者の役割] に移動し、変更する役割グループを選択し、[編集] アイコン \> **を** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。

2. 開く役割グループのプロパティ ページの [メンバー] **セクションで、** 次のいずれかの手順を実行します。

   - [追加 **] アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。 表示されるページで、追加するユーザーを見つけて、[追加] をクリックして **[->] をクリックします**。 ユーザーを選択し、 **必要に応じて [->** 追加] をクリックします。 完了したら、 **[OK]** をクリックします。

   - 削除するユーザーを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。

3. 完了したら、**[保存]** をクリックします。

   > [!NOTE]
   > 役割グループに対してメンバーを追加または削除した後、ユーザーは自身の管理者権限の変更を確認するためにサインアウトしてから、再度サインインしなければならない場合があります。

### <a name="use-the-eac-to-remove-role-groups"></a>EAC を使用して役割グループを削除する

組み込みの役割グループは削除できませんが、作成したカスタム役割グループは削除できます。

1. EAC で、[アクセス許可] **[管理者の役割]** \> **に移動します**。

2. 削除する役割グループを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-DeleteIcon.png) 。

3. 表示 **される確認** ウィンドウで [はい] をクリックします。

## <a name="use-powershell-to-manage-role-groups"></a>PowerShell を使用して役割グループを管理する

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>スタンドアロン EOP PowerShell を使用して役割グループを表示する

役割グループを表示するには、次の構文を使用します。

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

次の使用例は、すべての役割グループの概要リストを返します。

```PowerShell
Get-RoleGroup
```

次の使用例は、Recipient Administrators という名前の役割グループの詳細情報を返します。

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

この例では、ユーザー Julia がメンバーであるすべての役割グループを返します。 Julia の識別名 (DN) 値を使用する必要があります。これは、次のコマンドを実行して見つける必要があります `Get-User -Identity Julia | Format-List DistinguishedName` 。

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

構文およびパラメーターの詳細については、「[Get-RoleGroup](/powershell/module/exchange/Get-RoleGroup)」を参照してください。

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>スタンドアロン EOP PowerShell を使用して役割グループを作成する

新しい役割グループを作成する場合は、(グループの作成中または後に) すべての設定を手動で構成できます。 または、既存の役割グループをコピーして変更できます。

- 新しい役割グループを手動で作成するには、次の構文を使用します。

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - _Roles パラメーターは_、次の構文を使用して役割グループに割り当てる管理役割を指定します `"Role1","Role1",..."RoleN"` 。 **Get-ManagementRole** コマンドレットを使用して、使用できる役割を確認できます。

  - _Members パラメーター_ は、次の構文を使用して役割グループのメンバーを指定します `"Member1","Member2",..."MemberN"` 。 ユーザー、メールが有効なユニバーサル セキュリティ グループ (USG)、またはその他の役割グループ (セキュリティ プリンシパル) を指定できます。

  この例では、次の設定を使用して、"制限付き受信者管理" という名前の新しい役割グループを作成します。

  - [メール受信者] 役割は、役割グループに割り当てられます。

  - Kim と Martin のユーザーはメンバーとして追加されます。

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

     _Members パラメーター_ は、次の構文を使用して役割グループのメンバーを指定します `"Member1","Member2",..."MemberN"` 。 ユーザー、メールが有効なユニバーサル セキュリティ グループ (USG)、またはその他の役割グループ (セキュリティ プリンシパル) を指定できます。

     次の使用例は、組織の管理役割グループを "Limited Organization Management" という名前の新しい役割グループにコピーします。 役割グループのメンバーは、イザベル、カーター、および Lukas です。

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

構文とパラメーターの詳細については [、New-RoleGroup を参照してください](/powershell/module/exchange/New-RoleGroup)。

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>スタンドアロンの EOP PowerShell を使用して、役割グループ内のメンバーの一覧を変更する

- **Add-RoleGroupMember** コマンドレットと **Remove-RoleGroupMember** コマンドレットは、個々のメンバーを一度に 1 つ追加または削除します。 **Update-RoleGroupMember** コマンドレットは、メンバーの既存のリストを置き換えるまたは変更できます。

- 役割グループのメンバーには、ユーザー、メールが有効なユニバーサル セキュリティ グループ (USG)、または他の役割グループ (セキュリティ プリンシパル) を指定できます。

役割グループのメンバーを変更するには、次の構文を使用します。

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- メンバー _の_ 既存のリストを指定した値に置き換える場合は、次の構文を使用します `"Member1","Member2",..."MemberN"` 。

- メンバー _の既存のリスト_ を選択的に変更するには、次の構文を使用します `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` 。

この例では、ヘルプ デスク役割グループのすべての現在のメンバーを指定したユーザーに置き換えています。

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

この例では、Daigoro Akai を追加し、ヘルプ デスク役割グループのメンバーの一覧から Valeria Barrio を削除します。

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

構文とパラメーターの詳細については [、「Update-RoleGroupMember」を参照してください](/powershell/module/exchange/Update-RoleGroupMember)。

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>スタンドアロン EOP PowerShell を使用して役割グループを削除する

組み込みの役割グループは削除できませんが、作成したカスタム役割グループは削除できます。

カスタム役割グループを削除するには、次の構文を使用します。

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

この例では、Training Administrators 役割グループを削除します。

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

構文およびパラメーターの詳細については、「[Remove-RoleGroup](/powershell/module/exchange/Remove-RoleGroup)」を参照してください。

### <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

役割グループが正常にコピーされたことを確認するには、次のいずれかの手順を実行します。

- EAC で、[アクセス許可の管理者 **の** 役割] に移動し、役割グループが一覧表示 (または一覧に表示されていない \> ) を確認します。 役割グループを選択し、[詳細] ウィンドウで設定を確認するか、[編集] アイコンをクリックして設定 ![ ](../../media/ITPro-EAC-EditIcon.png) を確認します。

- Exchange Online PowerShell で、役割グループの名前に置き換え、次のコマンドを実行して役割グループが存在する (または存在しない) か確認し、設定 \<Role Group Name\> を確認します。

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```