---
title: Exchange Online メールボックスの保留を識別する方法
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
description: Microsoft 365のExchange Online メールボックスに配置できるさまざまな種類の保留リストを特定する方法について説明します。
ms.openlocfilehash: 4b4ff5064f59285412c4c20108df9dbbae992f7e
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65097758"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>Exchange Online メールボックスに保存されている保留の種類を特定する方法

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

この記事では、Microsoft 365のExchange Onlineメールボックスに配置されている保留を識別する方法について説明します。

Microsoft 365には、組織がメールボックスのコンテンツを完全に削除できないようにする方法がいくつか用意されています。 これにより、組織は、コンプライアンス規則を満たすために、または法的および他の種類の調査中にコンテンツを保持できます。 Office 365の保持機能 (*保留* とも呼ばれます) の一覧を次に示します。

- **[訴訟ホールド](create-a-litigation-hold.md):** Exchange Onlineのユーザー メールボックスに適用される保留。

- **[電子情報開示ホールド](create-ediscovery-holds.md):** セキュリティとコンプライアンス センターの Microsoft Purview 電子情報開示 (Standard) ケースに関連付けられている保留。 電子情報開示の保留は、ユーザーメールボックスと、Microsoft 365 グループとMicrosoft Teamsの対応するメールボックスに適用できます。

- **[インプレースホールド](/Exchange/security-and-compliance/create-or-remove-in-place-holds):** Exchange OnlineのExchange <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">管理センター</a>でIn-Place電子情報開示&保留ツールを使用してユーザーメールボックスに適用される保留。 

   > [!NOTE]
   > In-Place保留は廃止され、In-Place保留を作成したり、メールボックスに適用したりできなくなります。 ただし、In-Place保留は組織内のメールボックスに引き続き適用される可能性があるため、この記事に含まれています。 詳細については、「 [従来の電子情報開示ツールの廃止](legacy-ediscovery-retirement.md#in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center)」を参照してください。

- **[Microsoft 365アイテム保持ポリシー](retention.md):** Exchange Onlineのユーザー メールボックスと、Microsoft 365 グループとMicrosoft Teamsに対応するメールボックス内のコンテンツを保持 (保持、削除) するように構成できます。 アイテム保持ポリシーを作成して、ユーザー メールボックスに格納されているSkype for Business会話を保持することもできます。

  メールボックスに割り当てることができるMicrosoft 365アイテム保持ポリシーには 2 種類あります。

    - **特定の場所の保持ポリシー:** これらは、特定のユーザーのコンテンツの場所に割り当てられるポリシーです。 Exchange Online PowerShell の **Get-Mailbox** コマンドレットを使用して、特定のメールボックスに割り当てられているアイテム保持ポリシーに関する情報を取得します。 この種類のアイテム保持ポリシーの詳細については、アイテム保持ポリシードキュメントの [「特定の包含または除外を含む](retention-settings.md#a-policy-with-specific-inclusions-or-exclusions) ポリシー」セクションを参照してください。

    - **組織全体のアイテム保持ポリシー:** これらは、組織内のすべてのコンテンツの場所に割り当てられるポリシーです。 PowerShell の **Get-OrganizationConfig** コマンドレットExchange Online使用して、組織全体のアイテム保持ポリシーに関する情報を取得します。 この種類のアイテム保持ポリシーの詳細については、アイテム保持ポリシーのドキュメントの「 [場所全体に適用されるポリシー](retention-settings.md#a-policy-that-applies-to-entire-locations) 」セクションを参照してください。

- **[Microsoft 365保持ラベル](retention.md):** ユーザーがメールボックス内の *任意* のフォルダーまたはアイテムにMicrosoft 365保持ラベル (コンテンツを保持または保持して削除するように構成されているアイテム) を適用すると、メールボックスが訴訟ホールドに置かれたか、Microsoft 365アイテム保持ポリシーに割り当てられたかのようにメールボックスに保留が配置されます。 詳細については、この記事の「 [保持ラベルがフォルダーまたはアイテムに適用されているため、保留中のメールボックスを識別する](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) 」セクションを参照してください。

保留状態のメールボックスを管理するには、保持期間の変更、一時的または永続的な保留の削除、Microsoft 365アイテム保持ポリシーからのメールボックスの除外などのタスクを実行できるように、メールボックスに配置される保留の種類を特定する必要がある場合があります。 このような場合、最初の手順は、メールボックスに配置された保留の種類を特定することです。 また、複数の保留 (および異なる種類の保留) を 1 つのメールボックスに配置できるため、保留を削除または変更する場合は、メールボックスに配置されているすべての保留を特定する必要があります。

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a>手順 1: メールボックスに配置された保留の GUID を取得する

Exchange Online PowerShell で次の 2 つのコマンドレットを実行して、メールボックスに配置された保留の GUID を取得できます。 GUID を取得したら、それを使用して手順 2 の特定のホールドを識別します。 訴訟ホールドは GUID によって識別されません。 訴訟ホールドは、メールボックスに対して有効または無効になります。

- **Get-Mailbox:** このコマンドレットを使用して、メールボックスに対して訴訟ホールドが有効になっているかどうかを判断し、メールボックスに特に割り当てられている電子情報開示保留、In-Place保留、およびMicrosoft 365アイテム保持ポリシーの GUID を取得します。 このコマンドレットの出力は、メールボックスが組織全体のアイテム保持ポリシーから明示的に除外されているかどうかを示します。

- **Get-OrganizationConfig:** 組織全体のアイテム保持ポリシーの GUID を取得するには、このコマンドレットを使用します。

Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

### <a name="get-mailbox"></a>Get-Mailbox

次のコマンドを実行して、メールボックスに適用された保留ポリシーとMicrosoft 365アイテム保持ポリシーに関する情報を取得します。

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> InPlaceHolds プロパティに値が多すぎてすべての値が表示されない場合は、コマンドを `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` 実行して各 GUID を個別の行に表示できます。

次の表では、**Get-Mailbox** コマンドレットを実行するときに *InPlaceHolds* プロパティの値に基づいて、さまざまな種類の保留を識別する方法について説明します。

| ホールドの種類                                                          | 値の例                                                                                  | 保留を識別する方法                                                                                                                                                                                                                                                                                                                     |
| ------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 訴訟ホールド                                                    | `True`                                                                                         | 訴訟ホールドは、 *LitigationHoldEnabled* プロパティが [ `True`.                                                                                                                                                                                                                                         |
| 電子情報開示の保留                                                    | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`                                                     | *InPlaceHolds プロパティ* には、セキュリティとコンプライアンス センターの電子情報開示ケースに関連付けられているすべてのホールドの GUID が含まれています。 GUID はプレフィックス (統合ホールドを表す) で始まるので `UniH` 、これは電子情報開示ホールドであることを確認できます。                                                                                   |
| インプレース ホールド                                                      | `c0ba3ce811b6432a8751430937152491` <br/> or <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`        | *InPlaceHolds* プロパティには、メールボックスに配置されたIn-Placeホールドの GUID が含まれています。 GUID がプレフィックスで始まらないか、プレフィックスで始まる `cld` ので、これはIn-Placeホールドであることを確認できます。                                                                                                               |
| メールボックスに特に適用されるMicrosoft 365アイテム保持ポリシー | `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> or <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3` | InPlaceHolds プロパティには、メールボックスに適用される特定の場所のアイテム保持ポリシーの GUID が含まれています。 GUID はプレフィックスまたはプレフィックスで始まるので、アイテム保持ポリシーを`mbx``skp`識別できます。 プレフィックスは`skp`、アイテム保持ポリシーがユーザーのメールボックス内のSkype for Business会話に適用されることを示します。 |
| 組織全体のMicrosoft 365アイテム保持ポリシーから除外  | `-mbxe9b52bf7ab3b46a286308ecb29624696`                                                         | メールボックスが組織全体のMicrosoft 365アイテム保持ポリシーから除外されている場合、メールボックスが除外されるアイテム保持ポリシーの GUID は InPlaceHolds プロパティに表示され、プレフィックスによって`-mbx`識別されます。                                                                                                     |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
**Get-Mailbox** コマンドレットの実行時に *InPlaceHolds* プロパティが空の場合でも、メールボックスに適用される組織全体のMicrosoft 365アイテム保持ポリシーが 1 つ以上存在する可能性があります。 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) で次のコマンドを実行して、組織全体のMicrosoft 365アイテム保持ポリシーの GUID の一覧を取得します。

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> InPlaceHolds プロパティに値が多すぎてすべての値が表示されない場合は、コマンドを `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` 実行して各 GUID を個別の行に表示できます。

次の表では、組織全体の保留のさまざまな種類と、**Get-OrganizationConfig** コマンドレットを実行するときに *InPlaceHolds* プロパティに含まれる GUID に基づいて各種類を識別する方法について説明します。

| ホールドの種類                                                                                                | 値の例                           | 説明                                                                                                                                                                                                                                                            |
| -------------------------------------------------------------------------------------------------------- | --------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Exchange メールボックス、Exchangeパブリック フォルダー、Teams チャットに適用されるMicrosoft 365アイテム保持ポリシー | `mbx7cfb30345d454ac0a989ab3041051209:2` | Exchange メールボックス、Exchangeパブリック フォルダー、Microsoft Teamsの 1xN チャットに適用される組織全体のアイテム保持ポリシーは、プレフィックスで`mbx`始まる GUID によって識別されます。 1xN チャットは、個々のチャット参加者のメールボックスに格納されることに注意してください。  |
| Microsoft 365 グループおよびTeams チャネル メッセージに適用されるMicrosoft 365アイテム保持ポリシー                | `grp1a0a132ee8944501a4bb6a452ec31171:3` | Microsoft TeamsのMicrosoft 365 グループとチャネル メッセージに適用される組織全体のアイテム保持ポリシーは、プレフィックスで`grp`始まる GUID によって識別されます。 注: チャネル メッセージは、Microsoft チームに関連付けられているグループ メールボックスに格納されます。 |

Microsoft Teamsに適用されるアイテム保持ポリシーの詳細については、「[Microsoft Teamsのアイテム保持ポリシーの詳細」を](retention-policies-teams.md)参照してください。

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>アイテム保持ポリシーの InPlaceHolds 値の形式について

InPlaceHolds プロパティ内のアイテムをMicrosoft 365アイテム保持ポリシーとして識別するプレフィックス (mbx、skp、または grp) に加えて、この値には、ポリシー用に構成された保持アクションの種類を識別するサフィックスも含まれています。 たとえば、次の例では、アクション サフィックスが太字で強調表示されています。

   `skp127d7cf1076947929bf136b7a2a8c36f`**:1**

   `mbx7cfb30345d454ac0a989ab3041051209`**:2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**:3**

次の表では、3 つの可能な保持アクションを定義します。

| 値 | 説明                                                                                                                          |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **1** | アイテムを削除するようにアイテム保持ポリシーが構成されていることを示します。 ポリシーはアイテムを保持しません。                                  |
| **2** | アイテムを保持するようにアイテム保持ポリシーが構成されていることを示します。 保持期間の有効期限が切れた後、ポリシーはアイテムを削除しません。 |
| **3** | アイテム保持ポリシーがアイテムを保持するように構成され、保持期間が切れた後にアイテムを削除することを示します。             |

保持アクションの詳細については、「 [特定の期間のコンテンツを保持する](retention-settings.md#retaining-content-for-a-specific-period-of-time) 」セクションを参照してください。
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a>手順 2: GUID を使用してホールドを識別する

メールボックスに適用されるホールドの GUID を取得した後、次の手順では、その GUID を使用してホールドを識別します。 次のセクションでは、保留 GUID を使用して保留の名前 (およびその他の情報) を識別する方法について説明します。

### <a name="ediscovery-holds"></a>電子情報開示の保留

Security & Compliance Center PowerShell で次のコマンドを実行して、メールボックスに適用されている電子情報開示ホールドを特定します。 手順 1 で識別した電子情報開示ホールドに GUID (UniH プレフィックスを含まない) を使用します。 

セキュリティ/コンプライアンス センターの PowerShell に接続するには、「[セキュリティ/コンプライアンス センター PowerShell に接続する](/powershell/exchange/connect-to-scc-powershell)」を参照してください。

最初のコマンドは、保留に関する情報を含む変数を作成します。 この変数は、他のコマンドで使用されます。 2 番目のコマンドは、保留リストが関連付けられている電子情報開示ケースの名前を表示します。 3 番目のコマンドには、保留リストの名前と、保留が適用されるメールボックスの一覧が表示されます。

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

Exchange Online PowerShell で次のコマンドを実行して、メールボックスに適用されているIn-Place保留を識別します。 手順 1 で識別したIn-Placeホールドの GUID を使用します。 このコマンドには、保留リストの名前と、保留が適用されるメールボックスの一覧が表示されます。

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

In-Place保留の GUID がプレフィックスで `cld` 始まる場合は、前のコマンドを実行するときにプレフィックスを含めてください。

> [!IMPORTANT]
> メールボックス コンテンツを保持するためのさまざまな方法に投資し続ける中で、Exchange管理センター (EAC) でのIn-Place保留の廃止を発表します。 2020 年 7 月 1 日以降、Exchange Online で新しいインプレース ホールドを作成することはできなくなります。 ただし、EAC でIn-Place保留を管理したり、PowerShell で **Set-MailboxSearch** コマンドレットExchange Online使用したりすることはできます。 ただし、2020 年 10 月 1 日以降は、In-Place保留を管理することはできません。 EAC または **Remove-MailboxSearch** コマンドレットを使用してのみ削除できます。 インプレース ホールドの廃止に関する詳細情報は、「[従来の eDiscovery ツールの廃止](legacy-ediscovery-retirement.md)」を参照してください。

### <a name="microsoft-365-retention-policies"></a>Microsoft 365アイテム保持ポリシー

[Security & Compliance Center PowerShell にConnect](/powershell/exchange/connect-to-scc-powershell)し、次のコマンドを実行して、メールボックスに適用されるMicrosoft 365アイテム保持ポリシー (組織全体または特定の場所) を識別します。 手順 1 で識別した GUID (mbx、skp、または grp プレフィックスやアクション サフィックスを含まない) を使用します。

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>アイテム保持ラベルがフォルダーまたはアイテムに適用されているため、保留中のメールボックスを識別する

ユーザーが、メールボックス内の任意のフォルダーまたはアイテムにコンテンツを *保持* または *保持して削除* するように構成された保持ラベルを適用するたびに、 *ComplianceTagHoldApplied* メールボックス プロパティは True に設定 **されます**。 この場合、メールボックスは、Microsoft 365アイテム保持ポリシーに割り当てられた場合や訴訟ホールドに置かれた場合など、保留にされた場合と同様に扱われますが、注意が必要です。 *ComplianceTagHoldApplied* プロパティが **True** に設定されている場合、次のことが発生します。

- メールボックスまたはユーザーのMicrosoft 365 アカウントが削除されると、メールボックスは[非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)になります。
- メールボックス (プライマリ メールボックスまたはアーカイブ メールボックスが有効になっている場合) を無効にすることはできません。
- メールボックスから削除されたアイテムは、ラベルが付けられているかどうかに応じて、次の 2 つのパスのいずれかに従います。
    - **ラベルのないアイテム** は、メールボックスに保留が適用されない場合に削除されたアイテムと同じパスに従います。  これらのアイテムが完全に削除されるまでにかかる時間は、 [削除されたアイテムの保持](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder#deleted-item-retention) 構成と、メールボックスに対して [1 つのアイテムの回復](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder#single-item-recovery) が有効になっているかどうかによって決まります。
    - **ラベル付きアイテム** は、Microsoft 365アイテム保持ポリシーが適用された場合と同じように、個々のアイテム レベルで [回復可能なアイテム フォルダー](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder#recoverable-items-folder)内に保持されます。  複数のアイテムに異なるラベルがあり、異なる間隔でコンテンツを *保持* または *保持して削除* するように構成されている場合、各アイテムは、適用されたラベルの構成に基づいて保持されます。
- Microsoft 365保持ポリシー、電子情報開示ホールド、訴訟ホールドなどのその他の保留は、[保持の原則](retention.md#the-principles-of-retention-or-what-takes-precedence)に基づいてラベル付けされたアイテムが保持される期間を延長できます。

1 つのメールボックスの *ComplianceTagHoldApplied* プロパティの値を表示するには、[PowerShell で](/powershell/exchange/connect-to-exchange-online-powershell)次のコマンドExchange Online実行します。

```powershell
Get-Mailbox <username> | FL ComplianceTagHoldApplied
```

保持ラベルの詳細については、「 [保持](retention.md#retention-labels)ラベル」を参照してください。

## <a name="managing-mailboxes-on-delay-hold"></a>遅延ホールド時のメールボックスの管理

メールボックスから任意の種類の保留が削除されると、 *遅延ホールド* が適用されます。 つまり、メールボックスからデータが完全に削除 (削除) されないように、ホールドの実際の削除は 30 日間遅延されます。 これにより、管理者は、ホールドが削除された後に削除されるメールボックス アイテムを検索または回復できます。 次にマネージド フォルダー アシスタントがメールボックスを処理し、保留が削除されたことを検出すると、メールボックスに遅延ホールドが配置されます。 具体的には、マネージド フォルダー アシスタントが次のいずれかのメールボックス プロパティを True に設定すると、メールボックスに遅延ホールドが適用 **されます**。

- **DelayHoldApplied:** このプロパティは、ユーザーのメールボックスに格納されている電子メール関連のコンテンツ (OutlookとOutlook on the webを使用しているユーザーによって生成されます) に適用されます。

- **DelayReleaseHoldApplied:** このプロパティは、ユーザーのメールボックスに格納されているクラウドベースのコンテンツ (Microsoft Teams、Microsoft Forms、Microsoft Yammerなどの非Outlook アプリによって生成されます) に適用されます。 Microsoft アプリによって生成されたクラウド データは、通常、ユーザーのメールボックス内の非表示フォルダーに格納されます。

メールボックスに遅延ホールドが配置されている場合 (前のプロパティのいずれかが **True** に設定されている場合)、メールボックスは訴訟ホールドにあるかのように、保持期間が無制限であると見なされます。 30 日後、遅延ホールドは期限切れになり、Microsoft 365 保留が削除されるように (DelayHoldApplied プロパティまたは DelayReleaseHoldApplied プロパティを **False** に設定することで) 遅延ホールドの削除が自動的に試行されます。 これらのプロパティのいずれかを **False** に設定した後、削除対象としてマークされた対応するアイテムは、次にメールボックスが管理フォルダー アシスタントによって処理されるときに削除されます。

メールボックスの DelayHoldApplied プロパティと DelayReleaseHoldApplied プロパティの値を表示するには、[PowerShell で](/powershell/exchange/connect-to-exchange-online-powershell)次のコマンドExchange Online実行します。

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

有効期限が切れる前に遅延ホールドを削除するには、変更するプロパティに応じて、PowerShell で次のコマンドを実行Exchange Online(または両方) できます。

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

または

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

*RemoveDelayHoldApplied パラメーターまたは RemoveDelayReleaseHoldApplied* パラメーターを使用するには、Exchange Onlineで訴訟ホールド ロール *を* 割り当てる必要があります。 

非アクティブなメールボックスの遅延ホールドを削除するには、powerShell で次のいずれかのコマンドExchange Online実行します。

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

または

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> 前のコマンドで非アクティブなメールボックスを指定する最善の方法は、識別名または GUID 値Exchange使用することです。 これらの値のいずれかを使用すると、正しくないメールボックスを誤って指定することを避けられます。 

遅延保留を管理するためにこれらのパラメーターを使用する方法の詳細については、「 [Set-Mailbox](/powershell/module/exchange/set-mailbox)」を参照してください。

メールボックスを遅延ホールドで管理する場合は、次の点に注意してください。

- DelayHoldApplied プロパティまたは DelayReleaseHoldApplied プロパティのいずれかが **True** に設定され、メールボックス (または対応するユーザー アカウント) が削除された場合、メールボックスは非アクティブなメールボックスになります。 これは、いずれかのプロパティが **True** に設定されている場合、メールボックスは保留中と見なされ、保留状態のメールボックスを削除すると非アクティブなメールボックスが発生するためです。 メールボックスを削除し、非アクティブなメールボックスにするには、両方のプロパティを **False** に設定する必要があります。

- 前に説明したように、DelayHoldApplied プロパティまたは DelayReleaseHoldApplied プロパティが **True** に設定されている場合、メールボックスは無制限の保留期間の保留と見なされます。 ただし、メールボックス *内のすべての* コンテンツが保持されるわけではありません。 各プロパティに設定されている値によって異なります。 たとえば、メールボックスから保留が削除されるため、両方のプロパティが **True** に設定されているとします。 次に、(*RemoveDelayReleaseHoldApplied* パラメーターを使用して) 非Outlookクラウド データに適用される遅延ホールドのみを削除します。 次にマネージド フォルダー アシスタントがメールボックスを処理すると、削除対象としてマークされたOutlook以外のアイテムが削除されます。 DelayHoldApplied プロパティは引き続き **True** に設定されているため、削除用にマークされたOutlook項目は削除されません。 逆の場合も同様です。DelayHoldApplied が **False** に設定され、DelayReleaseHoldApplied が **True** に設定されている場合、削除対象としてマークされたOutlook項目のみが削除されます。

## <a name="how-to-confirm-that-an-organization-wide-retention-policy-is-applied-to-a-mailbox"></a>組織全体のアイテム保持ポリシーがメールボックスに適用されていることを確認する方法

組織全体のアイテム保持ポリシーがメールボックスに適用または削除されると、メールボックス診断ログをエクスポートすると、Exchange Onlineが実際にメールボックスにアイテム保持ポリシーを適用または削除したことを確認できます。 この情報を表示するには、まず [Powershell を](/powershell/exchange/connect-to-exchange-online-powershell)使用していくつかのことを検証Exchange Online必要があります。

### <a name="obtain-the-guids-for-any-retention-policies-explicitly-applied-to-a-mailbox"></a>メールボックスに明示的に適用されたすべてのアイテム保持ポリシーの GUID を取得する

```powershell
Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds
```

### <a name="obtain-the-guids-for-any-organization-wide-retention-policies-applied-to-mailboxes"></a>メールボックスに適用されている組織全体のアイテム保持ポリシーの GUID を取得する

```powershell
Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds
```

### <a name="get-the-mailbox-diagnostics-for-holdtracking"></a>HoldTracking のメールボックス診断を取得する

保留追跡メールボックス診断ログは、ユーザー メールボックスに適用された保留の履歴を保持します。

```powershell
$ht = Export-MailboxDiagnosticLogs <username> -ComponentName HoldTracking
$ht.MailboxLog | Convertfrom-Json
```

### <a name="review-the-results-of-the-mailbox-diagnostics-logs"></a>メールボックス診断ログの結果を確認する

前の手順からデータを収集した場合、結果のデータは次のようになります。

> **編**`  : 0001-01-01T00:00:00.0000000`
> **Hid**` : mbx7cfb30345d454ac0a989ab3041051209:1`
> **Ht**`  : 4`
> **Lsd**` : 2020-03-23T18:24:37.1884606Z`
> **Osd**` : 2020-03-23T18:24:37.1884606Z`

次の表を使用して、診断ログに一覧表示されている前の各値を理解するのに役立ちます。

| 値   | 説明 |
|:------- |:----------- |
| **ed**  | 終了日を示します。これは、アイテム保持ポリシーが無効になった日付です。 MinValue は、ポリシーがまだメールボックスに割り当てられているという意味です。 |
| **Hid** | アイテム保持ポリシーの GUID を示します。 この値は、メールボックスに割り当てられた明示的または組織全体のアイテム保持ポリシーに対して収集した GUID に関連付けられます。|
| **Lsd** | 最終開始日を示します。これは、アイテム保持ポリシーがメールボックスに割り当てられた日付です。|
| **Osd** | 元の開始日を示します。これは、アイテム保持ポリシーに関する情報Exchange最初に記録された日付です。 |
|||

アイテム保持ポリシーがメールボックスに適用されなくなった場合は、コンテンツの削除を防ぐために、ユーザーに一時的な遅延保留を設定します。 遅延ホールドは、コマンドを実行 `Set-Mailbox -RemoveDelayHoldApplied` して無効にすることができます。

## <a name="next-steps"></a>次の手順

メールボックスに適用されている保留を特定したら、保持期間の変更、一時的または永続的な保留の削除、非アクティブなメールボックスのMicrosoft 365アイテム保持ポリシーからの除外などのタスクを実行できます。 保留に関連するタスクの実行の詳細については、次のいずれかのトピックを参照してください。

- [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) で [Set-RetentionCompliancePolicy -Identity \<Policy Name> -AddExchangeLocationException \<user mailbox>](/powershell/module/exchange/set-retentioncompliancepolicy) コマンドを実行して、組織全体のMicrosoft 365アイテム保持ポリシーからメールボックスを除外します。 このコマンドは、 *ExchangeLocation* プロパティの値が等しい `All`アイテム保持ポリシーにのみ使用できます。

- [非アクティブなメールボックスの保持期間を変更する](change-the-hold-duration-for-an-inactive-mailbox.md)

- [非アクティブなメールボックスを削除する](delete-an-inactive-mailbox.md)

- [保留中のクラウド ベースのメールボックスの [回復可能なアイテム] フォルダーのアイテムを削除する](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
