---
title: 顧客キーの管理
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 顧客キーを設定した後、AKV キーを復元し、アクセス許可とデータ暗号化ポリシーを管理して、そのキーを管理する方法について説明します。
ms.openlocfilehash: 8f55667254ce7f5cbd9d4de274623ca4a3c4aa9d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909949"
---
# <a name="manage-customer-key"></a>顧客キーの管理

365 の顧客キーをOffice、この記事の説明に従ってキーを管理できます。 関連トピックの顧客キーの詳細について説明します。

## <a name="restore-azure-key-vault-keys"></a>Azure Key Vault キーの復元

復元を実行する前に、ソフト削除によって提供される回復機能を使用します。 顧客キーと一緒に使用するキーはすべて、ソフト削除を有効にする必要があります。 削除はごみ箱のように機能し、復元する必要なしに最大 90 日間の回復を可能にします。 キーまたはキー コンテナーが失われた場合など、極端な状況や異常な状況でのみ復元が必要です。 顧客キーで使用するキーを復元する必要がある場合は、Azure PowerShell で、次のように Restore-AzureKeyVaultKeyコマンドレットを実行します。
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

次に例を示します。
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

キー コンテナーに同じ名前のキーが既に含まれている場合、復元操作は失敗します。 Restore-AzKeyVaultKey、すべてのキー バージョンと、キー名を含むキーのすべてのメタデータを復元します。
  
## <a name="manage-key-vault-permissions"></a>キー コンテナーのアクセス許可を管理する

いくつかのコマンドレットを使用して、キー コンテナーのアクセス許可を表示したり、必要に応じて削除したりできます。 従業員がチームを離れる場合など、アクセス許可を削除する必要がある場合があります。 これらの各タスクについて、Azure PowerShell を使用します。 Azure Powershell の詳細については [、「Azure PowerShell の概要」を参照してください](/powershell/azure/)。

キー コンテナーのアクセス許可を表示するには、次のコマンドレットGet-AzKeyVaultします。

```powershell
Get-AzKeyVault -VaultName <vault name>
```

次に例を示します。

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

管理者のアクセス許可を削除するには、次のコマンドレットをRemove-AzKeyVaultAccessPolicyします。
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

次に例を示します。

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a>顧客キーを使用してデータ暗号化ポリシー (DEP) を管理する

顧客キーは、異なるサービス間で DEP を異なる方法で処理します。 たとえば、異なるサービスに対して異なる数の DEP を作成できます。

**Exchange Online と Skype for Business:** 最大 50 の DEP を作成できます。 手順については、「Exchange Online および Skype for Business で使用するデータ暗号化ポリシー [(DEP) の作成」を参照してください](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)。

**SharePoint Online、OneDrive for Business、Teams ファイル:** DEP は、地理的な場所 (geo とも呼ばれる) のデータに適用 _されます_。 365 の複数地域機能を使用Office地域ごとに 1 つの DEP を作成できます。 複数地域を使用していない場合は、1 つの DEP を作成できます。 通常、顧客キーを設定するときに DEP を作成します。 手順については [、「SharePoint Online および OneDrive for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)geo ごとにデータ暗号化ポリシー (DEP) を作成する」を参照してください。

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a>Exchange Online および Skype for Business 用に作成した DEP を表示する

PowerShell コマンドレットを使用して Exchange Online および Skype for Business 用に作成したすべての DEP の一覧を表示するには、Get-DataEncryptionPolicy手順を実行します。

1. 組織内でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して [、Exchange Online PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 組織内のすべての DEP を返す場合は、パラメーターを指定せずに Get-DataEncryptionPolicyコマンドレットを実行します。

   ```powershell
   Get-DataEncryptionPolicy
   ```

   このコマンドレットの詳細についてはGet-DataEncryptionPolicy [Get-DataEncryptionPolicy を参照してください](/powershell/module/exchange/get-dataencryptionpolicy)。

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>メールボックスをクラウドに移行する前に DEP を割り当てる

DEP を割り当てると、移行中に割り当てられた DEP を使用してメールボックスの内容が暗号化されます。 このプロセスは、メールボックスの移行、DEP の割り当て、暗号化の実行を待機するよりも効率的です。これには数時間または数日かかる場合があります。

メールボックスを 365 に移行する前に DEP をOfficeするには、Exchange Online PowerShell Set-MailUserコマンドレットを実行します。

1. 組織内でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して [、Exchange Online PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。

2. このコマンドレットをSet-MailUserします。

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   *GeneralMailboxOrMailUserIdParameter は* メールボックスを指定し *、DataEncryptionPolicyIdParameter* は DEP の ID です。 このコマンドレットの詳細についてはSet-MailUser [Set-MailUser を参照してください](/powershell/module/exchange/set-mailuser)。

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>メールボックスに割り当てられた DEP を決定する

メールボックスに割り当てられた DEP を確認するには、次のコマンドレットGet-MailboxStatisticsします。 コマンドレットは、一意の識別子 (GUID) を返します。
  
1. 組織内でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して [、Exchange Online PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   *GeneralMailboxOrMailUserIdParameter は* メールボックスを指定し、DataEncryptionPolicyID は DEP の GUID を返します。 このコマンドレットの詳細についてはGet-MailboxStatistics [Get-MailboxStatistics を参照してください](/powershell/module/exchange/get-mailboxstatistics)。
  
2. このコマンドレットGet-DataEncryptionPolicy実行して、メールボックスが割り当てられている DEP の表示名を確認します。
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   ここで *、GUID* は、前の手順の Get-MailboxStatisticsコマンドレットによって返される GUID です。

## <a name="verify-that-customer-key-has-finished-encryption"></a>顧客キーが暗号化を完了したのを確認する

顧客キーをロールしたばかりか、新しい DEP が割り当てられているか、メールボックスを移行したのかは、このセクションの手順を使用して、暗号化が完了します。

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a>Exchange Online と Skype for Business の暗号化が完了した場合の確認

メールボックスの暗号化には時間がかかる場合があります。 DEP を変更した後、または初めてメールボックスに DEP を割り当てると、暗号化の検証を試行するまで 72 時間待機することをお勧めします。
  
メールボックスが暗号化Get-MailboxStatisticsを判断するには、このコマンドレットを使用します。
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

IsEncrypted プロパティは、メールボックスが暗号化されている場合は **true、** メールボックスが暗号化されていない場合は **false** の値を返します。

メールボックスの移動を完了する時間は、メールボックスのサイズによって異なります。 新しい DEP の割り当てから 72 時間後に顧客キーがメールボックスを完全に暗号化しない場合は、Microsoft サポートにお問い合わせください。 このNew-MoveRequestは、ローカル メールボックスの移動に使用できなくなりました。 詳細については [、このお知](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) らせを参照してください。

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online、OneDrive for Business、Teams ファイルの暗号化が完了した場合の確認

次のように、Get-SPODataEncryptionPolicyコマンドレットを実行して、暗号化の状態を確認します。

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

このコマンドレットの出力には、次の情報が含まれます。
  
- 主キーの URI。

- セカンダリ キーの URI。

- geo の暗号化状態。 可能な状態は次のとおりです。

  - **未登録:** 顧客キーの暗号化がまだ適用されていません。

  - **登録:** 顧客キーの暗号化が適用され、ファイルが暗号化中です。 geo のキーが登録されている場合は、暗号化の進行状況を監視するために、geo 内のサイトが完了した割合に関する情報も表示されます。

  - **登録済み:** 顧客キーの暗号化が適用され、すべてのサイトのすべてのファイルが暗号化されています。

  - **ローリング:** キー ロールが進行中です。 geo のキーがローリングされている場合は、キー ロール操作を完了したサイトの割合に関する情報も表示され、進行状況を監視できます。

## <a name="unassign-a-dep-from-a-mailbox"></a>メールボックスからの DEP の割り当てを解除する

Set-mailbox PowerShell コマンドレットを使用してメールボックスから DEP の割り当てを解除し、にを設定 `DataEncryptionPolicy` します `$NULL` 。 このコマンドレットを実行すると、現在割り当てられている DEP の割り当てを解除し、既定の Microsoft 管理キーに関連付けられた DEP を使用してメールボックスを再暗号化します。 Microsoft マネージ キーで使用される DEP の割り当てを解除できません。 Microsoft 管理キーを使用しない場合は、別の DEP をメールボックスに割り当てできます。

PowerShell コマンドレットを使用してメールボックスから DEP の割り当てを解除Set-Mailbox手順を実行します。

1. 組織内でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して [、Exchange Online PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。

2. このコマンドレットをSet-Mailboxします。

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>キーを取り消し、データ削除パス プロセスを開始する

可用性キーを含むすべてのルート キーの失効を制御します。 顧客キーは、規制要件の出口計画の側面を制御します。 データを削除してサービスを終了するためにキーを取り消す場合、データ削除プロセスが完了すると、サービスは可用性キーを削除します。

Microsoft 365 は、データ削除パスを監査および検証します。 詳細については、「SSAE 18 SOC 2 Report available on the [Service Trust Portal」を参照してください](https://servicetrust.microsoft.com/)。 さらに、Microsoft では次のドキュメントを推奨しています。

- [Microsoft Cloud の金融機関のリスク評価とコンプライアンス ガイド](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [O365 Exit Planning に関する考慮事項](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

データ削除パスは、サービスによって若干異なります。

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Exchange Online と Skype for Business のカスタマー キーと可用性キーを取り消す

Exchange Online および Skype for Business のデータ削除パスを開始すると、DEP に永続的なデータ削除要求を設定します。 これにより、DEP が割り当てられているメールボックス内の暗号化されたデータが完全に削除されます。

PowerShell コマンドレットは一度に 1 つの DEP に対してしか実行できないので、データ削除パスを開始する前に、1 つの DEP をすべてのメールボックスに再割り当てする方法を検討してください。

> [!WARNING]
> データ削除パスを使用して、メールボックスのサブセットを削除しない。 このプロセスは、サービスを終了する顧客のみを対象とします。

データ削除パスを開始するには、次の手順を実行します。

1. Azure Key Vaults から "O365 Exchange Online" のラップとアンラップのアクセス許可を削除します。

2. 組織内でグローバル管理者特権を持つ仕事または学校のアカウントを使用して [、Exchange Online PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。

3. 削除するメールボックスを含む DEP ごとに、次のように [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) コマンドレットを実行します。

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   コマンドが失敗した場合は、このタスクで前に指定したように、Azure Key Vault の両方のキーから Exchange Online のアクセス許可を削除してください。Set-DataEncryptionPolicy コマンドレットを使用して PermanentDataPurgeRequested スイッチを設定すると、この DEP をメールボックスに割り当てなくなりました。

4. Microsoft のサポートに問い合わせ、データ削除 eDocument を要求します。

    Microsoft は、要求に応じて、データの削除を承認および承認する法的文書を送信します。 オンボーディング中に FastTrack オファーで承認者としてサインアップした組織内のユーザーは、このドキュメントに署名する必要があります。 通常、これは会社の役員または他の指定された人物で、組織に代わって書類に署名する法的権限を持ちます。

5. 代理人が法的文書に署名したら、それを Microsoft に返します (通常は eDoc 署名を通じて)。

    Microsoft が法的文書を受け取った後、Microsoft はコマンドレットを実行してデータ削除をトリガーし、最初にポリシーを削除し、メールボックスに完全な削除のマークを付け、可用性キーを削除します。 データ削除プロセスが完了すると、データは削除され、Exchange Online にアクセスできなくなり、回復できません。

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online、OneDrive for Business、Teams ファイルのカスタマー キーと可用性キーを取り消す

SharePoint Online、OneDrive for Business、Teams ファイルのデータ削除パスを開始するには、次の手順を実行します。

1. Azure Key Vault アクセスを取り消します。 すべてのキー コンテナー管理者は、アクセスを取り消すことに同意する必要があります。

   SharePoint Online の Azure Key Vault は削除されません。 キー コンテナーは、複数の SharePoint Online テナントと DEP 間で共有できます。

2. 可用性キーを削除するには、Microsoft にお問い合わせください。

    可用性キーを削除するために Microsoft に連絡すると、法的文書が送信されます。 オンボーディング中に FastTrack オファーで承認者としてサインアップした組織内のユーザーは、このドキュメントに署名する必要があります。 通常、これは会社の役員または他の指定された人物で、組織に代わって書類に署名する法的権限を持ちます。

3. 代理人が法的文書に署名したら、それを Microsoft に返します (通常は eDoc 署名を通じて)。

   Microsoft が法的文書を受け取った後、コマンドレットを実行して、テナント キー、サイト キー、およびドキュメントごとの個々のキーの暗号化削除を実行するデータ削除をトリガーし、キー階層を取り消し可能に壊します。 データ削除コマンドレットが完了すると、データは削除されます。

## <a name="related-articles"></a>関連記事

- [カスタマー キーによるサービスの暗号化](customer-key-overview.md)

- [可用性キーの詳細](customer-key-availability-key-understand.md)

- [顧客キーの設定](customer-key-set-up.md)

- [カスタマー キーまたは可用性キーをローリングまたはローテーションする](customer-key-availability-key-roll.md)

- [カスタマー ロックボックス](customer-lockbox-requests.md)

- [サービスの暗号化](office-365-service-encryption.md)