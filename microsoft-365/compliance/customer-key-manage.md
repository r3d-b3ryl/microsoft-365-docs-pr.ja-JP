---
title: 顧客キーを管理する
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
description: 顧客キーを設定した後、AKV キーを復元し、アクセス許可とデータ暗号化ポリシーを管理することによって、キーを管理する方法について説明します。
ms.openlocfilehash: 21c1fedce1ebc09e6c33b74a1b2c035c90988e12
ms.sourcegitcommit: f80c6c52e5b08290f74baec1d64c4070046c32e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2020
ms.locfileid: "44717308"
---
# <a name="manage-customer-key"></a>顧客キーを管理する

Office 365 の顧客キーを設定した後、この記事で説明されているようにキーを管理することができます。 関連するトピックの「顧客キー」を参照してください。

## <a name="restore-azure-key-vault-keys"></a>Azure Key Vault キーを復元する

復元を実行する前に、ソフト削除で提供される回復機能を使用します。 ユーザーキーで使用されるすべてのキーは、ソフト削除を有効にするために必要です。 ソフト削除は、ごみ箱と同じように動作し、復元する必要がなくても最大90日の復旧が可能です。 復元は、キーまたはキーの保管が失われた場合など、極端または異常な状況でのみ必要になります。 顧客キーと一緒に使用するためにキーを復元する必要がある場合は、Azure PowerShell で、AzureKeyVaultKey コマンドレットを次のように実行します。
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

例:
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

キー vault に同じ名前のキーが既に含まれている場合、復元操作は失敗します。 AzKeyVaultKey は、キーの名前を含むキーのすべてのキーバージョンとすべてのメタデータを復元します。
  
## <a name="manage-key-vault-permissions"></a>キーコンテナーのアクセス許可を管理する

いくつかのコマンドレットを使用して、重要な資格情報のアクセス許可を表示および削除できます。 たとえば、従業員がチームを離れるときにアクセス許可を削除する必要がある場合があります。 これらの各タスクでは、Azure PowerShell を使用します。 Azure Powershell の詳細については、「 [Azure powershell の概要](https://docs.microsoft.com/powershell/azure/)」を参照してください。

重要な資格情報コンテナーのアクセス許可を表示するには、-AzKeyVault コマンドレットを実行します。

```powershell
Get-AzKeyVault -VaultName <vault name>
```

例:

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

管理者のアクセス許可を削除するには、AzKeyVaultAccessPolicy コマンドレットを実行します。
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

例:

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a>顧客キーを使用してデータ暗号化ポリシー (DEPs) を管理する

顧客キーは、異なるサービス間で異なる方法で Ps を処理します。 たとえば、異なるサービスに対して異なる数の DEPs を作成することができます。

**Exchange Online と Skype For business:** 最大 50 DEPs を作成できます。 手順については、「 [Exchange Online および Skype For business で使用するデータ暗号化ポリシー (DEP) を作成する](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)」を参照してください。

**SharePoint Online、OneDrive For business、Teams の各ファイル:** DEP は、1つの地理的位置 ( _geo_とも呼ばれる) のデータに適用されます。 Office 365 の複数地域機能を使用する場合は、geo ごとに1つの DEP を作成できます。 複数地域を使用していない場合は、1つの DEP を作成できます。 通常は、顧客キーを設定するときに DEP を作成します。 手順については、「 [SharePoint Online および OneDrive For business geo のデータ暗号化ポリシー (DEP) を作成する](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)」を参照してください。

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a>Exchange Online と Skype for Business 用に作成した DEPs を表示する

Exchange Online と Skype for Business 用に作成したすべての DEPs の一覧を表示するには、次の手順を実行します。

1. 組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、 [Exchange Online PowerShell に接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)します。

2. 組織内のすべての DEPs を戻すには、パラメーターを指定せずに、コマンドレットを実行します。

  ```powershell
  Get-DataEncryptionPolicy
  ```

  Get-DataEncryptionPolicy コマンドレットの詳細については、「 [get-dataencryptionpolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy?view=exchange-ps)」を参照してください。

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>メールボックスをクラウドに移行する前に DEP を割り当てる

DEP 365 を割り当てると、移行時に、割り当てられた DEP を使用してメールボックスのコンテンツが暗号化されます。 このプロセスは、メールボックスを移行して DEP を割り当ててから、暗号化の実行を待機するよりも効率的です。これには、数時間または数日かかる場合があります。

Office 365 に移行する前に、メールボックスに DEP を割り当てるには、Exchange Online PowerShell で Set-MailUser コマンドレットを実行します。

1. 組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、 [Exchange Online PowerShell に接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)します。

2. Set-MailUser コマンドレットを実行します。

  ```powershell
  Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
  ```

  *GeneralMailboxOrMailUserIdParameter*にはメールボックスを指定し、 *Dataencryptionpolicyidparameter*は DEP の ID です。 Set-mailuser コマンドレットの詳細については、「 [set-mailuser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser?view=exchange-ps)」を参照してください。

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>メールボックスに割り当てられた DEP を決定する

メールボックスに割り当てられている DEP を特定するには、Get-mailboxstatistics コマンドレットを使用します。 コマンドレットは、一意の識別子 (GUID) を返します。
  
1. 組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、 [Exchange Online PowerShell に接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)します。

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   ここで、 *GeneralMailboxOrMailUserIdParameter*はメールボックスと DataEncryptionPolicyID を指定し、DEP の GUID を返します。 Get-mailboxstatistics コマンドレットの詳細については、「 [get-mailboxstatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics?view=exchange-ps)」を参照してください。
  
2. Get-DataEncryptionPolicy コマンドレットを実行して、メールボックスが割り当てられている DEP のフレンドリ名を検索します。
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   ここで、 *guid*は、前の手順で get-mailboxstatistics コマンドレットによって返される guid です。

## <a name="verify-that-customer-key-has-finished-encryption"></a>顧客キーが暗号化を完了したことを確認する

顧客キーをロールアウトし、新しい DEP を割り当てたか、メールボックスを移行したばかりの場合は、このセクションの手順を使用して暗号化が完了したことを確認します。

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a>Exchange Online と Skype for Business の暗号化が完了していることを確認する

メールボックスを暗号化するには、しばらく時間がかかることがあります。 DEP を変更した後、または初めてメールボックスに DEP を割り当てるときに、暗号化の検証を試行する前に、72時間待つことをお勧めします。
  
メールボックスが暗号化されているかどうかを確認するには、Get-mailboxstatistics コマンドレットを使用します。
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

IsEncrypted プロパティは、メールボックスが暗号化されている場合は**true**の値を返し、メールボックスが暗号化されていない場合は**false**の値を返します。

メールボックスの移動が完了するまでの時間は、メールボックスのサイズによって異なります。 新しい DEP を割り当てた時点から72時間後にメールボックスが完全に暗号化されていない場合は、Microsoft サポートにお問い合わせください。 New-moverequest コマンドレットは、ローカルメールボックスの移動では使用できなくなりました。 詳細については、[このお知らせ](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141)を参照してください。

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>SharePoint Online、OneDrive for Business、および Teams ファイルの暗号化が完了していることを確認する

Get-spodataencryptionpolicy コマンドレットを次のように実行して、暗号化の状態を確認します。

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

このコマンドレットの出力には次のものが含まれます。
  
- 主キーの URI。

- セカンダリキーの URI。

- Geo の暗号化の状態。 次の状態が考えられます。

  - **未登録:** 顧客キーの暗号化はまだ適用されていません。

  - **登録:** 顧客キーの暗号化が適用され、ファイルが暗号化されています。 Geo のキーが登録されている場合は、暗号化の進行状況を監視できるように、地域内のサイトの割合に関する情報も表示されます。

  - **登録済み:** 顧客キーの暗号化が適用され、すべてのサイトのすべてのファイルが暗号化されました。

  - **ローリング:** キーロールが進行中です。 Geo のキーがローリングの場合は、進行状況を監視できるように、キーロール操作を完了したサイトの割合に関する情報も表示されます。

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>キーを無効にし、データ削除パスプロセスを開始する

可用性キーを含むすべてのルートキーの取り消しを制御します。 顧客キーは、規制要件の終了計画についての制御を提供します。 データを削除してサービスを終了するためのキーを失効させる場合、データの削除プロセスが完了すると、サービスによって可用性キーが削除されます。

Microsoft 365 は、データ削除パスを監査して検証します。 詳細については、 [Service Trust Portal](https://servicetrust.microsoft.com/)で利用できる SSAE 18 SOC 2 レポートを参照してください。 さらに、Microsoft は次のドキュメントをお勧めします。

- [Microsoft クラウドでの金融機関のリスク評価およびコンプライアンスガイド](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [O365 終了計画に関する考慮事項](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

データ削除パスは、さまざまなサービス間で少し異なります。

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Exchange Online と Skype for Business の顧客キーと可用性キーを無効にする

Exchange Online と Skype for Business のデータ削除パスを開始するときは、DEP で永続的なデータ削除要求を設定します。 これにより、DEP が割り当てられているメールボックス内の暗号化されたデータが完全に削除されます。

一度に1つの DEP に対してのみ PowerShell コマンドレットを実行できるため、データの削除パスを開始する前に、すべてのメールボックスに対して単一の DEP を再割り当てすることを検討してください。

> [!WARNING]
> メールボックスのサブセットを削除するのには、データ削除パスを使用しないでください。 このプロセスは、サービスを終了しているお客様のみを対象としています。

データの削除パスを開始するには、次の手順を実行します。

1. Azure Key コンテナーから、"O365 Exchange Online" のラップとラップ解除のアクセス許可を削除します。

2. 組織のグローバル管理者特権を持つ職場または学校のアカウントを使用して、 [Exchange Online PowerShell に接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)します。

3. 削除するメールボックスを含む DEP ごとに、次のように[Set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy)コマンドレットを実行します。

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   コマンドが失敗した場合は、このタスクで前述したように、Azure Key Vault の両方のキーから Exchange Online アクセス許可が削除されていることを確認してください。PermanentDataPurgeRequested スイッチを設定して、このコマンドレットを使用すると、この DEP をメールボックスに割り当てることができなくなります。

4. Microsoft サポートに連絡し、データ削除 eDocument を要求します。

    要求に応じて、Microsoft から法的文書が送信され、データの削除を確認して承認します。 このドキュメントに署名する必要があるのは、オンボード時に FastTrack オファーで承認者としてサインアップした組織内のユーザーです。 通常、これは、組織の代わりに書類に署名することを正当に承認されている社内のエグゼクティブまたはその他の指定者です。

5. 担当者が法的文書に署名したら、Microsoft に返信します (通常は eDoc 署名を使用)。

    Microsoft が法的文書を受け取ると、Microsoft はコマンドレットを実行して、最初にポリシーを削除し、メールボックスの完全削除をマークし、可用性キーを削除する、データの削除をトリガーします。 データ削除プロセスが完了すると、データは削除され、Exchange Online からはアクセスできなくなります。復元することはできません。

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>SharePoint Online、OneDrive for Business、および Teams ファイルのお客様キーと可用性キーを無効にする

SharePoint Online、OneDrive for Business、および Teams ファイルのデータ削除パスを開始するには、次の手順を実行します。

1. Azure Key Vault アクセスを取り消します。 すべてのキーコンテナー管理者がアクセスを取り消すことに同意する必要があります。

   SharePoint Online の Azure キーコンテナーは削除しません。 キーコンテナーは、いくつかの SharePoint Online テナントと DEPs 間で共有される場合があります。

2. Microsoft に連絡して、空き時間情報キーを削除します。

    Microsoft に連絡して可用性キーを削除すると、法的文書が送信されます。 このドキュメントに署名する必要があるのは、オンボード時に FastTrack オファーで承認者としてサインアップした組織内のユーザーです。 通常、これは、組織の代わりに書類に署名する法的な権限を持つ、社内のエグゼクティブまたはその他の指定者です。

3. 代表者が法的文書に署名したら、マイクロソフトに返送します (通常は eDoc 署名を使用)。

   Microsoft が法的文書を受け取ったら、コマンドレットを実行して、テナントキー、サイトキー、および各ドキュメントの各キーの暗号化削除を実行するデータ削除をトリガーします。キー階層を irrevocably します。 データ削除コマンドレットが完了すると、データが削除されています。

## <a name="related-articles"></a>関連記事

- [顧客キーによるサービスの暗号化](customer-key-overview.md)

- [可用性キーについて](customer-key-availability-key-understand.md)

- [顧客キーを設定する](customer-key-set-up.md)

- [カスタマー キーまたは可用性キーをローリングまたはローテーションする](customer-key-availability-key-roll.md)

- [カスタマー ロックボックス](customer-lockbox-requests.md)

- [サービス暗号化](office-365-service-encryption.md)
