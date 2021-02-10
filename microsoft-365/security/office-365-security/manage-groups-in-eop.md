---
title: EOP でグループを管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: スタンドアロンの Exchange Online Protection (EOP) 組織の管理者は、Exchange 管理センター (EAC) とスタンドアロンの Exchange Online Protection (EOP) PowerShell で配布グループとメールが有効なセキュリティ グループを作成、変更、削除する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01fe5c6ab1555749d38f9c092b05aca9befb67fe
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166965"
---
# <a name="manage-groups-in-eop"></a>EOP でグループを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
-  [Exchange Online Protection スタンドアロン](https://go.microsoft.com/fwlink/?linkid=2148611)

Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織では、次の種類のグループを作成、変更、および削除できます。

- **配布グループ**: メール ユーザーまたは他の配布グループのコレクション。 たとえば、関心のある共通領域でメールを受信または送信する必要があるチームや他の臨時グループなどです。 配布グループは電子メール メッセージの配布専用であり、セキュリティ プリンシパルではありません (アクセス許可を割り当てすることはできません)。

- **メールが有効なセキュリティ グループ**: 管理者ロールのアクセス許可を必要とするメール ユーザーおよび他のセキュリティ グループのコレクションです。 たとえば、特定のユーザー グループに管理者アクセス許可を付与して、スパム対策とマルウェア対策の設定を構成できます。

    > [!NOTE]
    >
    > - 既定では、新しいメールが有効なセキュリティ グループは、外部 (認証されていない) 送信者からのメッセージを拒否します。
    >
    > - メールが有効なセキュリティ グループには配布グループを追加しません。

グループは、Exchange 管理センター (EAC) とスタンドアロンの EOP PowerShell で管理できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- Exchange 管理センターを開く方法については、 [スタンドアロン EOP の Exchange 管理センターを参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。

- スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- スタンドアロンの EOP PowerShell でグループを管理すると、調整が発生する可能性があります。 この記事の PowerShell の手順では、コマンドの結果が表示される数分前に伝達遅延が発生するバッチ処理方法を使用します。

- この記事の手順を実行する前に、Exchange Online Protection でアクセス許可を割り当てる必要があります。 具体的には、"Organization **Management/** 組織の管理" 役割グループと **"Recipient Management/** 受信者の管理" 役割グループに既定で割り当てられる **"Distribution Groups/** 配布グループ" 役割が必要です。 詳細については、「スタンドアロン [EOP のアクセス許可](feature-permissions-in-eop.md) 」および「EAC を使用して役割グループのメンバーの一覧 [を変更する」を参照してください](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- この記事の手順に適用できるキーボード ショートカットの詳細については [、Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)の Exchange 管理センターのキーボード ショートカットを参照してください。

> [!TIP]
> 問題が発生する場合 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) フォーラムでサポートをご依頼ください。

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>Exchange 管理センターを使用して配布グループを管理する

### <a name="use-the-eac-to-create-groups"></a>EAC を使用してグループを作成する

1. EAC で、 **[受信者]** \> **[グループ]** に移動します。

2. [ **新しい新規** ![ ] ](../../media/ITPro-EAC-AddIcon.png) アイコンをクリックし、次のいずれかのオプションを選択します。

   - **配布グループ**

   - **メールが有効なセキュリティ グループ**

3. 開く新しいグループ ページで、次の設定を構成します。 an が付いている設定 <sup>\*</sup> は必須です。

   - <sup>\*</sup>**表示名**: この名前は、組織のアドレス帳、このグループに電子メールが送信される際の [To:] 行、および EAC の **[グループ** ] リストに表示されます。 表示名は必須であり、一意である必要があります。また、ユーザーが何を認識しているかはユーザーに分かっている必要があります。

   - <sup>\*</sup>**[エイリアス**]: このボックスを使用して、グループのエイリアスの名前を入力します。 エイリアスは 64 文字以内で、一意である必要があります。 ユーザーが電子メール メッセージの [To] 行にエイリアスを入力すると、グループの表示名に解決されます。

   - <sup>\*</sup>**電子メール** アドレス : 電子メール アドレスは、at (@) 記号の左側のエイリアスと右側のドメインで構成されます。 既定では、エイリアス **の値は** エイリアス値に使用されますが、変更できます。 ドメイン値の場合は、ドロップダウンをクリックし、組織内のドメインを選択して承認します。

   - **説明**: この説明は、アドレス帳と EAC の [詳細] ウィンドウに表示されます。

   - <sup>\*</sup>**所有者**: グループ所有者はグループ メンバーシップを管理できます。 既定では、グループを作成するユーザーがグループの所有者になります。 グループには、最低 1 人の所有者が必要です。

     所有者を追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。 表示されるダイアログで、受信者またはグループを検索して選択し、[追加] **->。** 必要な回数だけこの手順を繰り返します。 完了したら、 **[OK]** をクリックします。

     所有者を削除するには、所有者を選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。

   - **メンバー**: グループ メンバーを追加および削除します。

     メンバーを追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。 表示されるダイアログで、受信者またはグループを検索して選択し、[追加] **->。** 必要な回数だけこの手順を繰り返します。 完了したら、 **[OK]** をクリックします。

     メンバーを削除するには、メンバーを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。

4. 完了したら、[保存] をクリック **して** 配布グループを作成します。

### <a name="use-the-eac-to-modify-distribution-groups"></a>EAC を使用して配布グループを変更する

1. EAC で、 **[受信者]** \> **[グループ]** に移動します。

2. グループの一覧で、変更する配布グループまたはメールが有効なセキュリティ グループを選択し、[編集] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。

3. 表示された配布グループのプロパティ ページで、次のいずれかのタブをクリックしてプロパティを表示または変更します。

   完了したら、**[保存]** をクリックします。

#### <a name="general"></a>全般

このタブを使用して、グループに関する基本情報を表示または変更します。

- **表示名**: この名前は、アドレス帳、このグループにメールが送信される際の [To] 行、および [グループ] リストに **表示されます**。 表示名は必須であり、ユーザーが内容を認識できるようにわかりやすい名前にする必要があります。 また、表示名は、ドメイン内で一意である必要があります。

  グループの名前付けポリシーを実装している場合、表示名は、ポリシーで定義されている名前付け形式に従う必要があります。

- **エイリアス**: 電子メール アドレスの @ 記号の左側に表示される部分です。 エイリアスを変更すると、グループのプライマリ SMTP アドレスも変更され、新しいエイリアスが含まれます。 また、以前のエイリアスが含まれている電子メール アドレスは、グループのプロキシ アドレスとして保持されます。

- **電子メール** アドレス : 電子メール アドレスは、at (@) 記号の左側のエイリアスと右側のドメインで構成されます。 既定では、エイリアス **の値は** エイリアス値に使用されますが、変更できます。 ドメイン値の場合は、ドロップダウンをクリックし、組織内のドメインを選択して承認します。

- **説明**: この説明は、アドレス帳と EAC の [詳細] ウィンドウに表示されます。

#### <a name="ownership"></a>Ownership

グループの所有者を割り当てるには、このタブを使用します。 グループ所有者はグループ メンバーシップを管理できます。 既定では、グループを作成するユーザーがグループの所有者になります。 グループには、最低 1 人の所有者が必要です。

所有者を追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。 表示されるダイアログで、受信者を見つけて選択し、[追加] **->。** 必要な回数だけこの手順を繰り返します。 完了したら、 **[OK]** をクリックします。

所有者を削除するには、所有者を選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。

#### <a name="membership"></a>メンバーシップ

グループ メンバーを追加または削除するには、このタブを使用します。 グループの所有者は、グループのメンバーである必要があります。

メンバーを追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。 表示されるダイアログで、受信者またはグループを検索して選択し、[追加] **->。** 必要な回数だけこの手順を繰り返します。 完了したら、 **[OK]** をクリックします。

メンバーを削除するには、メンバーを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。

### <a name="use-the-eac-to-remove-groups"></a>EAC を使用してグループを削除する

1. EAC で、 **[受信者]** \> **[グループ]** に移動します。

2. グループの一覧で、削除する配布グループを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。

## <a name="use-powershell-to-manage-groups"></a>PowerShell を使用してグループを管理する

### <a name="use-standalone-eop-powershell-to-view-groups"></a>スタンドアロンの EOP PowerShell を使用してグループを表示する

スタンドアロンの EOP PowerShell ですべての配布グループとメールが有効なセキュリティ グループの要約リストを返す場合は、次のコマンドを実行します。

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

グループ メンバーの一覧を返す場合は、グループの名前、エイリアス、または電子メール アドレスに置き換え、次の \<GroupIdentity\> コマンドを実行します。

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

構文およびパラメーターの詳細については [、「Get-Recipient」](https://docs.microsoft.com/powershell/module/exchange/get-recipient) および [「Get-DistributionGroupMember」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember)。

### <a name="use-standalone-eop-powershell-to-create-groups"></a>スタンドアロンの EOP PowerShell を使用してグループを作成する

スタンドアロンの EOP PowerShell で配布グループまたはメールが有効なセキュリティ グループを作成するには、次の構文を使用します。

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**注**:

- _Name パラメーター_ は必須で、最大長は 64 文字で、一意である必要があります。 _DisplayName_ パラメーターを使用しない場合 _、Name_ パラメーターの値が表示名に使用されます。

- Alias パラメーターを使用しない場合は、 _エイリアス_ 値に _Name_ パラメーターが使用されます。 スペースは削除されます。サポートされていない文字は疑問符 (?) に変換されます。

- _PrimarySmtpAddress_ パラメーターを使用しない場合は _、PrimarySmtpAddress_ パラメーターでエイリアス値が使用されます。

- _Type_ パラメーターを使用しない場合、既定値は Distribution です。

この例では、指定されたプロパティを持つ IT Administrators という名前の配布グループを作成します。

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

構文およびパラメーターの詳細については [、「New-EOPDistributionGroup」を参照してください](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)。

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>スタンドアロンの EOP PowerShell を使用してグループを変更する

スタンドアロンの EOP PowerShell でグループを変更するには、次の構文を使用します。

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

この例では、Seattle Employees グループのプライマリ SMTP アドレス (返信アドレスとも呼ばれる) を使用して、sea.employees@contoso.com。

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

この例では、Security Team グループの現在のメンバーを Kitty Petersen と Tyson Fawcett に置き換える。

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

この例では、グループの現在のメンバーを保持しながら、Tyson Fawcett という名前の新しいユーザーを Security Team という名前のグループに追加します。

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

構文およびパラメーターの詳細については[、「Set-EOPDistributionGroup」および](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup)[「Update-EOPDistributionGroupMember」を参照してください](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)。

### <a name="remove-a-group-using-remote-windows-powershell"></a>リモート デバイスを使用してグループを削除Windows PowerShell

この例では、IT Administrators という名前の配布グループを削除します。

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

構文およびパラメーターの詳細については [、「Remove-EOPDistributionGroup」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

配布グループまたはメールが有効なセキュリティ グループが正常に作成、変更、または削除されたことを確認するには、次の手順を実行します。

- EAC で、 **[受信者]** \> **[グループ]** に移動します。 グループが一覧に表示されている (または一覧に表示されていない) か確認し、グループの種類の **値を確認** します。 グループを選択して詳細ウィンドウに情報を表示するか、[編集]アイコンをクリックして ![ ](../../media/ITPro-EAC-AddIcon.png) 設定を表示します。

- スタンドアロンの EOP PowerShell で、次のコマンドを実行して、グループが一覧に表示されている (または一覧に表示されていない) か確認します。

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- グループの名前、エイリアス、または電子メール アドレスに置き換え、次のコマンドを実行して \<GroupIdentity\> 設定を確認します。

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- グループ メンバーを表示するには、グループの名前、エイリアス、または電子メール アドレスに置き換え、次 \<GroupIdentity\> のコマンドを実行します。

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
