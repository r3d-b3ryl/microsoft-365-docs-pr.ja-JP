---
title: 非アクティブなメールボックスを削除する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365非アクティブなメールボックスの内容を保持する必要がなくなった場合は、非アクティブなメールボックスを完全に削除できます。
ms.openlocfilehash: 1e518bda3d11ff17c4ce5aa1ebb6997f8bc09c4d
ms.sourcegitcommit: 570c3be37b6ab1d59a4988f7de9c9fb5ca38028f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2022
ms.locfileid: "65363135"
---
# <a name="delete-an-inactive-mailbox"></a>非アクティブなメールボックスを削除する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

非アクティブなメールボックスは、元従業員が組織を離れた後にメールを保持するために使用されます。 When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold. Also, it's possible that multiple holds might be placed on an inactive mailbox. For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds. さらに、Microsoft 365リテンション期間が非アクティブなメールボックスに適用される場合があります。 非アクティブなメールボックスからすべての保留ポリシーとアイテム保持ポリシーを削除して削除する必要があります。 After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.
  
> [!IMPORTANT]
> メールボックスのコンテンツを保持するためにさまざまな方法に投資を続ける中、Exchange 管理センターのインプレース ホールドを廃止することを発表します。 つまり、非アクティブなメールボックスを作成するには、訴訟ホールドとアイテム保持ポリシーを使用する必要があります。 2020 年 7 月 1 日以降、Exchange Online で新しいインプレース ホールドを作成することはできなくなります。 ただし、非アクティブなメールボックスに配置されたインプレース ホールドのホールド期間は引き続き変更できます。 ただし、2020 年 10 月 1 日以降、ホールド期間を変更することはできなくなります。 インプレース ホールドを削除することによってのみ、非アクティブなメールボックスを削除できます。 インプレース ホールドになっている既存の非アクティブなメールボックスは、ホールドが解除されるまで保持されます。 インプレース ホールドの廃止に関する詳細情報は、「[従来の eDiscovery ツールの廃止](legacy-ediscovery-retirement.md)」を参照してください。
  
保留リストが非アクティブなメールボックスから削除された結果の詳細については、「[詳細情報](#more-information)」セクションを参照してください。
  
## <a name="before-you-delete-an-inactive-mailbox"></a>非アクティブなメールボックスを削除する前に

- 非アクティブなメールボックスから訴訟ホールドを削除するには、Exchange Online PowerShell を使用する必要があります。 Exchange 管理センター (EAC) を使用することはできません。 詳しい手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- 非アクティブなメールボックスの内容は、ホールドを解除して、非アクティブなメールボックスを削除する前に別のメールボックスにコピーできます。 詳細については、「[Office 365で非アクティブなメールボックスを復元する](restore-an-inactive-mailbox.md)」を参照してください。

- 非アクティブなメールボックスから保留ポリシーまたはアイテム保持ポリシーを削除し、メールボックスの論理的に削除されたメールボックスの保持期間が切れた場合、183 日間の論理的に削除されたメールボックスの保持期間が経過すると、メールボックスは完全に削除されます。 論理的に削除されたメールボックスの保持期間の詳細については、この記事の [「詳細情報](#more-information) 」セクションを参照してください。 非アクティブなメールボックスが完全に削除された後は、回復できません。 ホールドを解除する前に、メールボックスの中身が不要かどうかを確認してください。 非アクティブなメールボックスを再アクティブ化する場合は、それを回復できます。 詳細については、「[Office 365で非アクティブなメールボックスを回復する](recover-an-inactive-mailbox.md)」を参照してください。

- 非アクティブなメールボックスの詳細については、「[非アクティブなメールボックスに関する詳細情報](inactive-mailboxes-in-office-365.md)」を参照してください。

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>手順 1: 非アクティブなメールボックスに設定されているホールドを特定する

前述のように、訴訟ホールド、In-Placeホールド、またはアイテム保持ポリシーは非アクティブなメールボックスに配置される可能性があります。 最初の手順として、非アクティブなメールボックスのホールドを識別します。
  
組織内のすべての非アクティブなメールボックスの保留リストの情報を表示するために、次のコマンドを実行します。
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

**LitigationHoldEnabled** プロパティの値が **True** になっている場合、非アクティブなメールボックスが訴訟ホールドに設定されていることを示します。 インプレース ホールドが非アクティブなメールボックスに設定されていると、保留リストの GUID が **InPlaceHolds** プロパティの値として表示されます。 たとえば、次の 2 つの非アクティブなメールボックスの結果は、訴訟ホールドが Ann Beebe に配置され、In-Placeホールドとアイテム保持ポリシーが Pilar Pinilla に配置されていることを示しています。
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, mbxba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> 多数のIn-Place保留ポリシーまたはアイテム保持ポリシーが非アクティブなメールボックスに配置されている場合、In-Place保留 GUID の一部が表示されるわけではありません。 次のコマンドを実行して、InPlaceHolds プロパティ内のすべての GUID を表示できます。  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
保留を識別する方法の詳細については、「 [メールボックスに配置された保留の種類を特定する方法」を](identify-a-hold-on-an-exchange-online-mailbox.md)参照してください。

## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>手順 2:非アクティブなメールボックスから保留リストを削除する

非アクティブなメールボックスにどの種類の保留リストが設定されているか (および複数の保留リストがあるかどうか) を特定したら、次の手順ではメールボックスの保留リストを削除します。前述のように、非アクティブなメールボックスを完全に削除するには、すべての保留リストを削除する必要があります。
  
### <a name="remove-a-litigation-hold"></a>訴訟ホールドを削除する

前述のように、非アクティブなメールボックスから訴訟ホールドを削除するには、Windows PowerShell を使用する必要があります。EAC は使用できません。次のコマンドを実行して、訴訟ホールドを削除します。
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> 非アクティブなメールボックスを特定するには、識別名または Exchange GUID 値を使用するのが最適です。これらの値のいずれかを使用すると、正しくないメールボックスを誤って指定することを回避できます。 
  
### <a name="remove-an-inactive-mailbox-from-a-retention-policy"></a>アイテム保持ポリシーから非アクティブなメールボックスを削除する

非アクティブなメールボックスをMicrosoft 365アイテム保持ポリシーから削除する手順は、非アクティブなメールボックスに割り当てられているアイテム保持ポリシーが組織全体か明示的かによって異なります。 は、非アクティブなメールボックスに割り当てられているアイテム保持ポリシーの種類に基づいて設定されます。

- 組織内のすべてのメールボックスに割り当てられた組織全体のアイテム保持ポリシー。 PowerShell の **Get-OrganizationConfig** コマンドレットExchange Online使用して、組織全体のアイテム保持ポリシーに関する情報を取得します。

- 特定のメールボックスに割り当てられている特定の場所のアイテム保持ポリシー。 これらは、特定のユーザーのコンテンツの場所に割り当てられるポリシーです。 PowerShell の **Get-Mailbox -IncludeInactiveMailbox** コマンドレット Exchange Onlineを使用して、特定の非アクティブなメールボックスに割り当てられているアイテム保持ポリシーに関する情報を取得します。

#### <a name="remove-an-inactive-mailbox-from-an-organization-wide-retention-policy"></a>組織全体のアイテム保持ポリシーから非アクティブなメールボックスを削除する

powerShell Exchange Online次のコマンドを実行して、組織全体のアイテム保持ポリシーから非アクティブなメールボックスを除外します。

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromOrgHolds <retention policy GUID without prefix or suffix>
```

非アクティブなメールボックスに適用される組織全体のアイテム保持ポリシーを特定し、アイテム保持ポリシーの GUID を取得する方法の詳細については、「 [メールボックスに配置された保留の種類を識別する方法」の](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig)「Get-OrganizationConfig」セクションを参照してください。

または、次のコマンドを実行して、組織全体のすべてのポリシーから非アクティブなメールボックスを削除することもできます。

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromAllOrgHolds
```

#### <a name="remove-an-inactive-mailbox-from-a-specific-location-retention-policy"></a>特定の場所のアイテム保持ポリシーから非アクティブなメールボックスを削除する

[Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) で次のコマンドを実行して、非アクティブなメールボックスを明示的なアイテム保持ポリシーから削除します。

```powershell
Set-RetentionCompliancePolicy -Identity <retention policy GUID without prefix or suffix> -RemoveExchangeLocation <identity of inactive mailbox>
```

非アクティブなメールボックスに適用されている特定の場所の保持ポリシーを特定し、アイテム保持ポリシーの GUID を取得する方法の詳細については、「メールボックス [に配置された保留の種類を識別する方法」の](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox)「Get-Mailbox」セクションを参照してください。

### <a name="remove-in-place-holds"></a>インプレース ホールドを削除する

 非アクティブなメールボックスからインプレース ホールドを削除する方法は 2 つあります。
  
- **In-Place Hold オブジェクトを削除します**。 完全に削除する非アクティブなメールボックスがIn-Place保留の唯一のソース メールボックスである場合は、In-Place Hold オブジェクトを削除するだけです。 

    > [!NOTE]
    > インプレース ホールド オブジェクトを削除する前に、保留リストを無効にする必要があります。保留リストを有効にしているインプレース ホールド オブジェクトを削除しようとすると、エラー メッセージが表示されます。 
  
- **非アクティブなメールボックスをIn-Placeホールドのソース メールボックスとして削除** します。 インプレース ホールドの他のソース メールボックスを保持する場合は、ソース メールボックスのリストから非アクティブなメールボックスを削除して、インプレース ホールド オブジェクトを保持することができます。

#### <a name="delete-an-in-place-hold"></a>In-Placeホールドを削除する

1. 削除するインプレース保持のプロパティを含む変数を作成します。[手順 1: 非アクティブなメールボックスに設定されているホールドを特定する](#step-1-identify-the-holds-on-an-inactive-mailbox) で取得したインプレース保持の GUID を使用します。

   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. インプレース ホールドの保留リストを無効にします。

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. インプレース ホールドを削除します。

   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="remove-an-inactive-mailbox-from-an-in-place-hold"></a>In-Placeホールドから非アクティブなメールボックスを削除する

インプレース ホールドに多数のソース メールボックスが含まれている場合、EAC の **[ソース]** ページに非アクティブなメールボックスがリストされないことがあります。インプレース ホールドを編集する場合、 **[ソース]** ページに最大 3,000 のメールボックスが表示されます。非アクティブなメールボックスが **[ソース]** ページにリストされない場合は、Exchange Online PowerShell を使用してインプレース ホールドから削除できます。 
  
1. 非アクティブなメールボックスに設定されたインプレース保持のプロパティを含む変数を作成します。[手順 1: 非アクティブなメールボックスに設定されているホールドを特定する](#step-1-identify-the-holds-on-an-inactive-mailbox) で取得したインプレース保持の GUID を使用します。

    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. 非アクティブなメールボックスがインプレース ホールドのソース メールボックスとしてリストされていることを確認します。 

   ```powershell
   $InPlaceHold.Sources
   ```

   > [!NOTE]
   > インプレース ホールドの *Sources* プロパティは、 *LegacyExchangeDN* プロパティでソース メールボックスを特定します。このプロパティは非アクティブなメールボックスを一意に特定するため、インプレース ホールドの *Sources* プロパティを削除すると、正しくないメールボックスの削除を回避できます。これはまた、2 つのメールボックスが同じエイリアスまたは SMTP アドレスを持っているときの問題も回避できます。 

3. 変数のソース メールボックスのリストから非アクティブなメールボックスを削除します。前の手順のコマンドで返された非アクティブなメールボックスの **LegacyExchangeDN** を必ず使用してください。 

    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    たとえば、次のコマンドは、Pilar Pinilla の非アクティブなメールボックスを削除します。

    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. 変数のソース メールボックスのリストから非アクティブなメールボックスが削除されていることを確認します。

   ```powershell
   $InPlaceHold.Sources
   ```

5. 非アクティブなメールボックスを含まないソース メールボックスの更新されたリストで、インプレース ホールドを変更します。

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. インプレース ホールドのソース メールボックスのリストから非アクティブなメールボックスが削除されていることを確認します。

   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a>詳細

- **非アクティブなメールボックスは、回復可能な削除によって削除されたメールボックスの一種です。** Exchange Onlineで、回復可能な削除によって削除されたメールボックスは、メールボックスが削除されてはいるものの、特定の保持期間内であれば回復することができます。 論理的に削除されたメールボックスが保留になっていない場合、メールボックスは 30 日以内に回復可能です。 非アクティブなメールボックス (削除される前の保留中のメールボックス) は、保留が削除されるまで、保留状態で論理的に削除されたままになります。 ホールドが非アクティブなメールボックスから削除されると、メールボックスは非アクティブ状態にならなくなります。 代わりに、論理的に削除され、保持が削除され、その間に回復可能になった日から 183 日間、Exchange Onlineのままになります。 183 日後、論理的に削除されたメールボックスは完全な削除としてマークされ、回復できません。

- **非アクティブなメールボックスに対する保留リストを削除した後はどうなりますか。** メールボックスは、論理的に削除された他のメールボックスと同様に扱われ、183 日間の論理的に削除されたメールボックスの保持期間が経過すると、完全な削除がマークされます。 この保持期間は、保留が非アクティブなメールボックスから削除された日付から開始されます。 *InactiveMailboxRetireTime* プロパティは、メールボックスが非アクティブ (保留時に論理的に削除) から非アクティブ (保留なしで論理的に削除) に切り替わるときに設定されます。 その時点で、 *InactiveMailboxRetireTime* プロパティは、遷移が発生した現在の日付に設定されます。 *InactiveMailboxRetireTime* プロパティが設定されているメールボックスを検索する (*MailboxLifeCycle* アシスタントと呼ばれる) 実行するアシスタントがあります。 "InactiveMailboxRetireTime + 183 日" が現在の日付より小さい場合、メールボックスは消去されます。

- **ホールドを解除した直後に、非アクティブなメールボックスは完全に削除されますか。** 以前は非アクティブだったメールボックスは、論理的に削除された状態で 183 日間使用できます。 183 日後、メールボックスは完全な削除のマークが付けられます。

- **ホールドを解除した後、どうすれば非アクティブなメールボックスの情報を表示できますか。** ホールドが削除され、非アクティブなメールボックスが論理的に削除されたメールボックスに戻った後、**Get-Mailbox** コマンドレットで *InactiveMailboxOnly* パラメーターを使用しても、そのメールボックスは返されません。 ただし、 **Get-Mailbox -SoftDeletedMailbox** コマンドを使用して、メールボックスの情報を表示できます。 たとえば、次のように入力します。

  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox,WasInactiveMailbox,InactiveMailboxRetireTime
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 6/16/2020 1:19:04 AM
  IsInactiveMailbox      : False
  WasInactiveMailbox     : True
  InactiveMailboxRetireTime : 9/30/2020 11:16:23 PM
  ```

  上の例では、 *WhenSoftDeleted* プロパティは論理的に削除された日付を識別します。この例では 2020 年 6 月 16 日です。 *WasInactiveMailbox* プロパティは、以前は非アクティブなメールボックスであったため、`True`一覧表示されます。 メールボックスは、2020 年 9 月 30 日から 183 日後に完全に削除されます。
