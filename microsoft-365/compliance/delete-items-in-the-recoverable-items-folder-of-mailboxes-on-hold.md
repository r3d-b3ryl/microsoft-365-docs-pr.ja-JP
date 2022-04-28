---
title: 回復可能なアイテム フォルダー内のアイテムを削除する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
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
description: 管理者が、Exchange Online メールボックスのユーザーの回復可能なアイテム フォルダー内のアイテムを削除する方法について説明します(そのメールボックスが訴訟ホールドに置かれている場合でも)。
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
ms.openlocfilehash: 808bc02eb711ff72ec8bd329b1367145d2d991a9
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65091745"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold"></a>保留中のクラウド ベースのメールボックスの 回復可能なアイテム フォルダーのアイテムを削除する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Exchange Online メールボックスの回復可能なアイテム フォルダーは、偶発的または悪意のある削除から保護するために存在します。 また、保留検索や電子情報開示検索など、コンプライアンス機能によって保持およびアクセスされるアイテムを格納するためにも使用されます。 ただし、組織によっては、削除する必要がある回復可能なアイテム フォルダーに意図せずに保持されたデータが含まれている場合があります。 たとえば、ビジネスに重大な影響を与える可能性のある機密情報や情報を含む電子メール メッセージを、ユーザーが知らず知らずのうちに送信または転送する場合があります。 メッセージが完全に削除された場合でも、メールボックスに訴訟ホールドが置かれているため、無期限に保持される可能性があります。 このシナリオは、データが意図せずにOffice 365に *流出* したため、データ *の流出* と呼ばれます。 このような場合は、Exchange Online メールボックスのユーザーの回復可能なアイテム フォルダー内のアイテムを削除できます。そのメールボックスが、Office 365の別の保留機能の 1 つで保留にされている場合でも、削除できます。 このような種類の保留には、訴訟ホールド、In-Place保留、電子情報開示保留、およびOffice 365またはMicrosoft 365のセキュリティおよびコンプライアンス センターで作成された保持ポリシーが含まれます。

この記事では、管理者が保留中のクラウドベースのメールボックスの回復可能なアイテム フォルダーからアイテムを削除する方法について説明します。 この手順では、メールボックスへのアクセスを無効にし、単一アイテムの回復を無効にし、管理フォルダー アシスタントでメールボックスの処理を無効にし、保留リストを一時的に削除し、回復可能なアイテム フォルダーからアイテムを削除してから、メールボックスを以前の構成に戻します。 その手順は次のとおりです。
  
[手順 1: メールボックスに関する情報を収集する](#step-1-collect-information-about-the-mailbox)

[手順 2: メールボックスを準備する](#step-2-prepare-the-mailbox)

[手順 3: メールボックスからすべての保留を削除する](#step-3-remove-all-holds-from-the-mailbox)

[手順 4: メールボックスから遅延ホールドを削除する](#step-4-remove-the-delay-hold-from-the-mailbox)

[手順 5: 回復可能なアイテム フォルダー内のアイテムを削除する](#step-5-delete-items-in-the-recoverable-items-folder)

[手順 6: メールボックスを以前の状態に戻す](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> この記事で説明する手順では、Exchange Online メールボックスからデータが完全に削除 (削除) されます。 つまり、回復可能なアイテム フォルダーから削除したメッセージは回復できず、法的検出やその他のコンプライアンス目的では使用できません。 Microsoft Purview コンプライアンス ポータルで作成された訴訟ホールド、In-Place保留、電子情報開示ホールド、またはアイテム保持ポリシーの一部として保留されているメールボックスからメッセージを削除する場合は、保留を削除する前にレコード管理または法務部門に問い合わせてください。 組織には、メールボックスの保留またはデータ流出インシデントが優先されるかどうかを定義するポリシーが含まれている場合があります。
  
## <a name="before-you-delete-items"></a>アイテムを削除する前に

- コンテンツ検索を作成して実行するには、電子情報開示管理者役割グループのメンバーであるか、コンプライアンス検索の管理役割が割り当てられている必要があります。 メッセージを削除するには、Organization Management 役割グループのメンバーであるか、検索と消去の管理役割が割り当てられている必要があります。 ユーザーを役割グループに追加する方法については、「 [電子情報開示アクセス許可の割り当て](./assign-ediscovery-permissions.md)」を参照してください。

- メールボックスが組織全体のアイテム保持ポリシーに割り当てられている場合は、回復可能なアイテム フォルダーからアイテムを削除する前に、そのメールボックスをポリシーから除外する必要があります。 ポリシーの変更を同期し、ポリシーからメールボックスを削除するには、最大で 24 時間かかる場合があります。 詳細については、この記事の「 [メールボックスからすべての保留を削除](#organization-wide-retention-policies) する」セクションの「組織全体のアイテム保持ポリシー」を参照してください。

- 保持ロックを使用してロックされているアイテム保持ポリシーを使用して、保持設定が割り当てられているメールボックスに対してこの手順を実行することはできません。 これは、このロックにより、ポリシーからメールボックスを削除または除外したり、メールボックスの管理フォルダー アシスタントを無効にしたりできないようにするためです。 保持ポリシーのロックの詳細については、「 [保持ロックを使用してアイテム保持ポリシーとアイテム保持ラベル ポリシーへの変更を制限する](retention-preservation-lock.md)」を参照してください。

- この記事で説明する手順は、非アクティブなメールボックスではサポートされていません。 これは、保留リスト (またはアイテム保持ポリシー) を削除した後、非アクティブなメールボックスに再適用できないためです。 非アクティブなメールボックスからホールドを削除すると、通常の論理的に削除されたメールボックスに変更され、マネージド フォルダー アシスタントによって処理された後、組織から完全に削除されます。

- メールボックスが保留にされていない (または 1 つのアイテムの回復が有効になっていない) 場合は、回復可能なアイテム フォルダーからアイテムを削除できます。 これを行う方法の詳細については、「 [組織内の電子メール メッセージを検索して削除する](./search-for-and-delete-messages-in-your-organization.md)」を参照してください。

## <a name="step-1-collect-information-about-the-mailbox"></a>手順 1: メールボックスに関する情報を収集する

この最初の手順では、この手順に影響を与える選択したプロパティをターゲット メールボックスから収集します。 これらのプロパティの一部を変更し、回復可能なアイテム フォルダーからアイテムを削除した後、手順 6 で元の値に戻すため、これらの設定を書き留めるか、テキスト ファイルに保存してください。 収集する必要があるメールボックスプロパティの一覧を次に示します。
  
- *SingleItemRecoveryEnabled*  and  *RetainDeletedItemsFor*. 必要に応じて、単一の回復を無効にし、手順 3 で削除されたアイテムの保持期間を長くします。

- *LitigationHoldEnabled*  と  *InPlaceHolds*。 手順 3 で一時的に削除できるように、メールボックスに配置されているすべての保留を特定する必要があります。 メールボックスに配置される可能性がある種類の保留を識別する方法のヒントについては、「 [詳細情報](#more-information) 」セクションを参照してください。

また、この手順で所有者 (または他のユーザー) がメールボックスにアクセスできないように、メールボックス クライアントアクセス設定を一時的に無効にする必要があります。 最後に、回復可能なアイテム フォルダー内のアイテムの現在のサイズと数を取得できます。 手順 5 の回復可能なアイテム フォルダー内のアイテムを削除した後、この情報を使用してアイテムが削除されたことを確認します。
  
1. [Exchange Online PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。 Exchange Onlineで適切な管理ロールが割り当てられている管理者アカウントのユーザー名とパスワードを必ず使用してください。

2. 次のコマンドを実行して、単一アイテムの回復と削除されたアイテムの保持期間に関する情報を取得します。

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   単一アイテムの回復が有効になっている場合は、手順 2. で無効にする必要があります。 削除されたアイテムの保持期間が 30 日間 (Exchange Onlineの最大値) に設定されていない場合は、手順 2. で増やすことができます。

3. 次のコマンドを実行して、メールボックスのメールボックス アクセス設定を取得します。

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   手順 2 で、これらのアクセス方法をすべて無効にします。

4. 次のコマンドを実行して、メールボックスに適用された保留ポリシーとアイテム保持ポリシーに関する情報を取得します。

    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```

    > [!TIP]
    > *InPlaceHolds* プロパティに値が多すぎてすべての値が表示されない場合は、コマンドを`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`実行して各値を個別の行に表示できます。
  
5. 次のコマンドを実行して、組織全体のアイテム保持ポリシーに関する情報を取得します。 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```

   組織に組織全体のアイテム保持ポリシーがある場合は、手順 3. でこれらのポリシーからメールボックスを除外する必要があります。 変更をレプリケートするには、最大で 24 時間かかる場合があります。

    > [!TIP]
    > *InPlaceHolds* プロパティに値が多すぎてすべての値が表示されない場合は、コマンドを`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`実行して各値を個別の行に表示できます。 
  
6. 次のコマンドを実行して、メールボックスに遅延ホールドが適用されているかどうかを確認します。

   ```powershell
   Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
   ```

   *DelayHoldApplied* プロパティまたは *DelayReleaseHoldApplied* プロパティの値が **True** に設定されている場合は、メールボックスに遅延ホールドが適用され、削除する必要があります。 遅延保留の詳細については、「 [手順 4: メールボックスから遅延ホールドを削除する」を](#step-4-remove-the-delay-hold-from-the-mailbox)参照してください。

   いずれかのプロパティの値が **False** に設定されている場合は、メールボックスに遅延ホールドが適用されず、手順 4 をスキップできます。

7. 次のコマンドを実行して、ユーザーのプライマリ メールボックスの回復可能なアイテム フォルダー内のフォルダーとサブフォルダー内のアイテムの現在のサイズと合計数を取得します。

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   ユーザーのアーカイブ メールボックスが有効になっている場合は、次のコマンドを実行して、アーカイブ メールボックス内の回復可能なアイテム フォルダー内のフォルダーとサブフォルダー内のアイテムのサイズと合計数を取得します。 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   手順 5 でアイテムを削除する場合は、ユーザーのプライマリ アーカイブ メールボックスの回復可能なアイテム フォルダー内のアイテムを削除するか、削除しないことを選択できます。 メールボックスに対して自動拡張アーカイブが有効になっている場合、補助アーカイブ メールボックス内のアイテムは削除されません。
  
## <a name="step-2-prepare-the-mailbox"></a>手順 2: メールボックスを準備する

メールボックスに関する情報を収集して保存した後、次の手順では、次のタスクを実行してメールボックスを準備します。
  
- メールボックス所有者が自分のメールボックスにアクセスできず、この手順でメールボックス データを変更できないように、メールボックスへの **クライアント アクセスを無効にします**。

- 手順 5. でアイテムを削除する前に、アイテムが回復可能なアイテム フォルダーから削除されないように、**削除されたアイテムの保持期間** を 30 日間 (Exchange Onlineの最大値) に増やします。

- 手順 5. の回復可能なアイテム フォルダーからアイテムを削除した後、アイテムを (削除されたアイテムの保持期間の間) 保持しないように、**1 つのアイテムの回復を無効にします**。

- **管理フォルダー アシスタントを無効にして** 、メールボックスを処理せず、手順 5. で削除したアイテムを保持します。

PowerShell で次の手順Exchange Online実行します。
  
1. 次のコマンドを実行して、メールボックスへのすべてのクライアント アクセスを無効にします。 コマンド構文は、すべてのクライアント アクセス方法がメールボックスで有効になっていることを前提としています。

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

    > [!NOTE]
    > メールボックスへのすべてのクライアント アクセス方法を無効にするには、最大で 60 分かかる場合があります。 これらのアクセス方法を無効にしても、メールボックス所有者が現在サインインしている場合、メールボックスの所有者は切断されないことに注意してください。 所有者がサインインしていない場合、これらのアクセス方法を無効にした後は、自分のメールボックスにアクセスできません。
  
2. 次のコマンドを実行して、削除されたアイテムの保持期間を最大 30 日間増やします。 これは、現在の設定が 30 日未満であることを前提としています。

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. 次のコマンドを実行して、単一アイテムの回復を無効にします。

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

    > [!NOTE]
    > 1 つのアイテムの回復を無効にするには、最大で 240 分かかる場合があります。 回復可能なアイテム フォルダー内のアイテムは、この期間が経過するまで削除しないでください。
  
4. マネージド フォルダー アシスタントがメールボックスを処理できないようにするには、次のコマンドを実行します。 前述のように、管理フォルダー アシスタントを無効にできるのは、保持ロックを持つアイテム保持ポリシーがメールボックスに適用されていない場合のみです。

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>手順 3: メールボックスからすべての保留を削除する

回復可能なアイテム フォルダーからアイテムを削除する前の最後の手順は、メールボックスに配置されたすべての保留 (手順 1 で特定した) を削除することです。 アイテムを回復可能なアイテム フォルダーから削除した後にアイテムを保持しないように、すべての保留を削除する必要があります。 次のセクションでは、メールボックス上のさまざまな種類の保留リストを削除する方法について説明します。 メールボックスに配置される可能性がある種類の保留を識別する方法のヒントについては、「 [詳細情報](#more-information) 」セクションを参照してください。 詳細については、「[Exchange Online メールボックスに配置された保留の種類を特定する方法](identify-a-hold-on-an-exchange-online-mailbox.md)」を参照してください。
  
> [!CAUTION]
> 既に説明したように、メールボックスから保留を削除する前に、レコード管理または法務部門に問い合わせてください。
  
### <a name="litigation-hold"></a>訴訟ホールド
  
Exchange Online PowerShell で次のコマンドを実行して、メールボックスから訴訟ホールドを削除します。

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

> [!NOTE]
> 単一アイテムの回復を無効にした場合と同様に、訴訟ホールドを削除するのに最大で 240 分かかる場合があります。 この期間が経過するまで、回復可能なアイテム フォルダーからアイテムを削除しないでください。
  
### <a name="in-place-hold"></a>インプレース ホールド
  
Exchange Online PowerShell で次のコマンドを実行して、メールボックスに配置されているIn-Place保留を識別します。 手順 1 で識別したIn-Placeホールドの GUID を使用します。

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

In-Place保留を特定したら、<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理センター (EAC)</a> または powerShell Exchange Onlineを使用して、メールボックスを保留から削除できます。 詳細については、「 [In-Placeホールドを作成または削除する](/exchange/security-and-compliance/create-or-remove-in-place-holds)」を参照してください。
  
### <a name="retention-policies-applied-to-specific-mailboxes"></a>特定のメールボックスに適用されるアイテム保持ポリシー
  
[Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) で次のコマンドを実行して、メールボックスに適用されるアイテム保持ポリシーを特定します。 このコマンドは、メールボックスに適用されたTeams会話保持ポリシーも返します。 手順 1 で特定したアイテム保持ポリシーに GUID (プレフィックスを`skp`含`mbx`まない) を使用します。

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

アイテム保持ポリシーを特定したら、コンプライアンス ポータルの **[データ ライフサイクル管理** > **の保持** ] ページに移動し、前の手順で特定したアイテム保持ポリシーを編集し、アイテム保持ポリシーに含まれる受信者の一覧からメールボックスを削除します。
  
### <a name="organization-wide-retention-policies"></a>組織全体に対するアイテム保持ポリシー
  
組織全体、Exchange全体、およびTeams全体のアイテム保持ポリシーは、組織内のすべてのメールボックスに適用されます。 これらは (メールボックス レベルではなく) 組織レベルで適用され、手順 1 で **Get-OrganizationConfig** コマンドレットを実行すると返されます。 [Security & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell) で次のコマンドを実行して、組織全体のアイテム保持ポリシーを識別します。 手順 1 で特定した組織全体のアイテム保持ポリシーに GUID (プレフィックスを含  `mbx` まない) を使用します。

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

組織全体のアイテム保持ポリシーを特定したら、コンプライアンス ポータルの **[データ ライフサイクル管理** > **の復元** ] ページに移動し、前の手順で特定した組織全体のアイテム保持ポリシーを編集し、除外された受信者の一覧にメールボックスを追加します。 これを行うと、アイテム保持ポリシーからユーザーのメールボックスが削除されます。

> [!IMPORTANT]
> 組織全体のアイテム保持ポリシーからメールボックスを除外すると、この変更を同期し、ポリシーからメールボックスを削除するのに最大で 24 時間かかる場合があります。

### <a name="retention-labels"></a>保持ラベル

ユーザーがコンテンツを保持するか、コンテンツを保持し、メールボックス内の任意のフォルダーまたはアイテムにコンテンツを削除するように構成されているラベルを適用するたびに、 *ComplianceTagHoldApplied* メールボックス プロパティは **True** に設定されます。 このような場合、メールボックスは訴訟ホールドに置かれたか、アイテム保持ポリシーに割り当てられたかのように、保留状態と見なされます。

*ComplianceTagHoldApplied* プロパティの値を表示するには、PowerShell で次のコマンドExchange Online実行します。

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

アイテム保持ラベルがフォルダーまたはアイテムに適用されているため、メールボックスが保留中であることが確認できたら、コンプライアンス ポータルのコンテンツ検索ツールを使用して、 **アイテム保持ラベル** 条件を使用してラベル付けされたアイテムを検索できます。 詳細については、以下を参照してください。

- アイテム保持ポリシーとアイテム保持ラベル[の詳細](retention.md#using-content-search-to-find-all-content-with-a-specific-retention-label)の「コンテンツ検索を使用して特定のアイテム保持ラベルを持つすべてのコンテンツを検索する」セクション

- コンテンツ検索の [キーワード クエリと検索条件](keyword-queries-and-search-conditions.md#conditions-for-common-properties)の [検索条件] セクション。

ラベルの詳細については、「 [アイテム保持ポリシーと保持ラベルの詳細](retention.md)」を参照してください。

### <a name="ediscovery-holds"></a>電子情報開示の保留
  
[Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) で次のコマンドを実行して、メールボックスに適用される電子情報開示ケース (*電子情報開示保留* と呼ばれる) に関連付けられている保留を特定します。 手順 1 で識別した電子情報開示ホールドの GUID (プレフィックスは含  `UniH` まない) を使用します。 2 番目のコマンドは、保留リストが関連付けられている電子情報開示ケースの名前を表示します。3 番目のコマンドには、保留リストの名前が表示されます。
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

電子情報開示ケースと保留リストの名前を特定したら、コンプライアンス センターの **電子情報開示** \> **電子情報開示** ページに移動し、ケースを開き、メールボックスを保留リストから削除します。 電子情報開示保留の識別の詳細については、「Exchange Online [メールボックスに配置された保留の種類を特定する方法」の](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)「電子情報開示保留」セクションを参照してください。
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>手順 4: メールボックスから遅延ホールドを削除する

メールボックスから任意の種類の保留が削除された後、 *DelayHoldApplied* または *DelayReleaseHoldApplied* メールボックス プロパティの値は True に設定 **されます**。 これは、次にマネージド フォルダー アシスタントがメールボックスを処理し、保留が削除されたことを検出したときに発生します。 これは *遅延ホールド* と呼ばれ、データがメールボックスから完全に削除されないように、ホールドの実際の削除が 30 日間遅延されることを意味します。 (遅延ホールドの目的は、保留が削除された後に削除されるメールボックス アイテムを検索または回復する機会を管理者に提供することです)。 メールボックスに遅延ホールドが置かれると、メールボックスは訴訟ホールドにあるかのように、無制限の期間保持されていると見なされます。 30 日後、遅延ホールドは期限切れになり、Microsoft 365は(*DelayHoldApplied* プロパティまたは *DelayReleaseHoldApplied* プロパティを **False** に設定することによって) 保留が削除されるように自動的に削除を試みます。 遅延ホールドの詳細については、「Exchange Online メールボックスに[配置された保留の種類を特定する方法」の「遅延ホールド時のメールボックスの](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)管理」セクションを参照してください。

*DelayHoldApplied* プロパティまたは *DelayReleaseHoldApplied* プロパティの値が **True** に設定されている場合は、次のいずれかのコマンドを実行して遅延ホールドを削除します。

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

または

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

*RemoveDelayHoldApplied または RemoveDelayReleaseHoldApplied* パラメーターを使用するには、Exchange Onlineで訴訟ホールド ロールを割り当てる必要があります。

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>手順 5: 回復可能なアイテム フォルダー内のアイテムを削除する

これで、Security & Compliance Center PowerShell の [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) コマンドレットと [New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) コマンドレットを使用して、回復可能なアイテム フォルダー内のアイテムを実際に削除する準備ができました。

回復可能なアイテム フォルダーにあるアイテムを検索するには、 *対象のコレクション* を実行することをお勧めします。 つまり、回復可能なアイテム フォルダー内のアイテムのみに検索範囲を絞り込みます。 これを行うには、 [ターゲット コレクションのコンテンツ検索の使用に関する](use-content-search-for-targeted-collections.md) 記事のスクリプトを実行します。 このスクリプトは、ターゲットの回復可能なアイテム フォルダー内のすべてのサブフォルダーのフォルダー ID プロパティの値を返します。 次に、検索クエリのフォルダー ID を使用して、そのフォルダー内にあるアイテムを返します。

ユーザーの回復可能なアイテム フォルダー内のアイテムを検索および削除するプロセスの概要を次に示します。

1. ターゲット ユーザーのメールボックス内のすべてのフォルダーのフォルダー ID を返すターゲット コレクション スクリプトを実行します。 このスクリプトは、同じ PowerShell セッションExchange Online PowerShell とセキュリティ &コンプライアンス PowerShell に接続します。 詳細については、「 [スクリプトを実行してメールボックスのフォルダーの一覧を取得する」を](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site)参照してください。

2. 回復可能なアイテム フォルダー内のすべてのサブフォルダーのフォルダー ID をコピーします。 または、スクリプトの出力をテキスト ファイルにリダイレクトすることもできます。

   アイテムを検索および削除できる回復可能なアイテム フォルダー内のサブフォルダーの一覧と説明を次に示します。

   - **削除**: 論理的に削除されたアイテムが含まれます。削除されたアイテムの保持期間が経過していません。 ユーザーは、Outlookの [削除済みアイテムの回復] ツールを使用して、このサブフォルダーから論理的に削除されたアイテムを回復できます。

   - **DiscoveryHolds**: 電子情報開示ホールドまたはアイテム保持ポリシーによって保持されているハード削除されたアイテムが含まれます。 このサブフォルダーは、エンド ユーザーには表示されません。

   - **[Holds**]: アイテム保持ポリシーまたはその他の種類の保留リストによって保持されている、Teamsやその他のクラウドベースのアプリからハード削除されたアイテムが含まれます。 このサブフォルダーは、エンド ユーザーには表示されません。

3. **New-ComplianceSearch** コマンドレット (Security & Compliance Center PowerShell) を使用するか、コンプライアンス センターのコンテンツ検索ツールを使用して、ターゲット ユーザーの回復可能なアイテム フォルダーからアイテムを返すコンテンツ検索を作成します。 これを行うには、検索するすべてのサブフォルダーの検索クエリに FolderId を含めます。 たとえば、次のクエリは、削除と電子DiscoveryHolds サブフォルダー内のすべてのメッセージを返します。

   ```text
   folderid:<folder ID of Deletions subfolder> OR folderid:<folder ID of DiscoveryHolds subfolder>
   ```

   フォルダー ID プロパティを使用するコンテンツ検索の実行の詳細と例については、「 [フォルダー ID を使用する」または「ターゲット コレクションを実行する](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection)」を参照してください。

   > [!NOTE]
   > **New-ComplianceSearch** コマンドレットを使用して回復可能なアイテム フォルダーを検索する場合は、必ず **Start-ComplianceSearch** コマンドレットを使用して検索を実行してください。

4. コンテンツ検索を作成し、削除するアイテムが返されることを検証したら、コマンド (Security & Compliance Center PowerShell) を使用 `New-ComplianceSearchAction -Purge -PurgeType HardDelete` して、前の手順で作成したコンテンツ検索によって返されたアイテムを完全に削除します。 たとえば、次のようなコマンドを実行できます。

   ```powershell
   New-ComplianceSearchAction -SearchName "RecoverableItems" -Purge -PurgeType HardDelete
   ```

5. 前のコマンドを実行すると、メールボックスあたり最大 10 個のアイテムが削除されます。 つまり、回復可能なアイテム フォルダーで削除するすべての項目を削除するには、コマンドを複数回実行 `New-ComplianceSearchAction -Purge` する必要がある場合があります。 追加のアイテムを削除するには、最初に前のコンプライアンス検索消去アクションを削除する必要があります。 これを行うには、コマンドレットを `Remove-ComplianceSearchAction` 実行します。 たとえば、前の手順で実行した消去アクションを削除するには、次のコマンドを実行します。

   ```powershell
   Remove-ComplianceSearchAction "RecoverableItems_Purge"
   ```

   これを行った後、新しいコンプライアンス検索消去アクションを作成して、より多くのアイテムを削除できます。 新しい消去アクションを作成する前に、各消去アクションを削除する必要があります。

   コンプライアンス検索アクションの一覧を取得するには、コマンドレットを `Get-ComplianceSearchAction` 実行します。 消去アクションは、検索名に追加することで `_Purge` 識別されます。

### <a name="verify-that-items-were-deleted"></a>アイテムが削除されたことを確認する

メールボックスの回復可能なアイテム フォルダーからアイテムが正常に削除されたことを確認するには、Exchange Online PowerShell の **Get-MailboxFolderStatistics** コマンドレットを使用して、回復可能なアイテム フォルダー内のアイテムのサイズと数を確認します。 これらの統計情報は、手順 1 で収集した統計と比較できます。
  
次のコマンドを実行して、ユーザーのプライマリ メールボックスの回復可能なアイテム フォルダー内のフォルダーとサブフォルダー内のアイテムの現在のサイズと合計数を取得します。
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

次のコマンドを実行して、ユーザーのアーカイブ メールボックスの回復可能なアイテム フォルダー内のフォルダーとサブフォルダー内のアイテムのサイズと合計数を取得します。

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>手順 6: メールボックスを以前の状態に戻す

最後の手順では、メールボックスを以前の構成に戻します。 つまり、手順 2 で変更したプロパティをリセットし、手順 3 で削除した保留を再適用します。 これには、次の内容が含まれます。
  
- 削除されたアイテムの保持期間を以前の値に戻します。 または、Exchange Onlineの最大値である 30 日間に設定したままにすることもできます。

- 1 つのアイテムの回復を再度有効にします。

- 所有者が自分のメールボックスにアクセスできるように、クライアント アクセス方法を再度有効にします。

- 削除した保留ポリシーとアイテム保持ポリシーを再適用します。

- マネージド フォルダー アシスタントを再度有効にして、メールボックスを処理します。

> [!IMPORTANT]
> マネージド フォルダー アシスタントでメールボックスの処理を再度有効にする前に、保持ポリシーまたはアイテム保持ポリシーを再適用してから 24 時間待機することをお勧めします (また、そのポリシーが適用されていることを確認します)。
  
PowerShell で次の手順 (指定された順序で) Exchange Online実行します。
  
1. 次のコマンドを実行して、削除されたアイテムの保持期間を元の値に戻します。 これは、前の設定が 30 日未満であることを前提としています。たとえば、14 日間です。

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. 次のコマンドを実行して、単一アイテムの回復を再度有効にします。

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. 次のコマンドを実行して、メールボックスへのすべてのクライアント アクセス方法を再度有効にします。

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. 手順 3 で削除した保留を再適用します。 保留の種類に応じて、次のいずれかの手順を使用します。

    **訴訟ホールド**

    次のコマンドを実行して、メールボックスの訴訟ホールドを再度有効にします。

    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **In-Place Hold**

    EAC (または PowerShell Exchange Online) を使用して、メールボックスをIn-Place保留に戻します。

    **特定のメールボックスに適用されるアイテム保持ポリシー**

    コンプライアンス ポータルを使用して、メールボックスをアイテム保持ポリシーに追加します。 コンプライアンス センターの **データ ライフサイクル管理** > **Retention** ページに移動し、アイテム保持ポリシーを編集し、アイテム保持ポリシーが適用されている受信者の一覧にメールボックスを追加します。

    **組織全体に対するアイテム保持ポリシー**

    組織全体またはExchange全体のアイテム保持ポリシーをポリシーから除外して削除した場合は、コンプライアンス ポータルを使用して、除外されたユーザーの一覧からメールボックスを削除します。 コンプライアンス センターの **データ ライフサイクル管理** > **Retention** ページに移動し、組織全体のアイテム保持ポリシーを編集し、除外された受信者の一覧からメールボックスを削除します。 これを行うと、アイテム保持ポリシーがユーザーのメールボックスに再適用されます。

    **電子情報開示ケースホールド**

    コンプライアンス ポータルを使用して、電子情報開示ケースに関連付けられている保留リストにメールボックスを追加します。 **eDiscoveryCore** >  ページに移動し、ケースを開き、メールボックスを保留リストに追加します。 

5. 次のコマンドを実行して、マネージド フォルダー アシスタントがメールボックスを再度処理できるようにします。 既に説明したように、Managed Folder Assistant を再度有効にする前に、保留ポリシーまたはアイテム保持ポリシーを再適用してから 24 時間待機することをお勧めします (また、そのポリシーが適用されていることを確認します)。

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. メールボックスが以前の構成に戻されたことを確認するには、次のコマンドを実行し、手順 1 で収集した設定と比較します。

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a>詳細

**Get-Mailbox** コマンドレットまたは **Get-OrganizationConfig** コマンドレットを実行するときに *、InPlaceHolds* プロパティの値に基づいてさまざまな種類の保留を識別する方法を示す表を次に示します。 詳細については、「[Exchange Online メールボックスに配置された保留の種類を特定する方法](identify-a-hold-on-an-exchange-online-mailbox.md)」を参照してください。

前述のように、回復可能なアイテム フォルダー内のアイテムを正常に削除するには、メールボックスからすべての保留ポリシーとアイテム保持ポリシーを削除する必要があります。
  
| ホールドの種類 | 値の例 | 保留を識別する方法 |
|:-----|:-----|:-----|
|訴訟ホールド  <br/> | `True` <br/> |*LitigationHoldEnabled*  プロパティが  `True` に設定されています。  <br/> |
|インプレース ホールド  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |*InPlaceHolds* プロパティには、メールボックスに配置されたIn-Placeホールドの GUID が含まれています。 GUID がプレフィックスで始まらないので、これはIn-Placeホールドであることを確認できます。  <br/> powerShell Exchange Onlineコマンドを`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL`使用して、メールボックスのIn-Place保留に関する情報を取得できます。  <br/> |
| 特定のメールボックスに適用されるコンプライアンス ポータルのアイテム保持ポリシー  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> or  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |**Get-Mailbox** コマンドレットを実行すると、*InPlaceHolds* プロパティには、メールボックスに適用されるアイテム保持ポリシーの GUID も含まれます。 GUID はプレフィックスで始まるので、アイテム保持ポリシーを  `mbx` 識別できます。 アイテム保持ポリシーの GUID がプレフィックスで`skp`始まる場合は、アイテム保持ポリシーがSkype for Business会話に適用されることを示します。  <br/> メールボックスに適用されるアイテム保持ポリシーを識別するには、Security & Compliance Center PowerShell で次のコマンドを実行します。 <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>このコマンドを実行する場合は、必ず、 `mbx` または  `skp` プレフィックスを削除してください。  <br/> |
|コンプライアンス ポータルの組織全体のアイテム保持ポリシー  <br/> |値なし  <br/> or  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696` (組織全体のポリシーからメールボックスが除外されていることを示します)  <br/> |**Get-Mailbox** コマンドレットを実行するときに *InPlaceHolds* プロパティが空の場合でも、メールボックスに 1 つ以上の組織全体のアイテム保持ポリシーが適用されている可能性があります。  <br/> これを確認するには、Exchange Online PowerShell でコマンドを実行`Get-OrganizationConfig | FL InPlaceHolds`して、組織全体のアイテム保持ポリシーの GUID の一覧を取得できます。 Exchange メールボックスに適用される組織全体のアイテム保持ポリシーの GUID はプレフィックスで`mbx`始まります。たとえば、 `mbxa3056bb15562480fadb46ce523ff7b02`  <br/> メールボックスに適用される組織全体のアイテム保持ポリシーを識別するには、Security & Compliance Center PowerShell で次のコマンドを実行します。 <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>組織全体のアイテム保持ポリシーからメールボックスが除外されている場合、**Get-Mailbox** コマンドレットを実行すると、アイテム保持ポリシーの GUID がユーザーのメールボックスの *InPlaceHolds* プロパティに表示されます。プレフィックス`-mbx`によって識別されます。たとえば、`-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|コンプライアンス ポータルでの電子情報開示ケースホールド  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |*InPlaceHolds* プロパティには、メールボックスに配置される可能性があるコンプライアンス ポータルの電子情報開示ケースに関連付けられているすべてのホールドの GUID も含まれています。 GUID が  `UniH` プレフィックスで始まっているため、これは電子情報開示ケース ホールドであることがわかります。  <br/> Security & Compliance Center PowerShell のコマンドレットを使用  `Get-CaseHoldPolicy` して、メールボックスのホールドが関連付けられている電子情報開示ケースに関する情報を取得できます。 たとえば、コマンド  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` を実行して、メールボックスにあるケースホールドの名前を表示できます。 Be sure to remove the  `UniH` プレフィックスを削除してください。  <br/><br/> メールボックスのホールドが関連付けられている電子情報開示ケースを識別するには、次のコマンドを実行します。<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`
