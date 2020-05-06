---
title: 保持されているクラウドメールボックス内のアイテムを削除する回復可能なアイテムフォルダー-管理者ヘルプ
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
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
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: '管理者の場合: Exchange Online メールボックスのユーザーの回復可能なアイテムフォルダーのアイテムを削除します (法的情報保留に設定されている場合も含む)。 これは、Microsoft 365 に誤ってこぼれたデータを削除する効果的な方法です。'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0e42249fb2ba7143c4c833193b31c72f0fb73137
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035891"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a>クラウドベースのメールボックスの [回復可能なアイテム] フォルダー内のアイテムを削除する-管理者向けヘルプ

Exchange Online メールボックスの回復可能なアイテムフォルダーは、偶発的または悪意のある削除から保護するために存在します。 また、保留や電子情報開示の検索など、コンプライアンス機能によって保持およびアクセスされるアイテムを格納するためにも使用されます。 ただし、状況によっては、削除する必要のある回復可能なアイテムフォルダーに誤って保持されていたデータが組織に存在する可能性があります。 たとえば、ユーザーが気付かないうちに機密情報や情報が含まれる電子メールメッセージを知らずに送信または転送することがあります。 メッセージが完全に削除された場合でも、メールボックスに法的情報保持が設定されているため、無期限に保持される可能性があります。 このシナリオは、データが Office 365 に誤って含まれていたため、データ流出と呼ばれます。 このような状況では、Exchange Online メールボックスのユーザーの回復可能なアイテムフォルダーのアイテムを削除することができます。これは、Office 365 のさまざまな保留機能のいずれかを使用して、そのメールボックスが保持されている場合でも削除できます。 これらの種類には、訴訟ホールド、インプレースホールド、電子情報開示の保持、および Office 365 または Microsoft 365 のセキュリティ/コンプライアンスセンターで作成されたアイテム保持ポリシーが含まれます。
  
 この記事では、保留中のクラウドベースのメールボックスの [回復可能なアイテム] フォルダーからアイテムを削除する方法について説明します。 この手順では、メールボックスへのアクセスを無効にし、単一アイテムの回復を無効にし、管理フォルダーアシスタントがメールボックスの処理を無効にし、保持を一時的に削除し、回復可能なアイテムフォルダーからアイテムを削除した後、メールボックスを以前の構成に戻す必要があります。 プロセスは次のとおりです。 
  
[手順 1: メールボックスに関する情報を収集する](#step-1-collect-information-about-the-mailbox)

[手順 2: メールボックスを準備する](#step-2-prepare-the-mailbox)

[手順 3: メールボックスからすべての保留リストを削除する](#step-3-remove-all-holds-from-the-mailbox)

[手順 4: メールボックスから遅延保持を削除する](#step-4-remove-the-delay-hold-from-the-mailbox)

[手順 5: 回復可能なアイテムフォルダーのアイテムを削除する](#step-5-delete-items-in-the-recoverable-items-folder)

[手順 6: メールボックスを以前の状態に戻す](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> この記事に記載されている手順により、Exchange Online メールボックスからデータが完全に削除 (パージ) されます。 これは、回復可能なアイテムフォルダーから削除されたメッセージを回復できず、法的証拠開示やその他の法令遵守のために利用できないことを意味します。 セキュリティ/コンプライアンスセンターで作成された訴訟ホールド、インプレースホールド、電子情報開示の保持、またはアイテム保持ポリシーの一部として保留になっているメールボックスからメッセージを削除する場合は、保留リストを削除する前に、レコード管理または法務部門に確認してください。 組織には、保留中のメールボックスとデータ流出インシデントのどちらを優先するかを定義するポリシーがあります。 
  
## <a name="before-you-begin"></a>はじめに

- コンテンツ検索を作成して実行するには、電子情報開示管理者役割グループのメンバーであるか、コンプライアンス検索の管理役割が割り当てられている必要があります。 メッセージを削除するには、Organization Management 役割グループのメンバーであるか、検索と消去の管理役割が割り当てられている必要があります。 ユーザーを役割グループに追加する方法の詳細については、「[セキュリティ/コンプライアンス センターの電子情報開示のアクセス許可を割り当てる](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions)」をご覧ください。

- この記事で説明する手順は、非アクティブなメールボックスではサポートされていません。 これは、削除した後、非アクティブなメールボックスに保持 (またはアイテム保持ポリシー) を再適用できないためです。 非アクティブなメールボックスからホールドを削除すると、その保留中のメールボックスは通常の回復可能な削除によって削除され、管理フォルダーアシスタントによる処理後は組織から完全に削除されます。

- 保持ロックでロックされているアイテム保持ポリシーに割り当てられているメールボックスに対してこの手順を実行することはできません。 これは、保持ロックによって、アイテム保持ポリシーからメールボックスを削除または除外したり、メールボックス上の管理フォルダーアシスタントを無効にしたりできないためです。 保持ポリシーのロックの詳細については、「[アイテム保持ポリシーのロック](retention-policies.md#locking-a-retention-policy)」を参照してください。

- メールボックスが保留になっていない (または単一アイテムの回復が有効になっていない) 場合は、回復可能なアイテムフォルダーからアイテムを削除することができます。 これを行う方法の詳細については、「[組織内での電子メールメッセージの検索と削除](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)」を参照してください。
  
## <a name="step-1-collect-information-about-the-mailbox"></a>手順 1: メールボックスに関する情報を収集する

最初の手順では、この手順に影響する、ターゲットメールボックスから選択したプロパティを収集します。 これらのプロパティの一部を変更し、[回復可能なアイテム] フォルダーからアイテムを削除した後に、手順6で元の値に戻すことができるように、これらの設定を書き留めておくか、テキストファイルに保存してください。 収集する必要があるメールボックスのプロパティの一覧を次に示します。
  
- *Singleitemrecoveryenabled*および*RetainDeletedItemsFor*。 必要に応じて、1回の回復を無効にして、手順3で削除済みアイテムの保存期間を延長します。 

- *LitigationHoldEnabled*および*InPlaceHolds*。 手順3で一時的に削除できるように、メールボックスに配置されているすべての保留リストを識別する必要があります。 メールボックスに配置される可能性のある型保持を特定する方法については、「[詳細情報](#more-information)」セクションを参照してください。 

また、この手順の実行中に所有者 (または他のユーザー) がメールボックスにアクセスできないように、メールボックスクライアントアクセスの設定を取得する必要があります。 最後に、[回復可能なアイテム] フォルダー内のアイテムの現在のサイズと数を取得することができます。 手順5で [回復可能なアイテム] フォルダーのアイテムを削除した後、この情報を使用してアイテムが削除されたことを確認します。
  
1. [Exchange Online PowerShell に接続します](https://go.microsoft.com/fwlink/?linkid=396554)。 Exchange Online で適切な管理役割が割り当てられている管理者アカウントには、必ずユーザー名とパスワードを使用してください。 
    
2. 単一アイテムの回復と削除済みアイテムの保存期間に関する情報を取得するには、次のコマンドを実行します。

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   単一アイテムの回復が有効になっている場合は、手順2で無効にする必要があります。 削除済みアイテムの保存期間が30日間 (Exchange Online の最大値) に設定されていない場合は、手順2で増やすことができます。 
    
3. 次のコマンドを実行して、メールボックスのメールボックスアクセス設定を取得します。 
    
    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   手順2では、これらのアクセス方法をすべて無効にします。
    
4. 次のコマンドを実行して、メールボックスに適用されている保留および保持ポリシーに関する情報を取得します。
    
    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > *InPlaceHolds*プロパティに含まれる値が多すぎて、一部が表示されていない場合は、 `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`コマンドを実行してそれぞれの値を別々の行に表示することができます。 
  
5. 組織全体のアイテム保持ポリシーに関する情報を取得するには、次のコマンドを実行します。 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   
   組織全体のアイテム保持ポリシーを使用している場合は、手順3でこれらのポリシーからメールボックスを除外する必要があります。

   > [!TIP]
    > *InPlaceHolds*プロパティに含まれる値が多すぎて、一部が表示されていない場合は、 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`コマンドを実行してそれぞれの値を別々の行に表示することができます。 
  
6. 次のコマンドを実行して、ユーザーのプライマリメールボックスの [回復可能なアイテム] フォルダー内のフォルダーとサブフォルダー内のアイテムの現在のサイズと合計数を取得します。 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   ユーザーのアーカイブメールボックスが有効になっている場合は、次のコマンドを実行して、アーカイブメールボックス内の [回復可能なアイテム] フォルダー内のフォルダーとサブフォルダー内のアイテムのサイズと合計数を取得します。 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   手順5でアイテムを削除する場合、ユーザーのプライマリアーカイブメールボックスの [回復可能なアイテム] フォルダー内のアイテムを削除するか、削除するかを選択できます。 メールボックスの自動拡張アーカイブが有効になっている場合、補助アーカイブメールボックス内のアイテムは削除されません。
  
## <a name="step-2-prepare-the-mailbox"></a>手順 2: メールボックスを準備する

メールボックスに関する情報を収集して保存した後、次の手順では、次のタスクを実行してメールボックスを準備します。 
  
- メールボックス**へのクライアントアクセスを無効**にして、メールボックスの所有者がメールボックスにアクセスできないようにして、この手順の実行中にメールボックスデータを変更しないようにします。 
    
- **削除済みアイテムの保存期間**を30日間 (Exchange Online の最大値) に増やして、手順5でアイテムを回復可能なアイテムフォルダーから削除されないようにします。 
    
- 手順5で [回復可能なアイテム] フォルダーからアイテムを削除した後に、アイテムが保持されないように、**単一アイテムの回復を無効**にします (削除済みアイテムの保存期間中)。 
    
- **管理フォルダーアシスタントを無効**にして、メールボックスが処理されず、手順5で削除されたアイテムを保持するようにします。 
    
Exchange Online PowerShell で次の手順を実行します。
  
1. 次のコマンドを実行して、メールボックスへのすべてのクライアントアクセスを無効にします。 コマンド構文では、すべてのクライアントアクセスメソッドがメールボックスで有効になっていることを前提としています。

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

   > [!NOTE]
    > メールボックスへのすべてのクライアントアクセス方法を無効にするには、最大60分かかる場合があります。 これらのアクセス方法を無効にしても、現在サインインしているメールボックスの所有者が切断されることに注意してください。 所有者がサインインしていない場合、これらのアクセス方法を無効にした後はメールボックスにアクセスできなくなります。 
  
2. 次のコマンドを実行して、削除済みアイテムの保存期間を最大で30日に増やします。 これは、現在の設定が30日未満であることを前提としています。 

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. 次のコマンドを実行して、単一アイテムの回復を無効にします。
    
    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > 単一アイテムの回復を無効にするには、最大60分かかる場合があります。 この期間が経過するまで、[回復可能なアイテム] フォルダー内のアイテムを削除しないでください。 
  
4. 管理フォルダーアシスタントがメールボックスを処理できないようにするには、次のコマンドを実行します。 前述したように、保持ロックが設定されたアイテム保持ポリシーがメールボックスに適用されていない場合にのみ、管理フォルダーアシスタントを無効にすることができます。 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>手順 3: メールボックスからすべての保留リストを削除する

回復可能なアイテムフォルダーからアイテムを削除する前の最後の手順は、メールボックスに配置されたすべてのホールド (手順1で特定した) を削除することです。 [回復可能なアイテム] フォルダーからアイテムを削除した後は、アイテムが保持されないように、すべての保留リストを削除する必要があります。 次のセクションでは、メールボックスにさまざまな種類の保留リストを削除する方法について説明します。 メールボックスに配置される可能性のある型保持を特定する方法については、「[詳細情報](#more-information)」セクションを参照してください。 詳細については、「 [Exchange Online メールボックスに配置されたホールドの種類を特定する方法](identify-a-hold-on-an-exchange-online-mailbox.md)」を参照してください。
  
> [!CAUTION]
> 前述したように、メールボックスから保留リストを削除する前に、レコード管理または法務部門に確認してください。 
  
 ### <a name="litigation-hold"></a>訴訟ホールド
  
Exchange Online PowerShell で次のコマンドを実行して、メールボックスから訴訟ホールドを削除します。

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> クライアントアクセス方法と単一アイテムの回復を無効にする場合と同様に、訴訟ホールドを削除するには最大60分かかる場合があります。 この期間が経過するまで、[回復可能なアイテム] フォルダーからアイテムを削除しないでください。 
  
 ### <a name="in-place-hold"></a>インプレース ホールド
  
Exchange Online PowerShell で次のコマンドを実行して、メールボックスに配置されているインプレースホールドを識別します。 手順1で特定したインプレースホールドの GUID を使用します。 

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

インプレースホールドを識別した後、Exchange 管理センター (EAC) または Exchange Online PowerShell を使用して、保留リストからメールボックスを削除できます。 詳細については、「[インプレース保持を作成または削除する](https://go.microsoft.com/fwlink/?linkid=852668)」を参照してください。
  
 ### <a name="retention-policies-applied-to-specific-mailboxes"></a>特定のメールボックスに適用されるアイテム保持ポリシー
  
[セキュリティ & コンプライアンスセンターの PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)で次のコマンドを実行して、メールボックスに適用されているアイテム保持ポリシーを識別します。 手順1で特定したアイテム`mbx`保持`skp`ポリシーの GUID (またはプレフィックスを含まない) を使用します。 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

アイテム保持ポリシーを特定したら、セキュリティ & コンプライアンスセンターの [ **Information ガバナンス** \>の**保持**] ページに移動し、前の手順で確認したアイテム保持ポリシーを編集して、アイテム保持ポリシーに含まれる受信者のリストからメールボックスを削除します。 
  
 ### <a name="organization-wide-retention-policies"></a>組織全体に対するアイテム保持ポリシー
  
組織全体および Exchange 全体のアイテム保持ポリシーは、組織内のすべてのメールボックスに適用されます。 これらは、(メールボックスレベルではなく) 組織レベルで適用され、手順1で取得した組織レベルの**config**コマンドレットを実行したときに返されます。 [セキュリティ & コンプライアンスセンターの PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)で次のコマンドを実行して、組織全体のアイテム保持ポリシーを特定します。 手順1で特定した組織`mbx`全体のアイテム保持ポリシーの GUID (プレフィックスを含まない) を使用します。 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

組織全体のアイテム保持ポリシーを特定したら、セキュリティ & コンプライアンスセンターの [ **Information ガバナンス** \>の**保持**] ページに移動し、前の手順で特定した組織全体のアイテム保持ポリシーを編集して、除外された受信者のリストにメールボックスを追加します。 この操作を行うと、ユーザーのメールボックスがアイテム保持ポリシーから削除されます。 

### <a name="retention-labels"></a>保持ラベル

ユーザーがコンテンツを保持するように設定されているラベルを適用するか、メールボックス内のフォルダーまたはアイテムを保持した後にコンテンツを削除すると、 *ComplianceTagHoldApplied* mailbox プロパティが**True**に設定されます。 このような場合、メールボックスは、訴訟ホールドの対象となっているか、アイテム保持ポリシーに割り当てられているかのように、保留中であると見なされます。

*ComplianceTagHoldApplied*プロパティの値を表示するには、Exchange Online PowerShell で次のコマンドを実行します。

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

フォルダーまたはアイテムに保持ラベルが適用されているためにメールボックスが保留になっていることを確認したら、セキュリティ/コンプライアンスセンターのコンテンツ検索ツールを使用して、ComplianceTag の検索条件を使用してラベル付きアイテムを検索できます。 詳細については、「[コンテンツ検索のキーワードクエリと検索条件](keyword-queries-and-search-conditions.md#conditions-for-common-properties)」の「検索条件」セクションを参照してください。

ラベルの詳細については、「[ラベルの概要](labels.md)」を参照してください。

 ### <a name="ediscovery-holds"></a>電子情報開示の保留
  
[セキュリティ & コンプライアンスセンターの PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)で次のコマンドを実行して、メールボックスに適用される電子情報開示ケース (*電子情報*開示の保留と呼ばれます) に関連付けられている保留リストを識別します。 手順1で特定した電子`UniH`情報開示ホールドの GUID (プレフィックスを含まない) を使用します。 2番目のコマンドは、保留が関連付けられている電子情報開示ケースの名前を表示します。3番目のコマンドは、保留の名前を表示します。 
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

電子情報開示のケースとホールドの名前を特定したら、コンプライアンスセンターの [**電子情報** \> **開示電子情報開示**] ページに移動し、ケースを開き、保留リストからメールボックスを削除します。 電子情報開示の保持の識別の詳細については、「How to the Exchange Online mailbox」に記載されている[保留の種類を特定する方法](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)」の「電子情報開示の保持」セクションを参照してください。
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>手順 4: メールボックスから遅延保持を削除する

メールボックスから何らかの種類の保留を解除した後、 *DelayHoldApplied*または*DelayReleaseHoldApplied* mailbox プロパティの値は**True**に設定されます。 これは、管理フォルダーアシスタントが次回メールボックスを処理し、ホールドが削除されたことを検出したときに発生します。 これは*遅延ホールド*と呼ばれ、データがメールボックスから完全に削除されないようにするために、保留リストの実際の削除が30日間延期されることを意味します。 (遅延保持の目的は、保留が解除された後に削除されるメールボックスアイテムを、管理者が検索または復旧する機会を管理者に提供することです)。 メールボックスに遅延保持が設定されている場合でも、メールボックスが訴訟ホールドの対象であったかのように、無期限に保持されていると見なされます。 30日後、遅延保持が有効期限切れになり、Microsoft 365 は遅延ホールド ( *DelayHoldApplied*または*DelayReleaseHoldApplied*プロパティを**False**に設定して) を自動的に削除して、ホールドが解除されるようにします。 遅延ホールドの詳細については、「 [Exchange Online メールボックスに配置された保留の種類を特定する方法](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)」の「遅延保持のメールボックスを管理する」を参照してください。

手順5でアイテムを削除する前に、メールボックスから遅延ホールドを削除する必要があります。 最初に、Exchange Online PowerShell で次のコマンドを実行して、遅延保持がメールボックスに適用されているかどうかを判断します。

```powershell
Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
```

*DelayHoldApplied*または*DelayReleaseHoldApplied*プロパティの値が**False**に設定されている場合、遅延保持はメールボックスに配置されていません。 [回復可能なアイテム] フォルダー内のアイテムを削除するには、手順5に進みます。

*DelayHoldApplied*または*DelayReleaseHoldApplied*プロパティの値が**True**に設定されている場合は、次のいずれかのコマンドを実行して遅延保持を削除します。

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

または

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

*RemoveDelayHoldApplied*または*RemoveDelayReleaseHoldApplied*パラメーターを使用するには、Exchange Online で法的情報保留の役割が割り当てられている必要があります。

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>手順 5: 回復可能なアイテムフォルダーのアイテムを削除する

これで、セキュリティ & コンプライアンスセンターで[new-compliancesearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)および new-compliancesearchaction コマンドレットを使用して、回復可能[な](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction)アイテムフォルダーのアイテムを実際に削除する準備ができました。 

これを行うには、「[メールメッセージの検索と削除](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)」を参照してください。

### <a name="verify-that-items-were-deleted"></a>アイテムが削除されたことを確認する

メールボックスの [回復可能なアイテム] フォルダーからアイテムが正常に削除されたことを確認するには、Exchange Online PowerShell で**get-mailboxfolderstatistics**コマンドレットを使用して、回復可能なアイテムフォルダー内のアイテムのサイズと数を確認します。 これらの統計情報は、手順1で収集したものと比較できます。 
  
で次のコマンドを実行して、ユーザーのプライマリメールボックスの [回復可能なアイテム] フォルダー内のフォルダーとサブフォルダー内のアイテムの現在のサイズと合計数を取得します。 
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

次のコマンドを実行して、ユーザーのアーカイブメールボックスの [回復可能なアイテム] フォルダー内のフォルダーとサブフォルダー内のアイテムのサイズと合計数を取得します。 

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>手順 6: メールボックスを以前の状態に戻す

最後の手順では、メールボックスを以前の構成に戻します。 これは、手順2で変更したプロパティをリセットし、手順3で削除した保留リストを再適用することを意味します。 これには以下が含まれます。
  
- 削除済みアイテムの保存期間を以前の値に戻します。 または、Exchange Online の最大値の30日間に設定しておくこともできます。
    
- 単一アイテムの回復を再び有効にします。
    
- 所有者が自分のメールボックスにアクセスできるように、クライアントアクセス方法を再度有効にします。
    
- 削除した保留リストとアイテム保持ポリシーを再適用します。
    
- 管理フォルダーアシスタントを再度有効にして、メールボックスを処理します。
    
> [!IMPORTANT]
> 管理フォルダーアシスタントを再度有効にしてからメールボックスを処理できるようにするには、保持ポリシーまたはアイテム保持ポリシーを再適用した後24時間待ってから、そのポリシーが適切に設定されていることを確認することをお勧めします。 
  
Exchange Online PowerShell で次の手順を実行します (指定された順序で)。
  
1. 削除済みアイテムの保存期間を元の値に戻すには、次のコマンドを実行します。 これは、前の設定が30日未満であることを前提としています。たとえば、14日になります。 
    
    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. 単一アイテムの回復を再び有効にするには、次のコマンドを実行します。
   
    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. 次のコマンドを実行して、すべてのクライアントアクセス方法をメールボックスに再び有効にします。
    
    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. 手順3で削除したホールドを再適用します。 保留の種類に応じて、次のいずれかの手順を使用します。
    
    **訴訟ホールド**
    
    メールボックスの訴訟ホールドを再び有効にするには、次のコマンドを実行します。
    
    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **In-Place Hold**
    
    EAC (または Exchange Online PowerShell) を使用して、メールボックスをインプレース保持に戻します。 
    
    **特定のメールボックスに適用されるアイテム保持ポリシー**
    
    セキュリティ & コンプライアンスセンターを使用して、メールボックスをアイテム保持ポリシーに追加し直します。 セキュリティ & コンプライアンスセンターの [ **Information ガバナンス** \>の**保持**] ページに移動し、アイテム保持ポリシーを編集して、アイテム保持ポリシーが適用されている受信者のリストにメールボックスを追加し直します。 
    
    **組織全体のアイテム保持ポリシー**
    
    組織全体または Exchange 全体のアイテム保持ポリシーをポリシーから除外して削除した場合は、セキュリティ & コンプライアンスセンターを使用して、除外するユーザーのリストからメールボックスを削除します。 セキュリティ & コンプライアンスセンターの [ **Information ガバナンス** \>の**保持**] ページに移動し、組織全体のアイテム保持ポリシーを編集して、除外された受信者のリストからメールボックスを削除します。 これを行うと、ユーザーのメールボックスにアイテム保持ポリシーが再適用されます。 
    
    **電子情報開示ケースの保持**
    
    セキュリティ & コンプライアンスセンターを使用して、電子情報開示ケースに関連付けられている保留リストにメールボックスを追加し直します。 [**電子情報** \> **開示電子情報開示**] ページに移動し、ケースを開いて、メールボックスを保持に戻します。 
    
5. 管理フォルダーアシスタントがメールボックスを再度処理できるようにするには、次のコマンドを実行します。 前述したように、管理フォルダーアシスタントを再度有効にする前に、保持ポリシーまたはアイテム保持ポリシーを再適用して24時間待ってから、そのポリシーが適切に設定されていることを確認することをお勧めします。 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. メールボックスが以前の構成に戻されたことを確認するには、次のコマンドを実行し、設定を手順1で収集したものと比較します。

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a>詳細情報

次の表は、 *InPlaceHolds*プロパティの値に基づいて、**メールボックスの取得**または取得、または**取得-組織の構成**のコマンドレットを実行した場合に、さまざまな種類の保留を識別する方法を示しています。 詳細については、「 [Exchange Online メールボックスに配置されたホールドの種類を特定する方法](identify-a-hold-on-an-exchange-online-mailbox.md)」を参照してください。

前述のように、[回復可能なアイテム] フォルダー内のアイテムを正常に削除する前に、保留リストとアイテム保持ポリシーをすべて削除する必要があります。 
  
|**ホールドの種類**|**値の例**|**保留リストを識別する方法**|
|:-----|:-----|:-----|
|訴訟ホールド  <br/> | `True` <br/> |*LitigationHoldEnabled*  プロパティが  `True` に設定されています。  <br/> |
|インプレース ホールド  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |*InPlaceHolds*プロパティには、メールボックスに配置されたインプレースホールドの GUID が含まれています。 GUID はプレフィックスで始まっていないため、これはインプレースホールドであることを伝えることができます。  <br/> Exchange Online の PowerShell `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL`でコマンドを使用して、メールボックスのインプレース保持に関する情報を取得できます。  <br/> |
| セキュリティ & コンプライアンスセンターで特定のメールボックスに適用されるアイテム保持ポリシー  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> または  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |**メールボックスの取得**コマンドレットを実行すると、 *InPlaceHolds*プロパティには、メールボックスに適用されているアイテム保持ポリシーの guid も含まれます。 GUID が`mbx`プレフィックスで始まっているため、アイテム保持ポリシーを識別できます。 アイテム保持ポリシーの GUID が`skp`プレフィックスで始まっている場合は、アイテム保持ポリシーが Skype for business の会話に適用されていることを示します。  <br/> メールボックスに適用されているアイテム保持ポリシーを識別するには、セキュリティ & コンプライアンスセンターの PowerShell で次のコマンドを実行します。 <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>このコマンドを実行する場合は、必ず、 `mbx` または  `skp` プレフィックスを削除してください。  <br/> |
|セキュリティ & コンプライアンスセンターの組織全体のアイテム保持ポリシー  <br/> |値なし  <br/> または  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696`(メールボックスが組織全体のポリシーから除外されていることを示します)  <br/> |*InPlaceHolds*コマンドレットの実行時にプロパティが空の場合でも、**メールボックスに**適用されている1つ以上の組織全体のアイテム保持ポリシーが残っている場合があります。  <br/> これを確認するには、Exchange `Get-OrganizationConfig | FL InPlaceHolds` Online PowerShell でコマンドを実行して、組織全体のアイテム保持ポリシーの guid の一覧を取得します。 Exchange メールボックスに適用される組織全体のアイテム保持ポリシーの GUID `mbx`は、先頭にプレフィックスが付いています。たとえば、 `mbxa3056bb15562480fadb46ce523ff7b02`のようになります。  <br/> メールボックスに適用されている組織全体のアイテム保持ポリシーを識別するには、セキュリティ & コンプライアンスセンターの PowerShell で次のコマンドを実行します。 <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>メールボックスが組織全体のアイテム保持ポリシーから除外されている場合、**メールボックス取得**コマンドレットを実行すると、アイテム保持ポリシーの GUID がユーザーのメールボックスの*InPlaceHolds*プロパティに表示されます。プレフィックス`-mbx`によって識別されます。例えば`-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|セキュリティ & コンプライアンスセンターにおける電子情報開示ケースホールド  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |*InPlaceHolds*プロパティには、メールボックスに配置される可能性のあるセキュリティ & コンプライアンスセンターの電子情報開示ケースに関連付けられている保留の GUID も含まれています。 GUID が  `UniH` プレフィックスで始まっているため、これは電子情報開示ケース ホールドであることがわかります。  <br/> セキュリティ & コンプライアンスセンター `Get-CaseHoldPolicy`の PowerShell でコマンドレットを使用して、メールボックスの保留リストに関連付けられている電子情報開示ケースに関する情報を取得できます。 たとえば、コマンド`Get-CaseHoldPolicy <hold GUID without prefix> | FL Name`を実行して、メールボックスにあるケースホールドの名前を表示できます。 Be sure to remove the  `UniH` プレフィックスを削除してください。  <br/><br/> メールボックスの保留リストが関連付けられている電子情報開示ケースを識別するには、次のコマンドを実行します。<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


