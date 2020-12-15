---
title: メールボックスの監査を管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
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
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
ms.custom: seo-marvel-apr2020
description: メールボックス監査ログは、Microsoft 365 では既定で有効になっています (既定では既定のメールボックス監査またはメールボックス監査とも呼ばれています)。 つまり、メールボックスの所有者、代理人、および管理者が実行した特定の操作は、メールボックス監査ログに自動的に記録され、メールボックスで実行されたアクティビティを検索できます。
ms.openlocfilehash: 8b199f2fe63f0304e705f32bab8191a966e63fce
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682548"
---
# <a name="manage-mailbox-auditing"></a>メールボックスの監査を管理する

2019 年 1 月から、Microsoft は、すべての組織のメールボックス監査ログを既定で有効にしています。 つまり、メールボックスの所有者、代理人、および管理者が実行する特定の操作は自動的にログに記録され、メールボックス監査ログでメールボックス監査レコードを検索すると、対応するメールボックス監査レコードを使用できます。 メールボックス監査を既定で有効にする前に、組織内のすべてのユーザー メールボックスに対して手動で有効にする必要があります。

メールボックス監査の既定の利点を次に示します。

- 新しいメールボックスを作成すると、監査が自動的に有効になります。 新しいユーザーに対して手動で有効にする必要はありません。

- 監査されるメールボックスアクションを管理する必要はない。 既定では、定義済みのメールボックス操作のセットがログオンの種類 (管理者、代理人、所有者) ごとに監査されます。

- Microsoft が新しいメールボックス アクションをリリースすると、既定で監査されるメールボックスアクションの一覧にアクションが自動的に追加される場合があります (適切なライセンスを持つユーザーが対象となります)。 つまり、メールボックスに対する新しいアクションの追加を監視する必要がなされません。

- 組織全体で一貫したメールボックス監査ポリシーを使用している (すべてのメールボックスに対して同じアクションを監査しているから)。

> [!NOTE]
>* 既定でメールボックス監査がリリースされた場合に覚えておく必要がある重要な点は、メールボックス監査を管理するために何もする必要はありません。 ただし、詳細については、既定の設定からメールボックス監査をカスタマイズするか、完全にオフにしてください。このトピックは役立ちます。
>- 既定では、E5 ユーザーのメールボックス監査イベントのみを、セキュリティ & コンプライアンス センターまたは Office 365 管理アクティビティ API 経由で監査ログ検索で使用できます。 詳細については、このトピックの「 [詳細」](#more-information) セクションを参照してください。

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>既定によるメールボックス監査の有効化がオンになっていることを確認する

組織でメールボックス監査が既定で有効になっていることを確認するには [、Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)で次のコマンドを実行します。

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

値 **False** は、メールボックス監査が既定で組織に対して有効になっているかどうかを示します。 これは、既定で組織の値が特定のメールボックスのメールボックス監査設定を上書きします。 たとえば、メールボックスのメールボックス監査が無効になっている場合 (メールボックスの *AuditEnabled* プロパティが **False)、** 既定でメールボックス監査が組織に対して有効になっているため、メールボックスの既定のメールボックス操作は引き続き監査されます。

特定のメールボックスに対してメールボックス監査を無効に維持するには、メールボックス所有者およびメールボックスへのアクセスを委任された他のユーザーに対してメールボックス監査バイパスを構成します。 詳細については、このトピックの「 [メールボックス監査ログの](#bypass-mailbox-audit-logging) バイパス」セクションを参照してください。

> [!NOTE]
> 組織でメールボックス監査が既定で有効になっている場合、影響を受けるメールボックスの *AuditEnabled* プロパティは False から **True** に変更 **されません**。 つまり、メールボックスの監査は既定でメールボックスの *AuditEnabled* プロパティを無視します。

## <a name="supported-mailbox-types"></a>サポートされるメールボックスの種類

次の表に、既定でメールボックス監査で現在サポートされているメールボックスの種類を示します。

|**メールボックスの種類**|**サポートされている**|**サポートされていない**|
|:---------|:---------:|:---------:|
|ユーザー メールボックス|![チェック マーク](../media/checkmark.png)||
|共有メールボックス|![チェック マーク](../media/checkmark.png)||
|Microsoft 365 グループ メールボックス|![チェック マーク](../media/checkmark.png)||
|リソース メールボックス||![チェック マーク](../media/checkmark.png)|
|パブリック フォルダー メールボックス||![チェック マーク](../media/checkmark.png)|

## <a name="logon-types-and-mailbox-actions"></a>ログオンの種類とメールボックスの操作

ログオンの種類は、メールボックスで監査されたアクションを実行したユーザーを分類します。 次の一覧では、メールボックス監査ログで使用されるログオンの種類について説明します。

- **所有者**: メールボックスの所有者 (メールボックスに関連付けられているアカウント)。

- **デリゲート**:

  - 別のメールボックスに対する SendAs、SendOnBehalf、または FullAccess のアクセス許可が割り当てられているユーザー。

  - ユーザーのメールボックスに対する FullAccess アクセス許可が割り当てられている管理者。

- **管理者**:

  - メールボックスは、次の Microsoft 電子情報開示ツールのいずれかを使用して検索されます。

    - コンプライアンス センターのコンテンツ検索。

    - コンプライアンス センターの電子情報開示または Advanced eDiscovery。

    - In-Place Exchange Online の電子情報開示。

  - メールボックスにアクセスするには、MAPI エディターのMicrosoft Exchange Server使用します。

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a>ユーザー メールボックスと共有メールボックスのメールボックスアクション

次の表では、ユーザー メールボックスと共有メールボックスのメールボックス監査ログで使用できるメールボックスの操作について説明します。

- チェック マーク ( ![チェック マーク](../media/checkmark.png)) は、ログオンの種類に対してメールボックスアクションをログに記録できる (すべての種類のログオンで使用可能なアクションではない) を示します。

- チェック マークの後にアスタリスク ( ) が付いている場合は、ログオンの種類に対してメールボックスの操作が既定 <sup>\*</sup> で記録されます。

- メールボックスへのフル アクセスのアクセス許可を持つ管理者は代理人と見なされます。

|**メールボックスの操作**|**説明**|**管理者**|**代理人**|**所有者**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**AddFolderPermissions**|**注**: この値はメールボックス アクションとして受け入れ可能ですが **、UpdateFolderPermissions** アクションには既に含まれており、個別に監査されません。 つまり、この値は使用しない必要があります。||||
|**ApplyRecord**|アイテムはレコードとしてラベル付けされます。|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|
|**コピーする**|メッセージが別のフォルダーにコピーされました。|![チェック マーク](../media/checkmark.png)|||
|**Create**|メールボックスの予定表、連絡先、メモ、またはタスク フォルダーにアイテムが作成されました (たとえば、新しい会議出席依頼が作成されます)。 メッセージの作成、送信、または受信は監査されません。 また、メールボックス フォルダーの作成も監査されません。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)|
|**Default**||![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|
|**FolderBind**|メールボックス フォルダーがアクセスされました。この操作は、管理者または委任されたユーザーがメールボックスを開いたときにも記録されます。<br/><br/> **注**: 代理人によって実行されたフォルダー バインド操作の監査レコードは統合されます。 24 時間以内に個々のフォルダー アクセスに対して 1 つの監査レコードが生成されます。|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|**HardDelete**|メッセージが [回復可能なアイテム] フォルダーから削除されました。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**MailItemsAccessed**|メール データには、メール プロトコルとクライアントがアクセスします。 この値は、E5 または E5 コンプライアンス アドオン サブスクリプション のユーザーにのみ使用できます。 詳細については、「調査のための [重要なイベントへのアクセス」を参照してください](advanced-audit.md#access-to-crucial-events-for-investigations)。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**MailboxLogin**|ユーザーが自分のメールボックスにサインインしました。 |||![チェック マーク](../media/checkmark.png)|
|**MessageBind**|メッセージがプレビュー ウィンドウで表示されたか、管理者によって開かされました。 **注**: この値はメールボックスアクションとして受け入れ可能ですが、これらのアクションはログに記録されません。|![チェック マーク](../media/checkmark.png)|||
|**ModifyFolderPermissions**|**注**: この値はメールボックス アクションとして受け入れ可能ですが **、UpdateFolderPermissions** アクションには既に含まれており、個別に監査されません。 つまり、この値は使用しない必要があります。||||
|**移動する**|メッセージが別のフォルダーに移動されました。|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|
|**MoveToDeletedItems**|メッセージが削除され、[削除済みアイテム] フォルダーに移動されました。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**RecordDelete**|レコードとしてラベル付けされたアイテムが回復可能な削除によって削除された (回復可能なアイテム フォルダーに移動された)。 レコードとしてラベル付けされたアイテムを完全に削除することはできません (回復可能なアイテム フォルダーから削除されます)。|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|
|**RemoveFolderPermissions**|**注**: この値はメールボックス アクションとして受け入れ可能ですが **、UpdateFolderPermissions** アクションには既に含まれており、個別に監査されません。 つまり、この値は使用しない必要があります。||||
|**SendAs**|SendAs アクセス許可を使用してメッセージが送信されました (他のユーザーがこのメールボックスの所有者を装ってメッセージを送信しました)。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|SendOnBehalf アクセス許可を使用してメッセージが送信されました (他のユーザーがこのメールボックスの所有者の代理人としてメッセージを送信しました)。この場合は、メッセージの名目上の送信者と実際の送信者が受信者に示されます。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|メッセージが完全に削除された、つまり [削除済みアイテム] フォルダーから削除されました。削除済み (回復可能) アイテムは、回復可能なアイテム フォルダーに移動されます。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**更新**|メッセージまたはそのプロパティが変更されました。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**UpdateCalendarDelegation**|メールボックスに予定表の委任が割り当てられました。予定表の委任により、同じ組織の他のユーザーに、メールボックス所有者の予定表を管理する権限が付与されます。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>||![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**UpdateComplianceTag**|別の保持ラベルがメール アイテムに適用されます (アイテムに割り当て可能な保持ラベルは 1 つのみです)。|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|
|**UpdateFolderPermissions**|フォルダーのアクセス許可が変更されました。 フォルダーのアクセス許可では、メールボックス内のフォルダーとそれらのフォルダーに格納されているメッセージにアクセスできる組織内のユーザーを制限します。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**UpdateInboxRules**|受信トレイ ルールが追加、削除、または変更されました。 受信トレイ ルールは、指定した条件に基づいてユーザーの受信トレイ内のメッセージを処理し、指定したフォルダーへのメッセージの移動やメッセージの削除など、ルールの条件が満たされた場合にアクションを実行するために使用されます。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|

> [!IMPORTANT]
> 組織で既定でメールボックス監査を有効にする前に、ログオンの種類を監査するようにメールボックスの操作をカスタマイズした場合、カスタマイズされた設定はメールボックスに保持され、このセクションで説明するように既定のメールボックス操作によって上書きされることはありません。 監査メールボックスの操作を既定値に戻すには (いつでも実行できます)、このトピックの「既定[](#restore-the-default-mailbox-actions)のメールボックス操作を復元する」を参照してください。

### <a name="mailbox-actions-for-microsoft-365-group-mailboxes"></a>Microsoft 365 グループ メールボックスのメールボックスアクション

メールボックス監査は既定で Microsoft 365 グループメールボックスにメールボックス監査ログを表示しますが、記録される項目をカスタマイズすることはできません (ログオンの種類に対してログに記録されるメールボックス操作を追加または削除することはできません)。

次の表では、ログオンの種類ごとに Microsoft 365 グループ のメールボックスに既定で記録されるメールボックスの操作について説明します。

Microsoft 365 グループ メールボックスへのフル アクセス許可を持つ管理者は代理人と見なされます。

|**メールボックスの操作**|**説明**|**管理者**|**代理人**|**所有者**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**Create**|予定表アイテムの作成。 メッセージの作成、送信、または受信は監査されません。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>||
|**HardDelete**|メッセージが [回復可能なアイテム] フォルダーから削除されました。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**MoveToDeletedItems**|メッセージが削除され、[削除済みアイテム] フォルダーに移動されました。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|SendAs アクセス許可を使用してメッセージが送信されました。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|SendOnBehalf アクセス許可を使用してメッセージが送信されました。 |![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|メッセージが完全に削除された、つまり [削除済みアイテム] フォルダーから削除されました。削除済み (回復可能) アイテムは、回復可能なアイテム フォルダーに移動されます。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**更新**|メッセージまたはそのプロパティが変更されました。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>ログオンの種類ごとに既定のメールボックスアクションがログに記録されるのを確認する

既定では、メールボックス監査は新しい *DefaultAuditSet* プロパティをすべてのメールボックスに追加します。 このプロパティの値は、(Microsoft によって管理される) 既定のメールボックスアクションがメールボックスで監査されているかどうかを示します。

ユーザー メールボックスまたは共有メールボックスの値を表示するには、メールボックスの名前、エイリアス、電子メール アドレス、またはユーザー プリンシパル名 (ユーザー名) に置き換え、Exchange Online PowerShell で次のコマンドを実行します \<MailboxIdentity\> 。

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

Microsoft 365 グループ メールボックスの値を表示するには、共有メールボックスの名前、エイリアス、または電子メール アドレスに置き換え、Exchange Online PowerShell で次のコマンドを \<MailboxIdentity\> 実行します。

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

値は `Admin, Delegate, Owner` 次を示します。

- 3 種類すべてのログオンに対する既定のメールボックスアクションが監査されます。 これは、Microsoft 365 グループ メールボックスに表示される唯一の値です。

- 管理者が *、ユーザー* メールボックスまたは共有メールボックスのログオンの種類に対する監査メールボックスアクションを変更していない。 これは、既定でメールボックス監査が組織で有効になった後の既定の状態です。

管理者がログオンの種類 **(Set-Mailbox** コマンドレットで *AuditAdmin、AuditDelegate、* または *AuditOwner* パラメーターを使用して) 監査されるメールボックスアクションを変更した場合、プロパティ値は異なります。

たとえば、ユーザー メールボックス `Owner` または共有メールボックスの *DefaultAuditSet* プロパティの値は、次の値を示します。

- メールボックス所有者の既定のメールボックスアクションは監査中です。

- 監査されるメールボックスの操作とログオン `Delegate` の種類 `Admin` は、既定のアクションから変更されています。

*DefaultAuditSet* プロパティの空白値は、ユーザー メールボックスまたは共有メールボックスで、3 種類すべてのログオンのメールボックスアクションが変更されたかどうかを示します。

詳細については、このトピックの「既定で記録されるメールボックス操作の [変更](#change-or-restore-mailbox-actions-logged-by-default) または復元」を参照してください。

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a>ログオンしているメールボックスの操作を表示する

ユーザー メールボックスまたは共有メールボックスで現在ログオンしているメールボックスアクションを表示するには、メールボックスの名前、エイリアス、電子メール アドレス、またはユーザー プリンシパル名 (ユーザー名) に置き換え、Exchange Online PowerShell で次のコマンドを 1 つ以上実行します。 \<MailboxIdentity\>

> [!NOTE]
> Microsoft 365 グループ メールボックス用の次の Get-Mailbox コマンドにスイッチを追加することもできますが、返される値は `-GroupMailbox` 見なされません。  Microsoft 365 グループ メールボックスに対して監査される既定の静的メールボックスアクションについては、このトピックの [「Microsoft 365 グループ](#mailbox-actions-for-microsoft-365-group-mailboxes) メールボックスのメールボックスアクション」セクションで説明しました。

#### <a name="owner-actions"></a>所有者の操作

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a>委任アクション

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a>管理者アクション

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>既定でログに記録されるメールボックスの操作を変更または復元する

前に説明したように、メールボックス監査を既定で有効にする主な利点の 1 つは、監査されるメールボックスの操作を管理する必要がなさいという利点です。 Microsoft がこれを行い、新しいメールボックス アクションがリリースされると、既定で監査される新しいメールボックス アクションが自動的に追加されます。

ただし、組織では、ユーザー メールボックスと共有メールボックスに対して異なるメールボックス操作のセットを監査する必要がある場合があります。 このセクションの手順では、ログオンの種類ごとに監査されるメールボックスアクションを変更する方法と、Microsoft が管理する既定のアクションに戻す方法について説明します。

> [!IMPORTANT]
> 次の手順を使用して、ユーザー メールボックスまたは共有メールボックスにログオンしているメールボックス操作をカスタマイズした場合、Microsoft によってリリースされた新しい既定のメールボックスアクションは、それらのメールボックスに対して自動的に監査されません。 新しいメールボックス アクションをカスタマイズしたアクションの一覧に手動で追加する必要があります。

### <a name="change-the-mailbox-actions-to-audit"></a>監査するメールボックスアクションを変更する

**Set-Mailbox** コマンドレットで *AuditAdmin、AuditDelegate、* または *AuditOwner* パラメーターを使用して、ユーザー メールボックスと共有メールボックスに対して監査されるメールボックスアクションを変更できます (Microsoft 365 グループ メールボックスの監査アクションはカスタマイズできません)。 

次の 2 つの異なる方法を使用して、メールボックスの操作を指定できます。

- *次の* 構文を使用して、既存のメールボックスアクションを置換 (上書き) します `action1,action2,...actionN` 。

- *次の構文を使用* して、他の既存の値に影響を与えることなく、メールボックスの操作を追加または `@{Add="action1","action2",..."actionN"}` 削除します `@{Remove="action1","action2",..."actionN"}` 。

この例では、SoftDelete と HardDelete を使用して既定のアクションを上書きして、"Gabriela Laureano" という名前のメールボックスの管理メールボックスアクションを変更します。

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

この例では、MailboxLogin 所有者のアクションをメールボックス フォルダーにlaura@contoso.onmicrosoft.com。

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

この例では、チーム ディスカッション メールボックスの MoveToDeletedItems 委任アクションを削除します。

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

使用する方法に関係なく、ユーザー メールボックスまたは共有メールボックスで監査メールボックスアクションをカスタマイズすると、次の結果が得られます。

- カスタマイズしたログオンの種類では、監査されるメールボックスアクションは Microsoft によって管理されなくなりました。

- カスタマイズしたログオンの種類は、前に説明したように、メールボックスの *DefaultAuditSet* プロパティ値 [に表示されなくなりました](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)。

### <a name="restore-the-default-mailbox-actions"></a>既定のメールボックス操作を復元する

ユーザー メールボックスまたは共有メールボックスで監査されるメールボックスアクションをカスタマイズした場合は、次の構文を使用して、1 つ以上のログオンの種類の既定のメールボックスアクションを復元できます。

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

複数の *DefaultAuditSet 値をコンマ* で区切って指定できます。

**注**: 次の手順は、Microsoft 365 グループ メールボックスには適用されません (ここで説明する既定の操作に限定 [されます](#mailbox-actions-for-microsoft-365-group-mailboxes))。

この例では、メールボックス サーバー上のすべてのログオンの種類に対する既定の監査メールボックスアクションをmark@contoso.onmicrosoft.com。

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

この例では、メールボックス chris@contoso.onmicrosoft.com の Admin ログオンの種類に対する既定の監査メールボックス アクションを復元しますが、委任ログオンの種類と所有者ログオンの種類に合わせてカスタマイズされた監査メールボックスアクションは残します。

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

ログオンの種類に対する既定の監査メールボックス操作を復元すると、次の結果が得られます。

- メールボックスアクションの現在のリストは、ログオンの種類の既定のメールボックスアクションに置き換えられる。

- Microsoft によってリリースされた新しいメールボックスアクションは、ログオンの種類の監査済みアクションの一覧に自動的に追加されます。

- メールボックス *の DefaultAuditSet* プロパティの値が更新され、復元されたログオンの種類が含まれます。

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>組織のメールボックス監査を既定で有効にする

Exchange Online PowerShell で次のコマンドを実行すると、組織全体のメールボックス監査を既定で無効にできます。

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

メールボックスの監査を既定で無効にした場合、次の結果が得られます。

- 組織のメールボックス監査は無効になっています。

- 既定でメールボックス監査を無効にした時間から、メールボックスで監査が有効になっている場合でも、メールボックスの操作は監査されません (メールボックスの *AuditEnabled* プロパティは **True** です)。

- 新しいメールボックスに対してメールボックス監査が有効になっていない場合、新規または既存のメールボックスの *AuditEnabled* プロパティを **True** に設定しても無視されます。

- メールボックス監査バイパスの関連付け設定 **(Set-MailboxAuditBypassAssociation** コマンドレットを使用して構成) は無視されます。

- 既存のメールボックス監査レコードは、レコードの監査ログの有効期限が切れるまで保持されます。

### <a name="turn-on-mailbox-auditing-on-by-default"></a>既定でメールボックス監査を有効にする

組織のメールボックス監査を有効に戻すには、Exchange Online PowerShell で次のコマンドを実行します。

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>メールボックス監査ログをバイパスする

現時点では、既定によるメールボックス監査の有効化が組織でオンになっている場合は、特定のメールボックスでメールボックス監査を無効にできません。 たとえば *、AuditEnabled メールボックス プロパティを* **False** に設定しても無視されます。

ただし、Exchange Online PowerShell で **Set-MailboxAuditBypassAssociation** コマンドレットを引き続き使用して、アクションが発生した場所に関係なく、指定したユーザーによるすべてのメールボックス操作がログに記録されるのを防ぐことが可能です。 例:

- バイパスされたユーザーによって実行されたメールボックス所有者の操作はログに記録されません。

- 他のユーザーのメールボックス (共有メールボックスを含む) でバイパスされたユーザーによって実行された委任アクションはログに記録されません。

- バイパスされたユーザーによって実行された管理者の操作はログに記録されません。

特定のユーザーのメールボックス監査ログをバイパスするには、ユーザーの名前、電子メール アドレス、エイリアス、またはユーザー プリンシパル名 (ユーザー名) に置き換え、次のコマンド \<MailboxIdentity\> を実行します。

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

特定のユーザーについて監査がバイパスされていることを確認するには、次のコマンドを実行します。

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

値 **True** は、メールボックス監査ログがユーザーに対してバイパスされるかどうかを示します。

## <a name="more-information"></a>詳細

- メールボックス監査ログは、すべての組織で既定で有効になっていますが、E5 ライセンスを持つユーザーだけが、既定でセキュリティ [&](search-the-audit-log-in-security-and-compliance.md) コンプライアンス センターまたは [Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)管理アクティビティ API を介して監査ログ検索でメールボックス監査ログ イベントを **返** します。

  E5 ライセンスのないユーザーのメールボックス監査ログ エントリを取得するには、次の方法があります。

  - 個々のメールボックスでメールボックス監査を手動で有効にします (コマンドを実行します `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` )。 この操作を行 &った後は、セキュリティ/コンプライアンス センターまたは Office 365 管理アクティビティ API を介して、監査ログ検索を使用できます。
  
    > [!NOTE]
    > メールボックスの監査がメールボックスで既に有効になっていると思うが、検索で結果が返されない場合は _、AuditEnabled_ パラメーターの値を次の値に変更してから、その値に戻 `$false` ります `$true` 。
  
  - Exchange Online PowerShell で次のコマンドレットを使用します。

    - [Search-MailboxAuditLog を使用](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) して、特定のユーザーのメールボックス監査ログを検索します。

    - [New-MailboxAuditLogSearch](https://docs.microsoft.com/powershell/module/exchange/new-mailboxauditlogsearch) は、メールボックス監査ログで特定のユーザーを検索し、その結果を電子メールで指定された受信者に送信します。

  - Exchange Online の Exchange 管理センター (EAC) を使用して、次のアクションを実行します。

    - [メールボックス監査ログのエクスポート](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)

    - [所有者以外のメールボックス アクセスのレポートを実行する](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- 既定では、メールボックス監査ログ レコードは削除される前に 90 日間保持されます。 Exchange Online PowerShell の **Set-Mailbox** コマンドレットの *AuditLogAgeLimit* パラメーターを使用して、監査ログ レコードの保存期限を変更できます。 ただし、この値を大きくしても、監査ログで 90 日以上前のイベントを検索できない。

  保存期間を増やす場合は、Exchange Online PowerShell で [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) コマンドレットを使用して、90 日より古いレコードについてユーザーのメールボックス監査ログを検索する必要があります。

- 組織のメールボックス監査が既定で有効にされる前に、メールボックスの *AuditLogAgeLimit* プロパティを変更した場合、メールボックスの既存の監査ログの保存期限は変更されません。 つまり、既定のメールボックス監査は、メールボックス監査レコードの現在の保存時間制限に影響を与えるという意味です。

- Microsoft 365 グループ メールボックスの *AuditLogAgeLimit* 値を変更するには、スイッチを `-GroupMailbox` **Set-Mailbox コマンドに含める必要** があります。

- メールボックス監査ログ レコードは、各ユーザーのメールボックスの [回復可能なアイテム] フォルダー内のサブフォルダー *(Audits* という名前) に格納されます。 メールボックス監査レコードと回復可能なアイテム フォルダーについては、次の点に注意してください。

  - メールボックス監査レコードは、回復可能なアイテム フォルダーの記憶域クォータ (既定では 30 GB) にカウントされます (警告クォータは 20 GB です)。 記憶域クォータは、次の場合に自動的に 100 GB に増加します (警告クォータは 90 GB です)。

    - メールボックスにホールドが適用されます。

    - メールボックスは、コンプライアンス センターのアイテム保持ポリシーに割り当てられます。

  - メールボックス監査レコードは、回復可能なアイテム [フォルダーのフォルダー制限にもカウントされます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)。 最大 300 万アイテム (監査レコード) を Audits サブフォルダーに格納できます。

    > [!NOTE]
    > メールボックス監査が既定で記憶域クォータまたは回復可能なアイテム フォルダーのフォルダー制限に影響を与える可能性は低い。

    - Exchange Online PowerShell で次のコマンドを実行すると、回復可能なアイテム フォルダーの Audits サブフォルダー内のアイテムのサイズと数を表示できます。

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - [回復可能なアイテム] フォルダー内の監査ログ レコードに直接アクセスすることはできません。代わりに **、Search-MailboxAuditLog** コマンドレットを使用するか、監査ログを検索してメールボックス監査レコードを検索して表示します。

- メールボックスが保留にされている場合、またはコンプライアンス センターのアイテム保持ポリシーに割り当てられている場合、監査ログ レコードは、メールボックスの *AuditLogAgeLimit* プロパティで定義されている期間 (既定では 90 日間) 保持されます。 保持中のメールボックスの監査ログ レコードを長く保持するには、メールボックスの *AuditLogAgeLimit* 値を増やす必要があります。

- 複数地域環境では、複数地域のメールボックスの監査はサポートされていません。 たとえば、異なる地理的位置にある共有メールボックスにアクセスする権限がユーザーに割り当てられている場合、そのユーザーが実行したメールボックス操作は、共有メールボックスのメールボックス監査ログに記録されません。
