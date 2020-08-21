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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: スタンドアロン Exchange Online Protection (EOP) 組織の管理者は、Exchange 管理センター (EAC) とスタンドアロン Exchange Online Protection (EOP) PowerShell で配布グループとメールが有効なセキュリティ グループを作成、変更、削除する方法を学習できます。
ms.openlocfilehash: e7b93b9d05fda7e4f5f8abea02fbe3f1c70a6c74
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826555"
---
# <a name="manage-groups-in-eop"></a>EOP でグループを管理する

Exchange Online メールボックスを持たないスタンドアロン Exchange Online Protection (EOP) 組織では、次の種類のグループを作成、変更、および削除できます。

- **配布グループ**: メール ユーザーまたは他の配布グループのコレクション。 たとえば、共通の関心領域でメールを送受信する必要があるチームやその他のアドホック グループなどです。 配布グループは、電子メール メッセージの配布のみに使用すり、セキュリティ プリンシパルではありません (配布グループにはアクセス許可を割り当てられません)。

- **メールが有効なセキュリティ グループ**: 管理者役割のアクセス許可が必要な、メール ユーザーとその他のセキュリティ グループのコレクション。 たとえば、特定のユーザー グループに管理者アクセス許可を付与して、スパム対策設定とマルウェア対策設定を構成できるようにすることができます。

    > [!NOTE]
    >
    > - 既定では、新しいメールが有効なセキュリティ グループは外部 (認証されていない) 送信者からのメッセージを拒否します。
    >
    > - メールが有効なセキュリティ グループには配布グループを追加しない。

グループは、Exchange 管理センター (EAC) とスタンドアロン EOP PowerShell で管理できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- Exchange 管理センターを開くには、「 [スタンドアロン EOP の Exchange 管理センター」を参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。

- スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- スタンドアロン EOP PowerShell でグループを管理しているときに、調整が発生する場合があります。 このトピックの PowerShell 手順ではバッチ処理方法を使用します。このメソッドでは、コマンドの結果が表示されるまで数分の伝達遅延が出ます。

- これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 具体的には、Distribution Groups 役割が必要です。既定では、OrganizationManagement (グローバル管理者) および RecipientManagement 役割グループに割り当てられます。 詳細については、「スタンドアロン [EOP のアクセス許可」を参照し、EAC](feature-permissions-in-eop.md) [を使用して役割グループ内のメンバーの一覧を変更します](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- このトピックの手順で使用可能なキーボード ショートカットについては [、Exchange Online の Exchange 管理センターのキーボード ショートカットを参照してください](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 問題が発生する場合 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) フォーラムでサポートをご依頼ください。

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>Exchange 管理センターを使用して配布グループを管理する

### <a name="use-the-eac-to-create-groups"></a>EAC を使用してグループを作成する

1. EAC で、 **[受信者]** \> **[グループ]** に移動します。

2. [ **新しい** ![ 新規作成] ](../../media/ITPro-EAC-AddIcon.png) アイコンをクリックし、次のいずれかのオプションを選択します。

   - **配布グループ**

   - **メールが有効なセキュリティ グループ**

3. 開いた新しいグループ ページで、次の設定を構成します。 必須のマークが付いいい <sup>\*</sup> いの設定は、必須です。

   - <sup>\*</sup>**表示名**: この名前は組織のアドレス帳、電子メールがこのグループに送信されるときの電子メールの送信先行、EAC **の [グループ]** 一覧に表示されます。 表示名は必須で、一意である必要があります。表示名は、ユーザーが内容を認識できるようにわかりやすい名前にするものでなけたものである必要があります。

   - <sup>\*</sup>**[エイリア**ス: このボックスに、グループのエイリアス名を入力します。] エイリアスは 64 文字以内で、一意である必要があります。 ユーザーが電子メール メッセージの [出す] 行にエイリアスを入力すると、グループの表示名に解決されます。

   - <sup>\*</sup>**Email address**: 電子メール アドレスは、アットマーク (@) の左に表示されるエイリアスと、右側のドメインで構成されます。 既定では、Alias 値 **はエイリア** ス値に使用されますが、変更はできます。 ドメイン値として、ドロップダウンをクリックして組織内のドメインを選びます。

   - **Description**: この説明は、アドレス帳と EAC の [詳細] ウィンドウに表示されます。

   - <sup>\*</sup>**Owners**: グループの所有者がグループ メンバーシップを管理できます。 既定では、グループを作成するユーザーがグループの所有者になります。 グループには、最低 1 人の所有者が必要です。

     所有者を追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。 表示されるダイアログで、受信者またはグループを検索して選択し、[追加 - **>**。 必要な回数だけこの手順を繰り返します。 完了したら、 **[OK]** をクリックします。

     所有者を削除するには、所有者を選択して、[削除] **アイコンをクリック** ![ します ](../../media/ITPro-EAC-RemoveIcon.gif) 。

   - **メンバー**: グループ メンバーを追加および削除します。

     メンバーを追加するには、[追加] **アイコン** ![ をクリックします ](../../media/ITPro-EAC-AddIcon.png) 。 表示されるダイアログで、受信者またはグループを検索して選択し、[追加 - **>**。 必要な回数だけこの手順を繰り返します。 完了したら、 **[OK]** をクリックします。

     メンバーを削除するには、メンバーを選択し、[削除] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。

4. 完了したら、[保存] をクリック **して配布** グループを作成します。

### <a name="use-the-eac-to-modify-distribution-groups"></a>EAC を使用して配布グループを変更する

1. EAC で、 **[受信者]** \> **[グループ]** に移動します。

2. グループの一覧で、変更する配布グループまたはメールが有効なセキュリティ グループを選択し、[編集] アイコン **をクリック** ![ します ](../../media/ITPro-EAC-AddIcon.png) 。

3. 開いた配布グループのプロパティ ページで、次のいずれかのタブをクリックして、プロパティを表示または変更します。

   完了したら、**[保存]** をクリックします。

#### <a name="general"></a>全般

このタブを使用して、グループに関する基本情報を表示または変更します。

- **表示名**: この名前はアドレス帳、電子メールがこのグループに送信されるときに [電子メール] 行、グループ一覧に **表示されます**。 表示名は必須であり、ユーザーが内容を認識できるようにわかりやすい名前にする必要があります。 また、表示名は、ドメイン内で一意である必要があります。

  グループの名前付けポリシーを実装している場合、表示名は、ポリシーで定義されている名前付け形式に従う必要があります。

- **Alias:** 電子メール アドレスの @ 記号の左に表示される部分を指定します。 エイリアスを変更すると、グループのプライマリ SMTP アドレスも変更され、新しいエイリアスが含まれます。 また、以前のエイリアスが含まれている電子メール アドレスは、グループのプロキシ アドレスとして保持されます。

- **Email address**: 電子メール アドレスは、アットマーク (@) の左に表示されるエイリアスと、右側のドメインで構成されます。 既定では、Alias 値 **はエイリア** ス値に使用されますが、変更はできます。 ドメイン値として、ドロップダウンをクリックして組織内のドメインを選びます。

- **Description**: この説明は、アドレス帳と EAC の [詳細] ウィンドウに表示されます。

#### <a name="ownership"></a>Ownership

このタブを使用して、グループの所有者を割り当てます。 グループ所有者はグループ メンバーシップを管理できます。 既定では、グループを作成するユーザーがグループの所有者になります。 グループには、最低 1 人の所有者が必要です。

所有者を追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。 表示されるダイアログで、受信者を検索して選択し **、[add ->] をクリック>。 ** 必要な回数だけこの手順を繰り返します。 完了したら、 **[OK]** をクリックします。

所有者を削除するには、所有者を選択して、[削除] **アイコンをクリック** ![ します ](../../media/ITPro-EAC-RemoveIcon.gif) 。

#### <a name="membership"></a>メンバーシップ

グループ メンバーを追加または削除するには、このタブを使用します。 グループ所有者がグループのメンバーである必要はかりません。

メンバーを追加するには、[追加] **アイコン** ![ をクリックします ](../../media/ITPro-EAC-AddIcon.png) 。 表示されるダイアログで、受信者またはグループを検索して選択し、[追加 - **>**。 必要な回数だけこの手順を繰り返します。 完了したら、 **[OK]** をクリックします。

メンバーを削除するには、メンバーを選択し、[削除] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。

### <a name="use-the-eac-to-remove-groups"></a>EAC を使用してグループを削除する

1. EAC で、 **[受信者]** \> **[グループ]** に移動します。

2. グループの一覧で、削除する配布グループを選択し、[削除] アイコン **をクリック** ![ します ](../../media/ITPro-EAC-RemoveIcon.gif) 。

## <a name="use-powershell-to-manage-groups"></a>PowerShell を使用してグループを管理する

### <a name="use-standalone-eop-powershell-to-view-groups"></a>スタンドアロン EOP PowerShell を使用してグループを表示する

スタンドアロン EOP PowerShell ですべての配布グループとメールが有効なセキュリティ グループの要約リストを返すには、次のコマンドを実行します。

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

グループ メンバーの一覧を返すには、グループ \<GroupIdentity\> の名前、エイリアス、またはメール アドレスに置き換え、次のコマンドを実行します。

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

構文およびパラメーターの詳細については[、「Get-Recipient」と](https://docs.microsoft.com/powershell/module/exchange/get-recipient)[「Get-DistributionGroupMember」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember)。

### <a name="use-standalone-eop-powershell-to-create-groups"></a>スタンドアロン EOP PowerShell を使用してグループを作成する

スタンドアロン EOP PowerShell で配布グループまたはメールが有効なセキュリティ グループを作成するには、次の構文を使用します。

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**注**:

- _Name パラメーターは_必須で、最大長は 64 文字で、一意である必要があります。 DisplayName パラメーターを使用し_なけら__、Name パラメーターの値_が表示名として使用されます。

- Alias パラメーターを使用しない場合 _、エイリア_ ス値 _として Name_ パラメーターが使用されます。 スペースは削除されます。サポートされていない文字は疑問符 (?) に変換されます。

- PrimarySmtpAddress パラメーターを使用しない _場合は、PrimarySmtpAddress_ パラメーターでエイリアス値 _が使用_ されます。

- _Type_パラメーターを使用しない場合、既定値は Distribution になります。

この例では、指定したプロパティを持つ IT Administrators という配布グループを作成します。

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

構文およびパラメーターの詳細については [、「New-EOPDistributionGroup」を参照してください](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)。

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>スタンドアロン EOP PowerShell を使用してグループを変更する

スタンドアロン EOP PowerShell でグループを変更するには、次の構文を使用します。

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

この例では、シアトルの従業員グループのプライマリ SMTP アドレス (返信アドレスとも呼ばれる) を再割り当てにsea.employees@contoso.com。

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

この例では、Security Team グループの現在のメンバーを Kitty Petersen と Tyson Fawcett で置き換えします。

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

この例では、Tyson Fawcett という名前の新しいユーザーを Security Team というグループに追加し、グループの現在のメンバーも保持します。

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

構文およびパラメーターの詳細については[、「Set-EOPDistributionGroup」と](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup)[「Update-EOPDistributionGroupMember」を参照してください](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)。

### <a name="remove-a-group-using-remote-windows-powershell"></a>リモート デバイスを使用してグループを削除Windows PowerShell

この例では、「IT Administrators」という名前の配布グループを削除します。

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

構文およびパラメーターの詳細については [、「Remove-EOPDistributionGroup」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

配布グループまたはメールが有効なセキュリティ グループの作成、変更、または削除が正常に行されたことを確認するには、次のいずれかの手順を実行します。

- EAC で、 **[受信者]** \> **[グループ]** に移動します。 グループがリストに表示されている (または一覧にない) ことを確認し、グループの種類の値 **を確認** します。 グループを選択して詳細ウィンドウに情報を表示するか、設定を **表示するための [** ![ 編集] アイコン ](../../media/ITPro-EAC-AddIcon.png) をクリックします。

- スタンドアロン EOP PowerShell で、次のコマンドを実行して、グループがリストに表示されている (または一覧にない) ことを確認します。

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- グループ \<GroupIdentity\> の名前、エイリアス、または電子メール アドレスを置き換え、次のコマンドを実行して設定を確認します。

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- グループ メンバーを表示するには、グループの \<GroupIdentity\> 名前、エイリアス、またはメール アドレスに置き換え、次のコマンドを実行します。

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
