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
description: メールボックスをOffice 365した後、非アクティブなメールボックスに割り当てられている保持ポリシーまたは保持ポリシー Office 365期間を変更します。
ms.openlocfilehash: 1698a252cad4cebcb09b7c3695b2cecf3184ba1f
ms.sourcegitcommit: a15ea6bc8f60895e791a08a5a88d346c6581ea38
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2021
ms.locfileid: "61144976"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>非アクティブなメールボックスの保持期間を変更する

非 [アクティブなメールボックス](inactive-mailboxes-in-office-365.md) とは、元従業員の電子メールが組織を離れた後に保持するために使用されるメールボックスの状態です。 メールボックスは、ユーザー オブジェクトが削除される前に、該当する保持が適用Microsoft 365非アクティブになります。  次の種類の保留リストは、ユーザー アカウントの削除時に非アクティブなメールボックスの作成を開始します。

- [Microsoft 365保持ポリシーとラベルの保持または](retention.md)保持と削除の設定

- 電子情報開示ケースに[関連付けられた保留](ediscovery.md)

- [訴訟ホールド](create-a-litigation-hold.md)

- 既存の保留In-Placeします。

> [!IMPORTANT]
> 上記の保持は、Microsoft 365 ユーザー アカウントの削除時にメールボックスが強制的に非アクティブになりますが、非アクティブなメールボックスの使用を積極的に計画する場合は、Microsoft 365 保持を使用強く推奨します。
>
> - 電子情報開示ホールドは、法的な問題に関連する特定の時間制限付きケースを対象とします。 ある時点で、法的ケースはおそらく終了し、ケースに関連付けられている保留リストは削除され、電子情報開示ケースは閉じ (または削除) されます。 非アクティブなメールボックスに配置された保留リストが電子情報開示ケースに関連付けられている場合、保留が解放された場合、または電子情報開示ケースが閉じたり削除された場合、非アクティブなメールボックスは完全に削除されます。
>
> - In-Place管理センターの保留Exchangeが廃止されました。 2020 年 7 月 1 日の現在、In-Placeで新しい保留リストを作成Exchange Online。 2020 年 10 月 1 日現在、インプレイスホールドの保持期間を変更できなくなりました。 保持が適用されている非アクティブなIn-Placeは、保留リストを削除することによってのみIn-Placeできます。 保持中の既存の非アクティブIn-Place保持は、保留が削除されるまで保持されます。 保留リストの削除のIn-Placeについては、「従来の電子情報開示ツールの使用を取り除 [く」を参照してください](legacy-ediscovery-retirement.md)。
>
> - [訴訟ホールド](create-a-litigation-hold.md) は、メールボックス内のコンテンツを保持し、ユーザー アカウントが削除された後に非アクティブにする代替方法として引き続きサポートされます。 ただし、古いテクノロジでは、代わりに、Microsoft 365使用することをお勧めします。

非アクティブになった後、回復可能なアイテム フォルダー[](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder)を含むメールボックスの内容は、非アクティブになる前にメールボックスに配置された保留が適用されなくなるまで保持されます。  

無期限の保持専用の Microsoft 365 保持ポリシーまたはラベル、電子情報開示ケース、訴訟ホールド (構成されていない) に関連付けられた保留など、該当するホールドが時間ベースではない場合、メールボックスコンテンツは保持が削除されるまで無期限に保持されます。 ```LitigationHoldDuration```  

ただし、保持が時間ベースの場合、メールボックスのコンテンツは保持期間が経過するまで保持され、その時点で回復可能なアイテム フォルダー内のアイテムは非アクティブなメールボックスから完全に削除 (パージ) されます。

> [!NOTE]
> 非アクティブなメールボックスの場合は、保持ポリシーまたはラベルの保持と削除Microsoft 365使用することをお勧めします。  保持のみ設定を選択すると、回復可能なアイテム フォルダーは保持期間の最後に削除されます。ただし、削除されていない他のアイテムは、非アクティブなメールボックス内に無期限に保持されます。

規制とポリシーが進化するにつれて、非アクティブなメールボックスに割り当てられた保留期間を変更する必要がある場合があります。  次の手順では、これを行う方法について説明します。

## <a name="connect-to-powershell"></a>Connect PowerShell へのアクセス

前述したように、さまざまな種類の保留リストが非アクティブなメールボックスの作成をトリガーする可能性があります。  このため、非アクティブなメールボックスに適用される保持期間を変更するには、まず、そのメールボックスに影響を与えるホールドの種類を特定する必要があります。  これを行うには、Exchange Online PowerShell を使用して保留の種類を特定し、非アクティブなメールボックスが Microsoft 365 保持ポリシーまたはラベルの影響を受ける場合は、セキュリティとコンプライアンス センター PowerShell を使用して特定のポリシーを識別する必要があります。

- コンプライアンス センター powerShell Exchange Onlineセキュリティ &接続するには、次のいずれかのトピックを参照してください。

  - [Exchange Online PowerShell への接続](/powershell/exchange/connect-to-exchange-online-powershell)

  - [セキュリティ/コンプライアンス センターの PowerShell に接続する](/powershell/exchange/connect-to-scc-powershell)

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>手順 1: 非アクティブなメールボックスに設定されているホールドを特定する

異なる種類の保留リストまたは 1 つ以上の Microsoft 365 保持ポリシーが非アクティブなメールボックスに配置される可能性があるため、最初の手順は非アクティブなメールボックスの保留リストを識別します。
  
PowerShell で次Exchange Onlineコマンドを実行して、組織内の特定の非アクティブなメールボックスの保留情報を表示します。
  
```powershell
Get-Mailbox -Identity <identity of inactive mailbox> -InactiveMailboxOnly | FL DisplayName,Name,DistinguishedName,ExchangeGuid,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,LitigationHoldDate,LitigationHoldOwner,InPlaceHolds,ComplianceTagHoldApplied
```

複数の非アクティブなメールボックスの保留の種類を特定する必要がある場合、組織に多数のメールボックスがある場合は、PowerShell を使用して表示できない場合があります。 この場合、次のコマンドを使用して該当する情報を CSV ファイルにエクスポートし、必要に応じて環境に合 ```Path``` って変更できます。

```powershell
Get-Mailbox -InactiveMailboxOnly -ResultSize Unlimited | Select DisplayName,Name,DistinguishedName,ExchangeGuid,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,LitigationHoldDate,LitigationHoldOwner,InPlaceHolds,ComplianceTagHoldApplied | Export-Csv -NoTypeInformation -Path "C:\Temp\InactiveMailboxHoldTypes.csv"
```

この例では、次の目的で、異なるホールド タイプを持つ 6 つの非アクティブなメールボックスの結果を示します。

> [!NOTE]
> 複数の種類のホールドを含む複数のホールドは、1 つの非アクティブなメールボックスに適用できます。
  
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

次の表は、上記の例から各メールボックスを非アクティブにするために使用された 6 つの異なる保留の種類を示しています。
  
|**非アクティブなメールボックス**|**ホールドの種類**|**非アクティブなメールボックスのホールドを識別する方法**|
|:-----|:-----|:-----|
|Ann Beebe  <br/> |訴訟ホールド  <br/> | この  `LitigationHoldEnabled`  プロパティは、メールボックスが  `True` 訴訟ホールド中であることを示す設定です。 <br/><br/> さらに、メールボックス アイテムが作成日 (送信/受信) から 365 日後に訴訟ホールドの対象とならなくなることを示す設定 `LitigationHoldDuration` `365.00:00:00` が設定されています。  <br/><br/> 訴訟 `LitigationHoldDate` ホールドが有効にされた日付を示し、訴訟ホールドを開始 `LitigationHoldOwner` した人物を識別します。 <br/> |
|Carol Olson  <br/> |Microsoft 365メールボックスに適用されるMicrosoft 365 コンプライアンス センターアイテム保持ポリシー  <br/> |この `InPlaceHolds` プロパティには、非アクティブなMicrosoft 365適用されるアイテム保持ポリシーの GUID が含まれる。 GUID はプレフィックスで始まり、またはで終わるので、これは特定のメールボックスに適用される保持ポリシー `mbx` です `:2` `:3` 。 <br/><br/> 詳細については、「保持ポリシー [の InPlaceHolds 値の形式について」を参照してください](identify-a-hold-on-an-exchange-online-mailbox.md#understanding-the-format-of-the-inplaceholds-value-for-retention-policies)。  <br/> |
|Megan Bowen <br/> | Microsoft 365保持または削除アクションを持つアイテム保持ラベルは、メールボックス内の少なくとも 1 つのアイテムに適用されます。  <br/> |プロパティ `ComplianceTagHoldApplied` は、アイテムに保持ラベルまたは保持ラベルと削除ラベルが付 `True` いたラベルを示しています。  <br/><br/> さらに、このプロパティには、非アクティブなメールボックスにMicrosoft 365保持ラベル ポリシーの GUID `InPlaceHolds` が含まれる。  <br/><br/> 詳細については、「保持ラベルがフォルダーまたはアイテムに適用されたため、保持中のメールボックスを識別する」 [を参照してください。](identify-a-hold-on-an-exchange-online-mailbox.md#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) <br/>  |
|Mario Necaise  <br/> |組織全体のMicrosoft 365アイテム保持ポリシー Microsoft 365 コンプライアンス センター  <br/> |プロパティ  `InPlaceHolds`  は空で `LitigationHoldEnabled` 、is `False` および is `ComplianceTagHoldApplied` `False` です。 これは、非アクティブなメールボックスが継承Exchange組織Microsoft 365保持ポリシーの 1 つ以上の場所が含まれるかどうかを示します。 <br/><br/> 詳細については、「組織全体のアイテム保持ポリシーがメールボックスに適用されるのを確認する [方法」を参照してください。](identify-a-hold-on-an-exchange-online-mailbox.md#how-to-confirm-that-an-organization-wide-retention-policy-is-applied-to-a-mailbox) <br/> |
|Abraham McMahon  <br/> |電子情報開示ケースの保持Microsoft 365 コンプライアンス センター  <br/> |このプロパティには、非アクティブなメールボックスに配置された電子情報開示ケースホールド  `InPlaceHolds`  の GUID が含まれる。 GUID が  `UniH` プレフィックスで始まっているため、これは電子情報開示ケース ホールドであることがわかります。  <br/><br/> 詳細については、「電子情報開示ホールド [」を参照してください](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)。 <br/> |
|Pilar Pinilla  <br/> |インプレース ホールド  <br/> |プロパティ  `InPlaceHolds`  には、非アクティブなメールボックスIn-Place保留リストの GUID が含まれる。 GUID はプレフィックスで始In-Place、これは保留の一部です。  <br/><br/> **注**: 2020 年 10 月 1 日現在、インプレイスホールドの保持期間は変更できません。 非アクティブなメールボックスの削除In-Place保持するユーザーのみを削除できます。 <br/><br/> 詳細については、「従来の電子 [情報開示ツールの削除」を参照してください](legacy-ediscovery-retirement.md)。 <br/> |

## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>手順 2: 非アクティブなメールボックスの保持期間を変更する

非アクティブなメールボックスに設定されているホールドの種類 (および複数のホールドがあるかどうか) を特定したら、次は、保持期間を変更します。  プロセスは、適用される保留の種類によって異なります。

- [アイテム保持ポリシーの期間Microsoft 365変更する](#change-the-duration-for-a-microsoft-365-retention-policy)

- [アイテム保持ラベルの期間Microsoft 365変更する](#change-the-duration-for-a-microsoft-365-retention-label)

- [電子情報開示ホールドの期間を変更する](#change-the-duration-for-an-ediscovery-hold)

- [訴訟ホールドの期間を変更する](#change-the-duration-for-a-litigation-hold)

- [保留の期間をIn-Placeする](#change-the-duration-for-an-in-place-hold)

### <a name="change-the-duration-for-a-microsoft-365-retention-policy"></a>アイテム保持ポリシーの期間Microsoft 365変更する

Microsoft 365 アイテム保持ポリシーの保持期間を変更するには、セキュリティとコンプライアンス センター PowerShell のメールボックスのプロパティから関連付けられた GUID を使用して実行して、非アクティブなメールボックスに影響を与えるポリシーを最初に特定する必要があります。 `Get-RetentionCompliancePolicy` `InPlaceHolds`

このコマンドを実行する場合は、必ず GUID からプレフィックスとサフィックスを削除してください。  たとえば、上記のサンプル情報を使用すると、その値を取得して削除し、ポリシー `InPlaceHolds` `mbxcdbbb86ce60342489bff371876e7f224:3` GUID `mbx` `:3` を取得します `cdbbb86ce60342489bff371876e7f224` 。  この例では、次のコマンドを実行します。

```powershell
Get-RetentionCompliancePolicy cdbbb86ce60342489bff371876e7f224 | FL Name
```

ポリシーの名前が分かったら、コンプライアンス センターで保持ポリシーをMicrosoft 365できます。  通常、アイテム保持ポリシーは複数の場所に適用されるので、ポリシーを変更すると、非アクティブとアクティブの両方の適用場所 (Exchange 以外の場所も含まれる場合があります) に影響を与える点に注意してください。  詳細については、「アイテム保持ポリシーの [作成と構成」を参照してください](create-retention-policies.md)。  

> [!IMPORTANT]
> 保持ロックが有効 [になっているアイテム](retention-preservation-lock.md) 保持ポリシーでは、保持期間が延長されますが、減少または削除は行えなく場合があります。

非アクティブなメールボックス、または特定の非アクティブなメールボックスの保持期間のみを変更する場合は、Azure AD 属性と Exchange[](retention.md#adaptive-or-static-policy-scopes-for-retention)属性とプロパティを使用して、特定のメールボックス (非アクティブ メールボックスなど) を個別にターゲットに設定できるアダプティブ ポリシー スコープを展開する場合があります。

### <a name="change-the-duration-for-a-microsoft-365-retention-label"></a>アイテム保持ラベルの期間Microsoft 365変更する

保持ポリシーと同様に、Microsoft 365 保持ラベルの保持期間を変更する場合は、セキュリティとコンプライアンス センター PowerShell のメールボックスのプロパティから関連付けられた GUID を使用して実行することにより、非アクティブなメールボックス内のコンテンツに影響を与えるラベルを発行するポリシーを最初に特定する必要があります。 `Get-RetentionCompliancePolicy` `InPlaceHolds`

このコマンドを実行する場合は、必ず GUID からプレフィックスとサフィックスを削除してください。  たとえば、上記のサンプル情報を使用すると、その値を取得して削除し、ポリシー `InPlaceHolds` `mbx6fe063689d404a5bb9940eed0f0bf5d2:1` GUID `mbx` `:1` を取得します `6fe063689d404a5bb9940eed0f0bf5d2` 。  この例では、次のコマンドを実行します。

```powershell
Get-RetentionCompliancePolicy 6fe063689d404a5bb9940eed0f0bf5d2 | FL Name
```

ポリシーを特定したら、発行済みラベルとその設定を知る必要があります。  ラベルは個々のアイテムに適用されます。ポリシーで発行されたラベルの数と設定によっては、コンテンツに影響を与えるラベルを直接識別できない場合があります。  

各ラベルが適用するコンテンツを識別するために使用できる方法の 1 つは、コンテンツ検索 [を使用する方法です](content-search.md)。  たとえば、上記のサンプル情報を使用して、ポリシーが複数のラベルを発行するとします。そのうちの 1 つは "HR-Content" という名前です。  正しい [アクセス](microsoft-365-compliance-center-permissions.md)許可を使用すると [、New-ComplianceSearch PowerShell](/powershell/module/exchange/new-compliancesearch)コマンドを使用してコンテンツ検索を実行し、非アクティブなメールボックスのプライマリ SMTP アドレスを指定し、事前にピリオド ( ) を付け、検証をスキップするパラメーターを指定 `.` `-AllowNotFoundExchangeLocationsEnabled $true` できます。

```powershell
New-ComplianceSearch -Name "MeganB Inactive Mailbox HR-Content Label Search" -ExchangeLocation .meganb@contoso.onmicrosoft.com -AllowNotFoundExchangeLocationsEnabled $true -ContentMatchQuery "compliancetag=HR-Content"
```

検索が作成されると、次のコマンドを使用して検索を開始します。

```powershell
Start-ComplianceSearch "MeganB Inactive Mailbox HR-Content Label Search"
```

この方法を使用すると、非アクティブなメールボックス内のコンテンツに適用される識別されたラベル ポリシーのラベルを特定して、保持期間を変更できます。 通常、保持ラベルは複数の場所に適用されるので、ラベルを変更すると、適用された場所とラベル付きコンテンツすべてが影響を受け、Exchange 以外の場所やコンテンツも含まれる場合があります。 詳細については、「アイテム保持ラベルを [作成してアプリに適用する」を参照してください](create-apply-retention-labels.md)。

> [!NOTE]
> すべての種類の保持ラベルを変更できるではありません。  一部のラベルでは、保持時間を増やしたり、保持期間を変更したりできない場合があります。

### <a name="change-the-duration-for-an-ediscovery-hold"></a>電子情報開示ホールドの期間を変更する

電子情報開示ケースに関連付けられた保留は無期限の保留です。つまり、変更できる保持期間はありません。 アイテムは永遠に保持されます。またはホールドが [削除されるまで](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold) 、またはケースが閉じられます。
  
### <a name="change-the-duration-for-a-litigation-hold"></a>訴訟ホールドの期間を変更する

非アクティブなメールボックスExchange Online訴訟ホールドの保持期間を変更するには、PowerShell を使用する必要があります。 EAC を使用することはできません。 保持期間を変更するには、次のコマンドを実行します。 この例では、保持期間は無制限の期間に変更されます。
  
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
    
- **非アクティブなメールボックスExchange MRM ポリシーは引き続き処理されますか?**  MRM アイテム保持ポリシーが非アクティブになる前にメールボックスに適用された場合、削除ポリシー (削除アクションで構成されたMRM 保持タグ) は、非アクティブなメールボックスで引き続き処理されます。 つまり、MRM 削除ポリシーでタグ付けされたアイテムは、保持期間が経過すると回復可能なアイテム フォルダーに移動されます。 それらのアイテムは保持期間を過ぎると非アクティブなメールボックスから消去されます。 非アクティブなメールボックスの保持期間が指定されていない場合、[回復可能なアイテム] フォルダー内のアイテムは無期限に保持されます。

    逆に、非アクティブなメールボックスに割り当てられた MRM 保持ポリシーに含まれるアーカイブ ポリシー **(MoveToArchive** アクションで構成された MRM 保持タグ) は無視されます。 つまり、非アクティブなメールボックス内のアーカイブ ポリシーのタグが付けられたアイテムは、保持期間を過ぎてもプライマリ メールボックスに残ります。 それらのアイテムは、アーカイブ メールボックスやアーカイブ メールボックス内の [回復可能なアイテム] フォルダーに移動されません。 無期限に保持されます。
    > [!NOTE]
    > ユーザー アカウントExchange削除しても、ユーザー 保持ポリシー (Exchange Online のメッセージング レコード管理 (MRM) 機能) を適用しても、非アクティブなメールボックスは作成されません。

- **通常のメールボックスと同様に、管理フォルダー アシスタント (MFA) は非アクティブなメールボックスも処理します。** このExchange Online MFA は約 7 日に 1 回メールボックスを処理します。 非アクティブなメールボックスの保持期間を変更したなら、 **Start-ManagedFolderAssistant** コマンドレットを使用して、非アクティブなメールボックスの新しい保持期間の処理を直ちに開始します。 次のコマンドを実行します。 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **多くの `InPlaceHolds` ユーザーが非アクティブなメールボックスに配置されている場合、すべての保留 GUID が表示されるのではありません。** 次のコマンドを実行して、非アクティブなメールボックスに配置されているすべての GUID `InPlaceHolds` を表示できます。
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
