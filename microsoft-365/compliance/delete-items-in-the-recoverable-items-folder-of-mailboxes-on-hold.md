---
title: クラウド メールボックスの保留リストの回復可能なアイテム フォルダー内のアイテムを削除する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
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
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: 管理者がユーザーの回復可能なアイテム フォルダー内のアイテムを Exchange Online メールボックスに対して削除する方法について説明します(そのメールボックスが法的に保持されている場合でも)。
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
ms.openlocfilehash: 89022e39aef17609774c90696e7bab54e66a95e0
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2021
ms.locfileid: "61421656"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold"></a>保留中のクラウド ベースのメールボックスの 回復可能なアイテム フォルダーのアイテムを削除する

偶発的または悪意のある削除から保護Exchange Onlineメールボックスの回復可能なアイテム フォルダーが存在します。 また、保持機能や電子情報開示検索などのコンプライアンス機能によって保持およびアクセスされるアイテムを格納するためにも使用されます。 ただし、組織によっては、削除する必要がある回復可能なアイテム フォルダーに意図せずに保持されたデータがある場合があります。 たとえば、ユーザーが知らないうちに、ビジネスに重大な影響を与える可能性がある機密情報や情報を含む電子メール メッセージを送信または転送する場合があります。 メッセージが完全に削除された場合でも、メールボックスに法的な保留が設定されたため、メッセージは無期限に保持される可能性があります。 このシナリオは *、データが* 意図せずにデータに流出したため、データ流出と呼Office 365。 このような状況では、Exchange Online メールボックスのユーザーの回復可能なアイテム フォルダー内のアイテムを削除できます 。Office 365 で保持機能が異なる場合でも、そのメールボックスを保留にします。 これらの種類の保持には、Office 365 または Microsoft 365 のセキュリティとコンプライアンス センターで作成された訴訟ホールド、In-Place 保持、電子情報開示保持、保持ポリシーが含まれます。

この記事では、管理者が保留状態のクラウドベースのメールボックスの回復可能なアイテム フォルダーからアイテムを削除する方法について説明します。 この手順では、メールボックスへのアクセスを無効にし、単一アイテムの回復を無効にし、管理フォルダー アシスタントによるメールボックスの処理を無効にし、保留リストを一時的に削除し、回復可能なアイテム フォルダーからアイテムを削除し、メールボックスを以前の構成に戻します。 その手順は次のとおりです。
  
[手順 1: メールボックスに関する情報を収集する](#step-1-collect-information-about-the-mailbox)

[手順 2: メールボックスを準備する](#step-2-prepare-the-mailbox)

[手順 3: メールボックスからすべての保留リストを削除する](#step-3-remove-all-holds-from-the-mailbox)

[手順 4: メールボックスから遅延ホールドを削除する](#step-4-remove-the-delay-hold-from-the-mailbox)

[手順 5: 回復可能なアイテム フォルダー内のアイテムを削除する](#step-5-delete-items-in-the-recoverable-items-folder)

[手順 6: メールボックスを以前の状態に戻す](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> この記事で説明する手順では、データがメールボックスから完全に削除 (削除) されるExchange Onlineされます。 つまり、[回復可能なアイテム] フォルダーから削除したメッセージは回復できないので、法的な検出や他のコンプライアンスの目的では使用できません。 Microsoft 365 コンプライアンス センター で作成された訴訟ホールド、In-Place ホールド、電子情報開示ホールド、または保持ポリシーの一部として保留にされているメールボックスからメッセージを削除する場合は、保留を削除する前にレコード管理または法務部門に確認してください。 組織には、メールボックスを保留にするか、データ流出インシデントが優先されるのかを定義するポリシーがある場合があります。
  
## <a name="before-you-delete-items"></a>アイテムを削除する前に

- コンテンツ検索を作成して実行するには、電子情報開示管理者役割グループのメンバーであるか、コンプライアンス検索の管理役割が割り当てられている必要があります。 メッセージを削除するには、Organization Management 役割グループのメンバーであるか、検索と消去の管理役割が割り当てられている必要があります。 役割グループにユーザーを追加する方法については、「電子情報開示のアクセス許可を割り当 [てる」を参照してください](./assign-ediscovery-permissions.md)。

- メールボックスが組織全体のアイテム保持ポリシーに割り当てられている場合は、回復可能なアイテム フォルダーからアイテムを削除する前に、ポリシーからメールボックスを除外する必要があります。 ポリシーの変更を同期し、ポリシーからメールボックスを削除するには、最大で 24 時間かかる場合があります。 詳細については、この記事の「メールボックスからすべての保持を削除する」[](#organization-wide-retention-policies)セクションの「組織全体の保持ポリシー」を参照してください。

- 保持設定が割り当てられているメールボックスに対して、保持ロックを使用してロックされているアイテム保持ポリシーを使用して、この手順を実行することはできません。 これは、このロックによって、ポリシーからメールボックスを削除または除外したり、メールボックスの管理フォルダー アシスタントを無効にしたりしないのでです。 保持ポリシーのロックの詳細については、「保持ロックを使用してアイテム保持ポリシーと保持ラベル ポリシーへの変更を制限する」 [を参照してください](retention-preservation-lock.md)。

- この記事で説明する手順は、非アクティブなメールボックスではサポートされていません。 これは、非アクティブなメールボックスを削除した後に、保持 (または保持ポリシー) を再適用できないためです。 非アクティブなメールボックスから保留リストを削除すると、そのメールボックスは通常の削除済みメールボックスに変更され、管理フォルダー アシスタントによって処理された後、組織から完全に削除されます。

- メールボックスが保留 (または単一アイテムの回復が有効になっていない) 場合は、[回復可能なアイテム] フォルダーからアイテムを削除できます。 これを行う方法の詳細については、「組織内の電子メール メッセージを検索および削除する」 [を参照してください](./search-for-and-delete-messages-in-your-organization.md)。

## <a name="step-1-collect-information-about-the-mailbox"></a>手順 1: メールボックスに関する情報を収集する

この最初の手順は、この手順に影響を与えるターゲット メールボックスから選択したプロパティを収集します。 これらの設定の一部を変更し、回復可能なアイテム フォルダーからアイテムを削除した後、手順 6 で元の値に戻すので、これらの設定を書き込むか、テキスト ファイルに保存してください。 収集する必要があるメールボックスのプロパティの一覧を次に示します。
  
- *SingleItemRecoveryEnabled および*  *RetainDeletedItemsFor*. 必要に応じて、手順 3 で単一の回復を無効にし、削除済みアイテムの保持期間を長くします。

- *LitigationHoldEnabled および*  *InPlaceHolds*. 手順 3 で一時的にメールボックスを削除するには、メールボックスに配置されている保留リストを特定する必要があります。 メールボックスに [配置される可能性](#more-information) がある種類の保持を特定する方法のヒントについては、「詳細」セクションを参照してください。

また、この手順で所有者 (または他のユーザー) がメールボックスにアクセスできない状態で一時的に無効にできるよう、メールボックス クライアント アクセス設定を取得する必要があります。 最後に、回復可能なアイテム フォルダー内のアイテムの現在のサイズと数を取得できます。 手順 5 の [回復可能なアイテム] フォルダー内のアイテムを削除した後、この情報を使用してアイテムが削除されたのを確認します。
  
1. [Exchange Online PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。 管理者アカウントで適切な管理役割が割り当てられている管理者アカウントには、必ずユーザー名とパスワードを使用Exchange Online。

2. 次のコマンドを実行して、単一アイテムの回復と削除済みアイテムの保持期間に関する情報を取得します。

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   単一アイテムの回復が有効になっている場合は、手順 2 で無効にする必要があります。 削除されたアイテムの保持期間が 30 日間 (Exchange Online の最大値) に設定されていない場合は、手順 2 で増やします。

3. 次のコマンドを実行して、メールボックスのメールボックス アクセス設定を取得します。

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   手順 2 で、これらすべてのアクセス方法を無効にします。

4. 次のコマンドを実行して、メールボックスに適用される保持ポリシーと保持ポリシーに関する情報を取得します。

    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```

    > [!TIP]
    > *InPlaceHolds* プロパティに値が多すぎて、すべての値が表示されない場合は、コマンドを実行して各値を個別の行 `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` に表示できます。
  
5. 次のコマンドを実行して、組織全体の保持ポリシーに関する情報を取得します。 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```

   組織に組織全体の保持ポリシーがある場合は、手順 3 でこれらのポリシーからメールボックスを除外する必要があります。 変更のレプリケートには最大 24 時間かかる場合があります。

    > [!TIP]
    > *InPlaceHolds* プロパティに値が多すぎて、すべての値が表示されない場合は、コマンドを実行して各値を個別の行 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` に表示できます。 
  
6. 次のコマンドを実行して、メールボックスに遅延ホールドが適用されるかどうかを判断します。

   ```powershell
   Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
   ```

   *DelayHoldApplied* プロパティまたは *DelayReleaseHoldApplied* プロパティの値が **True** に設定されている場合は、メールボックスに遅延ホールドが適用され、削除する必要があります。 遅延ホールドの詳細については、「手順 [4: メールボックス](#step-4-remove-the-delay-hold-from-the-mailbox)から遅延ホールドを削除する」を参照してください。

   いずれかのプロパティの値が **False** に設定されている場合は、メールボックスに遅延ホールドが適用されないので、手順 4 をスキップできます。

7. 次のコマンドを実行して、ユーザーのプライマリ メールボックスの回復可能なアイテム フォルダー内のフォルダーとサブフォルダー内のアイテムの現在のサイズと総数を取得します。

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   ユーザーのアーカイブ メールボックスが有効になっている場合は、次のコマンドを実行して、アーカイブ メールボックスの [回復可能なアイテム] フォルダー内のフォルダーとサブフォルダー内のアイテムのサイズと総数を取得します。 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   手順 5 でアイテムを削除すると、ユーザーのプライマリ アーカイブ メールボックスの回復可能なアイテム フォルダー内のアイテムを削除するか削除しないか選択できます。 メールボックスに対して自動拡張アーカイブが有効になっている場合、補助アーカイブ メールボックス内のアイテムは削除されません。
  
## <a name="step-2-prepare-the-mailbox"></a>手順 2: メールボックスを準備する

メールボックスに関する情報を収集して保存した後、次の手順では、次のタスクを実行してメールボックスを準備します。
  
- **メールボックスへのクライアント アクセスを無効** にして、メールボックスの所有者がメールボックスにアクセスして、この手順の間にメールボックス データに変更を加えきらなけい。

- 削除 **済みアイテム** の保持期間を 30 日 (Exchange Online の最大値) に増やして、手順 5 でアイテムを削除する前に[回復可能なアイテム] フォルダーからアイテムが削除されない。

- **手順** 5 の [回復可能なアイテム] フォルダーからアイテムを削除した後、アイテムを (削除済みアイテムの保持期間の間) 保持しないので、単一のアイテムの回復を無効にします。

- **管理フォルダー アシスタントを無効** にして、メールボックスを処理し、手順 5 で削除したアイテムを保持します。

PowerShell の次の手順をExchange Onlineします。
  
1. 次のコマンドを実行して、メールボックスへのすべてのクライアント アクセスを無効にします。 コマンド構文では、すべてのクライアント アクセス方法がメールボックスで有効になっていると仮定します。

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

    > [!NOTE]
    > メールボックスへのすべてのクライアント アクセス方法を無効にするには、最大 60 分かかる場合があります。 これらのアクセス方法を無効にしても、現在サインインしているメールボックスの所有者は切断されません。 所有者がサインインしていない場合、これらのアクセス方法が無効にされた後、所有者は自分のメールボックスにアクセスできなくなります。
  
2. 次のコマンドを実行して、削除済みアイテムの保持期間を最大 30 日間増やします。 これは、現在の設定が 30 日未満である必要があります。

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. 次のコマンドを実行して、単一アイテムの回復を無効にします。

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

    > [!NOTE]
    > 単一アイテムの回復を無効にするには、最大 240 分かかる場合があります。 この期間が経過するまで、[回復可能なアイテム] フォルダー内のアイテムを削除しない。
  
4. 次のコマンドを実行して、管理フォルダー アシスタントがメールボックスを処理できません。 前に説明したように、保持ロックを持つアイテム保持ポリシーがメールボックスに適用されていない場合にのみ、管理フォルダー アシスタントを無効にできます。

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>手順 3: メールボックスからすべての保留リストを削除する

回復可能なアイテム フォルダーからアイテムを削除する前の最後の手順は、メールボックスに配置された (手順 1 で識別した) すべての保留リストを削除します。 アイテムを [回復可能なアイテム] フォルダーから削除した後にアイテムを保持しないので、すべての保留リストを削除する必要があります。 次のセクションでは、メールボックスのさまざまな種類の保留リストを削除する方法について説明します。 メールボックスに [配置される可能性](#more-information) がある種類の保持を特定する方法のヒントについては、「詳細」セクションを参照してください。 詳細については、「How to identify of hold of placed on the Exchange Online メールボックス 」[を参照してください](identify-a-hold-on-an-exchange-online-mailbox.md)。
  
> [!CAUTION]
> 前に述べたように、メールボックスから保留リストを削除する前に、レコード管理部門または法務部門に確認してください。
  
### <a name="litigation-hold"></a>訴訟ホールド
  
PowerShell で次のコマンドをExchange Onlineメールボックスから訴訟ホールドを削除します。

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

> [!NOTE]
> 単一アイテムの回復を無効にした場合と同様に、訴訟ホールドを削除するには最大で 240 分かかる場合があります。 この期間が経過するまで、[回復可能なアイテム] フォルダーからアイテムを削除しない。
  
### <a name="in-place-hold"></a>インプレース ホールド
  
PowerShell で次のコマンドExchange Online実行して、メールボックスにIn-Place保持するサーバーを識別します。 手順 1 で特定In-Place保持の GUID を使用します。

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

保留リストをIn-Placeした後、Exchange 管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">(EAC)</a>または Exchange Online PowerShell を使用して、メールボックスを保留リストから削除できます。 詳細については、「Create [or remove an In-Place Hold 」を参照してください](/exchange/security-and-compliance/create-or-remove-in-place-holds)。
  
### <a name="retention-policies-applied-to-specific-mailboxes"></a>特定のメールボックスに適用されるアイテム保持ポリシー
  
セキュリティ センター PowerShell で次& [コマンドを](/powershell/exchange/connect-to-scc-powershell) 実行して、メールボックスに適用されるアイテム保持ポリシーを特定します。 このコマンドは、メールボックスに適用Teams保持ポリシーを返します。 手順 1 で識別したアイテム保持ポリシーの GUID (プレフィックスは含めない `mbx` `skp` ) を使用します。

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

アイテム保持ポリシーを特定した後  >  、Microsoft 365 コンプライアンス センター の [情報ガバナンスの保持] ページに移動し、前の手順で識別したアイテム保持ポリシーを編集し、保持ポリシーに含まれる受信者の一覧からメールボックスを削除します。
  
### <a name="organization-wide-retention-policies"></a>組織全体に対するアイテム保持ポリシー
  
組織全体、Exchange、Teams全体の保持ポリシーは、組織内のすべてのメールボックスに適用されます。 これらは組織レベル (メールボックス レベルではなく) で適用され、手順 1 で **Get-OrganizationConfig** コマンドレットを実行すると返されます。 コンプライアンス センター PowerShell のセキュリティ & [コマンドを](/powershell/exchange/exchange-online-powershell) 実行して、組織全体の保持ポリシーを識別します。 手順 1 で特定した組織全体の保持ポリシーの GUID (プレフィックスを含む  `mbx` ) を使用します。

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

組織全体の保持ポリシーを特定した後  >  、Microsoft 365 コンプライアンス センター の [情報ガバナンス保持] ページに移動し、前の手順で特定した各組織全体の保持ポリシーを編集し、除外された受信者の一覧にメールボックスを追加します。 これにより、ユーザーのメールボックスがアイテム保持ポリシーから削除されます。

> [!IMPORTANT]
> 組織全体のアイテム保持ポリシーからメールボックスを除外した後、この変更を同期してポリシーからメールボックスを削除するには、最大で 24 時間かかる場合があります。

### <a name="retention-labels"></a>保持ラベル

ユーザーがコンテンツを保持するか、保持し、メールボックス内の任意のフォルダーまたはアイテムにコンテンツを削除するように構成されたラベルを適用するたびに *、ComplianceTagHoldApplied* メールボックス プロパティは **True** に設定されます。 この場合、メールボックスは訴訟ホールドに置かれたか、保持ポリシーに割り当てられているかのように、保留と見なされます。

*ComplianceTagHoldApplied* プロパティの値を表示するには、PowerShell で次Exchange Onlineします。

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

アイテム保持ラベルがフォルダーまたはアイテムに適用されたため、メールボックスが保留状態にあると特定した後、Microsoft 365 コンプライアンス センター のコンテンツ検索ツールを使用して、保持ラベル条件を使用してラベル付きアイテムを検索できます。  詳細については、以下を参照してください。

- 「アイテム保持ポリシーと保持ラベルの詳細」の「コンテンツ検索を使用して特定の保持ラベルを持つすべてのコンテンツを[検索](retention.md#using-content-search-to-find-all-content-with-a-specific-retention-label)する」セクション

- コンテンツ検索のキーワード クエリと検索条件の 「検索条件 [」セクション](keyword-queries-and-search-conditions.md#conditions-for-common-properties)。

ラベルの詳細については、「アイテム保持ポリシーと [保持ラベルについて」を参照してください](retention.md)。

### <a name="ediscovery-holds"></a>電子情報開示の保留
  
セキュリティ & コンプライアンス センター [PowerShell](/powershell/exchange/connect-to-scc-powershell) で次のコマンドを実行して、メールボックスに適用される電子情報開示ケース (電子情報開示ホールドと呼 *ばれる)* に関連付けられている保留リストを識別します。 手順 1 で識別した電子情報開示ホールドの GUID (プレフィックスを含む  `UniH` ) を使用します。 2 番目のコマンドは、保留リストが関連付けられている電子情報開示ケースの名前を表示します。3 番目のコマンドは、保留リストの名前を表示します。
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

電子情報開示ケースと保留リストの名前を特定した後、コンプライアンス センターの電子情報開示電子情報開示ページに移動し、ケースを開き、メールボックスを保留リストから削除します \> 。 電子情報開示の保持を識別する方法の詳細については、「電子情報開示の保持」セクション「電子情報開示メールボックスに配置された保留の種類を識別する方法」[をExchange Onlineしてください](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)。
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>手順 4: メールボックスから遅延ホールドを削除する

メールボックスから任意の種類の保留リストを削除すると *、DelayHoldApplied* または *DelayReleaseHoldApplied* メールボックス プロパティの値が True に設定 **されます**。 これは、次に管理フォルダー アシスタントがメールボックスを処理し、保留リストが削除されたと検出した場合に発生します。 これは遅延保留と呼ばれて、メールボックスからデータが完全に削除されるのを防ぐために、実際の保留の削除が 30 日間遅れることを意味します。 (遅延ホールドの目的は、管理者に、保留リストが削除された後に削除されるメールボックス アイテムを検索または回復する機会を与える目的です。 メールボックスに遅延ホールドが設定されている場合でも、メールボックスが訴訟ホールドの対象である場合と同様に、メールボックスは無制限の期間保留であると見なされます。 30 日後に遅延保留が期限切れになると、Microsoft 365 は遅延ホールドを自動的に削除します *(DelayHoldApplied* プロパティまたは *DelayReleaseHoldApplied* プロパティを **False** に設定することで) 保留が削除されます。 遅延ホールドの詳細については、「方法[Exchange Online」](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)の「遅延ホールド時のメールボックスの管理」セクションを参照してください。

*DelayHoldApplied* プロパティまたは *DelayReleaseHoldApplied* プロパティの値が **True** に設定されている場合は、次のいずれかのコマンドを実行して遅延ホールドを削除します。

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

または

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

*RemoveDelayHoldApplied* または *RemoveDelayReleaseHoldApplied* パラメーターを使用するには、Exchange Onlineで法的保持ロールを割り当てる必要があります。

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>手順 5: 回復可能なアイテム フォルダー内のアイテムを削除する

セキュリティ & コンプライアンス センター PowerShell の [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) コマンドレットと [New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) コマンドレットを使用して、回復可能なアイテム フォルダー内のアイテムを実際に削除する準備ができました。

回復可能なアイテム フォルダーにあるアイテムを検索するには、対象のコレクションを実行することをお *勧めします*。 つまり、検索範囲を [回復可能なアイテム] フォルダーにあるアイテムにのみ絞り込む必要があります。 これを行うには、「対象のコレクションにコンテンツ検索を使用する」の記事 [でスクリプトを実行](use-content-search-for-targeted-collections.md) します。 このスクリプトは、ターゲットの回復可能なアイテム フォルダー内のすべてのサブフォルダーのフォルダー ID プロパティの値を返します。 次に、検索クエリのフォルダー ID を使用して、そのフォルダー内にあるアイテムを返します。

ユーザーの回復可能なアイテム フォルダー内のアイテムを検索および削除するプロセスの概要を次に示します。

1. ターゲット ユーザーのメールボックス内のすべてのフォルダーのフォルダー ID を返すターゲット コレクション スクリプトを実行します。 スクリプトは、同じ PowerShell セッションExchange Online PowerShell とセキュリティ &コンプライアンス PowerShell に接続します。 詳細については、「スクリプトを [実行してメールボックスのフォルダーの一覧を取得する」を参照してください](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site)。

2. 回復可能なアイテム フォルダー内のすべてのサブフォルダーのフォルダー ID をコピーします。 または、スクリプトの出力をテキスト ファイルにリダイレクトすることもできます。

   アイテムを検索および削除できる回復可能なアイテム フォルダー内のサブフォルダーの一覧と説明を次に示します。

   - **削除 :** 削除済みアイテムの保持期間が経過していない、削除済みアイテムが含まれます。 ユーザーは、このサブフォルダーの [削除済みアイテムの回復] ツールを使用して、このサブフォルダーから削除済みアイテムを回復Outlook。

   - **削除 :** 削除済みアイテムの保持期間が経過した、ハード削除されたアイテムが含まれます。 ユーザーは、回復可能なアイテム フォルダーからアイテムを削除することで、アイテムをハード削除することもできます。 メールボックスが保持されている場合、ハード削除されたアイテムは保持されます。 このサブフォルダーはエンド ユーザーには表示されません。

   - **DiscoveryHolds**: 電子情報開示ホールドまたはアイテム保持ポリシーによって保持されている、ハード削除されたアイテムが含まれます。 このサブフォルダーはエンド ユーザーには表示されません。

   - **SubstrateHolds**: 保持ポリシーまたは他の種類の保留によって保持されている Teams および他のクラウドベースのアプリからのハード削除されたアイテムが含まれます。 このサブフォルダーはエンド ユーザーには表示されません。

3. **New-ComplianceSearch** コマンドレット (セキュリティ & コンプライアンス センター PowerShell) を使用するか、コンプライアンス センターのコンテンツ検索ツールを使用して、ターゲット ユーザーの回復可能なアイテム フォルダーからアイテムを返すコンテンツ検索を作成します。 これを行うには、検索するサブフォルダーの検索クエリに FolderId を含める必要があります。 たとえば、次のクエリは、Purges サブフォルダーと eDiscoveryHolds サブフォルダー内のすべてのメッセージを返します。

   ```text
   folderid:<folder ID of Purges subfolder> OR folderid:<folder ID of DiscoveryHolds subfolder>
   ```

   フォルダー ID プロパティを使用するコンテンツ検索の実行の詳細と例については、「フォルダー ID を使用する」または「対象となるコレクションを実行する」 [を参照してください](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection)。

   > [!NOTE]
   > **New-ComplianceSearch** コマンドレットを使用して回復可能なアイテム フォルダーを検索する場合は **、Start-ComplianceSearch** コマンドレットを使用して検索を実行してください。

4. コンテンツ検索を作成し、削除するアイテムが返されたと検証したら、コマンド (セキュリティ & コンプライアンス センター PowerShell) を使用して、前の手順で作成したコンテンツ検索で返されたアイテムを完全に削除します。 `New-ComplianceSearchAction -Purge -PurgeType HardDelete` たとえば、次のようなコマンドを実行できます。

   ```powershell
   New-ComplianceSearchAction -SearchName "RecoverableItems" -Purge -PurgeType HardDelete
   ```

5. 前のコマンドを実行すると、メールボックスごとに最大 10 アイテムが削除されます。 つまり、[回復可能なアイテム] フォルダーで削除するアイテムを削除するには、コマンドを複数回実行 `New-ComplianceSearchAction -Purge` する必要があります。 追加のアイテムを削除するには、最初に以前のコンプライアンス検索削除アクションを削除する必要があります。 これを行うには、コマンドレットを実行 `Remove-ComplianceSearchAction` します。 たとえば、前の手順で実行した削除アクションを削除するには、次のコマンドを実行します。

   ```powershell
   Remove-ComplianceSearchAction "RecoverableItems_Purge"
   ```

   これを行った後、新しいコンプライアンス検索削除アクションを作成して、より多くのアイテムを削除できます。 新しい削除アクションを作成する前に、各削除アクションを削除する必要があります。

   コンプライアンス検索アクションの一覧を取得するには、コマンドレットを実行 `Get-ComplianceSearchAction` します。 削除アクションは、検索名 `_Purge` に追加することで識別されます。

### <a name="verify-that-items-were-deleted"></a>アイテムが削除されたのを確認する

メールボックスの回復可能なアイテム フォルダーからアイテムが正常に削除されたことを確認するには、Exchange Online PowerShell の **Get-MailboxFolderStatistics** コマンドレットを使用して、回復可能なアイテム フォルダー内のアイテムのサイズと数を確認します。 これらの統計は、手順 1 で収集した統計と比較できます。
  
次のコマンドを実行して、ユーザーのプライマリ メールボックスの回復可能なアイテム フォルダー内のフォルダーとサブフォルダー内のアイテムの現在のサイズと総数を取得します。
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

次のコマンドを実行して、ユーザーのアーカイブ メールボックスの回復可能なアイテム フォルダー内のフォルダーとサブフォルダー内のアイテムのサイズと総数を取得します。

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>手順 6: メールボックスを以前の状態に戻す

最後の手順では、メールボックスを以前の構成に戻します。 つまり、手順 2 で変更したプロパティをリセットし、手順 3 で削除した保留リストを再適用します。 これには、次の内容が含まれます。
  
- 削除済みアイテムの保持期間を以前の値に戻す。 または、この設定を 30 日に設定したままにしておき、Exchange Online。

- 単一アイテムの回復を再び有効にする。

- 所有者が自分のメールボックスにアクセスできるよう、クライアント アクセス方法を再び有効にします。

- 削除した保持ポリシーと保持ポリシーを再適用します。

- 管理フォルダー アシスタントを有効にし、メールボックスを処理します。

> [!IMPORTANT]
> Managed Folder Assistant を再び有効にしてメールボックスを処理する前に、保持ポリシーまたは保持ポリシーを再適用してから 24 時間待機することをお勧めします 。また、そのポリシーが適用されているのを確認することをお勧めします。
  
PowerShell で次の手順 (指定した順序で) をExchange Onlineします。
  
1. 次のコマンドを実行して、削除されたアイテムの保持期間を元の値に戻します。 これは、前の設定が 30 日未満である必要があります。たとえば、14 日間です。

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. 次のコマンドを実行して、単一アイテムの回復を再び有効にしてください。

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. 次のコマンドを実行して、メールボックスへのすべてのクライアント アクセス方法を再び有効にします。

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. 手順 3 で削除した保留リストを再適用します。 保留の種類に応じて、次のいずれかの手順を使用します。

    **訴訟ホールド**

    次のコマンドを実行して、メールボックスの訴訟ホールドを再び有効にします。

    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **In-Place Hold**

    EAC (または PowerShell Exchange Online) を使用して、メールボックスをサーバー保持にIn-Placeします。

    **特定のメールボックスに適用されるアイテム保持ポリシー**

    アイテム保持Microsoft 365 コンプライアンス センターにメールボックスを追加するには、次のコマンドを使用します。 コンプライアンス センターの **[情報ガバナンス** の保持] ページに移動し、保持ポリシーを編集し、保持ポリシーが適用されている受信者の一覧にメールボックスを  >  追加し戻します。

    **組織全体に対するアイテム保持ポリシー**

    組織全体または Exchange 全体のアイテム保持ポリシーをポリシーから除外して削除した場合は、Microsoft 365 コンプライアンス センター を使用して除外されたユーザーの一覧からメールボックスを削除します。 コンプライアンス センターの **[情報ガバナンス** 保持] ページに移動し、組織全体の保持ポリシーを編集し、除外された受信者の一覧からメールボックス  >  を削除します。 これにより、アイテム保持ポリシーがユーザーのメールボックスに再適用されます。

    **電子情報開示ケースホールド**

    電子情報開示ケースMicrosoft 365 コンプライアンス センター関連付けられている保留リストをメールボックスに追加するには、次の情報を使用します。 [電子情報開示コア **]**  >  **ページに移動** し、ケースを開き、メールボックスを保留リストに戻します。 

5. 次のコマンドを実行して、管理フォルダー アシスタントがメールボックスを再度処理できます。 前に述べたように、Managed Folder Assistant を再び有効にする前に、保持ポリシーまたは保持ポリシーを再適用してから 24 時間待機することをお勧めします (また、そのポリシーが適用されているのを確認してください)。

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. メールボックスが以前の構成に戻されたのを確認するには、次のコマンドを実行し、手順 1 で収集した設定と比較します。

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a>詳細情報

**Get-Mailbox** コマンドレットまたは **Get-OrganizationConfig** コマンドレットを実行するときに *、InPlaceHolds* プロパティの値に基づいてさまざまな種類の保留リストを識別する方法を示す表を次に示します。 詳細については、「メールボックスに配置された保留の種類を特定する方法」[を参照Exchange Onlineしてください](identify-a-hold-on-an-exchange-online-mailbox.md)。

前に説明したように、回復可能なアイテム フォルダー内のアイテムを正常に削除するには、メールボックスからすべての保持ポリシーと保持ポリシーを削除する必要があります。
  
| ホールドの種類 | 値の例 | 保留を識別する方法 |
|:-----|:-----|:-----|
|訴訟ホールド  <br/> | `True` <br/> |*LitigationHoldEnabled*  プロパティが  `True` に設定されています。  <br/> |
|インプレース ホールド  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |*InPlaceHolds* プロパティには、メールボックスにIn-Place保持の GUID が含まれる。 GUID はプレフィックスで始In-Place、これは保留の一部です。  <br/> PowerShell のコマンド `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` を使用Exchange Onlineメールボックスの保持に関するIn-Placeを取得できます。  <br/> |
| 特定のメールボックスに適用Microsoft 365 コンプライアンス センターアイテム保持ポリシー  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> または  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |**Get-Mailbox コマンドレットを実行** すると *、InPlaceHolds* プロパティには、メールボックスに適用される保持ポリシーの GUID も含まれる。 GUID はプレフィックスで始まるため、保持ポリシーを識別  `mbx` できます。 保持ポリシーの GUID がプレフィックスで始まる場合は、保持ポリシーがユーザーの会話に適用 `skp` Skype for Businessします。  <br/> メールボックスに適用されるアイテム保持ポリシーを識別するには、コンプライアンス センター PowerShell のセキュリティ &コマンドを実行します。 <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>このコマンドを実行する場合は、必ず、 `mbx` または  `skp` プレフィックスを削除してください。  <br/> |
|組織内の組織全体の保持ポリシー Microsoft 365 コンプライアンス センター  <br/> |値なし  <br/> または  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696` (メールボックスが組織全体のポリシーから除外される場合を示します)  <br/> |**Get-Mailbox** コマンドレットを実行するときに *InPlaceHolds* プロパティが空の場合でも、メールボックスに適用される組織全体の保持ポリシーが 1 つ以上存在する可能性があります。  <br/> これを確認するには、PowerShell でコマンドをExchange Online、組織全体の保持ポリシーの GUID の一覧 `Get-OrganizationConfig | FL InPlaceHolds` を取得できます。 メールボックスに適用される組織全体の保持ポリシーの GUID は、Exchangeプレフィックス `mbx` で始まります `mbxa3056bb15562480fadb46ce523ff7b02` 。たとえば。  <br/> メールボックスに適用される組織全体のアイテム保持ポリシーを識別するには、コンプライアンス センター PowerShell のセキュリティ &コマンドを実行します。 <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>メールボックスが組織全体のアイテム保持ポリシーから除外されている場合 **、Get-Mailbox** コマンドレットを実行すると、アイテム保持ポリシーの GUID がユーザーのメールボックスの *InPlaceHolds* プロパティに表示されます。プレフィックスによって識別されます `-mbx` 。たとえば、`-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|電子情報開示ケースの保持Microsoft 365 コンプライアンス センター  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |*InPlaceHolds* プロパティには、メールボックスに配置される可能性のある電子情報開示ケースに関連Microsoft 365 コンプライアンス センターの GUID も格納されます。 GUID が  `UniH` プレフィックスで始まっているため、これは電子情報開示ケース ホールドであることがわかります。  <br/> セキュリティ センター PowerShell のコマンドレット&使用して、メールボックスの保留が関連付けられている電子情報開示ケースに関する  `Get-CaseHoldPolicy` 情報を取得できます。 たとえば、このコマンドを実行して、メールボックス上のケースホールドの  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` 名前を表示できます。 Be sure to remove the  `UniH` プレフィックスを削除してください。  <br/><br/> メールボックスの保留が関連付けられている電子情報開示ケースを識別するには、次のコマンドを実行します。<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`
