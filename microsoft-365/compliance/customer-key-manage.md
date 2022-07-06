---
title: カスタマー キーを管理する
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: カスタマー キーを設定したら、AKV キーを復元し、アクセス許可を管理し、データ暗号化ポリシーを作成して割り当てることで、それを管理する方法について説明します。
ms.openlocfilehash: d9f9e992b78b673df08d0c0d5b12ba09cfa9ea84
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66637331"
---
# <a name="manage-customer-key"></a>カスタマー キーを管理する

カスタマー キーを設定したら、1 つ以上のデータ暗号化ポリシー (DEP) を作成して割り当てる必要があります。 DEP を割り当てたら、この記事で説明されているようにキーを管理できます。 カスタマー キーの詳細については、関連トピックを参照してください。

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a>すべてのテナント ユーザーに対して複数のワークロードで使用する DEP を作成する

開始する前に、カスタマー キーの設定に必要なタスクが完了していることを確認します。 詳細については、「 [顧客キーの設定](customer-key-set-up.md)」を参照してください。 DEP を作成するには、セットアップ中に取得したKey Vault URI が必要です。 詳細については、「[各 Azure Key Vault キーの URI を取得する](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)」を参照してください。

マルチワークロード DEP を作成するには、次の手順に従います。

1. ローカル コンピューターで、組織内のグローバル管理者またはコンプライアンス管理者のアクセス許可を持つ職場または学校アカウントを使用[して、Exchange Online PowerShell に接続](/powershell/exchange/connect-to-exchange-online-powershell)します。

2. DEP を作成するには、New-M365DataAtRestEncryptionPolicy コマンドレットを使用します。

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   ここで、

   - *PolicyName* は、ポリシーに使用する名前です。 名前にスペースを含めることはできません。 たとえば、Contoso_Global。

   - *KeyVaultURI1* は、ポリシーの最初のキーの URI です。 たとえば、「 <https://contosoWestUSvault1.vault.azure.net/keys/Key_01> 」のように入力します。

   - *KeyVaultURI2* は、ポリシー内の 2 番目のキーの URI です。 たとえば、「 <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02> 」のように入力します。 2 つの URI をコンマとスペースで区切ります。

   - *ポリシーの説明* は、ポリシーの目的を思い出すのに役立つ、ポリシーのわかりやすい説明です。 説明にはスペースを含めることができます。 たとえば、"テナント内のすべてのユーザーに対する複数のワークロードのルート ポリシー"。

例:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a>複数ワークロード ポリシーを割り当てる

Set-M365DataAtRestEncryptionPolicyAssignment コマンドレットを使用して DEP を割り当てます。 ポリシーを割り当てると、Microsoft 365 は DEP で識別されたキーを使用してデータを暗号化します。

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 ここで *、PolicyName* はポリシーの名前です。 たとえば、Contoso_Global。

例:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a>Exchange Online メールボックスで使用する DEP を作成する

開始する前に、Azure Key Vaultの設定に必要なタスクが完了していることを確認します。 詳細については、「 [顧客キーの設定](customer-key-set-up.md)」を参照してください。 次の手順は、PowerShell Exchange Onlineで完了します。

DEP は、Azure Key Vaultに格納されている一連のキーに関連付けられます。 Microsoft 365 のメールボックスに DEP を割り当てます。 その後、Microsoft 365 はポリシーで識別されたキーを使用してメールボックスを暗号化します。 DEP を作成するには、セットアップ中に取得したKey Vault URI が必要です。 詳細については、「[各 Azure Key Vault キーの URI を取得する](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)」を参照してください。

覚えて！ DEP を作成するときは、2 つの異なる Azure Key Vault に 2 つのキーを指定します。 geo 冗長性を確保するために、これらのキーを 2 つの別々の Azure リージョンに作成します。

メールボックスで使用する DEP を作成するには、次の手順に従います。

1. ローカル コンピューターで、組織内のグローバル管理者またはExchange Online管理者アクセス許可を持つ職場または学校アカウントを使用[して、powerShell Exchange Onlineに接続します](/powershell/exchange/connect-to-exchange-online-powershell)。

2. DEP を作成するには、次のコマンドを入力して、New-DataEncryptionPolicy コマンドレットを使用します。

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   ここで、

   - *PolicyName* は、ポリシーに使用する名前です。 名前にスペースを含めることはできません。 たとえば、USA_mailboxes。

   - *ポリシーの説明* は、ポリシーの目的を思い出すのに役立つ、ポリシーのわかりやすい説明です。 説明にはスペースを含めることができます。 たとえば、"米国とその地域のメールボックスのルート キー" などです。

   - *KeyVaultURI1* は、ポリシーの最初のキーの URI です。 たとえば、「 <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01> 」のように入力します。

   - *KeyVaultURI2* は、ポリシー内の 2 番目のキーの URI です。 たとえば、「 <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02> 」のように入力します。 2 つの URI をコンマとスペースで区切ります。

   例:

   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

構文とパラメーターの詳細については、「 [New-DataEncryptionPolicy](/powershell/module/exchange/new-dataencryptionpolicy)」を参照してください。

### <a name="assign-a-dep-to-a-mailbox"></a>メールボックスに DEP を割り当てる

Set-Mailbox コマンドレットを使用して、DEP をメールボックスに割り当てます。 ポリシーを割り当てると、Microsoft 365 は DEP で識別されたキーを使用してメールボックスを暗号化できます。

```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

ここで *、MailboxIdParameter は* ユーザー メールボックスを指定します。 Set-Mailbox コマンドレットの詳細については、「 [Set-Mailbox](/powershell/module/exchange/set-mailbox)」を参照してください。

ハイブリッド環境では、Exchange Online テナントに同期されるオンプレミスのメールボックス データに DEP を割り当てることができます。 この同期されたメールボックス データに DEP を割り当てるには、Set-MailUser コマンドレットを使用します。 ハイブリッド環境のメールボックス データの詳細については、ハイブリッド [モダン認証を使用した Outlook for iOS と Android を使用したオンプレミスのメールボックス](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)に関するページを参照してください。

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

ここで *、MailUserIdParameter* はメール ユーザー (メールが有効なユーザーとも呼ばれます) を指定します。 Set-MailUser コマンドレットの詳細については、「 [Set-MailUser](/powershell/module/exchange/set-mailuser)」を参照してください。

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online、OneDrive for Business、Teams ファイルで使用する DEP を作成する

開始する前に、Azure Key Vaultの設定に必要なタスクが完了していることを確認します。 詳細については、「 [顧客キーの設定](customer-key-set-up.md)」を参照してください。

SharePoint Online、OneDrive for Business、Teams ファイルの顧客キーを設定するには、SharePoint Online PowerShell で次の手順を実行します。

DEP は、Azure Key Vaultに格納されている一連のキーに関連付けます。 1 つの地理的な場所 (geo とも呼ばれる) 内のすべてのデータに DEP を適用します。 Office 365の複数地域機能を使用する場合は、geo ごとに異なるキーを使用する機能を使用して、geo ごとに 1 つの DEP を作成できます。 複数地域を使用していない場合は、SharePoint Online、OneDrive for Business、Teams ファイルで使用する DEP を組織内に 1 つ作成できます。 Microsoft 365 では、DEP で識別されたキーを使用して、その geo 内のデータを暗号化します。 DEP を作成するには、セットアップ中に取得したKey Vault URI が必要です。 詳細については、「[各 Azure Key Vault キーの URI を取得する](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)」を参照してください。

覚えて！ DEP を作成するときは、2 つの異なる Azure Key Vault に 2 つのキーを指定します。 geo 冗長性を確保するために、これらのキーを 2 つの別々の Azure リージョンに作成します。

DEP を作成するには、SharePoint Online PowerShell を使用する必要があります。

1. ローカル コンピューターで、組織内のグローバル管理者アクセス許可を持つ職場または学校アカウントを使用 [して、SharePoint Online PowerShell に接続します](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)。

2. Microsoft Office SharePoint Online管理シェルで、次のようにRegister-SPODataEncryptionPolicyコマンドレットを実行します。

   ```powershell
   Register-SPODataEncryptionPolicy -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   例:

   ```powershell
   Register-SPODataEncryptionPolicy -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a'
   ```

   DEP を登録すると、geo 内のデータで暗号化が開始されます。 暗号化には時間がかかる場合があります。 このパラメーターの使用の詳細については、「 [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps)」を参照してください。

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a>Exchange Online メールボックス用に作成した DEP を表示する

メールボックス用に作成したすべての DEP の一覧を表示するには、Get-DataEncryptionPolicy PowerShell コマンドレットを使用します。

1. 組織内のグローバル管理者アクセス許可を持つ職場または学校アカウントを使用[して、powerShell Exchange Onlineに接続します](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 組織内のすべての DEP を返すには、パラメーターを指定せずにGet-DataEncryptionPolicyコマンドレットを実行します。

   ```powershell
   Get-DataEncryptionPolicy
   ```

   Get-DataEncryptionPolicy コマンドレットの詳細については、「 [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy)」を参照してください。

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>メールボックスをクラウドに移行する前に DEP を割り当てる

DEP を割り当てると、Microsoft 365 は移行中に割り当てられた DEP を使用してメールボックスの内容を暗号化します。 このプロセスは、メールボックスを移行し、DEP を割り当て、暗号化が行われるのを待つよりも効率的です。これには数時間または数日かかる場合があります。

Office 365に移行する前にメールボックスに DEP を割り当てるには、powerShell でSet-MailUser コマンドレットExchange Online実行します。

1. 組織内のグローバル管理者アクセス許可を持つ職場または学校アカウントを使用[して、powerShell Exchange Onlineに接続します](/powershell/exchange/connect-to-exchange-online-powershell)。

2. Set-MailUser コマンドレットを実行します。

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   *GeneralMailboxOrMailUserIdParameter* はメールボックスを指定し、*DataEncryptionPolicyIdParameter* は DEP の ID です。 Set-MailUser コマンドレットの詳細については、「 [Set-MailUser](/powershell/module/exchange/set-mailuser)」を参照してください。

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>メールボックスに割り当てられている DEP を決定する

メールボックスに割り当てられている DEP を確認するには、Get-MailboxStatistics コマンドレットを使用します。 コマンドレットは一意の識別子 (GUID) を返します。

1. 組織内のグローバル管理者アクセス許可を持つ職場または学校アカウントを使用[して、powerShell Exchange Onlineに接続します](/powershell/exchange/connect-to-exchange-online-powershell)。

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   *GeneralMailboxOrMailUserIdParameter* はメールボックスを指定し、DataEncryptionPolicyID は DEP の GUID を返します。 Get-MailboxStatistics コマンドレットの詳細については、「 [Get-MailboxStatistics」を](/powershell/module/exchange/get-mailboxstatistics)参照してください。

2. Get-DataEncryptionPolicy コマンドレットを実行して、メールボックスが割り当てられている DEP のフレンドリ名を確認します。

   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   *GUID* は、前の手順でGet-MailboxStatistics コマンドレットによって返される GUID です。

## <a name="verify-that-customer-key-has-finished-encryption"></a>カスタマー キーの暗号化が完了したことを確認する

カスタマー キーのロール、新しい DEP の割り当て、メールボックスの移行のいずれであっても、このセクションの手順を使用して暗号化が完了していることを確認します。

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a>Exchange Online メールボックスの暗号化が完了していることを確認する

メールボックスの暗号化には時間がかかる場合があります。 初めて暗号化を行うには、サービスがメールボックスを暗号化する前に、メールボックスをデータベース間で完全に移動する必要もあります。

Get-MailboxStatistics コマンドレットを使用して、メールボックスが暗号化されているかどうかを確認します。

```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

IsEncrypted プロパティは、メールボックスが暗号化されている場合は **true** 、メールボックスが暗号化されていない場合は **false** の値を返します。 メールボックスの移動を完了する時間は、初めて DEP を割り当てるメールボックスの数とメールボックスのサイズによって異なります。 DEP を割り当てた 1 週間後にメールボックスが暗号化されていない場合は、Microsoft にお問い合わせください。

New-MoveRequest コマンドレットは、ローカル メールボックスの移動では使用できなくなりました。 詳細については、 [このお知らせ](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) を参照してください。

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online、OneDrive for Business、Teams ファイルの暗号化が完了していることを確認する

次のようにGet-SPODataEncryptionPolicyコマンドレットを実行して、暗号化の状態を確認します。

```PowerShell
   Get-SPODataEncryptionPolicy <SPOAdminSiteUrl>
```

このコマンドレットからの出力には、次のものが含まれます。

- 主キーの URI。

- セカンダリ キーの URI。

- geo の暗号化状態。 可能性のある状態は次のとおりです

  - **未登録：** カスタマー キーの暗号化はまだ適用されていません。

  - **登録：** カスタマー キーの暗号化が適用され、ファイルは暗号化中です。 geo のキーが登録されている場合は、暗号化の進行状況を監視できるように、geo 内のどの割合のサイトが完了しているかに関する情報も表示されます。

  - **登録：** カスタマー キーの暗号化が適用され、すべてのサイト内のすべてのファイルが暗号化されています。

  - **圧延：** キー ロールが進行中です。 geo のキーがローリングされている場合は、進行状況を監視できるように、キー ロール操作を完了したサイトの割合に関する情報も表示されます。

- また、オンボードされたサイトの割合も出力されます。

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a>複数のワークロードで使用する DEP の詳細を取得する

複数のワークロードで使用するために作成したすべての DEP の詳細を取得するには、次の手順を実行します。

1. ローカル コンピューターで、組織内のグローバル管理者またはコンプライアンス管理者のアクセス許可を持つ職場または学校アカウントを使用[して、Exchange Online PowerShell に接続](/powershell/exchange/connect-to-exchange-online-powershell)します。

   - 組織内のすべてのマルチワークロード DEP の一覧を返すには、このコマンドを実行します。

     ```powershell
     Get-M365DataAtRestEncryptionPolicy
     ```

   - 特定の DEP に関する詳細を返すには、このコマンドを実行します。 この例では、"Contoso_Global" という名前の DEP の詳細情報を返します。

     ```powershell
     Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a>マルチワークロード DEP の割り当て情報を取得する

テナントに現在割り当てられている DEP を確認するには、次の手順に従います。

1. ローカル コンピューターで、組織内のグローバル管理者またはコンプライアンス管理者のアクセス許可を持つ職場または学校アカウントを使用[して、Exchange Online PowerShell に接続](/powershell/exchange/connect-to-exchange-online-powershell)します。

2. このコマンドを入力します。

   ```powershell
   Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a>マルチワークロード DEP を無効にする

マルチワークロード DEP を無効にする前に、テナント内のワークロードから DEP の割り当てを解除します。 複数のワークロードで使用される DEP を無効にするには、次の手順を実行します。

1. ローカル コンピューターで、組織内のグローバル管理者またはコンプライアンス管理者のアクセス許可を持つ職場または学校アカウントを使用[して、Exchange Online PowerShell に接続](/powershell/exchange/connect-to-exchange-online-powershell)します。

2. Set-M365DataAtRestEncryptionPolicy コマンドレットを実行します。

   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

*ここで、PolicyName* はポリシーの名前または一意の ID です。 たとえば、Contoso_Global。

例:

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a>Azure Key Vault キーを復元する

復元を実行する前に、論理的な削除によって提供される回復機能を使用します。 カスタマー キーで使用されるすべてのキーは、論理的な削除を有効にする必要があります。 論理的な削除はごみ箱のように機能し、復元する必要なく最大 90 日間回復できます。 復元は、キーまたはキー コンテナーが失われた場合など、極端な状況や異常な状況でのみ必要です。 Customer Key で使用するためにキーを復元する必要がある場合は、Azure PowerShellで、次のようにRestore-AzureKeyVaultKeyコマンドレットを実行します。

```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

例:

```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

キー コンテナーに同じ名前のキーが既に含まれている場合、復元操作は失敗します。 Restore-AzKeyVaultKeyキーのバージョンと、キー名を含むキーのすべてのメタデータを復元します。

## <a name="manage-key-vault-permissions"></a>キー コンテナーのアクセス許可を管理する

キー コンテナーのアクセス許可を表示し、必要に応じて削除できるコマンドレットがいくつかあります。 たとえば、従業員がチームを離れた場合など、アクセス許可を削除することが必要になる場合があります。 これらのタスクごとに、Azure PowerShellを使用します。 Azure PowerShellの詳細については、「[Azure PowerShellの概要](/powershell/azure/)」を参照してください。

キー コンテナーのアクセス許可を表示するには、Get-AzKeyVault コマンドレットを実行します。

```powershell
Get-AzKeyVault -VaultName <vault name>
```

例:

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

管理者のアクセス許可を削除するには、Remove-AzKeyVaultAccessPolicy コマンドレットを実行します。

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

例:

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a>カスタマー キーから Microsoft マネージド キーにロールバックする

Microsoft マネージド キーに戻す必要がある場合は、次の操作を行うことができます。 オフボードすると、個々のワークロードでサポートされている既定の暗号化を使用してデータが再暗号化されます。 たとえば、Exchange Onlineでは、Microsoft マネージド キーを使用した既定の暗号化がサポートされます。

> [!IMPORTANT]
> オフボーディングはデータ消去と同じではありません。 データ消去では、Microsoft 365 から組織のデータが完全に暗号化削除されます。オフボードでは削除されません。 複数のワークロード ポリシーに対してデータ消去を実行することはできません。

**マルチワークロード DEP の割り当てにカスタマー キーを使用しない場合は、Microsoft 管理ポータルを使用してサポート チケットを提出し、要求に次の詳細を入力する必要があります。**

1. テナント FQDN
2. オフボード要求のテナント連絡先
3. オフボードの理由
4. 要求を M365 Customer Key チームに送信し、インシデントを含める必要があるメモをサービス チケットに含める#

Microsoft マネージド キーを使用してデータを再ラップするための適切なアクセス許可を持つカスタマー キーの AKVs と暗号化キーを保持する必要があります。 ご質問がある場合は、m365-ck@service.microsoft.com にお問い合わせください。

メールボックス レベルの DEP を使用して個々のメールボックスを暗号化しなくなった場合は、すべてのメールボックスからメールボックス レベルの DEP を割り当て解除できます。

メールボックス DEP の割り当てを解除するには、Set-Mailbox PowerShell コマンドレットを使用します。

1. 組織内のグローバル管理者アクセス許可を持つ職場または学校アカウントを使用[して、powerShell Exchange Onlineに接続します](/powershell/exchange/connect-to-exchange-online-powershell)。

2. Set-Mailbox コマンドレットを実行します。

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $null
   ```

このコマンドレットを実行すると、現在割り当てられている DEP の割り当てが解除され、既定の Microsoft マネージド キーに関連付けられている DEP を使用してメールボックスが再暗号化されます。 Microsoft マネージド キーで使用されている DEP の割り当てを解除することはできません。 Microsoft マネージド キーを使用しない場合は、別のカスタマー キー DEP をメールボックスに割り当てることができます。

> [!IMPORTANT]
> SharePoint Online、OneDrive for Business、Teams ファイルでは、カスタマー キーから Microsoft マネージド キーへのロールバックはサポートされていません。

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>キーを取り消し、データ消去パス プロセスを開始する

可用性キーを含むすべてのルート キーの失効を制御します。 顧客キーは、規制要件の終了計画の側面を制御します。 データを消去してサービスを終了するためにキーを取り消す場合、データ消去プロセスが完了すると、サービスは可用性キーを削除します。 これは、個々のメールボックスに割り当てられている Customer Key DEP でサポートされています。

Microsoft 365 は、データ消去パスを監査して検証します。 詳細については、 [Service Trust Portal](https://servicetrust.microsoft.com/) で入手できる SSAE 18 SOC 2 レポートを参照してください。 さらに、Microsoft では次のドキュメントをお勧めします。

- [Microsoft Cloud の金融機関向けのリスク評価とコンプライアンス ガイド](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [O365 Exit Planning に関する考慮事項](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

マルチワークロード DEP の削除は、Customer Key ではサポートされていません。 マルチワークロード DEP は、すべてのテナント ユーザー間で複数のワークロード間でデータを暗号化するために使用されます。 このような DEP を削除すると、複数のワークロード間のデータにアクセスできなくなります。 Microsoft 365 サービスを完全に終了することにした場合は、文書化されたプロセスごとにテナントの削除のパスを追及できます。 [Azure Active Directory でテナントを削除する方法について説明します](/azure/active-directory/enterprise-users/directory-delete-howto)。

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>カスタマー キーと、Exchange OnlineとSkype for Businessの可用性キーを取り消す

Exchange OnlineとSkype for Businessのデータ消去パスを開始すると、DEP に永続的なデータ消去要求が設定されます。 これにより、DEP が割り当てられているメールボックス内の暗号化されたデータが完全に削除されます。

PowerShell コマンドレットは一度に 1 つの DEP に対してのみ実行できるため、データ消去パスを開始する前に、1 つの DEP をすべてのメールボックスに再割り当てすることを検討してください。

> [!WARNING]
> メールボックスのサブセットを削除するには、データ消去パスを使用しないでください。 このプロセスは、サービスを終了する顧客のみを対象としています。

データ消去パスを開始するには、次の手順を実行します。

1. Azure Key Vaults から "O365 Exchange Online" のラップとラップ解除のアクセス許可を削除します。

2. 組織内のグローバル管理者特権を持つ職場または学校アカウントを使用[して、powerShell Exchange Onlineに接続](/powershell/exchange/connect-to-exchange-online-powershell)します。

3. 削除するメールボックスを含む DEP ごとに、次のように [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) コマンドレットを実行します。

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   コマンドが失敗した場合は、このタスクの前に指定したように、Azure Key Vaultの両方のキーからExchange Onlineアクセス許可が削除されていることを確認します。 Set-DataEncryptionPolicy コマンドレットを使用して PermanentDataPurgeRequested スイッチを設定すると、この DEP をメールボックスに割り当てできなくなります。

4. Microsoft サポートに問い合わせ、データ消去 eDocument を要求します。

    お客様の要求に応じて、Microsoft から、データの削除を確認および承認するための法的ドキュメントが送信されます。 オンボード中に FastTrack オファーで承認者としてサインアップした組織内のユーザーは、このドキュメントに署名する必要があります。 通常、これは会社の役員またはその他の指定された人物であり、組織に代わって書類に署名することを法的に承認されています。

5. 代理人が法的文書に署名したら、Microsoft に返します (通常は eDoc 署名を使用)。

    Microsoft が法的文書を受け取ると、Microsoft はコマンドレットを実行して、最初にポリシーを削除するデータ消去をトリガーし、メールボックスに完全な削除をマークしてから、可用性キーを削除します。 データ消去プロセスが完了すると、データは消去され、Exchange Onlineにアクセスできず、回復できません。

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online、OneDrive for Business、Teams ファイルのカスタマー キーと可用性キーを取り消す

SharePoint、職場または学校用の OneDrive、Teams ファイルの DEP の削除は、カスタマー キーではサポートされていません。 これらのマルチワークロード DEP は、すべてのテナント ユーザー間で複数のワークロード間でデータを暗号化するために使用されます。 このような DEP を削除すると、複数のワークロード間のデータにアクセスできなくなります。 Microsoft 365 サービスを完全に終了することにした場合は、文書化されたプロセスごとにテナントの削除のパスを追及できます。 [Azure Active Directory でテナントを削除](/azure/active-directory/enterprise-users/directory-delete-howto)する方法について説明します。

## <a name="related-articles"></a>関連記事

- [Microsoft Purview カスタマー キーを使用したサービスの暗号化](customer-key-overview.md)

- [可用性キーの詳細](customer-key-availability-key-understand.md)

- [カスタマー キーを設定する](customer-key-set-up.md)

- [カスタマー キーまたは可用性キーをローリングまたはローテーションする](customer-key-availability-key-roll.md)

- [カスタマー ロックボックス](customer-lockbox-requests.md)

- [サービス暗号化](office-365-service-encryption.md)
