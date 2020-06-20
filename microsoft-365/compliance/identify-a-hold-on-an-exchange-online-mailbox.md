---
title: Exchange Online メールボックスに保存されている保留の種類を特定する方法
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365 の Exchange Online メールボックスに配置できるさまざまな種類の保留リストを特定する方法について説明します。
ms.openlocfilehash: a1629e96352a8b98d1122e9b31b968cdce9efa33
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817606"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>Exchange Online メールボックスに保存されている保留の種類を特定する方法

この記事では、Microsoft 365 の Exchange Online メールボックスに配置された保留リストを特定する方法について説明します。

Microsoft 365 は、組織がメールボックスの内容が完全に削除されないようにする方法をいくつか提供します。 これにより、組織は、コンプライアンス規制や、法的およびその他の調査時に、コンテンツを保持することができます。 Office 365 の保持機能 (*保留*とも呼ばれます) の一覧を以下に示します。

- **[訴訟ホールド](create-a-litigation-hold.md):** Exchange Online のユーザーメールボックスに適用されるホールド。

- **[電子情報開示の保留リスト](create-ediscovery-holds.md):** セキュリティ/コンプライアンスセンターのコア電子情報開示ケースに関連付けられているホールド。 電子情報開示の保持は、Microsoft 365 グループおよび Microsoft Teams のユーザーメールボックスおよび対応するメールボックスに適用できます。

- **[インプレース保持](https://docs.microsoft.com/Exchange/security-and-compliance/create-or-remove-in-place-holds):** Exchange Online の Exchange 管理センターでインプレース電子情報開示 & 保持ツールを使用して、ユーザーメールボックスに適用されるホールド。

- ** [Microsoft 365 のアイテム保持ポリシー](retention-policies.md):** Exchange Online のユーザーメールボックスおよび Microsoft 365 グループおよび Microsoft Teams の対応するメールボックス内のコンテンツを保持 (または、保存してから削除する) するように構成できます。 また、ユーザーのメールボックスに格納されている Skype for Business の会話を保持するアイテム保持ポリシーを作成することもできます。

  メールボックスに割り当てることができる Microsoft 365 のアイテム保持ポリシーには、2種類あります。

    - **特定の場所保持ポリシー:** これらは、特定のユーザーのコンテンツの場所に割り当てられるポリシーです。 Exchange Online の PowerShell で、**メールボックスの取得**コマンドレットを使用して、特定のメールボックスに割り当てられているアイテム保持ポリシーに関する情報を取得します。

    - **組織全体のアイテム保持ポリシー:** これらは、組織内のすべてのコンテンツの場所に割り当てられるポリシーです。 組織全体のアイテム保持ポリシーについての情報を取得するには、Exchange Online の PowerShell で、" **get-help/** 組織全体の構成" コマンドレットを使用します。
    
  詳細については、「[アイテム保持ポリシーを組織全体または特定の場所に適用する](create-retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)」セクションを参照してください。

- **[Microsoft 365 の保持ラベル](labels.md):** ユーザーが microsoft 365 の保持ラベル (コンテンツを保持するように構成されているか、コンテンツを保持した後にコンテンツを削除するように構成されている) をメールボックス内の*任意*のフォルダーまたはアイテムに適用すると、メールボックスが訴訟ホールドの対象となっているか、microsoft 365 アイテム保持ポリシー 詳細については、この記事の「[フォルダーまたはアイテムに保持ラベルが適用されているため、保留中のメールボックスを識別](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item)する」を参照してください。

保留中のメールボックスを管理するには、保持期間の変更、一時的または完全に保持を削除する、または Microsoft 365 のアイテム保持ポリシーからメールボックスを除外するなどのタスクを実行できるように、メールボックスに設定されているホールドの種類を特定する必要がある場合があります。 このような場合は、最初の手順として、メールボックスに設定されている保留の種類を特定します。 また、複数のホールド (および異なる種類の保留リスト) を1つのメールボックスに配置することができるため、保留リストを削除または変更する場合は、メールボックスに設定されているすべての保留リストを特定する必要があります。

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a>手順 1: メールボックスに配置された保留リストの GUID を取得する

Exchange Online PowerShell で次の2つのコマンドレットを実行して、メールボックスに配置されている保留リストの GUID を取得できます。 GUID を取得した後、それを使用して、手順2で特定のホールドを識別します。 訴訟ホールドは GUID で識別されません。 訴訟ホールドは、メールボックスに対して有効または無効のどちらかになります。

- **取得-メールボックス:** このコマンドレットを使用して、メールボックスに対して訴訟ホールドが有効になっているかどうかを確認し、メールボックスに割り当てられている電子情報開示の保留リスト、インプレース保持、および Microsoft 365 アイテム保持ポリシーの Guid を取得します。 このコマンドレットの出力は、メールボックスが組織全体のアイテム保持ポリシーから明示的に除外されているかどうかも示します。

- **取得-組織の構成:** このコマンドレットを使用して、組織全体のアイテム保持ポリシーの Guid を取得します。

Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)」を参照してください。

### <a name="get-mailbox"></a>Get-Mailbox

次のコマンドを実行して、メールボックスに適用された保留リストと Microsoft 365 アイテム保持ポリシーに関する情報を取得します。

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> InPlaceHolds プロパティに含まれる値が多すぎて、一部が表示されていない場合は、コマンドを実行して `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` 各 GUID を別々の行に表示することができます。

次の表は、InPlaceHolds**コマンドレットを実行**するときに、 *InPlaceHolds*プロパティの値に基づいてさまざまな種類の保留リストを識別する方法を示しています。


|ホールドの種類  |値の例  |保留リストを識別する方法  |
|---------|---------|---------|
|訴訟ホールド     |    `True`     |     *LitigationHoldEnabled*プロパティがに設定されている場合、メールボックスに対して訴訟ホールドが有効になり `True` ます。    |
|電子情報開示の保留     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   *InPlaceHolds プロパティ*には、セキュリティ/コンプライアンスセンターの電子情報開示ケースに関連付けられている保留リストの GUID が含まれています。 GUID は `UniH` プレフィックス (統合された保持を示す) で始まっているため、これが電子情報開示の保留であることを伝えることができます。      |
|インプレース ホールド     |     `c0ba3ce811b6432a8751430937152491` <br/> または <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     *InPlaceHolds*プロパティには、メールボックスに配置されたインプレースホールドの GUID が含まれています。 GUID がプレフィックスで始まっていないか、プレフィックスで始まっていないため、これはインプレースホールドであると判断でき `cld` ます。     |
|メールボックスに特に適用される Microsoft 365 アイテム保持ポリシー     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> または <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     InPlaceHolds プロパティには、メールボックスに適用される特定の場所保持ポリシーの Guid が含まれています。 GUID はまたはプレフィックスで始まっているため、アイテム保持ポリシーを識別でき `mbx` `skp` ます。 プレフィックスは、 `skp` アイテム保持ポリシーがユーザーのメールボックス内の Skype For business の会話に適用されることを示します。    |
|組織全体の Microsoft 365 保持ポリシーから除外されます。     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     メールボックスが組織全体の Microsoft 365 アイテム保持ポリシーから除外されている場合、メールボックスが除外されるアイテム保持ポリシーの GUID は InPlaceHolds プロパティに表示され、接頭辞で識別され `-mbx` ます。    |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
**メールボックスの取得**コマンドレットを実行したときに*InPlaceHolds*プロパティが空の場合、依然として、1つ以上の組織全体の Microsoft 365 保持ポリシーがメールボックスに適用されている可能性があります。 Exchange Online PowerShell で次のコマンドを実行して、組織全体の Microsoft 365 保持ポリシーの Guid の一覧を取得します。

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> InPlaceHolds プロパティに含まれる値が多すぎて、一部が表示されていない場合は、コマンドを実行して `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` 各 GUID を別々の行に表示することができます。

次の表では、組織全体のさまざまな種類と、InPlaceHolds**コマンドレットを実行**するときに、 *InPlaceHolds*プロパティに含まれている guid に基づいて各種類を識別する方法について説明します。


|ホールドの種類  |値の例  |説明  |
|---------|---------|---------|
|Exchange メールボックス、Exchange パブリックフォルダー、およびチームチャットに適用される Microsoft 365 保持ポリシー    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   Exchange メールボックス、Exchange パブリックフォルダー、および Microsoft Teams の1xN チャットに適用される組織全体のアイテム保持ポリシーは、プレフィックスで始まる Guid によって識別され `mbx` ます。 注: 1xN チャットは、個々のチャット参加者のメールボックスに格納されます。      |
|Microsoft 365 のアイテム保持ポリシーを Microsoft 365 グループおよび Teams チャネルメッセージに適用する     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    Microsoft 365 グループおよび Microsoft Teams のチャネルメッセージに適用される組織全体のアイテム保持ポリシーは、プレフィックスで始まる Guid によって識別され `grp` ます。 注チャネルメッセージは、Microsoft teams に関連付けられているグループメールボックスに格納されます。     |

Microsoft Teams に適用される詳細なアイテム保持ポリシーについては、「[アイテム保持ポリシーの概要](create-retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)」の「teams の場所」セクションを参照してください。

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>保持ポリシーの InPlaceHolds 値の形式について

Microsoft 365 アイテム保持ポリシーとして InPlaceHolds プロパティのアイテムを識別するプレフィックス (、skp、または grp) に加えて、この値には、ポリシーに対して構成されている保持アクションの種類を識別するサフィックスも含まれています。 たとえば、次の例では、アクションのサフィックスが太字で強調表示されています。

   `skp127d7cf1076947929bf136b7a2a8c36f`**: 1**

   `mbx7cfb30345d454ac0a989ab3041051209`**: 2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**: 3**

次の表では、3つの保持アクションを定義します。

|値  |説明  |
|---------|---------|
|**1**     | アイテムを削除するようにアイテム保持ポリシーが構成されていることを示します。 ポリシーはアイテムを保持しません。        |
|**2**    |    アイテム保持ポリシーがアイテムを保持するように構成されていることを示します。 保持期間が経過すると、ポリシーによってアイテムが削除されることはありません。     |
|**3**     |   アイテム保持ポリシーがアイテムを保持するように構成されていて、保存期間が経過した後にアイテムを削除することを示します。      |

保持アクションの詳細については、「[アイテム保持ポリシーの概要](create-retention-policies.md#retaining-content-for-a-specific-period-of-time)」の「特定の期間だけコンテンツを保持する」を参照してください。
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a>手順 2: GUID を使用して保留リストを識別する

メールボックスに適用されている保留リストの GUID を取得した後、次の手順として、その GUID を使用して保留リストを識別します。 次のセクションでは、ホールド GUID を使用して、保留 (およびその他の情報) の名前を識別する方法を示します。

### <a name="ediscovery-holds"></a>電子情報開示の保留

セキュリティ & コンプライアンスセンターの PowerShell で次のコマンドを実行して、メールボックスに適用されている電子情報開示ホールドを識別します。 手順1で特定した電子情報開示の保留リストの GUID (UniH プレフィックスを含まない) を使用します。 最初のコマンドは、保留リストに関する情報を含む変数を作成します。 この変数は、他のコマンドで使用されます。 2番目のコマンドは、保留が関連付けられている電子情報開示ケースの名前を表示します。 3番目のコマンドは、保留リストの名前と、保留が適用されるメールボックスのリストを表示します。

```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold | FL Name,ExchangeLocation
```

セキュリティ & コンプライアンスセンター PowerShell に接続するには、「 [connect To security & powershell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)」を参照してください。

### <a name="in-place-holds"></a>インプレース ホールド

Exchange Online PowerShell で次のコマンドを実行して、メールボックスに適用されているインプレースホールドを識別します。 手順1で特定したインプレースホールドの GUID を使用します。 このコマンドは、保留リストの名前と、保留が適用されるメールボックスのリストを表示します。

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

インプレース保持の GUID がプレフィックスで始まる場合は、 `cld` 前のコマンドを実行するときに必ずプレフィックスを指定してください。

> [!IMPORTANT]
> メールボックスのコンテンツを保持するためのさまざまな方法に投資し続けるため、Exchange 管理センター (EAC) でのインプレースホールドの廃止を発表しています。 2020年7月1日以降、Exchange Online に新しいインプレースホールドを作成することはできません。 ただし、EAC でインプレースホールドを管理することも、Exchange Online PowerShell で**get-mailboxsearch**コマンドレットを使用することもできます。 ただし、2020年10月1日以降、インプレースホールドを管理することはできません。 これらのアドインは、EAC または**get-mailboxsearch**コマンドレットを使用して削除します。 インプレースホールドが廃止された場合の詳細については、「[従来の電子情報開示ツールの廃止](legacy-ediscovery-retirement.md)」を参照してください。

### <a name="microsoft-365-retention-policies"></a>Microsoft 365 のアイテム保持ポリシー

セキュリティ & コンプライアンスセンターの PowerShell で次のコマンドを実行して、メールボックスに適用されている Microsoft 365 アイテム保持ポリシー (組織全体または特定の場所) を識別します。 手順1で特定した GUID を使用します (この場合は、[説明]、[skp]、[grp prefix] または [action サフィックス] は含まれません)。

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>フォルダーまたはアイテムに保持ラベルが適用されているため、保留中のメールボックスを識別する

コンテンツを保持するように構成されている、またはメールボックス内の任意のフォルダーまたはアイテムにコンテンツを削除するように、ユーザーが保持ラベルを適用するときには、 *ComplianceTagHoldApplied* mailbox プロパティが**True**に設定されます。 このような場合、メールボックスは、訴訟ホールドの対象であるか、Microsoft 365 のアイテム保持ポリシーに割り当てられているかのように、保留中であると見なされます。 *ComplianceTagHoldApplied*プロパティが**True**に設定されている場合は、次のような状況が発生することがあります。

- メールボックスまたはユーザーのユーザーアカウントが削除されると、メールボックスは[非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)になります。
- メールボックスを無効にすることはできません (有効になっている場合、プライマリメールボックスまたはアーカイブメールボックスのいずれか)。
- メールボックス内のアイテムが予想よりも長く保持されている可能性があります。 これは、メールボックスが保持されているため、完全に削除 (パージ) されたアイテムがないためです。

*ComplianceTagHoldApplied*プロパティの値を表示するには、Exchange Online PowerShell で次のコマンドを実行します。

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

保持ラベルの詳細については、「 [Microsoft 365 の保持ラベルの概要](labels.md)」を参照してください。

## <a name="managing-mailboxes-on-delay-hold"></a>遅延保持時のメールボックスの管理

メールボックスから任意の種類の保留が削除されると、*遅延保持*が適用されます。 これは、データがメールボックスから完全に削除 (パージ) されないように、保留リストの実際の削除が30日間遅延されることを意味します。 これにより、管理者は、保留が解除された後に削除されるメールボックスアイテムを検索したり、回復したりする機会を得ることができます。 次回管理フォルダーアシスタントがメールボックスを処理し、ホールドが削除されたことを検出すると、メールボックスに遅延保持が適用されます。 具体的には、管理フォルダーアシスタントが次のいずれかのメールボックスプロパティを**True**に設定すると、遅延保持がメールボックスに適用されます。

- **DelayHoldApplied:** このプロパティは、ユーザーのメールボックスに格納されている電子メール関連のコンテンツ (Outlook および Outlook on the web を使用しているユーザーが生成) に適用されます。

- **DelayReleaseHoldApplied:** このプロパティは、ユーザーのメールボックスに格納されているクラウドベースのコンテンツ (Microsoft Teams、Microsoft Forms、microsoft Yammer などの Outlook 以外のアプリによって生成される) に適用されます。 Microsoft アプリによって生成されたクラウドデータは、通常、ユーザーのメールボックス内の隠しフォルダーに格納されます。
 
 メールボックスに遅延保持が設定されている場合 (前述のいずれかのプロパティが**True**に設定されている場合)、メールボックスが訴訟ホールドの対象であったかのように、そのメールボックスは依然として保留時間が無制限であると見なされます。 30日後、遅延保持が有効期限切れになり、Microsoft 365 は遅延ホールド (DelayHoldApplied または DelayReleaseHoldApplied プロパティを**False**に設定して) を自動的に削除して、ホールドが解除されるようにします。 これらのプロパティのいずれかを**False**に設定すると、削除対象としてマークされている対応するアイテムは、管理フォルダーアシスタントによって次回メールボックスが処理されるときに削除されます。

メールボックスの DelayHoldApplied プロパティと DelayReleaseHoldApplied プロパティの値を表示するには、Exchange Online PowerShell で次のコマンドを実行します。

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

遅延の期限が切れるまでの遅延を削除するには、Exchange Online PowerShell で次のコマンドのいずれか (または両方) を実行できます。変更するプロパティによって異なります。 
 
```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

または
 
```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

*RemoveDelayHoldApplied*パラメーターまたは*RemoveDelayReleaseHoldApplied*パラメーターを使用するには、Exchange Online で法的情報保留の役割が割り当てられている必要があります。 

非アクティブなメールボックスの遅延ホールドを削除するには、Exchange Online PowerShell で次のいずれかのコマンドを実行します。

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

または

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> 以前のコマンドで非アクティブなメールボックスを指定するには、その識別名または Exchange GUID 値を使用するのが最善の方法です。 これらの値のいずれかを使用すると、正しくないメールボックスを誤って指定することを避けられます。 

遅延保留を管理するためのこれらのパラメーターの使用の詳細については、「[メールボックスの設定](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)」を参照してください。

遅延ホールド時にメールボックスを管理する場合は、次の点に注意してください。

- DelayHoldApplied または DelayReleaseHoldApplied プロパティが**True**に設定されている場合、メールボックス (または対応するユーザーアカウント) が削除されると、メールボックスは非アクティブなメールボックスになります。 これは、いずれかのプロパティが**True**に設定されていて、保留中のメールボックスを削除すると非アクティブなメールボックスが保持されていると見なされるためです。 メールボックスを削除して非アクティブなメールボックスにしないようにするには、両方のプロパティを**False**に設定する必要があります。

- 前述したように、メールボックスは、DelayHoldApplied または DelayReleaseHoldApplied プロパティが**True**に設定されている場合、保持期間が無制限であると見なされます。 ただし、これはメールボックス内の*すべて*のコンテンツが保持されるという意味ではありません。 各プロパティに設定されている値によって決まります。 たとえば、ホールドがメールボックスから削除されているため、両方のプロパティが**True**に設定されているとします。 その後、( *RemoveDelayReleaseHoldApplied*パラメーターを使用して) Outlook 以外のクラウドデータに適用される遅延ホールドのみを削除します。 管理フォルダーアシスタントが次回メールボックスを処理するときに、削除がマークされた Outlook 以外のアイテムは削除されます。 DelayHoldApplied プロパティが**True**に設定されている場合でも、削除対象としてマークされた Outlook アイテムは削除されません。 反対に、DelayHoldApplied が**False**に設定され、DelayReleaseHoldApplied が**true**に設定されている場合は、削除がマークされた Outlook アイテムのみが削除されます。

## <a name="next-steps"></a>次の手順

メールボックスに適用されている保留リストを特定した後は、保留の期間の変更、一時的または完全に保持の削除、または Microsoft 365 のアイテム保持ポリシーから非アクティブなメールボックスを除外するなどのタスクを実行できます。 保留に関連するタスクの実行の詳細については、以下のいずれかのトピックを参照してください。

- セキュリティ & コンプライアンスセンターの PowerShell で、組織全体の Microsoft 365 保持ポリシーからメールボックスを除外するには、 [new-retentioncompliancepolicy-AddExchangeLocationException \<user mailbox> ](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy?view=exchange-ps)コマンドを実行します。 このコマンドは、 *Exchangelocation*プロパティの値がと等しいアイテム保持ポリシーにのみ使用でき `All` ます。

- Exchange Online PowerShell で[ExcludeFromOrgHolds \<hold GUID without prefix or suffix> ](https://docs.microsoft.com/powershell/module/exchange/set-mailbox?view=exchange-ps)コマンドを実行して、組織全体の Microsoft 365 保持ポリシーから非アクティブなメールボックスを除外します。

- [非アクティブなメールボックスの保持期間を変更する](change-the-hold-duration-for-an-inactive-mailbox.md)

- [非アクティブなメールボックスを削除する](delete-an-inactive-mailbox.md)

- [保留中のクラウド ベースのメールボックスの [回復可能なアイテム] フォルダーのアイテムを削除する](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
