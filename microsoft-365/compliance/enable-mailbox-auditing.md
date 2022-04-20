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
description: Microsoft 365では、既定でメールボックス監査ログが有効になります ("既定のメールボックス監査" または "既定のメールボックス監査" とも呼ばれます)。 この構成は、メールボックスの所有者、代理人、および管理者によって実行される特定のアクションがメールボックス監査ログに自動的に記録され、メールボックスで実行されたアクティビティを検索できることを意味します。
ms.openlocfilehash: bb8170b603bc72459e3bbd55fa256df188f42f65
ms.sourcegitcommit: e911dd506ea066795e418daf7b84c1e11381a21c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64952888"
---
# <a name="manage-mailbox-auditing"></a>メールボックスの監査を管理する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

2019 年 1 月以降、Microsoft はすべての組織で既定でメールボックス監査ログを有効にしています。 つまり、メールボックスの所有者、代理人、管理者によって実行される特定のアクションが自動的にログに記録され、メールボックス監査ログで検索すると、対応するメールボックス監査レコードを使用できるようになります。 メールボックス監査を既定で有効にする前に、組織内のすべてのユーザー メールボックスに対して手動で有効にする必要がありました。

既定では、メールボックス監査の利点をいくつか次に示します。

- 監査は、新しいメールボックスを作成するときに自動的に有効になります。 新しいユーザーに対して手動で有効にする必要はありません。
- 監査されるメールボックスアクションを管理する必要はありません。 定義済みのメールボックス アクションのセットは、ログオンの種類 (管理者、代理人、所有者) ごとに既定で監査されます。
- Microsoft が新しいメールボックス アクションをリリースすると、既定で監査されるメールボックス アクションの一覧にアクションが自動的に追加される場合があります (適切なライセンスを持つユーザーが対象)。 つまり、メールボックスに対する新しいアクションの追加を監視する必要はありません。
- 組織全体に一貫したメールボックス監査ポリシーがあります (すべてのメールボックスに対して同じアクションを監査しているため)。

> [!NOTE]
>
> - 既定でメールボックス監査のリリースについて覚えておく必要がある重要な点は、メールボックス監査を管理するために何もする必要がないことです。 ただし、詳細については、既定の設定からメールボックスの監査をカスタマイズするか、完全に無効にしてください。この記事は役に立ちます。
> - 既定では、E5 ユーザーのメールボックス監査イベントのみが、Microsoft Purview コンプライアンス ポータルまたは Office 365 Management Activity API を使用して監査ログ検索で使用できます。 詳細については、この記事の [「詳細情報](#more-information) 」セクションを参照してください。

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>既定によるメールボックス監査の有効化がオンになっていることを確認する

組織のメールボックス監査が既定で有効になっていることを確認するには、[powerShell で](/powershell/exchange/connect-to-exchange-online-powershell)次のコマンドExchange Online実行します。

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

**False** の値は、組織のメールボックス監査が既定で有効になっていることを示します。 これは、既定で組織の値によって、特定のメールボックスのメールボックス監査設定よりも優先されます。 たとえば、メールボックスに対してメールボックスの監査が無効になっている場合 ( *メールボックスの AuditEnabled* プロパティは **False** )、既定のメールボックス操作は、組織に対して既定でメールボックス監査が有効になっているため、メールボックスに対して監査されます。

特定のメールボックスに対してメールボックス監査を無効に保つために、メールボックスの所有者とメールボックスへのアクセスを委任された他のユーザーに対してメールボックス監査バイパスを構成します。 詳細については、この記事の後半の「 [メールボックス監査ログのバイパス](#bypass-mailbox-audit-logging) 」セクションを参照してください。

> [!NOTE]
> 組織のメールボックス監査が既定で有効になっている場合、影響を受けるメールボックスの *AuditEnabled* プロパティは **False** から **True** に変更されません。 つまり、メールボックスの監査は既定でメールボックスの *AuditEnabled* プロパティを無視します。

## <a name="supported-mailbox-types"></a>サポートされているメールボックスの種類

次の表は、既定でメールボックス監査によって現在サポートされているメールボックスの種類を示しています。

|メールボックスの種類|サポート|
|---|:---:|
|ユーザー メールボックス|![チェック マーク。](../media/checkmark.png)|
|共有メールボックス|![チェック マーク。](../media/checkmark.png)|
|Microsoft 365 グループ メールボックス|![チェック マーク。](../media/checkmark.png)|
|リソース メールボックス||
|パブリック フォルダー メールボックス||

## <a name="logon-types-and-mailbox-actions"></a>ログオンの種類とメールボックスの操作

ログオンの種類は、メールボックスで監査されたアクションを実行したユーザーを分類します。 次の一覧では、メールボックス監査ログで使用されるログオンの種類について説明します。

- **所有者**: メールボックスの所有者 (メールボックスに関連付けられているアカウント)。
- **デリゲート**:
  - SendAs、SendOnBehalf、または FullAccess アクセス許可が別のメールボックスに割り当てられているユーザー。
  - ユーザーのメールボックスに FullAccess アクセス許可が割り当てられている管理者。
- **管理者**:
  - メールボックスは、次のいずれかの Microsoft 電子情報開示ツールで検索されます。
    - コンプライアンス センターのコンテンツ検索。
    - コンプライアンス センターの電子情報開示またはAdvanced eDiscovery。
    - Exchange Onlineで電子情報開示をIn-Placeします。
  - メールボックスには、Microsoft Exchange Server MAPI エディターを使用してアクセスします。

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a>ユーザー メールボックスと共有メールボックスのメールボックス アクション

次の表では、ユーザー メールボックスと共有メールボックスのメールボックス監査ログで使用できるメールボックスアクションについて説明します。

- チェック マーク (![チェック マーク。](../media/checkmark.png)) は、ログオンの種類に対してメールボックス アクションをログに記録できることを示します (すべての種類のログオンに対してすべてのアクションを使用できるわけではありません)。
- チェック マークの後のアスタリスク ( <sup>\*</sup> ) は、ログオンの種類に対してメールボックスアクションが既定でログに記録されていることを示します。
- メールボックスに対するフル アクセス権限を持つ管理者は代理人と見なされることに注意してください。

|メールボックス アクション|説明|管理者|代理人|Owner|
|---|---|:---:|:---:|:---:|
|**AddFolderPermissions**|この値はメールボックス アクションとして受け入れられますが、 **UpdateFolderPermissions** アクションに既に含まれており、個別に監査されることはありません。 つまり、この値は使用しないでください。||||
|**ApplyRecord**|アイテムにはレコードとしてラベルが付けられます。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|
|**コピーする**|メッセージが別のフォルダーにコピーされました。|![チェック マーク。](../media/checkmark.png)|||
|**Create**|メールボックスの予定表、連絡先、下書き、メモ、またはタスク フォルダーにアイテムが作成されました (たとえば、新しい会議出席依頼が作成されます)。 メッセージの作成、送信、または受信は監査されません。 また、メールボックス フォルダーの作成も監査されません。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../media/checkmark.png)|
|**FolderBind**|メールボックス フォルダーがアクセスされました。この操作は、管理者または委任されたユーザーがメールボックスを開いたときにも記録されます。<br/><br/> **注**: デリゲートによって実行されるフォルダー バインド アクションの監査レコードは統合されます。 24 時間以内に個々のフォルダー アクセスに対して 1 つの監査レコードが生成されます。|![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)||
|**HardDelete**|メッセージが [回復可能なアイテム] フォルダーから削除されました。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|
|**MailboxLogin**|ユーザーが自分のメールボックスにサインインしている。|||![チェック マーク](../media/checkmark.png)|
|**MailItemsAccessed**|**注**: この値は、E5/A5/G5 ライセンスを持つユーザーにのみ使用できます。 詳細については、「[Microsoft Purview 監査のセットアップ (プレミアム)](set-up-advanced-audit.md)」を参照してください。 <br/><br/> メール データには、メール プロトコルとクライアントによってアクセスされます。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**MessageBind**|**注**: この値は、E5/A5/G5 ライセンス *を持たない* ユーザーにのみ使用できます。 <br/><br/> メッセージがプレビュー ウィンドウで表示されたか、管理者によって開かれた。|![チェック マーク](../media/checkmark.png)|||
|**ModifyFolderPermissions**|この値はメールボックス アクションとして受け入れられますが、 **UpdateFolderPermissions** アクションに既に含まれており、個別に監査されることはありません。 つまり、この値は使用しないでください。||||
|**移動する**|メッセージが別のフォルダーに移動されました。|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|
|**MoveToDeletedItems**|メッセージが削除され、[削除済みアイテム] フォルダーに移動されました。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**RecordDelete**|レコードとしてラベル付けされたアイテムが論理的に削除されました (回復可能なアイテム フォルダーに移動されました)。 レコードとしてラベル付けされたアイテムを完全に削除することはできません (回復可能なアイテム フォルダーから削除されます)。|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|
|**RemoveFolderPermissions**|この値はメールボックス アクションとして受け入れられますが、 **UpdateFolderPermissions** アクションに既に含まれており、個別に監査されることはありません。 つまり、この値は使用しないでください。||||
|**SearchQueryInitiated**|**注**: この値は、E5/A5/G5 ライセンスを持つユーザーにのみ使用できます。 詳細については、「[Microsoft Purview 監査のセットアップ (プレミアム)](set-up-advanced-audit.md)」を参照してください。 <br/><br/> ユーザーはOutlook (Windows、Mac、iOS、Android、またはOutlook on the web) またはメール アプリをWindows 10に使用してメールボックス内のアイテムを検索します。|||![チェック マーク](../media/checkmark.png)|
|**Send**|**注**: この値は、E5/A5/G5 ライセンスを持つユーザーにのみ使用できます。 詳細については、「[Microsoft Purview 監査のセットアップ (プレミアム)](set-up-advanced-audit.md)」を参照してください。 <br/><br/> ユーザーが電子メール メッセージを送信したり、電子メール メッセージに返信したり、電子メール メッセージを転送したりします。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>||![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|SendAs アクセス許可を使用してメッセージが送信されました (他のユーザーがこのメールボックスの所有者を装ってメッセージを送信しました)。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|SendOnBehalf アクセス許可を使用してメッセージが送信されました (他のユーザーがこのメールボックスの所有者の代理人としてメッセージを送信しました)。この場合は、メッセージの名目上の送信者と実際の送信者が受信者に示されます。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|メッセージが完全に削除された、つまり [削除済みアイテム] フォルダーから削除されました。削除済み (回復可能) アイテムは、回復可能なアイテム フォルダーに移動されます。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**Update**|メッセージまたはそのプロパティのいずれかが変更されました。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**UpdateCalendarDelegation**|メールボックスに予定表の委任が割り当てられました。予定表の委任により、同じ組織の他のユーザーに、メールボックス所有者の予定表を管理する権限が付与されます。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>||![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**UpdateComplianceTag**|別の保持ラベルがメール アイテムに適用されます (アイテムに割り当てられる保持ラベルは 1 つだけです)。|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|
|**UpdateFolderPermissions**|フォルダーのアクセス許可が変更されました。 フォルダーのアクセス許可では、メールボックス内のフォルダーとそれらのフォルダーに格納されているメッセージにアクセスできる組織内のユーザーを制限します。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**UpdateInboxRules**|受信トレイルールが追加、削除、または変更されました。 受信トレイ ルールは、指定した条件に基づいてユーザーの受信トレイ内のメッセージを処理し、ルールの条件が満たされたときにアクションを実行するために使用されます 。たとえば、メッセージを指定したフォルダーに移動したり、メッセージを削除したりします。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|

> [!IMPORTANT]
> 組織で既定でメールボックス監査が有効になっている *前* に、ログオンの種類を監査するようにメールボックスアクションをカスタマイズした場合、カスタマイズされた設定はメールボックスに保持され、このセクションで説明されているように既定のメールボックスアクションでは上書きされません。 監査メールボックスアクションを既定値に戻すには (いつでも実行できます)、この記事の「 [既定のメールボックスアクションの復元](#restore-the-default-mailbox-actions) 」セクションを参照してください。

### <a name="mailbox-actions-for-microsoft-365-group-mailboxes"></a>Microsoft 365 グループ メールボックスのメールボックス アクション

既定でメールボックスの監査をオンにすると、メールボックス監査ログがグループ メールボックスにMicrosoft 365されますが、ログに記録される内容をカスタマイズすることはできません (ログオンの種類に対してログに記録されるメールボックスアクションを追加または削除することはできません)。

次の表では、ログオンの種類ごとに既定でMicrosoft 365 グループ メールボックスに記録されるメールボックスアクションについて説明します。

Microsoft 365 グループ メールボックスに対するフル アクセス権限を持つ管理者は代理人と見なされることに注意してください。

|メールボックス アクション|説明|管理者|代理人|Owner|
|---|---|:---:|:---:|:---:|
|**Create**|予定表アイテムの作成。 メッセージの作成、送信、または受信は監査されません。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>||
|**HardDelete**|メッセージが [回復可能なアイテム] フォルダーから削除されました。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**MoveToDeletedItems**|メッセージが削除され、[削除済みアイテム] フォルダーに移動されました。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|SendAs アクセス許可を使用してメッセージが送信されました。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|SendOnBehalf アクセス許可を使用してメッセージが送信されました。|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|メッセージが完全に削除された、つまり [削除済みアイテム] フォルダーから削除されました。削除済み (回復可能) アイテムは、回復可能なアイテム フォルダーに移動されます。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|
|**Update**|メッセージまたはそのプロパティのいずれかが変更されました。|![チェック マーク。](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../media/checkmark.png)<sup>\*</sup>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>ログオンの種類ごとに既定のメールボックス アクションがログに記録されていることを確認する

既定でメールボックス監査をオンにすると、すべてのメールボックスに新しい *DefaultAuditSet* プロパティが追加されます。 このプロパティの値は、既定のメールボックス アクション (Microsoft によって管理) がメールボックスで監査されているかどうかを示します。

ユーザー メールボックスまたは共有メールボックスに値を表示するには、メールボックスの名前、エイリアス、電子メール アドレス、またはユーザー プリンシパル名 (ユーザー名) に置き換えて\<MailboxIdentity\>、powerShell で次のコマンドExchange Online実行します。

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

Microsoft 365 グループ メールボックスに値を表示するには、共有メールボックスの名前、エイリアス、または電子メール アドレスに置き換え\<MailboxIdentity\>、powerShell で次のコマンドExchange Online実行します。

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

値 `Admin, Delegate, Owner` は次を示します。

- 3 つのログオンの種類すべてに対する既定のメールボックス アクションが監査されています。 これは、Microsoft 365 グループ メールボックスに表示される唯一の値です。
- 管理者 *は、* ユーザー メールボックスまたは共有メールボックスのログオンの種類に対して監査対象のメールボックスアクションを変更していません。 これは、既定でメールボックス監査が組織で最初に有効になった後の既定の状態であることに注意してください。

管理者がログオンの種類に対して監査されるメールボックスアクションを変更したことがある場合 (**Set-Mailbox** コマンドレットで *AuditAdmin*、*AuditDelegate*、または *AuditOwner* パラメーターを使用)、プロパティ値は異なります。

たとえば、ユーザー メールボックスまたは共有メールボックスの *DefaultAuditSet* プロパティの値`Owner`は、次を示します。

- メールボックス所有者の既定のメールボックス アクションは監査中です。
- 監査対象のメールボックスアクションと`Admin`ログオンの`Delegate`種類は、既定のアクションから変更されています。

*DefaultAuditSet* プロパティの空白値は、ユーザー メールボックスまたは共有メールボックスで、3 つのログオンの種類すべてに対するメールボックスアクションが変更されたことを示します。

詳細については、この記事の [「既定でログに記録されたメールボックスアクションの変更または復元」](#change-or-restore-mailbox-actions-logged-by-default) セクションを参照してください。

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a>メールボックスにログオンしているメールボックスアクションを表示する

ユーザー メールボックスまたは共有メールボックスに現在ログオンしているメールボックスアクションを表示するには、メールボックスの名前、エイリアス、電子メール アドレス、またはユーザー プリンシパル名 (ユーザー名) に置き換え\<MailboxIdentity\>、PowerShell で次のコマンドを 1 つ以上実行Exchange Online。

> [!NOTE]
> Microsoft 365 グループ メールボックスの次の **Get-Mailbox** コマンドにスイッチを追加`-GroupMailbox`できますが、返される値は信じられません。 Microsoft 365 グループ メールボックスに対して監査される既定のメールボックスアクションと静的メールボックスアクションについては、この記事の「[Microsoft 365 グループ メールボックスのメールボックスアクション](#mailbox-actions-for-microsoft-365-group-mailboxes)」セクションで説明しています。

#### <a name="owner-actions"></a>所有者アクション

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a>アクションを委任する

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a>管理者のアクション

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>既定でログに記録されたメールボックスアクションを変更または復元する

前に説明したように、既定でメールボックス監査を有効にすることの主な利点の 1 つは、監査されるメールボックスアクションを管理する必要がないことです。 Microsoft はこれを行い、新しいメールボックスアクションが自動的に追加され、既定でリリースされると監査されます。

ただし、組織では、ユーザー メールボックスと共有メールボックスに対して異なるメールボックス アクションのセットを監査することが必要になる場合があります。 このセクションの手順では、ログオンの種類ごとに監査されるメールボックスアクションを変更する方法と、Microsoft が管理する既定のアクションに戻す方法について説明します。

> [!IMPORTANT]
> 次の手順を使用して、ユーザー メールボックスまたは共有メールボックスにログオンするメールボックスアクションをカスタマイズする場合、Microsoft によってリリースされた新しい既定のメールボックスアクションは、それらのメールボックスに対して自動的に監査されません。 カスタマイズしたアクションの一覧に新しいメールボックスアクションを手動で追加する必要があります。

### <a name="change-the-mailbox-actions-to-audit"></a>メールボックスアクションを監査に変更する

**Set-Mailbox** コマンドレットの *AuditAdmin*、*AuditDelegate*、または *AuditOwner* パラメーターを使用して、ユーザー メールボックスと共有メールボックスに対して監査されるメールボックスアクションを変更できます (Microsoft 365 グループ メールボックスの監査アクションはカスタマイズできません)。

メールボックスアクションを指定するには、次の 2 つの異なる方法を使用できます。

- 次の構文`action1,action2,...actionN`を使用して、既存のメールボックスアクションを *置き換える* (上書き) します。
- 次の構文を使用して、他の既存の値に影響を与えずにメールボックスアクションを *追加または*`@{Remove="action1","action2",..."actionN"}`削除します`@{Add="action1","action2",..."actionN"}`。

次の使用例は、既定のアクションを SoftDelete と HardDelete で上書きすることで、"Gabriela Laureano" という名前のメールボックスの管理者メールボックスアクションを変更します。

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

次の使用例は、MailboxLogin 所有者アクションをメールボックス laura@contoso.onmicrosoft.com に追加します。

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

次の使用例は、Team Discussion メールボックスの MoveToDeletedItems デリゲート アクションを削除します。

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

使用する方法に関係なく、ユーザー メールボックスまたは共有メールボックスに対する監査対象メールボックスアクションをカスタマイズすると、次の結果が得られます。

- カスタマイズしたログオンの種類の場合、監査対象のメールボックスアクションは Microsoft によって管理されなくなります。
- カスタマイズしたログオンの種類は、[前に説明](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)したように、メールボックスの *DefaultAuditSet* プロパティ値に表示されなくなりました。

### <a name="restore-the-default-mailbox-actions"></a>既定のメールボックスアクションを復元する

> [!NOTE]
> 次の手順は、Microsoft 365 グループ メールボックスには適用されません ([ここで説明するように](#mailbox-actions-for-microsoft-365-group-mailboxes)、既定のアクションに限定されます)。

ユーザー メールボックスまたは共有メールボックスで監査されるメールボックスアクションをカスタマイズした場合、次の構文を使用して、1 つまたはすべてのログオンの種類の既定のメールボックス アクションを復元できます。

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

複数の *DefaultAuditSet* 値をコンマで区切って指定できます

次の使用例は、メールボックス mark@contoso.onmicrosoft.com 上のすべてのログオンの種類に対する既定の監査対象メールボックス アクションを復元します。

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

次の使用例は、メールボックス chris@contoso.onmicrosoft.com の管理者ログオンの種類の既定の監査済みメールボックス アクションを復元しますが、委任ログオンと所有者ログオンの種類に対してカスタマイズされた監査済みメールボックスアクションは残します。

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

ログオンの種類に対する既定の監査対象メールボックス アクションを復元すると、次の結果が得られます。

- 現在のメールボックス アクションの一覧は、ログオンの種類の既定のメールボックス アクションに置き換えられます。
- Microsoft によってリリースされたすべての新しいメールボックス アクションは、ログオンの種類の監査済みアクションの一覧に自動的に追加されます。
- 復元されたログオンの種類を含めるために、メールボックスの *DefaultAuditSet* プロパティ値が更新されます。

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>組織のメールボックス監査を既定で無効にする

PowerShell で次のコマンドを実行すると、組織全体のメールボックス監査を既定でオフExchange Onlineできます。

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

既定でメールボックス監査を無効にすると、次の結果が得られます。

- 組織のメールボックス監査は無効になっています。
- メールボックスの監査を既定で無効にした時点から、メールボックスで監査が有効になっている場合でも、メールボックスの操作は監査されません (メールボックスの *AuditEnabled* プロパティは **True** です)。
- 新しいメールボックスに対してメールボックスの監査が有効になっていないと、新しいメールボックスまたは既存のメールボックスの *AuditEnabled* プロパティを **True** に設定することは無視されます。
- メールボックス監査バイパス関連付け設定 ( **Set-MailboxAuditBypassAssociation** コマンドレットを使用して構成) は無視されます。
- 既存のメールボックス監査レコードは、レコードの監査ログの有効期限が切れるまで保持されます。

### <a name="turn-on-mailbox-auditing-on-by-default"></a>既定でメールボックス監査をオンにする

組織のメールボックス監査を再度有効にするには、powerShell で次のコマンドExchange Online実行します。

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>メールボックス監査ログをバイパスする

現時点では、既定によるメールボックス監査の有効化が組織でオンになっている場合は、特定のメールボックスでメールボックス監査を無効にできません。 たとえば、 *AuditEnabled* メールボックス プロパティを **False** に設定することは無視されます。

ただし、Exchange Online PowerShell で **Set-MailboxAuditBypassAssociation** コマンドレットを使用して、アクションが発生した場所に関係なく、指定したユーザーによる *メールボックス操作の* ログ記録を防ぐことができます。 例:

- バイパスされたユーザーによって実行されたメールボックス所有者アクションはログに記録されません。
- バイパスされたユーザーが他のユーザーのメールボックス (共有メールボックスを含む) で実行した委任アクションはログに記録されません。
- バイパスされたユーザーによって実行された管理者アクションはログに記録されません。

特定のユーザーについてメールボックス監査ログをバイパスするには、\<MailboxIdentity\> をそのユーザーの名前、メール アドレス、エイリアス、またはユーザー プリンシパル名 (username) で置き換え、次のコマンドを実行します。

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

特定のユーザーについて監査がバイパスされていることを確認するには、次のコマンドを実行します。

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

値 **True** は、ユーザーのメールボックス監査ログがバイパスされることを示します。

## <a name="more-information"></a>詳細情報

- 既定ではすべての組織でメールボックス監査ログオンが有効になっていますが、E5 ライセンスを持つユーザーのみが [、Microsoft Purview コンプライアンス ポータル](search-the-audit-log-in-security-and-compliance.md)または [既定で Office 365 Management Activity API](/office/office-365-management-api/office-365-management-activity-api-reference) を使用して監査ログ検索でメールボックス監査ログ イベント **を** 返します。

  E5/A5/G5 ライセンスを持たないユーザーのメールボックス監査ログ エントリを取得するには、次のいずれかの回避策を使用できます。

  - 個々のメールボックスでメールボックス監査を手動で有効にします (コマンドを実行します `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true`)。 これを行った後は、Microsoft Purview コンプライアンス ポータルまたは Office 365 Management Activity API を使用して監査ログ検索を使用できます。

    > [!NOTE]
    > メールボックスでメールボックスの監査が既に有効になっているように見えるが、検索で結果が返されない場合は、 *AuditEnabled* パラメーターの値を `$false` 変更してから `$true`、 .

  - PowerShell で次のコマンドレットExchange Online使用します。
    - [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) を使用して、特定のユーザーのメールボックス監査ログを検索します。
    - [New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) を使用して、特定のユーザーのメールボックス監査ログを検索し、指定した受信者に電子メールで結果を送信します。

  - Exchange OnlineのExchange管理センター (EAC) を使用して、次の操作を実行します。
    - [メールボックス監査ログのエクスポート](/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)
    - [所有者以外のメールボックス アクセスのレポートを実行する](/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- 既定では、メールボックス監査ログ レコードは、削除される前に 90 日間保持されます。 PowerShell の **Set-Mailbox** コマンドレットの *AuditLogAgeLimit* パラメーターを使用して、監査ログ レコードの有効期間制限Exchange Online変更できます。 ただし、この値を大きくしても、監査ログで 90 日を超えるイベントを検索することはできません。

  年齢制限を引き上げる場合は、Exchange Online PowerShell の [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) コマンドレットを使用して、ユーザーのメールボックス監査ログで 90 日を超えるレコードを検索する必要があります。

- 組織のメールボックス監査が既定で有効になっている前にメールボックスの *AuditLogAgeLimit* プロパティを変更した場合、メールボックスの既存の監査ログの有効期間の制限は変更されません。 言い換えると、既定でメールボックス監査は、メールボックス監査レコードの現在の年齢制限には影響しません。

- Microsoft 365 グループ メールボックスの *AuditLogAgeLimit* 値を変更するには、メールボックスの **設定** コマンドにスイッチを含める`-GroupMailbox`必要があります。

- メールボックス監査ログ レコードは、各ユーザーのメールボックスの回復可能なアイテム フォルダー内のサブフォルダー ( *Audit* という名前) に格納されます。 メールボックス監査レコードと回復可能なアイテム フォルダーについては、次の点に注意してください。

  - メールボックス監査レコードは、回復可能なアイテム フォルダーのストレージ クォータ (既定では 30 GB) に対してカウントされます (警告クォータは 20 GB です)。 ストレージ クォータは、次の場合に自動的に 100 GB に増やされます (警告クォータは 90 GB)。
    - ホールドはメールボックスに配置されます。
    - メールボックスは、コンプライアンス センターのアイテム保持ポリシーに割り当てられます。

  - メールボックス監査レコードは、 [回復可能なアイテム フォルダーのフォルダーの制限](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)に対してもカウントされます。 監査サブフォルダーには、最大 300 万個のアイテム (監査レコード) を格納できます。

    > [!NOTE]
    > 既定でメールボックスの監査がストレージ クォータまたは回復可能なアイテム フォルダーのフォルダーの制限に影響を与える可能性は低くなります。

    - PowerShell Exchange Onlineで次のコマンドを実行して、[回復可能なアイテム] フォルダーの [監査] サブフォルダーにアイテムのサイズと数を表示できます。

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - 回復可能なアイテム フォルダー内の監査ログ レコードに直接アクセスすることはできません。代わりに、 **Search-MailboxAuditLog** コマンドレットを使用するか、監査ログを検索してメールボックス監査レコードを検索して表示します。

- メールボックスがコンプライアンス センターで保持またはアイテム保持ポリシーに割り当てられている場合、監査ログ レコードは、メールボックスの *AuditLogAgeLimit* プロパティによって定義されている期間 (既定では 90 日間) 保持されます。 保留中のメールボックスの監査ログ レコードを長く保持するには、メールボックスの *AuditLogAgeLimit* 値を増やす必要があります。

- 複数地域環境では、複数地域のメールボックスの監査はサポートされていません。 たとえば、異なる地理的位置にある共有メールボックスにアクセスする権限がユーザーに割り当てられている場合、そのユーザーが実行したメールボックス操作は、共有メールボックスのメールボックス監査ログに記録されません。 Exchange管理者監査イベントは、現在、既定の場所でのみ使用できます。
