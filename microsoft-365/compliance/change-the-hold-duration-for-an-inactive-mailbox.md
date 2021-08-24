---
title: 非アクティブなメールボックスの保持期間を変更する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
ms.custom:
- seo-marvel-apr2020
description: メールボックスをOffice 365した後、非アクティブなメールボックスに割り当てられている保持ポリシーまたは保持ポリシー Office 365期間を変更します。
ms.openlocfilehash: 02fb0ab1f598db3532f1544c041dfcffd3a2224a
ms.sourcegitcommit: 4582873483bd52bc790bf75b838cc505dc4bbeb4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2021
ms.locfileid: "58502893"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>非アクティブなメールボックスの保持期間を変更する

非アクティブなメールボックスは、退職して組織を離れた元従業員の電子メールを保持するために使用します。 訴訟ホールド、In-Place ホールド、Microsoft 365 アイテム保持ポリシー、または電子情報開示ケースに関連付けられている保留リストがメールボックスに配置され、対応するユーザー アカウントが削除された場合、メールボックスは非アクティブになります。 非アクティブなメールボックスのコンテンツは、非アクティブになる前にメールボックスに設定された保持期間の間保持されます。 保持期間は、[回復可能なアイテム] フォルダー内のアイテムを保持する期間を定義します。 [回復可能なアイテム] フォルダー内のアイテムの保持期間が過ぎると、アイテムは非アクティブなメールボックスから完全に削除 (消去) されます。 メールボックスを非アクティブにした後で、非アクティブなメールボックスに割り当てられた保持ポリシー Microsoft 365保持ポリシーの期間を変更できます。
  
> [!IMPORTANT]
> メールボックスのコンテンツを保持するためにさまざまな方法に投資を続ける中、Exchange 管理センターのインプレース ホールドを廃止することを発表します。 つまり、非アクティブなメールボックスを作成するには、訴訟ホールドMicrosoft 365保持ポリシーを使用する必要があります。 2020 年 4 月 1 日から、In-Place で新しいExchange Online。 ただし、非アクティブなメールボックスに配置されたインプレース ホールドのホールド期間は引き続き変更できます。 ただし、2020 年 7 月 1 日から、保持期間を変更する必要があります。 インプレース ホールドを削除することによってのみ、非アクティブなメールボックスを削除できます。 インプレース ホールドになっている既存の非アクティブなメールボックスは、ホールドが解除されるまで保持されます。 インプレース ホールドの廃止に関する詳細情報は、「[従来の eDiscovery ツールの廃止](legacy-ediscovery-retirement.md)」を参照してください。
  
## <a name="connect-to-powershell"></a>Connect PowerShell へのアクセス

- You have to use Exchange Online PowerShell to change the hold duration for a Litigation Hold on an inactive mailbox. You can't use the Exchange admin center (EAC). But you can use Exchange Online PowerShell or the EAC to change the hold duration for an In-Place Hold. セキュリティとコンプライアンス センターまたはセキュリティ & コンプライアンス センター PowerShell を使用して、Microsoft 365保持ポリシーの保持期間を変更できます。
    
- コンプライアンス センター powerShell Exchange Onlineセキュリティ &接続するには、次のいずれかのトピックを参照してください。
    
  - [Exchange Online PowerShell への接続](/powershell/exchange/connect-to-exchange-online-powershell)
    
  - [セキュリティ/コンプライアンス センターの PowerShell に接続する](/powershell/exchange/connect-to-scc-powershell)
    
- 電子情報開示ケースに関連付けられた保留は無限保持であり、変更できる保持期間はありません。 アイテムは、ホールドが削除されて非アクティブなメールボックスが削除されるまで無限に保持されます。
    
- 非アクティブなメールボックスの詳細については、「非アクティブなメールボックス」を参照[Microsoft 365。](inactive-mailboxes-in-office-365.md)
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>手順 1: 非アクティブなメールボックスに設定されているホールドを特定する

異なる種類の保留リストまたは 1 つ以上の Microsoft 365 保持ポリシーが非アクティブなメールボックスに配置される可能性があるため、最初の手順は非アクティブなメールボックスの保留リストを識別します。
  
Exchange Online PowerShell で次のコマンドを実行して、組織内のすべての非アクティブなメールボックスのホールドの情報を表示します。
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```

**LitigationHoldEnabled** プロパティの値が **True** になっている場合、非アクティブなメールボックスは訴訟ホールド中ということになります。 In-Place 保持ポリシー、電子情報開示保持ポリシー、または Microsoft 365 保持ポリシーが非アクティブなメールボックスに配置されている場合、保持ポリシーまたは保持ポリシーの GUID が **InPlaceHolds** プロパティの値として表示されます。 たとえば、5 つの非アクティブなメールボックスの結果を次に示します。 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```

次の表は、各メールボックスを非アクティブにするのに使用された 5 つの異なる種類のホールドを示しています。
  
|**非アクティブなメールボックス**|**ホールドの種類**|**非アクティブなメールボックスのホールドを識別する方法**|
|:-----|:-----|:-----|
|Ann Beebe  <br/> |訴訟ホールド  <br/> |*LitigationHoldEnabled*  プロパティが  `True` に設定されています。  <br/> |
|Pilar Pinilla  <br/> |インプレース ホールド  <br/> |*InPlaceHolds*  プロパティには非アクティブなメールボックスに設定されたインプレース ホールドの GUID が含まれています。ID がプレフィックスから始まっていないため、これはインプレース ホールドだとわかります。  <br/> Exchange Online PowerShell で  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` コマンドを使用して、非アクティブのメールボックスのインプレース ホールドについての情報を取得できます。  <br/> |
|Mario Necaise  <br/> |組織全体のMicrosoft 365アイテム保持ポリシー Microsoft 365 コンプライアンス センター  <br/> |*InPlaceHolds*  プロパティが空になっています。 これは、1 つ以上の組織全体または (Exchange) Microsoft 365が非アクティブなメールボックスに適用されます。 この場合、PowerShell でコマンドをExchange Onlineして、組織全体のアイテム保持ポリシーの `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` GUID のMicrosoft 365取得できます。 メールボックスに適用される組織全体の保持ポリシーの GUID は、Exchangeプレフィックスで始まる。たとえば `mbx` `mbxa3056bb15562480fadb46ce523ff7b02` 、 です。  <br/> <br/>非アクティブなMicrosoft 365に適用されるアイテム保持ポリシーを識別するには、コンプライアンス センター PowerShell のセキュリティ &コマンドを実行します。  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|Carol Olson  <br/> |Microsoft 365に適用されるセキュリティ & コンプライアンス センターのアイテム保持ポリシー  <br/> |*InPlaceHolds* プロパティには、非アクティブなメールボックスにMicrosoft 365保持ポリシーの GUID が含まれる。 GUID が  `mbx` プレフィックスで始まっているため、これは特定のメールボックスに適用されたアイテム保持ポリシーであることがわかります。 非アクティブなメールボックスに適用される保持ポリシーの GUID がプレフィックスで始まった場合、保持ポリシーがユーザーの会話に適用Skype for Business `skp` されます。  <br/><br/> 非アクティブなMicrosoft 365に適用されるアイテム保持ポリシーを識別するには、コンプライアンス センター PowerShell のセキュリティ &コマンドを実行します。<br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/>このコマンドを実行する場合は、必ず、 `mbx` または  `skp` プレフィックスを削除してください。  <br/> |
|Abraham McMahon  <br/> |電子情報開示ケースの保持Microsoft 365 コンプライアンス センター  <br/> |*InPlaceHolds*  プロパティに、非アクティブなメールボックスに設定されている電子情報開示ケース ホールドの GUID が含まれています。GUID が  `UniH` プレフィックスで始まっているため、これは電子情報開示ケース ホールドであることがわかります。  <br/> Security & コンプライアンス センター PowerShell のコマンドレットを使用して、非アクティブなメールボックスの保留が関連付けられている電子情報開示ケースに関する情報  `Get-CaseHoldPolicy` を取得できます。 For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the inactive mailbox. Be sure to remove the  `UniH` プレフィックスを削除してください。  <br/><br/> 非アクティブなメールボックスのホールドが関連付けられている電子情報開示ケースを特定するには、次のコマンドを実行します。  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> **注:** 非アクティブなメールボックスに電子情報開示ホールドを使用することをお勧めしません。 That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. ある時点で、法的ケースはおそらく終了し、ケースに関連付けられている保留リストは削除され、電子情報開示ケースは閉じ (または削除) されます。 実際、非アクティブなメールボックスに配置された保留リストが電子情報開示ケースに関連付けられている場合、ホールドが解放された場合、または電子情報開示ケースが閉じたり削除された場合、非アクティブなメールボックスは完全に削除されます。 

アイテム保持ポリシーのMicrosoft 365詳細については、「アイテム保持ポリシーと保持ラベルについて」[を参照してください](retention.md)。
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>手順 2: 非アクティブなメールボックスの保持期間を変更する

非アクティブなメールボックスに設定されているホールドの種類 (および複数のホールドがあるかどうか) を特定したら、次は、保持期間を変更します。 
  
### <a name="change-the-duration-for-a-litigation-hold"></a>訴訟ホールドの期間を変更する

Exchange Online PowerShell を使用して、非アクティブなメールボックスに配置されている訴訟ホールドの保持期間を変更する方法を次に示します。EAC を使用することはできません。保持期間を変更するには、次のコマンドを実行します。この例では、保持期間を無期限に変更しています。
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

結果として、非アクティブなメールボックス内のアイテムは、無期限に、あるいは、ホールドが削除されるか保持期間が別の値に変更されるまで、保持されます。
  
> [!TIP]
> 非アクティブなメールボックスを特定する最もよい方法は、 **Distinguished Name** または **Exchange GUID** の値を使用することです。これらの値のいずれかを使用すると、正しくないメールボックスを誤って指定することを避けられます。 
  
### <a name="change-the-duration-for-an-in-place-hold"></a>インプレース ホールドの期間を変更する

 In-Place保留は廃止され、変更できなくなりました。 非アクティブなメールボックスにIn-Place保持が適用されている場合は、保持期間を変更できません。 削除できるのは、非アクティブなIn-Place削除される保留リストの保持のみです。 詳細については、「非アクティブな [メールボックスを削除する」を参照してください](delete-an-inactive-mailbox.md#remove-in-place-holds)。
  
## <a name="more-information"></a>詳細情報

- **非アクティブなメールボックス内のアイテムの保持期間はどのように計算されますか。** 保持期間は、メールボックス アイテムを受信または作成した最初の日付から計算されます。 
    
- **保持期間を過ぎるとどうなりますか。** [回復可能なアイテム] フォルダー内のアイテムの保持期間を過ぎると、アイテムは非アクティブなメールボックスから完全に削除 (消去) されます。 非アクティブなメールボックスに保持期間が指定されていない場合、回復可能なアイテム フォルダー内のアイテムは削除されません (非アクティブなメールボックスの保持期間が変更されていない限り)。 
    
- **Exchange アイテム保持ポリシーの処理は、非アクティブなメールボックスに対しても継続されますか。** メールボックスが非アクティブになったときにメールボックスに Exchange アイテム保持ポリシー (Exchange Online の機能であるメッセージング レコード管理 (MRM)) が適用されていた場合は、その非アクティブなメールボックスに対して削除ポリシー ( **Delete** 保持アクションが設定された保持タグ) の処理が継続されます。つまり、保持期間を過ぎると、削除ポリシーのタグが付けられたアイテムは [回復可能なアイテム] フォルダーに移動されます。その後、保持期間を過ぎると、それらのアイテムは非アクティブなメールボックスから消去されます。 
    
    逆に、非アクティブなメールボックスに割り当てられた保持ポリシーにアーカイブ ポリシー ( **MoveToArchive** 保持アクションが設定された保持タグ) が含まれている場合、それらはすべて無視されます。つまり、非アクティブなメールボックス内のアーカイブ ポリシーのタグが付けられたアイテムは、保持期間を過ぎてもプライマリ メールボックスに残ります。それらのアイテムは、アーカイブ メールボックスやアーカイブ メールボックス内の [回復可能なアイテム] フォルダーに移動されません。ユーザーは非アクティブなメールボックスにサインインできないので、アーカイブ ポリシーを処理するためにデータセンターのリソースを消費する理由はありません。 

- **訴訟ホールドの新しい保持期間を確認するには、次のコマンドを実行します。** 

   ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

- **通常のメールボックスのように、管理フォルダー アシスタント (MFA) は非アクティブなメールボックスも処理します。** このExchange Online MFA は約 7 日に 1 回メールボックスを処理します。 非アクティブなメールボックスの保持期間を変更したなら、 **Start-ManagedFolderAssistant** コマンドレットを使用して、非アクティブなメールボックスの新しい保持期間の処理を直ちに開始します。 次のコマンドを実行します。 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **非アクティブなメールボックスに多数の保留リストが配置されている場合は、すべての保留 GUID が表示されません。** 非アクティブなメールボックスに設定されているすべてのホールド (訴訟ホールドを除く) の GUID を表示するには、次のコマンドを実行します。 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```