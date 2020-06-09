---
title: EOP でグループを管理する
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
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Standalone Exchange Online Protection (EOP) 組織内の管理者は、Exchange 管理センター (EAC) とスタンドアロン Exchange Online Protection (EOP) PowerShell で、配布グループとメールが有効なセキュリティグループを作成、変更、および削除する方法を学習できます。
ms.openlocfilehash: 42086b67e22df4725bf07bf227853c070f936f24
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616504"
---
# <a name="manage-groups-in-eop"></a>EOP でグループを管理する

Exchange Online メールボックスを使用しないスタンドアロンの Exchange Online Protection (EOP) 組織では、次の種類のグループを作成、変更、および削除できます。

- **配布グループ**: メールユーザーまたは他の配布グループのコレクション。 たとえば、関係する共通領域で電子メールを送受信する必要がある teams やその他の臨時グループがあります。 配布グループは、電子メールメッセージの配布専用であり、セキュリティプリンシパルではありません (アクセス許可を割り当てることはできません)。

- **メールが有効なセキュリティグループ**: 管理者の役割に対するアクセス許可を必要とする、メールユーザーおよびその他のセキュリティグループのコレクション。 たとえば、特定のユーザーグループに管理者アクセス許可を付与して、スパム対策とマルウェア対策設定を構成できるようにする場合があります。

    > [!NOTE]
    > <ul><li>既定では、新しいメールが有効なセキュリティグループは、外部 (認証されていない) 送信者からのメッセージを拒否します。</li><li>メールが有効なセキュリティグループに配布グループを追加しないでください。</li></ul>.

グループを管理するには、Exchange 管理センター (EAC) とスタンドアロン EOP PowerShell を使用します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- Exchange 管理センターを開くには、「 [exchange admin center in STANDALONE EOP](exchange-admin-center-in-exchange-online-protection-eop.md)」を参照してください。

- スタンドアロンの EOP PowerShell に接続するには、「 [Exchange Online Protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- スタンドアロンの EOP PowerShell でグループを管理する場合、調整が発生する可能性があります。 このトピックの PowerShell の手順では、コマンドの結果が表示されるまでに数分の遅延が発生するバッチ処理方式を使用しています。

- これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 具体的には、既定では、組織の管理 (グローバル管理者) および受信者管理役割グループに割り当てられている配布グループの役割が必要です。 詳細については、「 [Permissions in STANDALONE EOP](feature-permissions-in-eop.md) 」を参照して、EAC を使用して、[役割グループのメンバーの一覧を変更](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)します。

- このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。

> [!TIP]
> 問題がある場合は、 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)フォーラムでヘルプを要求します。

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>Exchange 管理センターを使用して配布グループを管理する

### <a name="use-the-eac-to-create-groups"></a>EAC を使用してグループを作成する

1. EAC で、 **[受信者]** \> **[グループ]** に移動します。

2. [**新しい** ![ 新規作成] アイコンをクリックし、 ](../../media/ITPro-EAC-AddIcon.png) 次のいずれかのオプションを選択します。

   - **配布グループ**

   - **メールが有効なセキュリティ グループ**

3. 開いた [新しいグループ] ページで、次の設定を構成します。 でマークされた設定 <sup>\*</sup> は必須です。

   - <sup>\*</sup>[**表示名**]: この名前は、組織のアドレス帳、このグループに電子メールが送信されるときの宛先行、EAC の [**グループ**] リストに表示されます。 表示名は必須であり、一意である必要があります。わかりやすい名前にする必要があります。ユーザーがわかるようにします。

   - <sup>\*</sup>**エイリアス**: このボックスを使用して、グループのエイリアス名を入力します。 エイリアスは64文字を超えることはできず、一意である必要があります。 ユーザーが電子メールメッセージの [宛先] 行にエイリアスを入力すると、グループの表示名に解決されます。

   - <sup>\*</sup>**メールアドレス**: メールアドレスは、アットマーク記号 (@) の左側にあるエイリアスと、右側のドメインで構成されます。 既定では、エイリアスの値がエイリアスの値に使用**されます**が、これは変更できます。 [ドメイン] の値に対して、ドロップダウンをクリックして、組織内のドメインを選択して承認します。

   - **説明**: この説明は、アドレス帳と EAC の詳細ウィンドウに表示されます。

   - <sup>\*</sup>**所有者**: グループの所有者は、グループのメンバーシップを管理できます。 既定では、グループを作成するユーザーがグループの所有者になります。 グループには、最低 1 人の所有者が必要です。

     所有者を追加するには **、[追加** ![ ] アイコンをクリックし ](../../media/ITPro-EAC-AddIcon.png) ます。 表示されるダイアログで、受信者またはグループを見つけて選択し、[ **>**] をクリックします。 必要な回数だけこの手順を繰り返します。 完了したら、 **[OK]** をクリックします。

     所有者を削除するには、所有者を選択し、[削除] [削除] アイコン**をクリックし** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) ます。

   - **Members**: グループメンバーを追加および削除します。

     メンバーを追加するには **、[追加** ![ ] アイコンをクリックし ](../../media/ITPro-EAC-AddIcon.png) ます。 表示されるダイアログで、受信者またはグループを見つけて選択し、[ **>**] をクリックします。 必要な回数だけこの手順を繰り返します。 完了したら、 **[OK]** をクリックします。

     メンバーを削除するには、メンバーを選択し、[削除] [削除] アイコン**をクリックし** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) ます。

4. 完了したら、[**保存**] をクリックして配布グループを作成します。

### <a name="use-the-eac-to-modify-distribution-groups"></a>EAC を使用して配布グループを変更する

1. EAC で、 **[受信者]** \> **[グループ]** に移動します。

2. グループの一覧で、変更する配布グループまたはメールが有効なセキュリティグループを選択し、[編集] 編集アイコン**をクリックし** ![ ](../../media/ITPro-EAC-AddIcon.png) ます。

3. 開いた配布グループのプロパティページで、次のタブのいずれかをクリックして、プロパティを表示または変更します。

   完了したら、**[保存]** をクリックします。

#### <a name="general"></a>全般

このタブを使用して、グループに関する基本情報を表示または変更します。

- [**表示名**]: この名前はアドレス帳、このグループに電子メールを送信するときの [宛先] 行、および [**グループ] リスト**に表示されます。 表示名は必須であり、ユーザーが内容を認識できるようにわかりやすい名前にする必要があります。 また、表示名は、ドメイン内で一意である必要があります。

  グループの名前付けポリシーを実装している場合、表示名は、ポリシーで定義されている名前付け形式に従う必要があります。

- **エイリアス**: これは、電子メールアドレスの @ 記号の左に表示される部分です。 エイリアスを変更すると、グループのプライマリ SMTP アドレスも変更され、新しいエイリアスが含まれます。 また、以前のエイリアスが含まれている電子メール アドレスは、グループのプロキシ アドレスとして保持されます。

- **メールアドレス**: メールアドレスは、アットマーク記号 (@) の左側にあるエイリアスと、右側のドメインで構成されます。 既定では、エイリアスの値がエイリアスの値に使用**されます**が、これは変更できます。 [ドメイン] の値に対して、ドロップダウンをクリックして、組織内のドメインを選択して承認します。

- **説明**: この説明は、アドレス帳と EAC の詳細ウィンドウに表示されます。

#### <a name="ownership"></a>Ownership

このタブを使用して、グループの所有者を割り当てます。 グループの所有者は、グループのメンバーシップを管理できます。 既定では、グループを作成するユーザーがグループの所有者になります。 グループには、最低 1 人の所有者が必要です。

所有者を追加するには **、[追加** ![ ] アイコンをクリックし ](../../media/ITPro-EAC-AddIcon.png) ます。 表示されるダイアログで、受信者を検索して選択し、[追加] をクリックし **>** します。 必要な回数だけこの手順を繰り返します。 完了したら、 **[OK]** をクリックします。

所有者を削除するには、所有者を選択し、[削除] [削除] アイコン**をクリックし** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) ます。

#### <a name="membership"></a>メンバーシップ

グループ メンバーを追加または削除するには、このタブを使用します。 グループの所有者は、グループのメンバーである必要はありません。

メンバーを追加するには **、[追加** ![ ] アイコンをクリックし ](../../media/ITPro-EAC-AddIcon.png) ます。 表示されるダイアログで、受信者またはグループを見つけて選択し、[ **>**] をクリックします。 必要な回数だけこの手順を繰り返します。 完了したら、 **[OK]** をクリックします。

メンバーを削除するには、メンバーを選択し、[削除] [削除] アイコン**をクリックし** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) ます。

### <a name="use-the-eac-to-remove-groups"></a>EAC を使用してグループを削除する

1. EAC で、 **[受信者]** \> **[グループ]** に移動します。

2. グループの一覧で、削除する配布グループを選択し、[削除] [削除] アイコン**をクリックし** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) ます。

## <a name="use-powershell-to-manage-groups"></a>PowerShell を使用してグループを管理する

### <a name="use-standalone-eop-powershell-to-view-groups"></a>スタンドアロンの EOP PowerShell を使用してグループを表示する

スタンドアロン EOP PowerShell のすべての配布グループとメールが有効なセキュリティグループの要約リストを返すには、次のコマンドを実行します。

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

グループメンバーの一覧を取得するには、を \<GroupIdentity\> グループの名前、エイリアス、または電子メールアドレスに置き換えて、次のコマンドを実行します。

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

構文およびパラメーターの詳細については、「 [get-distributiongroupmember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember) [」を参照して](https://docs.microsoft.com/powershell/module/exchange/get-recipient)ください。

### <a name="use-standalone-eop-powershell-to-create-groups"></a>スタンドアロンの EOP PowerShell を使用してグループを作成する

スタンドアロン EOP PowerShell で配布グループまたはメールが有効なセキュリティグループを作成するには、次の構文を使用します。

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**注**:

- _Name_パラメーターは必須で、最大長は64文字で、一意である必要があります。 _DisplayName_パラメーターを使用しない場合、 _name_パラメーターの値が表示名として使用されます。

- _Alias_パラメーターを使用しない場合、 _Name_パラメーターはエイリアスの値として使用されます。 スペースは削除されます。サポートされていない文字は疑問符 (?) に変換されます。

- _Primarysmtpaddress_パラメーターを使用しない場合、エイリアスの値は_primarysmtpaddress_パラメーターで使用されます。

- _Type_パラメーターを使用しない場合、既定値は Distribution になります。

この例では、指定されたプロパティを使用して、IT 管理者という名前の配布グループを作成します。

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

構文およびパラメーターの詳細については、「 [New-Eop/グループ](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)」を参照してください。

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>スタンドアロンの EOP PowerShell を使用してグループを変更する

スタンドアロン EOP PowerShell でグループを変更するには、次の構文を使用します。

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

この例では、シアトルの従業員グループのプライマリ SMTP アドレス (返信アドレスとも呼ばれます) を sea.employees@contoso.com に変更します。

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

この例では、セキュリティチームグループの現在のメンバーを、キティー Petersen Tyson Fawcett と置き換えます。

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

この例では、グループの現在のメンバーを保持しながら、Tyson Fawcett という名前の新しいユーザーをセキュリティチームという名前のグループに追加します。

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

構文およびパラメーターの詳細については、「 [update-eopdistributiongroupmember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)」[を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup)。

### <a name="remove-a-group-using-remote-windows-powershell"></a>リモートの Windows PowerShell を使用してグループを削除する

この例では、IT 管理者という名前の配布グループを削除します。

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

構文およびパラメーターの詳細については、「[削除-Eop/グループ](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)」を参照してください。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

配布グループまたはメールが有効なセキュリティグループの作成、変更、または削除が正常に行われたことを確認するには、次のいずれかの手順を実行します。

- EAC で、 **[受信者]** \> **[グループ]** に移動します。 グループが表示されている (またはリストされていない) ことを確認し、**グループの種類**の値を確認します。 グループを選択して、詳細ウィンドウに情報を表示するか、[編集アイコンの**編集**] をクリックして ![ 設定を表示し ](../../media/ITPro-EAC-AddIcon.png) ます。

- スタンドアロン EOP PowerShell で次のコマンドを実行して、グループが一覧に表示されている (または一覧に表示されていない) ことを確認します。

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- を \<GroupIdentity\> グループの名前、エイリアス、または電子メールアドレスに置き換え、次のコマンドを実行して設定を確認します。

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- グループメンバーを表示するには、を \<GroupIdentity\> グループの名前、エイリアス、または電子メールアドレスに置き換えて、次のコマンドを実行します。

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
