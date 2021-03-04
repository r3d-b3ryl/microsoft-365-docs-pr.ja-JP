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
description: Microsoft 365 の Exchange Online メールボックスに配置できるさまざまな種類の保留リストを識別する方法について説明します。
ms.openlocfilehash: a5bea8cd279bb980ba2f8a57950c8a66857ba502
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423628"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>Exchange Online メールボックスに保存されている保留の種類を特定する方法

この記事では、Microsoft 365 の Exchange Online メールボックスに配置された保留を識別する方法について説明します。

Microsoft 365 では、組織がメールボックスコンテンツが完全に削除されるのを防ぐ方法がいくつか用意されています。 これにより、組織はコンプライアンス規制を満たすために、または法的および他の種類の調査中にコンテンツを保持できます。 365 の保持機能 (ホールドとも呼 *ばれる)* の一Officeします。

- **[訴訟ホールド](create-a-litigation-hold.md):** Exchange Online のユーザー メールボックスに適用される保持。

- **[電子情報開示の保持](create-ediscovery-holds.md):** セキュリティとコンプライアンス センターの Core 電子情報開示ケースに関連付けられている保持。 電子情報開示ホールドは、ユーザー メールボックスと、Microsoft 365 グループおよび Microsoft Teams の対応するメールボックスに適用できます。

- **[インプレイス保持](https://docs.microsoft.com/Exchange/security-and-compliance/create-or-remove-in-place-holds):** Exchange Online の Exchange 管理センターで電子情報開示In-Place保持&を使用してユーザー メールボックスに適用される保持。 

   > [!NOTE]
   > In-Place保留リストは廃止され、保留リストを作成したりIn-Placeメールボックスに適用したりすることはできません。 ただし、In-Place保持は組織内のメールボックスに引き続き適用される可能性があります。これがこの記事に含まれている理由です。 詳細については、「従来の電子 [情報開示ツールの削除」を参照してください](legacy-ediscovery-retirement.md#in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center)。

- **[Microsoft 365 アイテム保持ポリシー](retention.md):** Exchange Online および Microsoft 365 グループおよび Microsoft Teams の対応するメールボックス内のユーザー メールボックス内のコンテンツを保持 (または保持および削除) するように構成できます。 ユーザー のメールボックスに格納されている Skype for Business の会話を保持するアイテム保持ポリシーを作成できます。

  メールボックスに割り当て可能な Microsoft 365 アイテム保持ポリシーには、2 種類があります。

    - **特定の場所保持ポリシー:** これらは、特定のユーザーのコンテンツの場所に割り当てられるポリシーです。 Exchange Online **PowerShell の Get-Mailbox** コマンドレットを使用して、特定のメールボックスに割り当てられた保持ポリシーに関する情報を取得します。 この種類のアイテム保持ポリシーの詳細については、「アイテム保持ポリシー[](create-retention-policies.md#a-policy-with-specific-inclusions-or-exclusions)のドキュメントから特定の包含または除外を含むポリシー」セクションを参照してください。

    - **組織全体の保持ポリシー:** これらは、組織内のすべてのコンテンツの場所に割り当てられるポリシーです。 Exchange Online **PowerShell の Get-OrganizationConfig** コマンドレットを使用して、組織全体の保持ポリシーに関する情報を取得します。 この種類のアイテム保持ポリシーの詳細については、アイテム保持ポリシーのドキュメントのセクション [「](create-retention-policies.md#a-policy-that-applies-to-entire-locations) 場所全体に適用されるポリシー」を参照してください。

- **[Microsoft 365](retention.md)** 保持ラベル : ユーザーがメールボックス内の任意のフォルダーまたはアイテムに Microsoft 365 アイテム保持ラベル (コンテンツを保持または保持し、削除するように構成されているラベル) を適用すると、メールボックスが訴訟ホールドに置かれたか、Microsoft 365 アイテム保持ポリシーに割り当てられているかのようにメールボックスに保持が配置されます。 詳細については、この [記事の「](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) 保持ラベルがフォルダーまたはアイテムに適用されたため、保持中のメールボックスを識別する」セクションを参照してください。

保留メールボックスを管理するには、保持期間の変更、保留期間の一時的または完全な削除、Microsoft 365 アイテム保持ポリシーからメールボックスを除外するなどのタスクを実行するために、メールボックスに配置される保留の種類を特定する必要があります。 このような場合、最初の手順は、メールボックスに配置された保留の種類を識別します。 また、1 つのメールボックスに複数の保留リスト (および異なる種類の保留リスト) を配置できるので、保留リストを削除または変更する場合は、メールボックスに置かれたすべての保留リストを識別する必要があります。

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a>手順 1: メールボックスに配置された保留の GUID を取得する

Exchange Online PowerShell で次の 2 つのコマンドレットを実行して、メールボックスに配置された保留リストの GUID を取得できます。 GUID を取得した後、手順 2 で特定のホールドを識別するために GUID を使用します。 訴訟ホールドは GUID によって識別されません。 訴訟ホールドは、メールボックスで有効または無効になります。

- **Get-Mailbox:** このコマンドレットを使用して、メールボックスに対して訴訟ホールドが有効になっているかどうかを判断し、メールボックスに特別に割り当てられている電子情報開示ホールド、In-Place 保持、および Microsoft 365 アイテム保持ポリシーの GUID を取得します。 このコマンドレットの出力は、メールボックスが組織全体の保持ポリシーから明示的に除外されたかどうかを示します。

- **Get-OrganizationConfig:** このコマンドレットを使用して、組織全体の保持ポリシーの GUID を取得します。

Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

### <a name="get-mailbox"></a>Get-Mailbox

次のコマンドを実行して、メールボックスに適用される保留リストと Microsoft 365 アイテム保持ポリシーに関する情報を取得します。

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> InPlaceHolds プロパティに値が多すぎて、すべての値が表示されない場合は、コマンドを実行して各 GUID を個別の行 `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` に表示できます。

次の表では **、Get-Mailbox** コマンドレットを実行するときに *InPlaceHolds* プロパティの値に基づいて、さまざまな種類の保留リストを識別する方法について説明します。

|ホールドの種類  |値の例  |保留を識別する方法  |
|---------|---------|---------|
|訴訟ホールド     |    `True`     |     *LitigationHoldEnabled* プロパティがに設定されている場合、メールボックスに対して訴訟ホールドが有効になります `True` 。    |
|電子情報開示の保留     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   *InPlaceHolds プロパティには*、セキュリティとコンプライアンス センターの電子情報開示ケースに関連付けられた任意のホールドの GUID が含まれる。 GUID はプレフィックス (統合ホールドを表す) で始まるので、これは電子情報開示 `UniH` ホールドであることを示します。      |
|インプレース ホールド     |     `c0ba3ce811b6432a8751430937152491` <br/> または <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     *InPlaceHolds* プロパティには、メールボックスにIn-Place保持の GUID が含まれる。 GUID はプレフィックスで始In-Placeプレフィックスで始まるので、これは保留の一部です `cld` 。     |
|メールボックスに特に適用される Microsoft 365 アイテム保持ポリシー     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> または <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     InPlaceHolds プロパティには、メールボックスに適用される特定の場所保持ポリシーの GUID が含まれる。 GUID はプレフィックスで始まるため、保持ポリシー `mbx` を識別 `skp` できます。 プレフィックス `skp` は、アイテム保持ポリシーがユーザーのメールボックス内の Skype for Business の会話に適用されるかどうかを示します。    |
|組織全体の Microsoft 365 アイテム保持ポリシーから除外     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     メールボックスが組織全体の Microsoft 365 アイテム保持ポリシーから除外されている場合、メールボックスが除外されるアイテム保持ポリシーの GUID は InPlaceHolds プロパティに表示され、プレフィックスで識別されます。 `-mbx`    |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
**Get-Mailbox** コマンドレットを実行するときに *InPlaceHolds* プロパティが空の場合は、1 つ以上の組織全体の Microsoft 365 アイテム保持ポリシーがメールボックスに適用される場合があります。 Exchange Online PowerShell で次のコマンドを実行して、組織全体の Microsoft 365 アイテム保持ポリシーの GUID の一覧を取得します。

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> InPlaceHolds プロパティに値が多すぎて、すべての値が表示されない場合は、コマンドを実行して各 GUID を個別の行 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` に表示できます。

次の表では **、Get-OrganizationConfig** コマンドレットの実行時に *InPlaceHolds* プロパティに含まれる GUID に基づいて、さまざまな種類の組織全体のホールドと各種類を識別する方法について説明します。

|ホールドの種類  |値の例  |説明  |
|---------|---------|---------|
|Exchange メールボックス、Exchange パブリック フォルダー、Teams チャットに適用される Microsoft 365 アイテム保持ポリシー    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   Microsoft Teams の Exchange メールボックス、Exchange パブリック フォルダー、および 1xN チャットに適用される組織全体の保持ポリシーは、プレフィックスで始まる GUID によって識別 `mbx` されます。 メモ 1xN チャットは、個々のチャット参加者のメールボックスに格納されます。      |
|Microsoft 365 グループおよび Teams チャネル メッセージに適用される Microsoft 365 アイテム保持ポリシー     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    Microsoft Teams の Microsoft 365 グループおよびチャネル メッセージに適用される組織全体の保持ポリシーは、プレフィックスで始まる GUID によって識別 `grp` されます。 メモ チャネル メッセージは、Microsoft チームに関連付けられているグループ メールボックスに格納されます。     |

Microsoft Teams に適用されるアイテム保持ポリシーの詳細については、「Microsoft Teams のアイテム保持ポリシー [について」を参照してください](retention-policies-teams.md)。

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>アイテム保持ポリシーの InPlaceHolds 値の形式について

InPlaceHolds プロパティ内のアイテムを Microsoft 365 アイテム保持ポリシーとして識別するプレフィックス (mbx、skp、または grp) に加えて、この値には、ポリシーに構成されている保持アクションの種類を識別するサフィックスも含まれる。 たとえば、次の例では、アクション サフィックスが太字で強調表示されます。

   `skp127d7cf1076947929bf136b7a2a8c36f`**:1**

   `mbx7cfb30345d454ac0a989ab3041051209`**:2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**:3**

次の表では、3 つの保持アクションを定義します。

|値  |説明  |
|---------|---------|
|**1**     | アイテムを削除するようにアイテム保持ポリシーが構成されていることを示します。 ポリシーはアイテムを保持しない。        |
|**2**    |    アイテムを保持するようにアイテム保持ポリシーが構成されていることを示します。 保持期間が過ぎると、ポリシーはアイテムを削除しません。     |
|**3**     |   アイテムを保持し、アイテム保持期間が経過した後にアイテムを削除するようにアイテム保持ポリシーが構成されていることを示します。      |

保持アクションの詳細については、「特定の期間のコンテンツ [を保持する」セクションを参照](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) してください。
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a>手順 2: GUID を使用して保留を特定する

メールボックスに適用される保留の GUID を取得した後、次の手順では、その GUID を使用して保留を識別します。 次のセクションでは、保留リスト GUID を使用して保留リストの名前 (および他の情報) を識別する方法を示します。

### <a name="ediscovery-holds"></a>電子情報開示の保留

セキュリティ センター PowerShell で次&コマンドを実行して、メールボックスに適用される電子情報開示ホールドを識別します。 手順 1 で識別した電子情報開示ホールドの GUID (UniH プレフィックスを含む) を使用します。 

コンプライアンス センター PowerShell &に接続するには、「Connect  [to Security to Security & PowerShell」を参照してください](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。

最初のコマンドは、保留に関する情報を含む変数を作成します。 この変数は、他のコマンドで使用されます。 2 番目のコマンドは、保留リストが関連付けられている電子情報開示ケースの名前を表示します。 3 番目のコマンドは、保留リストの名前と、保留が適用されるメールボックスの一覧を表示します。

```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold | FL Name,ExchangeLocation
```

### <a name="in-place-holds"></a>インプレース ホールド

Exchange Online PowerShell で次のコマンドを実行して、メールボックスにIn-Place保留リストを識別します。 手順 1 で特定In-Place保持の GUID を使用します。 このコマンドは、保留リストの名前と、保留が適用されるメールボックスの一覧を表示します。

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

保留リストの GUID In-Placeプレフィックスで始まる場合は、前のコマンドを実行するときにプレフィックス `cld` を必ず含める必要があります。

> [!IMPORTANT]
> メールボックス コンテンツを保持するためのさまざまな方法で投資を続ける中で、Exchange 管理センター (EAC) での In-Place 保持の削除を発表します。 2020 年 7 月 1 日以降、Exchange Online で新しいインプレース ホールドを作成することはできなくなります。 ただし、EAC で、または Exchange Online PowerShell In-Place **Set-MailboxSearch** コマンドレットを使用して、引き続き保留リストを管理できます。 ただし、2020 年 10 月 1 日から、保留の管理In-Placeされます。 削除できるのは、EAC または **Remove-MailboxSearch コマンドレットを使用する場合** のみです。 インプレース ホールドの廃止に関する詳細情報は、「[従来の eDiscovery ツールの廃止](legacy-ediscovery-retirement.md)」を参照してください。

### <a name="microsoft-365-retention-policies"></a>Microsoft 365 アイテム保持ポリシー

セキュリティ & コンプライアンス センター PowerShell で次のコマンドを実行して、メールボックスに適用される Microsoft 365 アイテム保持ポリシー (組織全体または特定の場所) を識別します。 手順 1 で識別した GUID (mbx、skp、grp プレフィックス、またはアクション サフィックスを含む) を使用します。

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>保持ラベルがフォルダーまたはアイテムに適用されたため、保持中のメールボックスを識別する

ユーザーがコンテンツを保持するか、保持し、メールボックス内の任意のフォルダーまたはアイテムにコンテンツを削除するように構成されている保持ラベルを適用するたびに *、ComplianceTagHoldApplied* メールボックス プロパティは **True** に設定されます。 この場合、メールボックスは訴訟ホールドに置かれたか、Microsoft 365 アイテム保持ポリシーに割り当てられているかのように、保留と見なされます。 *ComplianceTagHoldApplied プロパティ* が **True** に設定されている場合、次のことが発生する可能性があります。

- メールボックスまたはユーザーのユーザー アカウントが削除された場合、メールボックスは非アクティブな [メールボックスになります](inactive-mailboxes-in-office-365.md)。
- メールボックス (プライマリ メールボックスまたはアーカイブ メールボックスが有効な場合) を無効にすることはできません。
- メールボックス内のアイテムは、予想よりも長く保持される場合があります。 これは、メールボックスが保留であるため、アイテムが完全に削除 (削除) されていないためです。

*ComplianceTagHoldApplied* プロパティの値を表示するには、Exchange Online PowerShell で次のコマンドを実行します。

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

保持ラベルの詳細については、「保持ラベル」 [を参照してください](retention.md#retention-labels)。

## <a name="managing-mailboxes-on-delay-hold"></a>遅延ホールド時のメールボックスの管理

メールボックスから任意の種類の保留が削除されると、遅延 *保留が* 適用されます。 つまり、メールボックスからデータが完全に削除 (削除) されるのを防ぐために、保持の実際の削除が 30 日間遅れることを意味します。 これにより、管理者は保留リストが削除された後に削除されるメールボックス アイテムを検索または回復できます。 Managed Folder Assistant が次にメールボックスを処理し、保留リストが削除されたと検出すると、遅延ホールドがメールボックスに配置されます。 具体的には、Managed Folder Assistant が次のいずれかのメールボックス プロパティを True に設定すると、メールボックスに遅延ホールドが適用 **されます**。

- **DelayHoldApplied:** このプロパティは、ユーザーのメールボックスに格納されている電子メール関連のコンテンツ (Outlook と Outlook on the web を使用するユーザーによって生成される) に適用されます。

- **DelayReleaseHoldApplied:** このプロパティは、ユーザーのメールボックスに格納されているクラウドベースのコンテンツ (Microsoft Teams、Microsoft Forms、Microsoft Yammer などの Outlook 以外のアプリによって生成される) に適用されます。 Microsoft アプリによって生成されるクラウド データは、通常、ユーザーのメールボックス内の非表示のフォルダーに格納されます。

メールボックスに遅延ホールドが設定されている場合 (前のプロパティのどちらかが **True** に設定されている場合)、メールボックスは、メールボックスが訴訟ホールドの場合と同様に、無制限の保持期間の保留と見なされます。 30 日が経過すると、遅延ホールドの有効期限が切れ、Microsoft 365 は遅延ホールドを自動的に削除します (DelayHoldApplied プロパティまたは DelayReleaseHoldApplied プロパティを **False** に設定することで) 保留が削除されます。 これらのプロパティのいずれかを **False** に設定すると、削除のマークが付いた対応するアイテムは、次に管理フォルダー アシスタントによってメールボックスが処理された場合に削除されます。

メールボックスの DelayHoldApplied プロパティと DelayReleaseHoldApplied プロパティの値を表示するには、Exchange Online PowerShell で次のコマンドを実行します。

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

有効期限が切れる前に遅延ホールドを削除するには、変更するプロパティに応じて、Exchange Online PowerShell で次のコマンドのいずれかを実行できます。

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

または

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

*RemoveDelayHoldApplied* パラメーターまたは *RemoveDelayReleaseHoldApplied* パラメーターを使用するには、Exchange Online の法的保持役割を割り当てる必要があります。 

非アクティブなメールボックスの遅延ホールドを削除するには、Exchange Online PowerShell で次のいずれかのコマンドを実行します。

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

または

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> 前のコマンドで非アクティブなメールボックスを指定する最善の方法は、識別名または Exchange GUID 値を使用します。 これらの値のいずれかを使用すると、正しくないメールボックスを誤って指定することを避けられます。 

遅延ホールドの管理にこれらのパラメーターを使用する方法の詳細については [、「Set-Mailbox」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)。

遅延ホールド時にメールボックスを管理する場合は、次のことを念頭に置いておきます。

- DelayHoldApplied プロパティまたは DelayReleaseHoldApplied プロパティが **True** に設定され、メールボックス (または対応するユーザー アカウント) が削除された場合、メールボックスは非アクティブなメールボックスになります。 これは、いずれかのプロパティが **True** に設定されている場合にメールボックスが保留状態であると見なされ、保留状態のメールボックスを削除すると、非アクティブなメールボックスになります。 メールボックスを削除して非アクティブなメールボックスにしない場合は、両方のプロパティを False に設定する必要 **があります**。

- 前に述べたように、DelayHoldApplied プロパティまたは DelayReleaseHoldApplied プロパティが True に設定されている場合、メールボックスは無制限の保留期間の保留と見な **されます**。 ただし、メールボックス内のすべての *コンテンツが保持* されるわけではありません。 各プロパティに設定されている値に依存します。 たとえば、保持はメールボックスから削除されるので、両方のプロパティが **True** に設定されているとします。 次に、Outlook 以外のクラウド データに適用される遅延ホールドのみを削除します *(RemoveDelayReleaseHoldApplied* パラメーターを使用します)。 次に管理フォルダー アシスタントがメールボックスを処理すると、削除のマークが付いた Outlook 以外のアイテムが削除されます。 DelayHoldApplied プロパティがまだ True に設定されている場合、削除用にマークされた Outlook アイテムは削除 **されません**。 反対の値も true になります。DelayHoldApplied が **False** に設定され、DelayReleaseHoldApplied が **True** に設定されている場合、削除対象としてマークされた Outlook アイテムだけが削除されます。

## <a name="next-steps"></a>次の手順

メールボックスに適用される保留リストを特定した後、保留期間の変更、保留期間の一時的または完全な削除、Microsoft 365 アイテム保持ポリシーから非アクティブなメールボックスの除外などのタスクを実行できます。 保留リストに関連するタスクの実行の詳細については、次のいずれかのトピックを参照してください。

- セキュリティ & コンプライアンス センター PowerShell で[Set-RetentionCompliancePolicy \<Policy Name> -Identity -AddExchangeLocationException \<user mailbox> ](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)コマンドを実行して、組織全体の Microsoft 365 アイテム保持ポリシーからメールボックスを除外します。 このコマンドは *、ExchangeLocation* プロパティの値が等しいアイテム保持ポリシーにのみ使用できます `All` 。

- [非アクティブなメールボックスの保持期間を変更する](change-the-hold-duration-for-an-inactive-mailbox.md)

- [非アクティブなメールボックスを削除する](delete-an-inactive-mailbox.md)

- [保留中のクラウド ベースのメールボックスの [回復可能なアイテム] フォルダーのアイテムを削除する](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
