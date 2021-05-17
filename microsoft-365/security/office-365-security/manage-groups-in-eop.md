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
description: スタンドアロン Exchange Online Protection (EOP) 組織の管理者は、Exchange 管理センター (EAC) およびスタンドアロン Exchange Online Protection (EOP) PowerShell で配布グループとメールが有効なセキュリティ グループを作成、変更、削除する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b9d83f2fb59ee8f8d2d3035045ed438d5ba45851
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599571"
---
# <a name="manage-groups-in-eop"></a>EOP でグループを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
-  [Exchange Online Protectionスタンドアロン](exchange-online-protection-overview.md)

メールボックスをExchange Online Protectionスタンドアロン Exchange Online (EOP) 組織では、次の種類のグループを作成、変更、および削除できます。

- **配布グループ**: メール ユーザーまたは他の配布グループのコレクション。 たとえば、関心のある共通領域で電子メールを受信または送信する必要があるチームや他のアドホック グループ。 配布グループは、電子メール メッセージの配布専用であり、セキュリティ プリンシパルではありません (アクセス許可を割り当てすることはできません)。

- **メールが有効なセキュリティ グループ**: 管理者ロールのアクセス許可を必要とするメール ユーザーと他のセキュリティ グループのコレクション。 たとえば、スパム対策とマルウェア対策の設定を構成できるよう、特定のグループのユーザーに管理者アクセス許可を与える場合があります。

    > [!NOTE]
    >
    > - 既定では、新しいメールが有効なセキュリティ グループは、外部 (認証されていない) 送信者からのメッセージを拒否します。
    >
    > - メールが有効なセキュリティ グループに配布グループを追加しない。

管理センター (EAC) Exchangeスタンドアロン EOP PowerShell でグループを管理できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- 管理センターを開Exchange、スタンドアロン[EOP Exchange管理センターを参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。

- スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- スタンドアロン EOP PowerShell でグループを管理すると、調整が発生する可能性があります。 この記事の PowerShell プロシージャでは、バッチ処理メソッドを使用して、コマンドの結果が表示される数分前に伝達遅延が発生します。

- この記事の手順を実行するには、Exchange Online Protectionにアクセス許可を割り当てる必要があります。 具体的には、既定で組織の **管理役割グループ** と受信者管理役割グループに割り当てられている配布 **グループの役割** が必要です。 詳細については、「スタンドアロン [EOP のアクセス](feature-permissions-in-eop.md) 許可」および「役割グループのメンバーの一覧を [変更する EAC](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)を使用する」を参照してください。

- この記事の手順 Exchangeに適用されるキーボード ショートカットの詳細については、「Exchange Online の管理センターのキーボード ショートカット」[を参照Exchange Online。](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> 問題が発生する場合 [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) フォーラムでサポートをご依頼ください。

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>管理センター Exchange使用して配布グループを管理する

### <a name="use-the-eac-to-create-groups"></a>EAC を使用してグループを作成する

1. EAC で、 **[受信者]** \> **[グループ]** に移動します。

2. [ **新しい** ![ 新規] アイコン ](../../media/ITPro-EAC-AddIcon.png) をクリックし、次のいずれかのオプションを選択します。

   - **配布グループ**

   - **メールが有効なセキュリティ グループ**

3. 開く新しいグループ ページで、次の設定を構成します。 <sup>\*</sup> の付いた設定は必須項目です。

   - <sup>\*</sup>**表示名**: この名前は組織のアドレス帳、このグループにメールを送信するときの電子メールの宛先行、EAC の **グループ** 一覧に表示されます。 表示名は必須であり、一意の名前でユーザーが内容を認識できるようにわかりやすい名前にする必要があります。

   - <sup>\*</sup>**エイリアス**: このボックスには、グループのエイリアス名を入力します。 エイリアスは 64 文字以内で、一意である必要があります。 ユーザーがメール メッセージの 宛先行にエイリアスを入力すると、グループの表示名に変換されます。

   - <sup>\*</sup>**メール アドレス**: メール アドレスは、アット (@) 記号の左側のエイリアス、右側のドメインで構成されています。 既定では、エイリアスの値には **エイリアス** が使用されますが、変更することができます。 ドメイン値の場合は、ドロップダウンをクリックし、組織内のドメインを選択して承諾します。

   - **説明**: この説明は、アドレス帳と EAC の [詳細] ウィンドウに表示されます。

   - <sup>\*</sup>**所有者**: グループ所有者はグループ メンバーシップを管理できます。 既定では、グループを作成するユーザーがグループの所有者になります。 グループには、最低 1 人の所有者が必要です。

     所有者を追加するには、 **[追加]** ![[追加] アイコン](../../media/ITPro-EAC-AddIcon.png) をクリックします。 表示されるダイアログで、受信者またはグループを検索して選択し、[->] **をクリックします**。 必要な回数だけこの手順を繰り返します。 完了したら、**[OK]** をクリックします。

     所有者を削除するには、所有者を選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。

   - **メンバー**: グループ メンバーを追加および削除します。

     メンバーを追加するには、**[追加]** ![[追加] アイコン](../../media/ITPro-EAC-AddIcon.png) をクリックします。 表示されるダイアログで、受信者またはグループを検索して選択し、[->] **をクリックします**。 必要な回数だけこの手順を繰り返します。 完了したら、**[OK]** をクリックします。

     メンバーを削除するには、メンバーを選択し、**[削除]** ![[削除] アイコン](../../media/ITPro-EAC-RemoveIcon.gif) をクリックします。

4. 完了したら、[保存] をクリック **して** 配布グループを作成します。

### <a name="use-the-eac-to-modify-distribution-groups"></a>EAC を使用して配布グループを変更する

1. EAC で、 **[受信者]** \> **[グループ]** に移動します。

2. グループの一覧で、変更する配布グループまたはメールが有効なセキュリティ グループを選択し、[編集] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。

3. プロパティを表示または変更するには、開いた配布グループのプロパティのページで以下のタブをクリックします。

   完了したら、**[保存]** をクリックします。

#### <a name="general"></a>全般

このタブを使用して、グループに関する基本情報を表示または変更します。

- **表示名**: この名前は共有アドレス帳、このグループにメールを送信するときのメールの宛先行、**グループ一覧** に表示されます。 表示名は必須であり、ユーザーが内容を認識できるようにわかりやすい名前にする必要があります。 また、表示名は、ドメイン内で一意である必要があります。

  グループの名前付けポリシーを実装している場合、表示名は、ポリシーで定義されている名前付け形式に従う必要があります。

- **エイリアス**: これは、メール アドレスのアット (@) 記号の左側に表示されている部分です。 エイリアスを変更すると、グループのプライマリ SMTP アドレスも変更され、新しいエイリアスが含まれます。 また、以前のエイリアスが含まれている電子メール アドレスは、グループのプロキシ アドレスとして保持されます。

- **メール アドレス**: メール アドレスは、アット (@) 記号の左側のエイリアス、右側のドメインで構成されています。 既定では、エイリアスの値には **エイリアス** が使用されますが、変更することができます。 ドメイン値の場合は、ドロップダウンをクリックし、組織内のドメインを選択して承諾します。

- **説明**: この説明は、アドレス帳と EAC の [詳細] ウィンドウに表示されます。

#### <a name="ownership"></a>所有権

このタブを使用して、グループの所有者を割り当てます。 グループ所有者は、グループ メンバーシップを管理できます。 既定では、グループを作成するユーザーがグループの所有者になります。 グループには、最低 1 人の所有者が必要です。

所有者を追加するには、 **[追加]** ![[追加] アイコン](../../media/ITPro-EAC-AddIcon.png) をクリックします。 表示されるダイアログで、受信者を探して選択し、**[追加 ->]** をクリックします。 必要な回数だけこの手順を繰り返します。 完了したら、**[OK]** をクリックします。

所有者を削除するには、所有者を選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。

#### <a name="membership"></a>メンバーシップ

グループ メンバーを追加または削除するには、このタブを使用します。 グループ所有者がグループのメンバーである必要はありません。

メンバーを追加するには、**[追加]** ![[追加] アイコン](../../media/ITPro-EAC-AddIcon.png) をクリックします。 表示されるダイアログで、受信者またはグループを検索して選択し、[->] **をクリックします**。 必要な回数だけこの手順を繰り返します。 完了したら、**[OK]** をクリックします。

メンバーを削除するには、メンバーを選択し、**[削除]** ![[削除] アイコン](../../media/ITPro-EAC-RemoveIcon.gif) をクリックします。

### <a name="use-the-eac-to-remove-groups"></a>EAC を使用してグループを削除する

1. EAC で、 **[受信者]** \> **[グループ]** に移動します。

2. グループの一覧で、削除する配布グループを選択し、[削除] アイコン **を** ![ クリックします ](../../media/ITPro-EAC-RemoveIcon.gif) 。

## <a name="use-powershell-to-manage-groups"></a>PowerShell を使用してグループを管理する

### <a name="use-standalone-eop-powershell-to-view-groups"></a>スタンドアロン EOP PowerShell を使用してグループを表示する

スタンドアロン EOP PowerShell のすべての配布グループとメールが有効なセキュリティ グループの概要リストを取得するには、次のコマンドを実行します。

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

グループ メンバーの一覧を取得するには、グループの名前、エイリアス、または電子メール アドレスに置き換え、 \<GroupIdentity\> 次のコマンドを実行します。

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

構文とパラメーターの詳細については [、「Get-Recipient」](/powershell/module/exchange/get-recipient) および [「Get-DistributionGroupMember」を参照してください](/powershell/module/exchange/get-distributiongroupmember)。

### <a name="use-standalone-eop-powershell-to-create-groups"></a>スタンドアロン EOP PowerShell を使用してグループを作成する

スタンドアロン EOP PowerShell で配布グループまたはメールが有効なセキュリティ グループを作成するには、次の構文を使用します。

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**注**:

- _Name パラメーター_ は必須で、最大長は 64 文字で、一意である必要があります。 DisplayName パラメーターを使用しない場合は _、Name_ パラメーターの値が表示名に使用されます。

- Alias パラメーターを使用しない場合は、 _エイリアス_ 値に _Name_ パラメーターが使用されます。 スペースは削除されます。サポートされていない文字は疑問符 (?) に変換されます。

- _PrimarySmtpAddress_ パラメーターを使用しない場合は _、PrimarySmtpAddress_ パラメーターでエイリアス値が使用されます。

- Type パラメーターを使用しない場合 _、既定値_ は Distribution です。

次の使用例は、指定したプロパティを持つ IT Administrators という名前の配布グループを作成します。

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

構文とパラメーターの詳細については [、「New-EOPDistributionGroup」を参照してください](/powershell/module/exchange/New-EOPDistributionGroup)。

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>スタンドアロン EOP PowerShell を使用してグループを変更する

スタンドアロン EOP PowerShell のグループを変更するには、次の構文を使用します。

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

この例では、Seattle Employees グループのプライマリ SMTP アドレス (返信アドレスとも呼ばれる) を変更して、sea.employees@contoso.com。

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

この例では、セキュリティ チーム グループの現在のメンバーを Kitty Petersen および Tyson Fawcett に置き換える。

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

構文とパラメーターの詳細については [、「Set-EOPDistributionGroup」](/powershell/module/exchange/set-eopdistributiongroup) および [「Update-EOPDistributionGroupMember」を参照してください](/powershell/module/exchange/update-eopdistributiongroupmember)。

### <a name="remove-a-group-using-remote-windows-powershell"></a>リモート サーバーを使用してグループを削除Windows PowerShell

この例では、IT 管理者という名前の配布グループを削除します。

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

構文とパラメーターの詳細については [、「Remove-EOPDistributionGroup」を参照してください](/powershell/module/exchange/remove-eopdistributiongroup)。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

配布グループまたはメールが有効なセキュリティ グループを正常に作成、変更、または削除されたことを確認するには、次の手順を実行します。

- EAC で、 **[受信者]** \> **[グループ]** に移動します。 グループが一覧表示 (またはリストされていない) を確認し、[グループの種類] の値 **を確認** します。 グループを選択し、[詳細] ウィンドウで情報を表示するか、[ **編集]** アイコンをクリックして設定 ![ ](../../media/ITPro-EAC-AddIcon.png) を表示します。

- スタンドアロンの EOP PowerShell で、次のコマンドを実行して、グループが一覧表示 (または一覧に表示されていない) を確認します。

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- グループの名前、エイリアス、または電子メール アドレスに置き換え、次のコマンドを実行して設定 \<GroupIdentity\> を確認します。

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- グループ メンバーを表示するには、グループの名前、エイリアス、または電子メール アドレスに置き換え、 \<GroupIdentity\> 次のコマンドを実行します。

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```