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
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
description: メールボックス監査ログは、既定で有効になっています (既定Microsoft 365既定のメールボックス監査またはメールボックス監査とも呼ばれています)。 つまり、メールボックスの所有者、代理人、管理者によって実行される特定のアクションは、メールボックス監査ログに自動的に記録され、メールボックスで実行されたアクティビティを検索できます。
ms.openlocfilehash: 06386651c163fa3e4408f2e7a918fe30030ede06
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2021
ms.locfileid: "61423409"
---
# <a name="manage-mailbox-auditing"></a>メールボックスの監査を管理する

2019 年 1 月から、Microsoft はすべての組織で既定でメールボックス監査ログを有効にしています。 つまり、メールボックスの所有者、代理人、管理者によって実行される特定のアクションは自動的にログに記録され、メールボックス監査ログでメールボックス監査レコードを検索するときに対応するメールボックス監査レコードを使用できます。 既定でメールボックス監査を有効にする前に、組織内のすべてのユーザー メールボックスに対して手動で有効にする必要があります。

既定では、メールボックス監査の利点を次に示します。

- 新しいメールボックスを作成すると、監査が自動的に有効になります。 新しいユーザーに対して手動で有効にする必要はありません。
- 監査されるメールボックスアクションを管理する必要はない。 既定では、ログオンの種類 (管理者、代理人、所有者) ごとに、定義済みのメールボックス アクションのセットが監査されます。
- Microsoft が新しいメールボックス アクションをリリースすると、既定で監査されるメールボックス アクションの一覧 (適切なライセンスを持つユーザーに応じて) にアクションが自動的に追加される場合があります。 つまり、メールボックスに新しいアクションを追加する監視を行う必要がなされません。
- 組織全体で一貫したメールボックス監査ポリシーがあります (すべてのメールボックスに対して同じアクションを監査しているから)。

> [!NOTE]
>
> - 既定では、メールボックス監査のリリースについて覚えておく必要がある重要な点は、メールボックス監査を管理するために何もする必要はありません。 ただし、詳細については、既定の設定からメールボックス監査をカスタマイズするか、完全にオフにするか、この記事を参照してください。
> - 既定では、E5 ユーザーのメールボックス監査イベントだけが、Microsoft 365 コンプライアンス センター または Office 365 管理アクティビティ API を介して監査ログ検索で使用できます。 詳細については、この記事の [「詳細」](#more-information) セクションを参照してください。

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>既定によるメールボックス監査の有効化がオンになっていることを確認する

組織で既定でメールボックス監査が有効になっていることを確認するには[、PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)で次のコマンドExchange Onlineします。

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

値 **False は** 、既定でメールボックス監査が組織に対して有効になっている状態を示します。 既定では、組織の値がオンの場合、特定のメールボックスのメールボックス監査設定が上書きされます。 たとえば、メールボックスのメールボックス監査が無効になっている場合 (メールボックスの *AuditEnabled* プロパティは **False)、** 既定ではメールボックス監査が組織で有効になっているため、メールボックスの既定のメールボックス操作は引き続き監査されます。

特定のメールボックスに対してメールボックス監査を無効に保つために、メールボックス所有者およびメールボックスへのアクセスを委任された他のユーザーのメールボックス監査バイパスを構成します。 詳細については、この記事の「 [メールボックス監査ログのバイパス](#bypass-mailbox-audit-logging) 」セクションを参照してください。

> [!NOTE]
> 組織で既定でメールボックス監査が有効になっている場合、影響を受けるメールボックスの *AuditEnabled* プロパティは False から True に **変更****されません**。 つまり、既定でメールボックスの監査は、メールボックスの *AuditEnabled* プロパティを無視します。

## <a name="supported-mailbox-types"></a>サポートされているメールボックスの種類

次の表に、既定でメールボックス監査で現在サポートされているメールボックスの種類を示します。

<br>

****

|メールボックスの種類|サポート|
|---|:---:|
|ユーザー メールボックス|![チェック マーク。](../media/checkmark.png)|
|共有メールボックス|![チェック マーク。](../media/checkmark.png)|
|Microsoft 365 グループ メールボックス|![チェック マーク。](../media/checkmark.png)|
|リソース メールボックス||
|パブリック フォルダー メールボックス||
|

## <a name="logon-types-and-mailbox-actions"></a>ログオンの種類とメールボックスの操作

ログオンの種類は、メールボックスで監査された操作を行ったユーザーを分類します。 次の一覧では、メールボックス監査ログで使用されるログオンの種類について説明します。

- **所有者**: メールボックスの所有者 (メールボックスに関連付けられているアカウント)。
- **デリゲート**:
  - SendAs、SendOnBehalf、または FullAccess アクセス許可が別のメールボックスに割り当てられているユーザー。
  - ユーザーのメールボックスに FullAccess アクセス許可が割り当てられている管理者。
- **管理者**:
  - メールボックスは、次の Microsoft 電子情報開示ツールのいずれかを使用して検索されます。
    - コンプライアンス センターのコンテンツ検索。
    - コンプライアンス センター Advanced eDiscovery電子情報開示または電子情報開示。
    - In-Placeで電子情報開示をExchange Online。
  - メールボックスにアクセスするには、MAPI エディター Microsoft Exchange Server使用します。

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a>ユーザー メールボックスと共有メールボックスのメールボックスアクション

次の表では、ユーザー のメールボックスと共有メールボックスのメールボックス監査ログで使用できるメールボックスの操作について説明します。

- チェック マーク (![チェック マーク。](../media/checkmark.png)) は、ログオンの種類に対してメールボックス アクションをログに記録できる (すべての種類のログオンに対してすべてのアクションが使用できる場合ではない) を示します。
- チェック マークの後にアスタリスク ( ) を指定すると、ログオンの種類に対して既定でメールボックスアクション <sup>\*</sup> がログに記録されます。
- メールボックスに対するフル アクセス許可を持つ管理者は代理人と見なされます。

<br>

****

|メールボックスアクション|説明|管理者|代理人|Owner|
|---|---|:---:|:---:|:---:|
|**AddFolderPermissions**|この値はメールボックス アクションとして受け入れ可能ですが **、UpdateFolderPermissions** アクションに既に含まれており、個別に監査されません。 つまり、この値を使用しない。||||
|**ApplyRecord**|アイテムはレコードとしてラベル付けされます。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|
|**コピーする**|メッセージが別のフォルダーにコピーされました。|![チェック マーク。](../media/checkmark.png)|||
|**Create**|メールボックス内の予定表、連絡先、メモ、またはタスク フォルダーにアイテムが作成されました (たとえば、新しい会議出席依頼が作成されます)。 メッセージの作成、送信、または受信は監査されません。 また、メールボックス フォルダーの作成も監査されません。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../media/checkmark.png)|
|**FolderBind**|メールボックス フォルダーがアクセスされました。この操作は、管理者または委任されたユーザーがメールボックスを開いたときにも記録されます。<br/><br/> **注**: 代理人によって実行されるフォルダー バインド アクションの監査レコードは統合されます。 24 時間以内に個々のフォルダー アクセスに対して 1 つの監査レコードが生成されます。|![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)||
|**HardDelete**|メッセージが [回復可能なアイテム] フォルダーから削除されました。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|
|**MailboxLogin**|ユーザーが自分のメールボックスにサインインしました。|||![チェック マーク](../media/checkmark.png)|
|**MailItemsAccessed**|**注**: この値は、E5 または E5 コンプライアンス アドオンのサブスクリプション ユーザーにのみ使用できます。 詳細については、「Set [up Advanced Audit in Microsoft 365」 を参照してください](set-up-advanced-audit.md)。 <p> メール データは、メール プロトコルとクライアントによってアクセスされます。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**MessageBind**|**注**: この値は、E3 ユーザー (E5 または E5 コンプライアンス アドオン サブスクリプションのないユーザー) でのみ使用できます。 <p> メッセージがプレビュー ウィンドウで表示されたか、管理者によって開かされました。|![チェック マーク](../media/checkmark.png)|||
|**ModifyFolderPermissions**|この値はメールボックス アクションとして受け入れ可能ですが **、UpdateFolderPermissions** アクションに既に含まれており、個別に監査されません。 つまり、この値を使用しない。||||
|**移動する**|メッセージが別のフォルダーに移動されました。|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|
|**MoveToDeletedItems**|メッセージが削除され、[削除済みアイテム] フォルダーに移動されました。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**RecordDelete**|レコードとしてラベル付けされたアイテムが削除されました (回復可能なアイテム フォルダーに移動)。 レコードとしてラベル付けされたアイテムを完全に削除することはできません (回復可能なアイテム フォルダーから削除)。|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|
|**RemoveFolderPermissions**|この値はメールボックス アクションとして受け入れ可能ですが **、UpdateFolderPermissions** アクションに既に含まれており、個別に監査されません。 つまり、この値を使用しない。||||
|**SearchQueryInitiated**|**注**: この値は、E5 または E5 コンプライアンス アドオンのサブスクリプション ユーザーにのみ使用できます。 詳細については、「Set [up Advanced Audit in Microsoft 365」 を参照してください](set-up-advanced-audit.md)。 <p> ユーザーは Outlook (Windows、Mac、iOS、Android、Outlook on the web) または Windows 10 のメール アプリを使用してメールボックス内のアイテムを検索します。|||![チェック マーク](../media/checkmark.png)|
|**Send**|**注**: この値は、E5 または E5 コンプライアンス アドオンのサブスクリプション ユーザーにのみ使用できます。 詳細については、「Set [up Advanced Audit in Microsoft 365」 を参照してください](set-up-advanced-audit.md)。 <p> ユーザーが電子メール メッセージを送信したり、電子メール メッセージに返信したり、電子メール メッセージを転送したりします。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>||![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|SendAs アクセス許可を使用してメッセージが送信されました (他のユーザーがこのメールボックスの所有者を装ってメッセージを送信しました)。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|SendOnBehalf アクセス許可を使用してメッセージが送信されました (他のユーザーがこのメールボックスの所有者の代理人としてメッセージを送信しました)。この場合は、メッセージの名目上の送信者と実際の送信者が受信者に示されます。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|メッセージが完全に削除された、つまり [削除済みアイテム] フォルダーから削除されました。削除済み (回復可能) アイテムは、回復可能なアイテム フォルダーに移動されます。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**更新**|メッセージまたはプロパティが変更されました。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**UpdateCalendarDelegation**|メールボックスに予定表の委任が割り当てられました。予定表の委任により、同じ組織の他のユーザーに、メールボックス所有者の予定表を管理する権限が付与されます。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>||![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**UpdateComplianceTag**|別の保持ラベルがメール アイテムに適用されます (アイテムに割り当て可能な保持ラベルは 1 つのみです)。|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|
|**UpdateFolderPermissions**|フォルダーのアクセス許可が変更されました。 フォルダーのアクセス許可では、メールボックス内のフォルダーとそれらのフォルダーに格納されているメッセージにアクセスできる組織内のユーザーを制限します。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**UpdateInboxRules**|受信トレイ ルールが追加、削除、または変更されました。 受信トレイ ルールは、指定した条件に基づいてユーザーの受信トレイ内のメッセージを処理し、指定したフォルダーへのメッセージの移動やメッセージの削除など、ルールの条件が満たされた場合にアクションを実行するために使用されます。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|

> [!IMPORTANT]
> 既定でメールボックス監査が組織で有効にされる前に、ログオンの種類を監査するようにメールボックスアクションをカスタマイズした場合、カスタマイズされた設定はメールボックスに保持され、このセクションで説明する既定のメールボックスアクションでは上書きされません。 監査メールボックスのアクションを既定値 (いつでも実行できる) に戻すには、この記事の後半[](#restore-the-default-mailbox-actions)の「既定のメールボックスアクションの復元」セクションを参照してください。

### <a name="mailbox-actions-for-microsoft-365-group-mailboxes"></a>グループ メールボックスのMicrosoft 365アクション

既定でメールボックスの監査を行う場合、メールボックス監査ログは Microsoft 365 グループ メールボックスになりますが、ログに記録されている項目をカスタマイズすることはできません (ログオンの種類に対してログに記録されるメールボックスアクションを追加または削除することはできません)。

次の表では、ログオンの種類ごとにグループ メールボックスに既定Microsoft 365ログに記録されるメールボックスの操作について説明します。

グループ メールボックスへのフル アクセス権限を持つ管理者はMicrosoft 365代理人と見なされます。

<br>

****

|メールボックスアクション|説明|管理者|代理人|Owner|
|---|---|:---:|:---:|:---:|
|**Create**|予定表アイテムの作成。 メッセージの作成、送信、または受信は監査されません。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>||
|**HardDelete**|メッセージが [回復可能なアイテム] フォルダーから削除されました。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**MoveToDeletedItems**|メッセージが削除され、[削除済みアイテム] フォルダーに移動されました。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|SendAs アクセス許可を使用してメッセージが送信されました。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|SendOnBehalf アクセス許可を使用してメッセージが送信されました。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|メッセージが完全に削除された、つまり [削除済みアイテム] フォルダーから削除されました。削除済み (回復可能) アイテムは、回復可能なアイテム フォルダーに移動されます。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**更新**|メッセージまたはプロパティが変更されました。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>ログオンの種類ごとに既定のメールボックスアクションがログに記録されるのを確認する

既定でメールボックス監査を実行すると、新しい *DefaultAuditSet* プロパティがすべてのメールボックスに追加されます。 このプロパティの値は、既定のメールボックスアクション (Microsoft によって管理される) がメールボックスで監査されているかどうかを示します。

ユーザー メールボックスまたは共有メールボックスに値を表示するには、メールボックスの名前、エイリアス、電子メール アドレス、またはユーザー プリンシパル名 (ユーザー名) に置き換え、Exchange Online PowerShell で次の \<MailboxIdentity\> コマンドを実行します。

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

グループ メールボックスの値Microsoft 365表示するには、共有メールボックスの名前、エイリアス、または電子メール アドレスに置き換え、PowerShell で次の \<MailboxIdentity\> コマンドExchange Onlineします。

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

この値 `Admin, Delegate, Owner` は、次の値を示します。

- 3 つのログオンの種類すべてに対する既定のメールボックスアクションが監査中です。 これは、グループ メールボックスに表示されるMicrosoft 365値です。
- 管理者は *、ユーザー メールボックス* または共有メールボックス上のログオンの種類に対する監査メールボックスアクションを変更していない。 これは、既定でメールボックス監査が組織で最初に有効になった後の既定の状態です。

管理者がログオンの種類 **(Set-Mailbox** コマンドレットで AuditAdmin、AuditDelegate、または *AuditOwner* パラメーターを使用して) 監査されるメールボックスアクションを変更した場合、プロパティ値は異なります。

たとえば、ユーザー メールボックスまたは `Owner` 共有メールボックス *の DefaultAuditSet* プロパティの値は、次の値を示します。

- メールボックス所有者の既定のメールボックスアクションが監査中です。
- 監査されたメールボックスアクションとログオン `Delegate` の種類は `Admin` 、既定のアクションから変更されています。

*DefaultAuditSet* プロパティの空の値は、ユーザー メールボックスまたは共有メールボックスで 3 つのログオンの種類すべてが変更されたメールボックスアクションを示します。

詳細については、この記事の「 [既定](#change-or-restore-mailbox-actions-logged-by-default) でログに記録されたメールボックスアクションの変更または復元」セクションを参照してください。

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a>メールボックスにログオンしているメールボックスのアクションを表示する

現在ユーザー メールボックスまたは共有メールボックスにログオンしているメールボックスアクションを確認するには、メールボックスの名前、エイリアス、電子メール アドレス、またはユーザー プリンシパル名 (ユーザー名) に置き換え、Exchange Online PowerShell で次のコマンドの 1 つ以上 \<MailboxIdentity\> を実行します。

> [!NOTE]
> グループ メールボックスの次の Get-Mailbox コマンドにスイッチMicrosoft 365追加することもできますが、返される値は `-GroupMailbox` 使用できません。  グループ メールボックスに対して監査される既定および静的なメールボックスアクションMicrosoft 365、この記事の前の「Microsoft 365 グループ メールボックスのメールボックスアクション」セクションで説明します。 [](#mailbox-actions-for-microsoft-365-group-mailboxes)

#### <a name="owner-actions"></a>所有者の操作

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a>代理アクション

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a>管理アクション

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>既定でログに記録されたメールボックスの操作を変更または復元する

前に説明したように、既定でメールボックスの監査を行う主な利点の 1 つは、監査されるメールボックスアクションを管理する必要がなさそうである。 Microsoft はこれを行い、既定で監査される新しいメールボックス アクションがリリースされると自動的に追加されます。

ただし、組織は、ユーザーのメールボックスと共有メールボックスに対して、異なるメールボックスアクションのセットを監査する必要がある場合があります。 このセクションの手順では、ログオンの種類ごとに監査されるメールボックスアクションを変更する方法と、Microsoft が管理する既定のアクションに戻す方法を示します。

> [!IMPORTANT]
> 次の手順を使用して、ユーザー メールボックスまたは共有メールボックスにログオンしているメールボックスアクションをカスタマイズした場合、Microsoft によってリリースされた新しい既定のメールボックスアクションは、それらのメールボックスで自動的に監査されません。 カスタマイズしたアクションの一覧に新しいメールボックス アクションを手動で追加する必要があります。

### <a name="change-the-mailbox-actions-to-audit"></a>メールボックスの操作を監査に変更する

**Set-Mailbox** コマンドレットの *AuditAdmin、AuditDelegate、* または *AuditOwner* パラメーターを使用して、ユーザー メールボックスおよび共有メールボックスに対して監査されるメールボックス アクションを変更できます (Microsoft 365 グループ メールボックスの監査アクションはカスタマイズできません)。 

2 つの異なる方法を使用して、メールボックスの操作を指定できます。

- *次* の構文を使用して、既存のメールボックスアクションを置換 (上書き) します `action1,action2,...actionN` 。
- *次の構文を使用* して、他の既存の値に影響を与えることなくメールボックスアクションを追加または `@{Add="action1","action2",..."actionN"}` 削除します `@{Remove="action1","action2",..."actionN"}` 。

この例では、SoftDelete と HardDelete を使用して既定のアクションを上書きすることで、"ガブリエラ Laureano" という名前のメールボックスの管理メールボックスアクションを変更します。

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

次の使用例は、MailboxLogin 所有者アクションをメールボックス サーバーに追加 laura@contoso.onmicrosoft.com。

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

この例では、チーム ディスカッション メールボックスの MoveToDeletedItems デリゲート アクションを削除します。

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

使用する方法に関係なく、ユーザー メールボックスまたは共有メールボックスに対して監査されたメールボックスアクションをカスタマイズすると、次の結果が得られます。

- カスタマイズしたログオンの種類では、監査されたメールボックスアクションは Microsoft によって管理されなくなりました。
- カスタマイズしたログオンの種類は、前に説明したように、メールボックス *の DefaultAuditSet* プロパティ値 [に表示されなくなりました](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)。

### <a name="restore-the-default-mailbox-actions"></a>既定のメールボックス操作を復元する

> [!NOTE]
> 次の手順は、グループ メールボックスMicrosoft 365適用されません (ここで説明する既定のアクションに限定[されます](#mailbox-actions-for-microsoft-365-group-mailboxes))。

ユーザー メールボックスまたは共有メールボックスで監査されるメールボックスアクションをカスタマイズした場合は、次の構文を使用して、1 つ以上のログオンの種類の既定のメールボックス アクションを復元できます。

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

複数の *DefaultAuditSet* 値をコンマで区切って指定できます

次の使用例は、メールボックス サーバー上のすべてのログオンの種類に対する既定の監査 mark@contoso.onmicrosoft.com。

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

この例では、メールボックス chris@contoso.onmicrosoft.com の管理者ログオンの種類に対する既定の監査メールボックス アクションを復元しますが、代理人ログオンの種類と所有者のログオンの種類に合わせてカスタマイズされた監査メールボックスアクションは残ります。

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

ログオンの種類に対する既定の監査メールボックス アクションを復元すると、次の結果が得られます。

- メールボックスアクションの現在のリストは、ログオンの種類の既定のメールボックス アクションに置き換えられる。
- Microsoft によってリリースされた新しいメールボックス アクションは、ログオンの種類の監査済みアクションの一覧に自動的に追加されます。
- メールボックス *の DefaultAuditSet* プロパティ値が更新され、復元されたログオンの種類が含まれます。

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>組織の既定でメールボックス監査を無効にする

PowerShell で次のコマンドを実行すると、組織全体のメールボックス監査を既定で無効Exchange Onlineできます。

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

既定でメールボックス監査を無効にした場合、次の結果が得られます。

- 組織のメールボックス監査は無効になっています。
- 既定でメールボックス監査を無効にした時刻から、メールボックスで監査が有効になっている場合でも、メールボックスの操作は監査されません (メールボックスの *AuditEnabled* プロパティは **True** です)。
- 新しいメールボックスのメールボックス監査は有効ではなく、新しいメールボックスまたは既存のメールボックスの *AuditEnabled* プロパティを **True** に設定しても無視されます。
- メールボックス監査バイパス関連付け設定 **(Set-MailboxAuditBypassAssociation** コマンドレットを使用して構成) は無視されます。
- 既存のメールボックス監査レコードは、レコードの監査ログの有効期限が切れるまで保持されます。

### <a name="turn-on-mailbox-auditing-on-by-default"></a>既定でメールボックス監査を有効にする

組織のメールボックス監査を有効に戻す場合は、PowerShell で次のコマンドExchange Onlineします。

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>メールボックス監査ログをバイパスする

現時点では、既定によるメールボックス監査の有効化が組織でオンになっている場合は、特定のメールボックスでメールボックス監査を無効にできません。 たとえば *、AuditEnabled メールボックス プロパティを* **False に設定すると** 、無視されます。

ただし、Exchange Online PowerShell の **Set-MailboxAuditBypassAssociation** コマンドレットを使用して、アクションが発生した場所に関係なく、指定したユーザーによるメールボックスアクションのログが記録されるのを防ぐことはできます。 例:

- バイパスされたユーザーによって実行されるメールボックス所有者の操作はログに記録されません。
- 他のユーザーのメールボックス (共有メールボックスを含む) でバイパスされたユーザーによって実行される委任アクションはログに記録されません。
- バイパスされたユーザーが実行した管理アクションはログに記録されません。

特定のユーザーのメールボックス監査ログをバイパスするには、ユーザーの名前、電子メール アドレス、エイリアス、またはユーザー プリンシパル名 (ユーザー名) に置き換え、次の \<MailboxIdentity\> コマンドを実行します。

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

特定のユーザーについて監査がバイパスされていることを確認するには、次のコマンドを実行します。

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

値 **True は** 、メールボックス監査ログがユーザーに対してバイパスされるかどうかを示します。

## <a name="more-information"></a>詳細情報

- メールボックス監査ログオンは既定ですべての組織で有効になっていますが [、E5](search-the-audit-log-in-security-and-compliance.md)ライセンスを持つユーザーだけが、Microsoft 365 コンプライアンス センター または [Office 365 管理](/office/office-365-management-api/office-365-management-activity-api-reference)アクティビティ API を介して監査ログ検索でメールボックス監査ログ イベントを既定で **返** します。

  E5 ライセンスのないユーザーのメールボックス監査ログ エントリを取得するには、次の処理を実行できます。

  - 個々のメールボックスでメールボックス監査を手動で有効にします (コマンドを実行します `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` )。 この操作を行った後、監査ログ検索は、Microsoft 365 コンプライアンス センター管理アクティビティ API をOffice 365使用できます。

    > [!NOTE]
    > メールボックス監査が既にメールボックスで有効になっていると思うが、検索で結果が返されない場合は _、AuditEnabled_ パラメーターの値をに変更してからに `$false` 戻します `$true` 。

  - PowerShell で次のコマンドレットをExchange Onlineします。
    - [Search-MailboxAuditLog を](/powershell/module/exchange/search-mailboxauditlog) 使用して、特定のユーザーのメールボックス監査ログを検索します。
    - [New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) を使用して、特定のユーザーのメールボックス監査ログを検索し、指定した受信者に電子メールで結果を送信します。

  - 次の<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchangeを実行するには、Exchange Online管理センター (EAC)</a>を使用します。
    - [メールボックス監査ログのエクスポート](/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)
    - [所有者以外のメールボックス アクセスのレポートを実行する](/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- 既定では、メールボックス監査ログ レコードは削除される前に 90 日間保持されます。 監査ログ レコードの有効期限を変更するには、PowerShell の **Set-Mailbox** コマンドレットの *AuditLogAgeLimit* パラメーターをExchange Onlineできます。 ただし、この値を増やすと、監査ログで 90 日より前のイベントを検索できます。

  年齢制限を増やす場合は、Exchange Online PowerShell の[Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog)コマンドレットを使用して、ユーザーのメールボックス監査ログで 90 日以上前のレコードを検索する必要があります。

- 既定で組織のメールボックス監査が有効にされる前に、メールボックスの *AuditLogAgeLimit* プロパティを変更した場合、メールボックスの既存の監査ログの年齢制限は変更されません。 つまり、既定でメールボックスを監査しても、メールボックス監査レコードの現在の年齢制限には影響はありません。

- グループ メールボックスの *AuditLogAgeLimit* 値をMicrosoft 365するには、Set-Mailbox コマンドにスイッチを含 `-GroupMailbox` **める必要** があります。

- メールボックス監査ログ レコードは、各ユーザーのメールボックスの回復可能なアイテム フォルダーのサブフォルダー *(Audits)* に格納されます。 メールボックス監査レコードと回復可能なアイテム フォルダーについては、次の点に注意してください。

  - メールボックス監査レコードは、回復可能なアイテム フォルダーの記憶域クォータに対してカウントされます (既定では 30 GB です (警告クォータは 20 GB)。 記憶域クォータは、次の場合に自動的に 100 GB (90 GB の警告クォータ) に増加します。
    - メールボックスに保留が設定されます。
    - メールボックスは、コンプライアンス センターのアイテム保持ポリシーに割り当てられます。

  - メールボックス監査レコードは、回復可能なアイテム [フォルダーのフォルダー制限にもカウントされます](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)。 Audits サブフォルダーには、最大 300 万アイテム (監査レコード) を格納できます。

    > [!NOTE]
    > 既定でメールボックスの監査が記憶域クォータまたは回復可能なアイテム フォルダーのフォルダー制限に影響を与える可能性は低い。

    - PowerShell で次のコマンドをExchange Onlineして、[回復可能なアイテム] フォルダーの Audits サブフォルダーにアイテムのサイズと数を表示できます。

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - [回復可能なアイテム] フォルダーの監査ログ レコードに直接アクセスすることはできません。代わりに **、Search-MailboxAuditLog** コマンドレットを使用するか、監査ログを検索してメールボックス監査レコードを検索および表示します。

- メールボックスを保留にするか、コンプライアンス センターのアイテム保持ポリシーに割り当てられている場合、監査ログ レコードは、メールボックスの *AuditLogAgeLimit* プロパティによって定義されている期間 (既定では 90 日間) 保持されます。 メールボックスの保留時間に対して監査ログ レコードを長く保持するには、メールボックスの *AuditLogAgeLimit* 値を増やす必要があります。

- 複数地域環境では、複数地域のメールボックスの監査はサポートされていません。 たとえば、異なる地理的位置にある共有メールボックスにアクセスする権限がユーザーに割り当てられている場合、そのユーザーが実行したメールボックス操作は、共有メールボックスのメールボックス監査ログに記録されません。
