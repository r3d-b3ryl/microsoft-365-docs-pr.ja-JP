---
title: 非アクティブなメールボックスの保持期間を変更する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/29/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
ms.custom:
- seo-marvel-apr2020
description: Office 365 メールボックスが非アクティブになった後、非アクティブなメールボックスに割り当てられている保持またはOffice 365アイテム保持ポリシーの期間を変更します。
ms.openlocfilehash: f9db81631c563bb985d087b4dfd12ae784c825ff
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66015838"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>非アクティブなメールボックスの保持期間を変更する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

[非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)は、元従業員が組織を離れた後にメールを保持するために使用されるメールボックスの状態です。 Microsoft 365 ユーザー オブジェクトが削除される前に、該当するホールドが適用されると、メールボックスは非アクティブになります。  次の種類の保留は、ユーザー アカウントの削除時に非アクティブなメールボックスの作成を開始します。

- 保持または保持と削除の設定を使用して[アイテム保持ポリシーとラベルをMicrosoft 365](retention.md)する

- [電子情報開示](ediscovery.md)ケースに関連付けられた保留リスト

- [訴訟ホールド](create-a-litigation-hold.md)

- 既存のIn-Place保留。

> [!IMPORTANT]
> 上記のいずれかの保留は、ユーザー アカウントの削除時にメールボックスを強制的に非アクティブにMicrosoft 365しますが、アクティブでないメールボックスを事前に使用する計画を立てる場合は、Microsoft 365リテンション期間を使用することを強くお勧めします。
>
> - 電子情報開示保留は、法的な問題に関連する特定の期限付きケースを対象としています。 ある時点で、訴訟はおそらく終了し、ケースに関連付けられている保留が削除され、電子情報開示ケースは終了 (または削除) されます。 非アクティブなメールボックスに配置された保留が電子情報開示ケースに関連付けられている場合、および保留が解放されるか、電子情報開示ケースが閉じられるか削除された場合、非アクティブなメールボックスは完全に削除されます。
>
> - Exchange管理センターのIn-Place保留は廃止されました。 2020 年 7 月 1 日の時点で、Exchange Onlineで新しいIn-Place保留を作成できませんでした。 2020 年 10 月 1 日以降、インプレース ホールドの保留期間は変更できませんでした。 In-Place保留が適用されている非アクティブなメールボックスは、In-Place保留を削除することによってのみ削除できます。 In-Place保留になっている既存の非アクティブなメールボックスは、保留が削除されるまで引き続き保持されます。 In-Place保留の詳細については、「 [従来の電子情報開示ツールの廃止](legacy-ediscovery-retirement.md)」を参照してください。
>
> - [訴訟ホールド](create-a-litigation-hold.md) は、メールボックス内のコンテンツを保持し、ユーザー アカウントが削除された後に非アクティブにする代替方法として引き続きサポートされます。 ただし、古いテクノロジとして、代わりにMicrosoft 365リテンション期間を使用することをお勧めします。

非アクティブになると、 [回復可能なアイテム フォルダー](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) を含むメールボックスの内容は、非アクティブ化される前にメールボックスに配置された保留が適用されなくなるまで保持されます。  

適用される保留が時間ベースでない場合 (無期限保持のみのMicrosoft 365アイテム保持ポリシーまたはラベルに関連付けられている保留、電子情報開示ケースまたは訴訟ホールド (構成されていない```LitigationHoldDuration```場合) など)、メールボックスのコンテンツは、保持が削除されるまで無期限に保持されます。  

ただし、ホールドが時間ベースの場合、メールボックスの内容は保持期間の有効期限が切れるまで保持されます。この時点で、回復可能なアイテム フォルダー内のすべてのアイテムは非アクティブなメールボックスから完全に削除 (削除) されます。

> [!NOTE]
> 非アクティブなメールボックスの場合は、Microsoft 365アイテム保持ポリシーまたはラベルの保持と削除の設定を使用することをお勧めします。  保持のみの設定を選択した場合、回復可能なアイテム フォルダーは保留期間の最後に消去されますが、削除されていない他のアイテムは非アクティブなメールボックス内に無期限に残ります。

規制とポリシーが進化するにつれて、非アクティブなメールボックスに割り当てられているホールドの期間を変更する必要がある状況が生じることがあります。  次の手順では、これを行う方法の概要を示します。

## <a name="connect-to-powershell"></a>PowerShell へのConnect

前述のように、さまざまな種類の保留が非アクティブなメールボックスの作成をトリガーする可能性があります。  このため、非アクティブなメールボックスに適用される保留期間を変更するには、まず、そのメールボックスに影響を与える保留の種類を特定する必要があります。  これを行うには、Exchange Online PowerShell を使用して保留の種類を特定する必要があります。非アクティブなメールボックスがMicrosoft 365アイテム保持ポリシーまたはラベルの影響を受ける場合は、Security & Compliance PowerShell を使用して特定のポリシーを識別する必要もあります。

- Exchange Online PowerShell または Security & Compliance PowerShell に接続するには、次のいずれかのトピックを参照してください。

  - [Exchange Online PowerShell への接続](/powershell/exchange/connect-to-exchange-online-powershell)

  - [セキュリティ/コンプライアンス PowerShell に接続する](/powershell/exchange/connect-to-scc-powershell)

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>手順 1: 非アクティブなメールボックスに設定されているホールドを特定する

さまざまな種類の保留または 1 つ以上のMicrosoft 365アイテム保持ポリシーが非アクティブなメールボックスに配置される可能性があるため、最初の手順は非アクティブなメールボックスの保留を識別することです。
  
Exchange Online PowerShell で次のコマンドを実行して、組織内の特定の非アクティブなメールボックスの保留情報を表示します。
  
```powershell
Get-Mailbox -Identity <identity of inactive mailbox> -InactiveMailboxOnly | FL DisplayName,Name,DistinguishedName,ExchangeGuid,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,LitigationHoldDate,LitigationHoldOwner,InPlaceHolds,ComplianceTagHoldApplied
```

複数の非アクティブなメールボックスの保留の種類を特定する必要があり、組織に多数のメールボックスがある場合は、PowerShell を使用して表示することが管理できなくなる可能性があります。 この場合、次のコマンドを使用して、該当するすべての情報を CSV ファイルにエクスポートし、必要に応じて環境に ```Path``` 合わせて変更できます。

```powershell
Get-Mailbox -InactiveMailboxOnly -ResultSize Unlimited | Select DisplayName,Name,DistinguishedName,ExchangeGuid,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,LitigationHoldDate,LitigationHoldOwner,InPlaceHolds,ComplianceTagHoldApplied | Export-Csv -NoTypeInformation -Path "C:\Temp\InactiveMailboxHoldTypes.csv"
```

この例では、次に示す 6 つの非アクティブなメールボックスの結果を示しています。保留の種類は異なります。

> [!NOTE]
> 複数の種類の保留を含む複数の保留は、1 つの非アクティブなメールボックスに適用できます。
  
```text
DisplayName              : Ann Beebe
Name                     : annb
DistinguishedName        : CN=annb,OU=Soft Deleted
                           Objects,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange
                           Hosted Organizations,DC=NAMPR06A007,DC=PROD,DC=OUTLOOK,DC=COM
ExchangeGuid             : 664ef44e-c1a0-47b0-9553-2ecdfc6ef840
IsInactiveMailbox        : True
LitigationHoldEnabled    : True
LitigationHoldDuration   : 365.00:00:00
LitigationHoldDate       : 10/25/2021 6:54:57 PM
LitigationHoldOwner      : admin@contoso.com
InPlaceHolds             : {}
ComplianceTagHoldApplied : False
...
DisplayName              : Carol Olson
Name                     : carolo
DistinguishedName        : CN=carolo,OU=Soft Deleted
                           Objects,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange
                           Hosted Organizations,DC=NAMPR06A007,DC=PROD,DC=OUTLOOK,DC=COM
ExchangeGuid             : e646a369-00bf-43d3-837a-8eae8b301d44
IsInactiveMailbox        : True
LitigationHoldEnabled    : False
LitigationHoldDuration   : Unlimited
LitigationHoldDate       :
LitigationHoldOwner      :
InPlaceHolds             : {mbxcdbbb86ce60342489bff371876e7f224:3}
ComplianceTagHoldApplied : False
...
DisplayName              : Megan Bowen
Name                     : meganb
DistinguishedName        : CN=meganb,OU=Soft Deleted
                           Objects,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange
                           Hosted Organizations,DC=NAMPR06A007,DC=PROD,DC=OUTLOOK,DC=COM
ExchangeGuid             : 36ec77cb-c524-468a-a8e8-bfb75e01a176
IsInactiveMailbox        : True
LitigationHoldEnabled    : False
LitigationHoldDuration   : Unlimited
LitigationHoldDate       :
LitigationHoldOwner      :
InPlaceHolds             : {mbx6fe063689d404a5bb9940eed0f0bf5d2:1}
ComplianceTagHoldApplied : True
...
DisplayName              : Mario Necaise
Name                     : marion
DistinguishedName        : CN=marion,OU=Soft Deleted
                           Objects,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange
                           Hosted Organizations,DC=NAMPR06A007,DC=PROD,DC=OUTLOOK,DC=COM
ExchangeGuid             : 0579e039-a695-40d5-8f0a-0dc04f4b4c8f
IsInactiveMailbox        : True
LitigationHoldEnabled    : False
LitigationHoldDuration   : Unlimited
LitigationHoldDate       :
LitigationHoldOwner      :
InPlaceHolds             : {}
ComplianceTagHoldApplied : False
...
DisplayName              : Abraham McMahon
Name                     : abrahamm
DistinguishedName        : CN=abrahamm,OU=Soft Deleted
                           Objects,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange
                           Hosted Organizations,DC=NAMPR06A007,DC=PROD,DC=OUTLOOK,DC=COM
ExchangeGuid             : 55ad8905-4e68-4c8d-940d-e068ec6b51fc
IsInactiveMailbox        : True
LitigationHoldEnabled    : False
LitigationHoldDuration   : Unlimited
LitigationHoldDate       :
LitigationHoldOwner      :
InPlaceHolds             : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
ComplianceTagHoldApplied : False
...
DisplayName              : Pilar Pinilla
Name                     : pilarp
DistinguishedName        : CN=pilarp,OU=Soft Deleted
                           Objects,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange
                           Hosted Organizations,DC=NAMPR06A007,DC=PROD,DC=OUTLOOK,DC=COM
ExchangeGuid             : 8d7867d6-bb6d-4cd8-a51f-09d208f97fcc
IsInactiveMailbox        : True
LitigationHoldEnabled    : False
LitigationHoldDuration   : Unlimited
LitigationHoldDate       :
LitigationHoldOwner      :
InPlaceHolds             : {c0ba3ce811b6432a8751430937152491}
ComplianceTagHoldApplied : False
```

次の表は、上の例から各メールボックスを非アクティブにするために使用された 6 種類のホールドの種類を示しています。
  
|**非アクティブなメールボックス**|**ホールドの種類**|**非アクティブなメールボックスのホールドを識別する方法**|
|:-----|:-----|:-----|
|Ann Beebe  <br/> |訴訟ホールド  <br/> | このプロパティは  `LitigationHoldEnabled`  、メールボックスが訴訟ホールドであることを示すために設定  `True` されます。 <br/><br/> さらに、 `LitigationHoldDuration` メールボックス アイテムが作成日 (送信/受信) の 365 日後に訴訟ホールドの対象にならなくなったことを示す設定 `365.00:00:00` になっています。  <br/><br/> これは `LitigationHoldDate` 、LitigationHold が有効になった日付を示し、 `LitigationHoldOwner` 訴訟ホールドを開始したユーザーを識別します。 <br/> |
|Carol Olson  <br/> |特定のメールボックスに適用される Microsoft Purview コンプライアンス ポータルからアイテム保持ポリシーをMicrosoft 365する  <br/> |プロパティ`InPlaceHolds`には、非アクティブなメールボックスに適用されるMicrosoft 365アイテム保持ポリシーの GUID が含まれています。 これは、GUID がプレフィックスで始まり、末尾が a または `:3`1 で終わる`:2`ため、特定の`mbx`メールボックスに適用されるアイテム保持ポリシーであることを確認できます。 <br/><br/> 詳細については、「 [アイテム保持ポリシーの InPlaceHolds 値の形式について」を](identify-a-hold-on-an-exchange-online-mailbox.md#understanding-the-format-of-the-inplaceholds-value-for-retention-policies)参照してください。  <br/> |
|Megan Bowen <br/> | 保持または保持と削除のアクションを含む保持ラベルMicrosoft 365、メールボックス内の少なくとも 1 つのアイテムに適用されます  <br/> |この `ComplianceTagHoldApplied` プロパティは、 `True` アイテムに保持ラベルまたは保持ラベルと削除ラベルが付けられているかどうかを示します。  <br/><br/> さらに、プロパティには、`InPlaceHolds`非アクティブなメールボックスに適用されるMicrosoft 365アイテム保持ラベル ポリシーの GUID が含まれています。  <br/><br/> 詳細については、「[保持ラベルがフォルダーまたはアイテムに適用されているため、保留中のメールボックスを識別する」を](identify-a-hold-on-an-exchange-online-mailbox.md#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item)参照してください。 <br/>  |
|Mario Necaise  <br/> |Microsoft Purview コンプライアンス ポータルからの組織全体のMicrosoft 365保持ポリシー <br/> |プロパティは  `InPlaceHolds`  空であり、 `LitigationHoldEnabled` `False` `ComplianceTagHoldApplied` 次の値です `False`。 これは、非アクティブなメールボックスが継承している組織に適用されるアイテム保持ポリシー Microsoft 365 1 つまたは複数の (Exchange) 場所全体を示します。 <br/><br/> 詳細については、「[組織全体のアイテム保持ポリシーがメールボックスに適用されていることを確認する方法」を](identify-a-hold-on-an-exchange-online-mailbox.md#how-to-confirm-that-an-organization-wide-retention-policy-is-applied-to-a-mailbox)参照してください。 <br/> |
|Abraham McMahon  <br/> |Microsoft Purview コンプライアンス ポータルでの電子情報開示ケースホールド  <br/> |この  `InPlaceHolds`  プロパティには、非アクティブなメールボックスに配置される電子情報開示ケースホールドの GUID が含まれています。 GUID が  `UniH` プレフィックスで始まっているため、これは電子情報開示ケース ホールドであることがわかります。  <br/><br/> 詳細については、「 [電子情報開示保留](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)」を参照してください。 <br/> |
|Pilar Pinilla  <br/> |インプレース ホールド  <br/> |この  `InPlaceHolds`  プロパティには、非アクティブなメールボックスに配置されるIn-Placeホールドの GUID が含まれています。 GUID がプレフィックスで始まらないので、これはIn-Placeホールドであることを確認できます。  <br/><br/> **注**: 2020 年 10 月 1 日以降、インプレース ホールドの保留期間は変更できなくなります。 In-Placeホールドのみを削除すると、非アクティブなメールボックスが削除されます。 <br/><br/> 詳細については、「 [従来の電子情報開示ツールの廃止](legacy-ediscovery-retirement.md)」を参照してください。 <br/> |

## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>手順 2: 非アクティブなメールボックスの保持期間を変更する

非アクティブなメールボックスに設定されているホールドの種類 (および複数のホールドがあるかどうか) を特定したら、次は、保持期間を変更します。  プロセスは、適用される保留の種類によって異なります。

- [Microsoft 365アイテム保持ポリシーの期間を変更する](#change-the-duration-for-a-microsoft-365-retention-policy)

- [Microsoft 365保持ラベルの期間を変更する](#change-the-duration-for-a-microsoft-365-retention-label)

- [電子情報開示ホールドの期間を変更する](#change-the-duration-for-an-ediscovery-hold)

- [訴訟ホールドの期間を変更する](#change-the-duration-for-a-litigation-hold)

- [In-Placeホールドの期間を変更する](#change-the-duration-for-an-in-place-hold)

### <a name="change-the-duration-for-a-microsoft-365-retention-policy"></a>Microsoft 365アイテム保持ポリシーの期間を変更する

Microsoft 365アイテム保持ポリシーの保持期間を変更するには、まず、Security & Compliance PowerShell のメールボックスのプロパティから`InPlaceHolds`関連付けられた GUID を使用して実行`Get-RetentionCompliancePolicy`して、非アクティブなメールボックスに影響を与えるポリシーを特定する必要があります。

このコマンドを実行するときは、必ず GUID からプレフィックスとサフィックスを削除してください。  たとえば、上記のサンプル情報を使用すると、値を`InPlaceHolds``mbxcdbbb86ce60342489bff371876e7f224:3`取得してから削除`mbx`し`:3`、ポリシー GUID として `cdbbb86ce60342489bff371876e7f224`.  この例では、次を実行します。

```powershell
Get-RetentionCompliancePolicy cdbbb86ce60342489bff371876e7f224 | FL Name
```

ポリシーの名前がわかったら、Microsoft Purview コンプライアンス ポータルでアイテム保持ポリシーを変更するだけです。  通常、アイテム保持ポリシーは複数の場所に適用されるため、ポリシーを変更すると、適用されているすべての場所 (非アクティブとアクティブの両方) に影響します。これには、Exchange以外の場所も含まれる場合があります。  詳細については、「 [アイテム保持ポリシーの作成と構成](create-retention-policies.md)」を参照してください。  

> [!IMPORTANT]
> [保持ロック](retention-preservation-lock.md)が有効になっているアイテム保持ポリシーは、保持期間を延長できますが、減少または削除することはできません。

非アクティブなメールボックス、または特定の非アクティブなメールボックスのみの保持期間を変更する場合は、Azure AD とExchange属性とプロパティを使用して、特定のメールボックスや非アクティブなメールボックスなどのメールボックスの種類を個別にターゲット設定するために使用できる[アダプティブ ポリシー スコープ](retention.md#adaptive-or-static-policy-scopes-for-retention)の展開を検討できます。

### <a name="change-the-duration-for-a-microsoft-365-retention-label"></a>Microsoft 365保持ラベルの期間を変更する

アイテム保持ポリシーと同様に、Microsoft 365アイテム保持ラベルの保持期間を変更する場合は、まず、Security & Compliance PowerShell のメールボックスのプロパティから`InPlaceHolds`関連付けられた GUID を使用して実行`Get-RetentionCompliancePolicy`することで、非アクティブなメールボックス内のコンテンツに影響を与えるラベルを公開するポリシーを特定する必要があります。

このコマンドを実行するときは、必ず GUID からプレフィックスとサフィックスを削除してください。  たとえば、上記のサンプル情報を使用すると、値を`InPlaceHolds``mbx6fe063689d404a5bb9940eed0f0bf5d2:1`取得してから削除`mbx`し`:1`、ポリシー GUID として `6fe063689d404a5bb9940eed0f0bf5d2`.  この例では、次を実行します。

```powershell
Get-RetentionCompliancePolicy 6fe063689d404a5bb9940eed0f0bf5d2 | FL Name
```

ポリシーを特定すると、発行されたラベルとその設定がわかります。  ラベルは個々のアイテムに適用されるため、ポリシーとその設定で発行されたラベルの数によっては、コンテンツに影響を与えているラベルを直接特定できない場合があります。  

各ラベルが適用されるコンテンツを識別するために使用できる方法の 1 つは、 [Content Search](content-search.md) を使用することです。  たとえば、上記のサンプル情報を使用して、ポリシーが複数のラベルを発行するとします。そのうちの 1 つは "HR-Content" という名前です。  [適切なアクセス許可](microsoft-365-compliance-center-permissions.md)を使用すると、[New-ComplianceSearch PowerShell コマンド](/powershell/module/exchange/new-compliancesearch)を使用してコンテンツ検索を実行し、非アクティブなメールボックスのプライマリ SMTP アドレス (ピリオド (`.`) を事前に指定し、検証を`-AllowNotFoundExchangeLocationsEnabled $true`スキップするパラメーターを指定できます。

```powershell
New-ComplianceSearch -Name "MeganB Inactive Mailbox HR-Content Label Search" -ExchangeLocation .meganb@contoso.onmicrosoft.com -AllowNotFoundExchangeLocationsEnabled $true -ContentMatchQuery "compliancetag=HR-Content"
```

検索が作成されたら、次のコマンドを使用して検索を開始します。

```powershell
Start-ComplianceSearch "MeganB Inactive Mailbox HR-Content Label Search"
```

この方法を使用すると、識別されたラベル ポリシーのどのラベルが非アクティブなメールボックス内のコンテンツに適用され、保持期間を変更できるかを特定できます。 保持ラベルは通常、複数の場所に適用されるため、ラベルを変更すると、適用されたすべての場所とラベル付けされたコンテンツに影響します。これには、Exchange以外の場所やコンテンツも含まれる場合があります。 詳細については、「 [アイテム保持ラベルを発行してアプリに適用する](create-apply-retention-labels.md)」を参照してください。

> [!NOTE]
> すべての種類の保持ラベルを変更できるわけではありません。  一部のラベルでは、リテンション期間を長くすることしかできない場合もあれば、保持期間をまったく変更できない場合もあります。

### <a name="change-the-duration-for-an-ediscovery-hold"></a>電子情報開示ホールドの期間を変更する

電子情報開示ケースに関連付けられている保留は無期限の保留であり、変更できる保留期間がないことを意味します。 アイテムは無期限に保持されるか、 [保持が削除されるか](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold) 、ケースが閉じられるまで保持されます。
  
### <a name="change-the-duration-for-a-litigation-hold"></a>訴訟ホールドの期間を変更する

Exchange Online PowerShell を使用して、非アクティブなメールボックスに配置される訴訟ホールドのホールド期間を変更する必要があります。 EAC を使用することはできません。 保持期間を変更するには、次のコマンドを実行します。 この例では、保留期間は無制限の期間に変更されます。
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

結果として、非アクティブなメールボックス内のアイテムは、無期限に、あるいは、ホールドが削除されるか保持期間が別の値に変更されるまで、保持されます。
  
> [!TIP]
> 非アクティブなメールボックスを特定する最もよい方法は、 **Distinguished Name** または **Exchange GUID** の値を使用することです。これらの値のいずれかを使用すると、正しくないメールボックスを誤って指定することを避けられます。

### <a name="change-the-duration-for-an-in-place-hold"></a>インプレース ホールドの期間を変更する

In-Place保留は廃止され、変更できなくなります。 非アクティブなメールボックスにIn-Place保留が適用されている場合、保留期間を変更することはできません。 In-Placeホールドのみを削除すると、非アクティブなメールボックスが削除されます。 詳細については、「 [非アクティブなメールボックスを削除する」を](delete-an-inactive-mailbox.md#remove-in-place-holds)参照してください。
  
## <a name="more-information"></a>詳細情報

- **非アクティブなメールボックス内のアイテムの保持期間はどのように計算されますか。** 保持期間は、メールボックス アイテムを受信または作成した最初の日付から計算されます。
    
- **保持期間を過ぎるとどうなりますか。** [回復可能なアイテム] フォルダー内のアイテムの保持期間を過ぎると、アイテムは非アクティブなメールボックスから完全に削除 (消去) されます。 非アクティブなメールボックスに保持期間が指定されていない場合、回復可能なアイテム フォルダー内のアイテムは削除されません (非アクティブなメールボックスの保留期間が変更されない限り)。 
    
- **EXCHANGE MRM ポリシーは、非アクティブなメールボックスで引き続き処理されますか?**  MRM アイテム保持ポリシーが非アクティブになる前にメールボックスに適用された場合、削除ポリシー ( **削除** アクションで構成された MRM アイテム保持タグ) は、非アクティブなメールボックスで引き続き処理されます。 つまり、MRM 削除ポリシーでタグ付けされたアイテムは、保持期間の有効期限が切れると、回復可能なアイテム フォルダーに移動されます。 それらのアイテムは保持期間を過ぎると非アクティブなメールボックスから消去されます。 非アクティブなメールボックスの保持期間が指定されていない場合、[回復可能なアイテム] フォルダー内のアイテムは無期限に保持されます。

    逆に、非アクティブなメールボックスに割り当てられている MRM アイテム保持ポリシーに含まれるアーカイブ ポリシー ( **MoveToArchive** アクションで構成された MRM リテンション タグ) は無視されます。 つまり、非アクティブなメールボックス内のアーカイブ ポリシーのタグが付けられたアイテムは、保持期間を過ぎてもプライマリ メールボックスに残ります。 それらのアイテムは、アーカイブ メールボックスやアーカイブ メールボックス内の [回復可能なアイテム] フォルダーに移動されません。 無期限に保持されます。
    > [!NOTE]
    > Exchangeアイテム保持ポリシー (Exchange Onlineのメッセージング レコード管理または MRM 機能) を適用しても、ユーザー アカウントが削除されたときに非アクティブなメールボックスは作成されません。

- **通常のメールボックスと同様に、マネージド フォルダー アシスタント (MFA) も非アクティブなメールボックスを処理します。** Exchange Onlineでは、MFA はメールボックスを約 7 日に 1 回処理します。 非アクティブなメールボックスの保持期間を変更したなら、 **Start-ManagedFolderAssistant** コマンドレットを使用して、非アクティブなメールボックスの新しい保持期間の処理を直ちに開始します。 次のコマンドを実行します。 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **多数 `InPlaceHolds` が非アクティブなメールボックスに配置されている場合、すべての保留 GUID が表示されるわけではありません。** 次のコマンドを実行して、非アクティブなメールボックスに配置されているすべての `InPlaceHolds` GUID を表示できます。
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
