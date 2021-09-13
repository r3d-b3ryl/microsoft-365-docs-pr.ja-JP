---
title: 顧客キーの管理
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 顧客キーを設定した後、AKV キーを復元し、アクセス許可を管理し、データ暗号化ポリシーを作成および割り当て、管理する方法について説明します。
ms.openlocfilehash: 7fc985aaaf0cf0222a6cd02063207b2b1709ac25
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216884"
---
# <a name="manage-customer-key"></a>顧客キーの管理

顧客キーの設定がOffice 365、1 つ以上のデータ暗号化ポリシー (DEP) を作成して割り当てる必要があります。 DEP を割り当てしたら、この記事の説明に従ってキーを管理できます。 関連トピックの顧客キーの詳細について説明します。

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a>すべてのテナント ユーザーに対して複数のワークロードで使用する DEP を作成する

開始する前に、顧客のセットアップに必要なタスクが完了している必要があります。 詳細については、「 [顧客キーの設定」を参照してください](customer-key-set-up.md)。 DEP を作成するには、セットアップ時に取得した Key Vault URI が必要です。 詳細については、「Azure [Key Vault キーごとに URI を取得する」を参照してください](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)。

複数ワークロード DEP を作成するには、次の手順を実行します。
  
1. ローカル コンピューターで、組織でグローバル管理者またはコンプライアンス管理者のアクセス許可を持つ仕事または学校のアカウントを使用して、Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)に接続します。Windows PowerShell ウィンドウで。

2. DEP を作成するには、次のコマンドレットNew-M365DataAtRestEncryptionPolicyします。

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   ここで、

   - *PolicyName* は、ポリシーに使用する名前です。 名前にスペースを含めることはできません。 たとえば、Contoso_Global。

   - *KeyVaultURI1 は* 、ポリシーの最初のキーの URI です。 たとえば、<https://contosoWestUSvault1.vault.azure.net/keys/Key_01> などです。

   - *KeyVaultURI2* は、ポリシー内の 2 番目のキーの URI です。 たとえば、<https://contosoCentralUSvault1.vault.azure.net/keys/Key_02> などです。 2 つの URI をコンマとスペースで区切ります。

   - *ポリシーの* 説明は、ポリシーの内容を思い出すのに役立つ、ユーザーフレンドリーなポリシーの説明です。 説明にスペースを含めることができます。 たとえば、「テナント内のすべてのユーザーに対する複数のワークロードのルート ポリシー」です。

例:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a>複数ワークロード ポリシーの割り当て

このコマンドレットを使用して DEP をSet-M365DataAtRestEncryptionPolicyAssignmentします。 ポリシーを割り当てるとMicrosoft 365 DEP で識別されたキーを使用してデータが暗号化されます。

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 PolicyName *は* ポリシーの名前です。 たとえば、Contoso_Global。

例:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a>メールボックスで使用する DEP をExchange Onlineする

開始する前に、Azure Key Vault のセットアップに必要なタスクが完了している必要があります。 詳細については、「 [顧客キーの設定」を参照してください](customer-key-set-up.md)。 これらの手順は、リモートでユーザーに接続し、Exchange OnlineをWindows PowerShell。

DEP は、Azure Key Vault に格納されている一連のキーに関連付けられる。 DEP をメールボックスに割り当てるには、Microsoft 365。 Microsoft 365ポリシーで識別されたキーを使用してメールボックスを暗号化します。 DEP を作成するには、セットアップ時に取得した Key Vault URI が必要です。 詳細については、「Azure [Key Vault キーごとに URI を取得する」を参照してください](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)。

覚えておいてください! DEP を作成する場合は、2 つの異なる Azure キー コンテナーに 2 つのキーを指定します。 地理的冗長性を確保するために、これらのキーを 2 つの別個の Azure リージョンに作成します。

メールボックスで使用する DEP を作成するには、次の手順を実行します。
  
1. ローカル コンピューターで、組織内にグローバル管理者または Exchange Online 管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)に接続します。Windows PowerShell ウィンドウ。

2. DEP を作成するには、次のコマンドNew-DataEncryptionPolicyコマンドを使用します。

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   ここで、

   - *PolicyName* は、ポリシーに使用する名前です。 名前にスペースを含めることはできません。 たとえば、USA_mailboxes。

   - *ポリシーの* 説明は、ポリシーの内容を思い出すのに役立つ、ユーザーフレンドリーなポリシーの説明です。 説明にスペースを含めることができます。 たとえば、「米国とその地域のメールボックスのルート キー」です。

   - *KeyVaultURI1 は* 、ポリシーの最初のキーの URI です。 たとえば、<https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01> などです。

   - *KeyVaultURI2* は、ポリシー内の 2 番目のキーの URI です。 たとえば、<https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02> などです。 2 つの URI をコンマとスペースで区切ります。

   例:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

構文とパラメーターの詳細については [、「New-DataEncryptionPolicy」を参照してください](/powershell/module/exchange/new-data-encryptionpolicy)。

### <a name="assign-a-dep-to-a-mailbox"></a>メールボックスへの DEP の割り当て

DEP をメールボックスに割り当てるには、このコマンドレットSet-Mailboxします。 ポリシーを割り当てるとMicrosoft 365 DEP で識別されたキーを使用してメールボックスを暗号化できます。
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

*MailboxIdParameter はユーザー* メールボックスを指定します。 このコマンドレットの詳細についてはSet-Mailbox [Set-Mailbox を参照してください](/powershell/module/exchange/set-mailbox)。

ハイブリッド環境では、DEP をオンプレミスのメールボックス データに割り当て、そのデータをテナントにExchange Onlineできます。 この同期されたメールボックス データに DEP を割り当てるには、次のコマンドレットSet-MailUserします。 ハイブリッド環境のメールボックス データの詳細については、「ハイブリッドモダン認証を使用した iOS および Android 用 Outlookを使用するオンプレミスのメールボックス」[を参照してください](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)。

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

*MailUserIdParameter はメール* ユーザー (メールが有効なユーザーとも呼ばれる) を指定します。 このコマンドレットの詳細についてはSet-MailUser [Set-MailUser を参照してください](/powershell/module/exchange/set-mailuser)。

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a>オンライン、オンライン、SharePoint、およびOneDrive for Businessで使用Teamsする

開始する前に、Azure Key Vault のセットアップに必要なタスクが完了している必要があります。 詳細については、「 [顧客キーの設定」を参照してください](customer-key-set-up.md)。
  
SharePoint Online、OneDrive for Business、および Teams ファイルのカスタマー キーを設定するには、SharePoint Online と Windows PowerShell でリモート接続して、これらの手順を実行します。
  
DEP を Azure Key Vault に格納されている一連のキーに関連付ける。 DEP は、地理と呼ばれる 1 つの地理的な場所のすべてのデータに適用します。 Office 365 の複数地域機能を使用する場合は、geo ごとに異なるキーを使用する機能を使用して、地域ごとに 1 つの DEP を作成できます。 複数地域を使用していない場合は、SharePoint Online、OneDrive for Business、および Teams ファイルで使用するために、組織内に 1 つの DEP をTeamsできます。 Microsoft 365 DEP で識別されたキーを使用して、その地域のデータを暗号化します。 DEP を作成するには、セットアップ時に取得した Key Vault URI が必要です。 詳細については、「Azure [Key Vault キーごとに URI を取得する」を参照してください](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)。
  
覚えておいてください! DEP を作成する場合は、2 つの異なる Azure キー コンテナーに 2 つのキーを指定します。 地理的冗長性を確保するために、これらのキーを 2 つの別個の Azure リージョンに作成します。
  
DEP を作成するには、サーバーを使用してオンラインSharePointリモート接続するWindows PowerShell。
  
1. ローカル コンピューターで、組織内にグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、オンライン[PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)ConnectをSharePointします。

2. [管理シェルMicrosoft Office SharePoint Onlineで、次のようにRegister-SPODataEncryptionPolicyコマンドレットを実行します。

   ```powershell
   Register-SPODataEncryptionPolicy <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   例:
  
   ```powershell
   Register-SPODataEncryptionPolicy  https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   DEP を登録すると、geo のデータで暗号化が開始されます。 暗号化には時間がかかる場合があります。 このパラメーターの使用の詳細については [、「Register-SPODataEncryptionPolicy」を参照してください](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps)。

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a>メールボックス用に作成した DEP をExchange Onlineする

メールボックス用に作成したすべての DEP の一覧を表示するには、PowerShell コマンドレットGet-DataEncryptionPolicy使用します。

1. 組織でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して[、PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)にExchange Onlineします。

2. 組織内のすべての DEP を返す場合は、パラメーターを指定せずに Get-DataEncryptionPolicyコマンドレットを実行します。

   ```powershell
   Get-DataEncryptionPolicy
   ```

   このコマンドレットの詳細についてはGet-DataEncryptionPolicy [Get-DataEncryptionPolicy を参照してください](/powershell/module/exchange/get-dataencryptionpolicy)。

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>メールボックスをクラウドに移行する前に DEP を割り当てる

DEP を割り当てるMicrosoft 365、移行中に割り当てられた DEP を使用してメールボックスの内容を暗号化します。 このプロセスは、メールボックスの移行、DEP の割り当て、暗号化の実行を待機するよりも効率的です。これには数時間または数日かかる場合があります。

DEP をメールボックスに移行する前にメールボックスに割り当てるにはOffice 365 PowerShell で Set-MailUser コマンドレットExchange Onlineします。

1. 組織でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して[、PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)にExchange Onlineします。

2. このコマンドレットをSet-MailUserします。

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   *GeneralMailboxOrMailUserIdParameter は* メールボックスを指定し *、DataEncryptionPolicyIdParameter* は DEP の ID です。 このコマンドレットの詳細についてはSet-MailUser [Set-MailUser を参照してください](/powershell/module/exchange/set-mailuser)。

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>メールボックスに割り当てられた DEP を決定する

メールボックスに割り当てられた DEP を確認するには、次のコマンドレットGet-MailboxStatisticsします。 コマンドレットは、一意の識別子 (GUID) を返します。
  
1. 組織でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して[、PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)にExchange Onlineします。

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

顧客キーをロールしたかどうか、新しい DEP を割り当てたか、メールボックスを移行した場合でも、このセクションの手順を使用して、暗号化が完了します。

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a>メールボックスの暗号化が完了Exchange Onlineする

メールボックスの暗号化には時間がかかる場合があります。 初めて暗号化を行う場合は、サービスがメールボックスを暗号化する前に、メールボックスをあるデータベースから別のデータベースに完全に移動する必要があります。
  
メールボックスが暗号化Get-MailboxStatisticsを判断するには、このコマンドレットを使用します。
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

IsEncrypted プロパティは、メールボックスが暗号化されている場合は true、メールボックスが暗号化されていない場合は **false** の値を返します。 メールボックスの移動を完了する時間は、初めて DEP を割り当てるメールボックスの数と、メールボックスのサイズによって異なります。 DEP を割り当てた時刻から 1 週間後にメールボックスが暗号化されていない場合は、Microsoft にお問い合わせください。

このNew-MoveRequestは、ローカル メールボックスの移動に使用できなくなりました。 詳細については [、このお知](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) らせを参照してください。

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>オンライン、SharePoint、OneDrive for BusinessファイルTeams確認する

次のように、Get-SPODataEncryptionPolicyコマンドレットを実行して、暗号化の状態を確認します。

```PowerShell
   Get-SPODataEncryptionPolicy <SPOAdminSiteUrl>
```

このコマンドレットの出力には、次の情報が含まれます。
  
- 主キーの URI。

- セカンダリ キーの URI。

- geo の暗号化状態。 可能な状態は次のとおりです。

  - **未登録:** 顧客キーの暗号化がまだ適用されていません。

  - **登録:** 顧客キーの暗号化が適用され、ファイルが暗号化中です。 geo のキーが登録されている場合は、暗号化の進行状況を監視するために、geo 内のサイトが完了した割合に関する情報も表示されます。

  - **登録済み:** 顧客キーの暗号化が適用され、すべてのサイトのすべてのファイルが暗号化されています。

  - **ローリング:** キー ロールが進行中です。 geo のキーがローリングされている場合は、キー ロール操作を完了したサイトの割合に関する情報も表示され、進行状況を監視できます。

- また、オンボーディングされたサイトの割合も出力されます。

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a>複数のワークロードで使用する DEP の詳細を取得する

複数のワークロードで使用するために作成した DEP の詳細を取得するには、次の手順を実行します。

1. ローカル コンピューターで、組織でグローバル管理者またはコンプライアンス管理者のアクセス許可を持つ仕事または学校のアカウントを使用して、Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)に接続します。Windows PowerShell ウィンドウで。

   - 組織内のすべての複数ワークロード DEP の一覧を取得するには、次のコマンドを実行します。

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - 特定の DEP に関する詳細を返す場合は、次のコマンドを実行します。 この例では、"Contoso_Global" という名前の DEP の詳細情報を返Contoso_Global。

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a>複数ワークロードの DEP 割り当て情報を取得する

現在テナントに割り当てられている DEP を確認するには、次の手順を実行します。 

1. ローカル コンピューターで、組織でグローバル管理者またはコンプライアンス管理者のアクセス許可を持つ仕事または学校のアカウントを使用して、Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)に接続します。Windows PowerShell ウィンドウで。

2. このコマンドを入力します。

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a>複数ワークロード DEP を無効にする

マルチワークロード DEP を無効にする前に、テナント内のワークロードから DEP の割り当てを解除します。 複数のワークロードで使用される DEP を無効にするには、次の手順を実行します。

1. ローカル コンピューターで、組織でグローバル管理者またはコンプライアンス管理者のアクセス許可を持つ仕事または学校のアカウントを使用して、Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)に接続します。Windows PowerShell ウィンドウで。

2. このコマンドレットをSet-M365DataAtRestEncryptionPolicyします。
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

PolicyName *は* 、ポリシーの名前または一意の ID です。 たとえば、Contoso_Global。

例:

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a>Azure Key Vault キーの復元

復元を実行する前に、ソフト削除によって提供される回復機能を使用します。 顧客キーと一緒に使用するキーはすべて、ソフト削除を有効にする必要があります。 削除はごみ箱のように機能し、復元する必要なしに最大 90 日間の回復を可能にします。 キーまたはキー コンテナーが失われた場合など、極端な状況や異常な状況でのみ復元が必要です。 顧客キーで使用するキーを復元する必要がある場合は、次Azure PowerShell、Restore-AzureKeyVaultKeyコマンドレットを実行します。
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

例:
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

キー コンテナーに同じ名前のキーが既に含まれている場合、復元操作は失敗します。 Restore-AzKeyVaultKey、すべてのキー バージョンと、キー名を含むキーのすべてのメタデータを復元します。
  
## <a name="manage-key-vault-permissions"></a>キー コンテナーのアクセス許可を管理する

いくつかのコマンドレットを使用して、キー コンテナーのアクセス許可を表示したり、必要に応じて削除したりできます。 従業員がチームを離れる場合など、アクセス許可を削除する必要がある場合があります。 これらの各タスクに対して、このタスクを使用Azure PowerShell。 詳細については、「Azure PowerShellの[概要」を参照Azure PowerShell。](/powershell/azure/)

キー コンテナーのアクセス許可を表示するには、次のコマンドレットGet-AzKeyVaultします。

```powershell
Get-AzKeyVault -VaultName <vault name>
```

例:

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

管理者のアクセス許可を削除するには、次のコマンドレットをRemove-AzKeyVaultAccessPolicyします。
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

例:

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a>顧客キーから Microsoft マネージ キーへのロールバック

Microsoft で管理されているキーに戻す必要がある場合は、可能です。 オフボードの場合、データは、個々のワークロードでサポートされる既定の暗号化を使用して再暗号化されます。 たとえば、Microsoft Exchange Onlineキーを使用した既定の暗号化がサポートされている場合です。

> [!IMPORTANT]
> オフボードは、データ削除と同じではありません。 データの削除は、組織のデータを完全に暗号化削除し、Microsoft 365オフボードから削除します。 複数のワークロード ポリシーに対してデータ削除を実行できない。

マルチワークロード DEP の割り当てに顧客キーを使用しない場合は、顧客キーから "offboard" への要求を受け取って Microsoft サポートに連絡する必要があります。 サポート チームに、顧客キー チームに対してサービス要求Microsoft 365依頼します。 質問がある場合 m365-ck@service.microsoft.com に問い合わせください。

メールボックス レベルの DEP を使用して個々のメールボックスを暗号化しない場合は、すべてのメールボックスからメールボックス レベルの DEP の割り当てを解除できます。

メールボックス DEP の割り当てを解除するには、PowerShell コマンドレットSet-Mailbox使用します。

1. 組織でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して[、PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)にExchange Onlineします。

2. このコマンドレットをSet-Mailboxします。

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

このコマンドレットを実行すると、現在割り当てられている DEP の割り当てを解除し、既定の Microsoft 管理キーに関連付けられた DEP を使用してメールボックスを再暗号化します。 Microsoft マネージ キーで使用される DEP の割り当てを解除できません。 Microsoft で管理されているキーを使用しない場合は、別の顧客キー DEP をメールボックスに割り当てできます。

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>キーを取り消し、データ削除パス プロセスを開始する

可用性キーを含むすべてのルート キーの失効を制御します。 顧客キーは、規制要件の出口計画の側面を制御します。 データを削除してサービスを終了するためにキーを取り消す場合、データ削除プロセスが完了すると、サービスは可用性キーを削除します。 これは、個々のメールボックスに割り当てられている顧客キー DEP でサポートされます。

Microsoft 365削除パスを監査および検証します。 詳細については、「SSAE 18 SOC 2 Report available on the [Service Trust Portal」を参照してください](https://servicetrust.microsoft.com/)。 さらに、Microsoft では次のドキュメントを推奨しています。

- [Microsoft Cloud の金融機関のリスク評価とコンプライアンス ガイド](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [O365 Exit Planning に関する考慮事項](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

複数ワークロード DEP の削除は、顧客キーのMicrosoft 365サポートされていません。 マルチワークロード DEP は、すべてのテナント ユーザーで複数のワークロード間でデータを暗号化するために使用されます。 このような DEP を削除すると、複数のワークロード間のデータにアクセスできなくなります。 サービスを完全に終了Microsoft 365場合は、文書化されたプロセスごとにテナントの削除のパスを追求できます。 「[テナントを削除する方法」を参照Azure Active Directory。](/azure/active-directory/enterprise-users/directory-delete-howto)

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>顧客キーとユーザーキーの可用性キーをExchange Online Skype for Business

データ の削除パスを開始Exchange Online、Skype for Business DEP に永続的なデータ削除要求を設定します。 これにより、DEP が割り当てられているメールボックス内の暗号化されたデータが完全に削除されます。

PowerShell コマンドレットは一度に 1 つの DEP に対してしか実行できないので、データ削除パスを開始する前に、1 つの DEP をすべてのメールボックスに再割り当てする方法を検討してください。

> [!WARNING]
> データ削除パスを使用して、メールボックスのサブセットを削除しない。 このプロセスは、サービスを終了する顧客のみを対象とします。

データ削除パスを開始するには、次の手順を実行します。

1. Azure Key Vaults から "O365 Exchange Online" のラップとアンラップのアクセス許可を削除します。

2. 組織でグローバル管理者特権を持つ仕事または学校のアカウントを使用して[、PowerShell Exchange Online接続します](/powershell/exchange/connect-to-exchange-online-powershell)。

3. 削除するメールボックスを含む DEP ごとに、次のように [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) コマンドレットを実行します。

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   コマンドが失敗した場合は、このタスクで前に指定したように、Azure Key Vault のExchange Onlineのアクセス許可を削除してください。Set-DataEncryptionPolicy コマンドレットを使用して PermanentDataPurgeRequested スイッチを設定すると、この DEP をメールボックスに割り当てなくなりました。

4. Microsoft のサポートに問い合わせ、データ削除 eDocument を要求します。

    Microsoft は、要求に応じて、データの削除を承認および承認する法的文書を送信します。 オンボーディング中に承認者としてFastTrack組織内のユーザーは、このドキュメントに署名する必要があります。 通常、これは会社の役員または他の指定された人物で、組織に代わって書類に署名する法的権限を持ちます。

5. 代理人が法的文書に署名したら、それを Microsoft に返します (通常は eDoc 署名を通じて)。

    Microsoft が法的文書を受け取った後、Microsoft はコマンドレットを実行してデータ削除をトリガーし、最初にポリシーを削除し、メールボックスに完全な削除のマークを付け、可用性キーを削除します。 データの削除プロセスが完了すると、データは削除され、Exchange Onlineにアクセスできなくなり、回復できません。

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>お客様の顧客キーとオンライン、SharePoint、OneDrive for BusinessファイルTeams取り消す

Online、SharePoint、および OneDrive for BusinessファイルTeams削除パスを開始するには、次の手順を実行します。

1. Azure Key Vault アクセスを取り消します。 すべてのキー コンテナー管理者は、アクセスを取り消すことに同意する必要があります。

   オンラインの Azure Key Vault はSharePointされません。 キー コンテナーは、複数のオンライン テナントSharePoint DEP 間で共有できます。

2. 可用性キーを削除するには、Microsoft にお問い合わせください。

    可用性キーを削除するために Microsoft に連絡すると、法的文書が送信されます。 オンボーディング中に承認者としてFastTrack組織内のユーザーは、このドキュメントに署名する必要があります。 通常、これは会社の役員または他の指定された人物で、組織に代わって書類に署名する法的権限を持ちます。

3. 代理人が法的文書に署名したら、それを Microsoft に返します (通常は eDoc 署名を通じて)。

   Microsoft が法的文書を受け取った後、コマンドレットを実行して、テナント キー、サイト キー、およびドキュメントごとの個々のキーの暗号化削除を実行するデータ削除をトリガーし、キー階層を取り消し可能に壊します。 データ削除コマンドレットが完了すると、データは削除されます。

## <a name="related-articles"></a>関連記事

- [カスタマー キーによるサービスの暗号化](customer-key-overview.md)

- [可用性キーの詳細](customer-key-availability-key-understand.md)

- [顧客キーの設定](customer-key-set-up.md)

- [カスタマー キーまたは可用性キーをローリングまたはローテーションする](customer-key-availability-key-roll.md)

- [カスタマー ロックボックス](customer-lockbox-requests.md)

- [サービスの暗号化](office-365-service-encryption.md)
