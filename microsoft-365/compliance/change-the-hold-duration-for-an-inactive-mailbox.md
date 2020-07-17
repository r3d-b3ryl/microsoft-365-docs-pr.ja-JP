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
description: Office 365 メールボックスが非アクティブになった後、非アクティブなメールボックスに割り当てられているホールドまたは Office 365 アイテム保持ポリシーの期間を変更します。
ms.openlocfilehash: 675e6eb36f762a50c3caafce07d09fda9ba9d98e
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126378"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>非アクティブなメールボックスの保持期間を変更する

非アクティブなメールボックスは、退職して組織を離れた元従業員の電子メールを保持するために使用します。 メールボックスは、訴訟ホールド、インプレースホールド、Microsoft 365 アイテム保持ポリシー、または電子情報開示ケースに関連付けられた保留リストがメールボックスに配置され、対応するユーザーアカウントが削除されると、非アクティブになります。 非アクティブなメールボックスのコンテンツは、非アクティブになる前にメールボックスに設定された保持期間の間、保持されます。 保持期間は、[回復可能なアイテム] フォルダー内のアイテムを保持する期間を定義します。 [回復可能なアイテム] フォルダー内のアイテムの保持期間が過ぎると、アイテムは非アクティブなメールボックスから完全に削除 (消去) されます。 メールボックスが非アクティブになった後は、非アクティブなメールボックスに割り当てられている保留または Microsoft 365 アイテム保持ポリシーの期間を変更できます。
  
> [!IMPORTANT]
> メールボックスのコンテンツを保持するためのさまざまな方法に投資し続けるので、Exchange 管理センターでのインプレースホールドの廃止を発表しています。 つまり、非アクティブなメールボックスを作成するには、訴訟ホールドと Microsoft 365 のアイテム保持ポリシーを使用する必要があります。 2020年4月1日以降、Exchange Online に新しいインプレースホールドを作成することはできません。 ただし、非アクティブなメールボックスに設定されたインプレースホールドの保持期間を変更することはできます。 ただし、2020年7月1日以降、保持期間を変更することはできません。 インプレースホールドを削除しても、非アクティブなメールボックスを削除することはできません。 インプレース保持されている既存の非アクティブなメールボックスは、保留が解除されるまで保持されます。 インプレースホールドが廃止された場合の詳細については、「[従来の電子情報開示ツールの廃止](legacy-ediscovery-retirement.md)」を参照してください。
  
## <a name="connect-to-powershell"></a>PowerShell への接続

- You have to use Exchange Online PowerShell to change the hold duration for a Litigation Hold on an inactive mailbox. You can't use the Exchange admin center (EAC). But you can use Exchange Online PowerShell or the EAC to change the hold duration for an In-Place Hold. セキュリティ/コンプライアンスセンターまたはセキュリティ & コンプライアンスセンターの PowerShell を使用して、Microsoft 365 のアイテム保持ポリシーの保持期間を変更できます。
    
- Exchange Online PowerShell または Security & コンプライアンスセンター PowerShell に接続するには、次のいずれかのトピックを参照してください。
    
  - [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [セキュリティ/コンプライアンス センターの PowerShell に接続する](https://go.microsoft.com/fwlink/?linkid=799771)
    
- 電子情報開示ケースに関連付けられている保留は無限保持で、変更可能な保持期間がないことを意味します。 アイテムは、ホールドが削除されて非アクティブなメールボックスが削除されるまで無限に保持されます。
    
- 非アクティブなメールボックスの詳細については、「 [Microsoft 365 の非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)」を参照してください。
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>手順 1: 非アクティブなメールボックスに設定されているホールドを特定する

非アクティブなメールボックスには、さまざまな種類の保留または1つ以上の Microsoft 365 保持ポリシーが設定されている場合があるため、最初の手順は非アクティブなメールボックスの保留リストを識別することです。
  
Exchange Online PowerShell で次のコマンドを実行して、組織内のすべての非アクティブなメールボックスのホールドの情報を表示します。
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```

**LitigationHoldEnabled** プロパティの値が **True** になっている場合、非アクティブなメールボックスは訴訟ホールド中ということになります。 インプレースホールド、電子情報開示の保持、または Microsoft 365 のアイテム保持ポリシーが非アクティブなメールボックスに設定されている場合、保留またはアイテム保持ポリシーの GUID が**InPlaceHolds**プロパティの値として表示されます。 たとえば、次の例は、5つの非アクティブなメールボックスの結果を示しています。 
  
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
|Mario Necaise  <br/> |セキュリティ & コンプライアンスセンターの組織全体にわたる Microsoft 365 のアイテム保持ポリシー  <br/> |*InPlaceHolds*  プロパティが空になっています。 これは、1つ以上の組織全体または (Exchange ワイド) Microsoft 365 アイテム保持ポリシーが非アクティブなメールボックスに適用されることを示します。 この場合、 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` Exchange Online PowerShell でコマンドを実行して、組織全体の Microsoft 365 保持ポリシーの guid の一覧を取得できます。 Exchange メールボックスに適用される組織全体のアイテム保持ポリシーの GUID は、というプレフィックスで始まり `mbx` ます (例:) `mbxa3056bb15562480fadb46ce523ff7b02` 。  <br/> <br/>非アクティブなメールボックスに適用されている Microsoft 365 アイテム保持ポリシーを識別するには、Security & コンプライアンスセンターの PowerShell で次のコマンドを実行します。  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|Carol Olson  <br/> |特定のメールボックスに適用されるセキュリティ & コンプライアンスセンターの Microsoft 365 アイテム保持ポリシー  <br/> |*InPlaceHolds*プロパティには、非アクティブなメールボックスに適用される Microsoft 365 アイテム保持ポリシーの GUID が含まれています。 GUID が  `mbx` プレフィックスで始まっているため、これは特定のメールボックスに適用されたアイテム保持ポリシーであることがわかります。 非アクティブなメールボックスに適用されたアイテム保持ポリシーの GUID がプレフィックスで開始されている場合は `skp` 、アイテム保持ポリシーが Skype For business の会話に適用されることを示します。  <br/><br/> 非アクティブなメールボックスに適用されている Microsoft 365 アイテム保持ポリシーを識別するには、Security & コンプライアンスセンターの PowerShell で次のコマンドを実行します。<br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/>このコマンドを実行する場合は、必ず、 `mbx` または  `skp` プレフィックスを削除してください。  <br/> |
|Abraham McMahon  <br/> |セキュリティ & コンプライアンスセンターにおける電子情報開示ケースホールド  <br/> |*InPlaceHolds*  プロパティに、非アクティブなメールボックスに設定されている電子情報開示ケース ホールドの GUID が含まれています。GUID が  `UniH` プレフィックスで始まっているため、これは電子情報開示ケース ホールドであることがわかります。  <br/> `Get-CaseHoldPolicy`セキュリティ & コンプライアンスセンターの PowerShell でコマンドレットを使用して、非アクティブなメールボックスの保留リストが関連付けられている電子情報開示ケースに関する情報を取得できます。 For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the inactive mailbox. Be sure to remove the  `UniH` プレフィックスを削除してください。  <br/><br/> 非アクティブなメールボックスのホールドが関連付けられている電子情報開示ケースを特定するには、次のコマンドを実行します。  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> **注:** 非アクティブなメールボックスに対して電子情報開示保持を使用することはお勧めしません。 That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. いずれかの時点で、訴訟ケースが終了し、ケースに関連付けられている保留リストが削除され、電子情報開示ケースがクローズされる (または削除される) 場合があります。 実際には、非アクティブなメールボックスに配置されたホールドが電子情報開示ケースに関連付けられていて、保留が解除されるか、または電子情報開示ケースが閉じられるか削除されると、非アクティブなメールボックスは完全に削除されます。 

Microsoft 365 の保持ポリシーの詳細については、「[アイテム保持ポリシーと保持ラベルについ](retention.md)て」を参照してください。
  
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

 インプレース ホールドの保持期間の変更は、EAC か Exchange Online PowerShell を使用して行うことができます。 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a>EAC を使用して保持期間を変更する

1. 変更するインプレース ホールドの名前が分かっている場合は、次の手順に進みます。 そうでない場合は、次のコマンドを実行して、非アクティブなメールボックスに設定されたインプレース ホールドの名前を取得します。 [手順 1](#step-1-identify-the-holds-on-an-inactive-mailbox)で取得したインプレースホールドの GUID を使用します。

    ```powershell
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
3. 変更するインプレースホールドを選択し、[編集アイコンの**編集**] を選択し ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) ます。
    
4. [**インプレースの電子情報開示 &amp; 保持**のプロパティ] ページで、[**インプレースホールド**] を選択します。 
    
5. 現在の保持期間に基づいて、次のいずれかの操作を実行します。
    
    1. 無制限にアイテムを保持するには、[**無期限に保持**] を選択します。 
    
    2. 特定の期間のアイテムを保持するために **、受信日を基準**としてアイテムを保持する日数を指定します。 Type the number of days that you want to hold items for. 
    
    ![インプレース ホールド期間の変更に関するスクリーン ショット](../media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. [**保存**] を選択します。
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a>Exchange Online PowerShell を使用して保持期間を変更する

1. 変更するインプレース ホールドの名前が分かっている場合は、次の手順に進みます。 そうでない場合は、次のコマンドを実行して、非アクティブなメールボックスに設定されたインプレース ホールドの名前を取得します。 [手順 1](#step-1-identify-the-holds-on-an-inactive-mailbox)で取得したインプレースホールドの GUID を使用します。

    ```powershell
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. 保持期間を変更するには、次のコマンドを実行します。 この例では、保持期間を2555日 (約7年間) に変更します。 
    
    ```powershell
    Set-MailboxSearch <identity of In-Place Hold> -ItemHoldPeriod 2555
    ```

     保持期間を無制限の期間に変更するには、 _-ItemHoldPeriod unlimited_ を使用します。
  
## <a name="more-information"></a>詳細情報

- **非アクティブなメールボックス内のアイテムの保持期間はどのように計算されますか。** 保持期間は、メールボックス アイテムを受信または作成した最初の日付から計算されます。 
    
- **保持期間を過ぎるとどうなりますか。** [回復可能なアイテム] フォルダー内のアイテムの保持期間を過ぎると、アイテムは非アクティブなメールボックスから完全に削除 (消去) されます。 非アクティブなメールボックスに設定されている保持期間が指定されていない場合、[回復可能なアイテム] フォルダー内のアイテムは削除されません (非アクティブなメールボックスの保持期間が変更されていない場合)。 
    
- **Exchange アイテム保持ポリシーの処理は、非アクティブなメールボックスに対しても継続されますか。** メールボックスが非アクティブになったときにメールボックスに Exchange アイテム保持ポリシー (Exchange Online の機能であるメッセージング レコード管理 (MRM)) が適用されていた場合は、その非アクティブなメールボックスに対して削除ポリシー ( **Delete** 保持アクションが設定された保持タグ) の処理が継続されます。つまり、保持期間を過ぎると、削除ポリシーのタグが付けられたアイテムは [回復可能なアイテム] フォルダーに移動されます。その後、保持期間を過ぎると、それらのアイテムは非アクティブなメールボックスから消去されます。 
    
    逆に、非アクティブなメールボックスに割り当てられた保持ポリシーにアーカイブ ポリシー ( **MoveToArchive** 保持アクションが設定された保持タグ) が含まれている場合、それらはすべて無視されます。つまり、非アクティブなメールボックス内のアーカイブ ポリシーのタグが付けられたアイテムは、保持期間を過ぎてもプライマリ メールボックスに残ります。それらのアイテムは、アーカイブ メールボックスやアーカイブ メールボックス内の [回復可能なアイテム] フォルダーに移動されません。ユーザーは非アクティブなメールボックスにサインインできないので、アーカイブ ポリシーを処理するためにデータセンターのリソースを消費する理由はありません。 
    
- **新しい保持期間を確認するには、次のコマンドのいずれかを実行します。** 最初のコマンドは訴訟ホールド用で、2 番目はインプレース ホールド用です。 

    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```powershell
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- **通常のメールボックスのように、管理フォルダー アシスタント (MFA) は非アクティブなメールボックスも処理します。** Exchange Online では、MFA は約7日に1回、メールボックスを処理します。 非アクティブなメールボックスの保持期間を変更したなら、 **Start-ManagedFolderAssistant** コマンドレットを使用して、非アクティブなメールボックスの新しい保持期間の処理を直ちに開始します。 次のコマンドを実行します。 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **非アクティブなメールボックスに多数のホールドが設定されている場合、保留中の Guid のすべてが表示されるわけではありません。** 非アクティブなメールボックスに設定されているすべてのホールド (訴訟ホールドを除く) の GUID を表示するには、次のコマンドを実行します。 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
