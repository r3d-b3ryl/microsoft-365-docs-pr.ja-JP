---
title: テナント間でのメールボックスの移行
description: Microsoft 365 または 365 テナント間でOffice移動する方法。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: 09/21/2020
ms.reviewer: georgiah
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: 63eab8c44651bfc2865e9bf6c577c1ebe13381fc
ms.sourcegitcommit: 21b0ea5715e20b4ab13719eb18c97fadb49b563d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49624768"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>テナント間メールボックスの移行 (プレビュー)

以前は、Exchange Online テナントが同じ Exchange Online サービス内の別のテナントにメールボックスを移動する必要がある場合、メールボックスをオンプレミスに完全にオフボードしてから、新しいテナントにオンボードする必要がありました。 新しいテナント間メールボックス移行機能により、移行元テナントと移行先テナントの両方のテナント管理者は、オンプレミス システムで最小限のインフラストラクチャ依存関係を持つテナント間でメールボックスを移動できます。 これにより、メールボックスをオフボードおよびオンボードする必要が削除されます。

一般に、合併または分割時には、ユーザーとコンテンツを新しいテナントに移動する機能が必要です。 ターゲット テナント管理者が移動を実行すると、オンプレミスからクラウド オンボーディングへの移行と同様にプル移動と呼ばれる。

テナント間の Exchange メールボックスの移動はテナント管理者によって完全にセルフサービスされ、ユーザーを新しい組織に移行するために必要な大規模なワークフローにスクリプト化できる既知のインターフェイスを使用します。 管理者は、メールボックスの移動管理役割を介して使用可能なコマンドレットを使用して、テナント間の移動 `New-MigrationBatch` を実行できます。 移動プロセスには、メールボックスの同期中および最終処理時のテナント承認チェックが含まれます。 
 
移行するユーザーは、移行先のテナント Exchange Online システムに MailUsers として存在し、テナント間の移動を有効にする特定の属性でマークされている必要があります。 ターゲット テナントで適切に設定されていないユーザーの移動は、システムによって失敗します。  

移動が完了すると、移動元システムメールボックスが MailUser に変換され、targetAddress (Exchange では ExternalEmailAddress として表示されます) に宛先テナントへのルーティング アドレスがスタンプされます。 このプロセスは、従来の MailUser をソース テナントに残し、一期間の共同存在とメール ルーティングを可能にします。 ビジネス プロセスが許可されている場合、ソース テナントはソース MailUser を削除するか、メール連絡先に変換できます。 

テナント間の Exchange メールボックスの移行は、ハイブリッドまたはクラウドのテナント、またはこの 2 つの組み合わせでのみサポートされます。

この記事では、テナント間のメールボックス移動のプロセスについて説明し、コンテンツ移動のソーステナントとターゲット テナントを準備する方法に関するガイダンスを提供します。  

## <a name="preparing-source-and-target-tenants"></a>ソース テナントとターゲット テナントの準備

テナント間の Exchange メールボックス移行機能では、テナント間の移行に対する承認とスコープが必要です。 Azure Enterprise アプリケーションと Key Vault ストレージ ソリューションを使用して、テナント管理者は、あるテナントから別のテナントへの Exchange Online メールボックス移行の承認とスコープの両方を管理できます。 テナント間のメールボックス移動は、テナントペア間の認証に使用される Azure Active Directory (Azure AD) アプリケーションを確立するための招待と同意モデルをサポートしています。 組織上の関係や移行エンドポイントなどの追加コンポーネントも必要です。

このセクションには、ターゲット ディレクトリ内の MailUser ユーザー オブジェクトを準備するために必要な具体的な手順は含まれていますが、移行バッチを送信するサンプル コマンドも含めもありません。 この情報については [、「移行先のユーザー オブジェクトを準備する」](#prepare-target-user-objects-for-migration) を参照してください。

## <a name="prerequisites"></a>前提条件

テナント間のメールボックス移動機能では [、Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) がテナント ペア固有の Azure アプリケーションを確立して、あるテナントから別のテナントへのメールボックスの移行を認証および承認するために使用される証明書/シークレットを安全に保存してアクセスする必要があります。テナント間で証明書/シークレットを共有するための要件は削除されます。 

開始する前に、Azure Key Vault、メールボックス アプリケーションの移動、EXO 移行エンドポイント、EXO 組織の関係を構成するために、展開スクリプトを実行するために必要なアクセス許可を持っている必要があります。 通常、グローバル管理者には、すべての構成手順を実行する権限があります。

さらに、セットアップを実行する前に、ソース テナントのメールが有効なセキュリティ グループが必要です。 これらのグループは、移行元 (またはリソースと呼ばれる場合があります) テナントからターゲット テナントに移動できるメールボックスの一覧の範囲を指定するために使用されます。 これにより、移動元テナント管理者は、移動する必要がある特定のメールボックスセットを制限またはスコープ設定して、意図しないユーザーの移行を防止できます。 入れ子になったグループはサポートされていません。

また、Microsoft 365 テナント ID を取得するには、信頼できるパートナー企業 (メールボックスの移動先) と連絡を取る必要があります。 このテナント ID は、[組織の関係] フィールドで使用 `DomainName` されます。

サブスクリプションのテナント ID を取得するには、Microsoft 365 管理センターにサインインし、次に移動します [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) 。 テナント ID プロパティのコピー アイコンをクリックして、クリップボードにコピーします。

プロセスのしくみを次に示します。

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="メールボックス移行のためのテナントの準備。":::

[このイメージのより大きなバージョンを参照してください](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)。

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a>テナントを準備する

セットアップ スクリプトを実行すると、大きなレベルで次の構成操作が実行されます。

ターゲット テナントを準備します。

1. 既存の Azure リソース グループが指定されていない場合は、新しい Azure リソース グループが作成されます (SCRIPT)。
2. 既存の Key Vault が指定されていない場合は、新しいキー コンテナーが作成されます (SCRIPT)。
3. 新しいアクセス ポリシーが、Office 365 Exchange Online メールボックス移行アプリケーション (SCRIPT) 用に作成されます。
4. シークレットを移行アプリケーション (SCRIPT) に保持するために、新しい証明書 (または指定されている場合は既存の証明書) が作成されます。
5. 新しい Azure AD アプリケーションが作成されます (SCRIPT)。
6. 証明書/シークレットが移行アプリケーション (SCRIPT) にアップロードされます。
7. メールボックス移行のアクセス許可は、アプリケーション (SCRIPT) に割り当てられます。
8. 展開スクリプトは、ターゲット管理者が自分のアプリケーション (SCRIPT) に同意するまで一時停止します。
9. ターゲット テナント管理者は、アプリケーションに付与されたアクセス許可に同意します (MANUAL)。
10. 組織上の関係は、ターゲット テナント (SCRIPT) に対して作成されます。
11. 移行エンドポイントが作成され、メールボックスがターゲット テナント (SCRIPT) にプルされます。

ソース テナントを準備します。

1. 移行元テナント管理者は、ターゲット テナントからのメールボックス移行アプリケーションへの招待に同意します (MANUAL)。
2. 移行元テナント管理者は、移行アプリケーション (MANUAL) によって移動が許可されているメールボックスの一覧を含むメールが有効なセキュリティ グループをテナントに作成します。
3. 移動要求 (SCRIPT) を受け入れるには、OAuth 検証にメールボックス移行アプリケーションを使用する必要があるという組織上の関係がターゲット テナントに対して作成されます。

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>ターゲット テナント管理者向けステップ バイ ステップの手順

1. GitHub SetupCrossTenantRelationshipForTargetTenant.ps1、ターゲット テナントのセットアップ用のスクリプトを [ダウンロードします](https://github.com/microsoft/cross-tenant/releases/tag/Preview)。 
2. スクリプト (SetupCrossTenantRelationshipForTargetTenant.ps1) を、スクリプトを実行するコンピューターに保存します。
3. Exchange Online ターゲット テナントへのリモート PowerShell 接続を作成します。 繰り返しますが、Azure Key Vault のストレージと証明書、メールボックス アプリケーションの移動、EXO 移行エンドポイント、EXO 組織の関係を構成するために、展開スクリプトを実行するために必要なアクセス許可を持っている必要があります。
4. ファイル フォルダー ディレクトリをスクリプトの場所に変更するか、スクリプトがリモート PowerShell セッションの現在の場所に保存されているのを確認します。
5. 次のパラメーターと値を使用してスクリプトを実行します。

    | パラメーター | 値 | 必須またはオプション
    |---------------------------------------------|-----------------|--------------|
    | -ResourceTenantDomain                       | ソース テナント ドメイン (fabrikam.onmicrosoft.com など)。 | 必須 |
    | -ResourceTenantAdminEmail                   | ソース テナント管理者のメール アドレス。 これは、移行先の管理者から送信されたメールボックス移行アプリケーションの使用に同意する移行元テナント管理者です。これは、アプリケーションの電子メールの招待を受け取る管理者です。 | 必須 |
    | -TargetTenantDomain                         | ターゲット テナント ドメイン (contoso.onmicrosoft.com など)。 | 必須 |
    | -ResourceTenantId                           | ソース テナント組織 ID (GUID)。 | 必須 |
    | -SubscriptionId                             | リソースの作成に使用する Azure サブスクリプション。 | 必須 |
    | -ResourceGroup                              | Key Vault を含む、または含む Azure リソース グループ名。 | 必須 |
    | -KeyVaultName                               | メールボックス移行アプリケーションの証明書/シークレットを格納する Azure Key Vault インスタンス。 | 必須 |
    | -CertificateName                            | キー コンテナー内の証明書を生成または検索する場合の証明書名。 | 必須 |
    | -CertificateSubject                         | AZURE Key Vault 証明書のサブジェクト名 (CN=contoso_fabrikam など)。 | 必須 |
    | -ExistingApplicationId                      | 既に作成されている場合に使用するメール移行アプリケーション。 | Optional |
    | -AzureAppPermissions                        | Exchange や MSGraph (メールボックスを移動するための Exchange、このアプリケーションを使用してリソース テナントに同意リンクへの招待を送信するための MSGraph) など、メールボックス移行アプリケーションに与える必要があるアクセス許可。 | 必須 |
    | -UseAppAndCertGeneratedForSendingInvitation | 移行元テナント管理者に同意リンクの招待状を送信するために使用する、移行用に作成されたアプリケーションを使用するパラメーター。指定しない場合、ターゲット管理者の資格情報で Azure 招待マネージャーに接続し、ターゲット管理者として招待を送信するように求めるメッセージが表示されます。 | Optional |
    | -KeyVaultAuditStorageAccountName            | Key Vault の監査ログが格納されるストレージ アカウント。 | Optional |
    | -KeyVaultAuditStorageResourceGroup          | Key Vault 監査ログを格納するためのストレージ アカウントを含むリソース グループ。 | Optional |
    ||||

    >[!Note]
    > スクリプトを実行する前に、Azure AD PowerShell モジュールがインストールされていることを確認してください。 インストール手順については ![ 、 ](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-5.1.0) こちらを参照してください。

6. スクリプトは一時停止し、このプロセス中に作成された Exchange メールボックス移行アプリケーションに同意するか、同意を求めるメッセージが表示されます。 次に例を示します。

    ```powershell
    PS C:\PowerShell\> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

    cmdlet Get-Credential at command pipeline position 1
    Supply values for the following parameters:
    Credential
    Setting up key vault in the fabrikam.onmicrosoft.com tenant

    Name                                     Account                                 SubscriptionName                        Environment                             TenantId
        ----                                     -------                                 ----------------                        -----------                             --------
    Pay-As-You-Go (ewe23423-a3327-34232-343... Admin@fabrikam... Pay-As-You-Go                           AzureCloud                              dsad938432-dd8e-s9034-bf9a-83984293n43
    Auditing setup successfully for Cross-TenantMovesVault
    Exchange application given access to KeyVault Cross-TenantMovesVault
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - Directory.ReadWrite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ```  

7. URL はリモート PowerShell セッションに表示されます。 テナントの同意のために提供されたリンクをコピーし、Web ブラウザーに貼り付けます。

8. グローバル管理者の資格情報でサインインします。 次の画面が表示された場合は、[承諾] を選択 **します**。

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="[アクセス許可を受け入れる] ダイアログ ボックス":::

9. リモート PowerShell セッションに戻り、Enter キーを押して続行します。

10. スクリプトは、残りのセットアップ オブジェクトを構成します。 次に例を示します。

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

ターゲット管理者のセットアップが完了しました。

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>ソース テナント管理者の詳しい手順

1.  セットアップ中に、ターゲット管理者によって指定された -ResourceTenantAdminEmail としてメールボックスにサインインします。 ターゲット テナントからメールへの招待を検索し、[開始] ボタン **を選択** します。

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="招待されたダイアログ ボックス":::

2. [承諾 **] を選択** して招待を承諾します。

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="アクセス許可を受け入れるダイアログ ボックス":::

   > [!NOTE]
   > このメールが届かできない場合、または見つからない場合は、ターゲットテナント管理者に直接 URL が提供されます。この URL を指定すると、招待を承諾できます。 URL は、ターゲット テナント管理者のリモート PowerShell セッションのトランスクリプト内に含む必要があります。

3. Microsoft 365 管理センターまたはリモート PowerShell セッションで、1 つ以上のメールが有効なセキュリティ グループを作成し、移動元テナントからターゲット テナントに移動 (プル) するためにターゲット テナントが許可するメールボックスの一覧を制御します。 このグループを事前に設定する必要はありますが、セットアップ手順 (スクリプト) を実行するには、少なくとも 1 つのグループを指定する必要があります。 ネスト グループはサポートされていません。 

4. GitHub リポジトリSetupCrossTenantRelationshipForTargetResource.ps1ソース テナントのセットアップ用の次のスクリプトをダウンロードします [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) 。 

5. Exchange 管理者のアクセス許可を使用して、ソース テナントへのリモート PowerShell 接続を作成します。 Azure アプリケーションの作成プロセスのため、グローバル管理者のアクセス許可はソース テナントを構成する必要はありません。ターゲット テナントのみを構成します。

6. ディレクトリをスクリプトの場所に変更するか、スクリプトがリモート PowerShell セッションの現在の場所に保存されているのを確認します。

7. 次の必須パラメーターと値を使用してスクリプトを実行します。

    | パラメーター | 値 |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | 移行対象の ID/メールボックスのソース テナントによって作成された、メールが有効なセキュリティ グループ。 |
    | -ResourceTenantDomain | ソース テナントドメイン名 (fabrikam.onmicrosoft.com など)。 |
    | -TargetTenantDomain | ターゲット テナントのドメイン名 (contoso.onmicrosoft.com など)。 |
    | -ApplicationId | 移行に使用されるアプリケーションの Azure アプリケーション ID (GUID)。 Azure portal (Azure AD、エンタープライズ アプリケーション、アプリ名、アプリケーション ID) 経由で利用できるアプリケーション ID、または招待メールに含まれているアプリケーション ID。  |
    | -TargetTenantId | ターゲット テナントのテナント ID。 たとえば、Azure ADテナントのテナント ID contoso.onmicrosoft.comします。 |
    |||

    次に例を示します。
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

これで、ソース管理者のセットアップが完了しました。

### <a name="verify-setup"></a>セットアップを確認する

移行元テナントと移行先テナントの両方の組織上の関係と、ターゲット内の移行エンドポイントが正常に作成されたことを確認します。

#### <a name="target-tenant"></a>ターゲット テナント

**組織の関係**

組織の関係オブジェクトが作成され、このコマンドで構成されていることを確認します。

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
次に例を示します：

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

**移行エンドポイント**

移行エンドポイント オブジェクトが作成され、このコマンドで構成されていることを確認します。

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

次に例を示します。

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a>ソース テナント

**組織の関係**

組織の関係オブジェクトが作成され、このコマンドで構成されていることを確認します。

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

次に例を示します。

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a>メールボックスを元のソースに戻す

メールボックスを元のソース テナントに戻す必要がある場合は、新しい移行元テナントと新しいターゲット テナントの両方で同じ手順とスクリプトを実行する必要があります。 既存の Organization Relationship オブジェクトは更新または追加され、再作成されません。

## <a name="prepare-target-user-objects-for-migration"></a>移行のターゲット ユーザー オブジェクトを準備する

テナント間の移動を有効にするには、移行先のテナントと Exchange Online システム (MailUsers として) に特定の属性がマークされている必要があります。 ターゲット テナントで適切に設定されていないユーザーの移動は、システムによって失敗します。 次のセクションでは、ターゲット テナントの MailUser オブジェクトの要件について詳しい説明を示します。

### <a name="prerequisites"></a>前提条件
  
次のオブジェクトと属性がターゲット組織で設定されている必要があります。  

1. 移動元の組織から移動するメールボックスの場合は、移動先の組織で MailUser オブジェクトを準備する必要があります。 
   - 移動先 MailUser には、移動元のメールボックスから次の属性を設定するか、新しいユーザー オブジェクトで割り当てる必要があります。
      - ExchangeGUID (ソースからターゲットへの直接フロー) – メールボックス GUID が一致している必要があります。 移動先オブジェクトに存在しない場合、移動プロセスは続行できません。 
      - ArchiveGUID (ソースからターゲットへの直接フロー) – アーカイブ GUID は一致する必要があります。 移動先オブジェクトに存在しない場合、移動プロセスは続行できません。 (これは、移動元メールボックスがアーカイブが有効な場合にのみ必要です)。 
      - LegacyExchangeDN (proxyAddress としてフロー"x500: <LegacyExchangeDN> ") – LegacyExchangeDN は、ターゲット MailUser に x500: proxyAddress として存在する必要があります。 移動先オブジェクトに存在しない場合、移動プロセスは続行できません。 
      - UserPrincipalName – UPN は、ユーザーの新しい ID または対象の会社 (たとえば、user@northwindtraders.onmicrosoft.com)。 
      - プライマリ SMTPAddress – プライマリ SMTP アドレスは、ユーザーの新しい会社に合わせて調整されます (たとえば、user@northwind.com)。 
      - TargetAddress/ExternalEmailAddress – MailUser は、ソース テナントでホストされているユーザーの現在のメールボックスを参照します (例: user@contoso.onmicrosoft.com)。 この値を割り当てる場合は、PrimarySMTPAddress を割り当て中または割り当て中か、この値によって PrimarySMTPAddress が設定され、移動エラーが発生する可能性があります。 
      - ソース メールボックスから移動先 MailUser に従来の smtp プロキシ アドレスを追加することはできません。 たとえば、テナント オブジェクトcontoso.com MEU に対するfabrikam.onmicrosoft.comを維持することはできません。 ドメインは、1 つの Azure ADまたは Exchange Online テナントにのみ関連付けられている。
 
    ターゲット MailUser オブジェクトの例:
 
    | 属性             | 値                                                                                                                    |
    |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
    | エイリアス                 | Laran                                                                                                                    |
    | RecipientType         | MailUser                                                                                                                 |
    | RecipientTypeDetails  | MailUser                                                                                                                 |
    | UserPrincipalName     | LaraN@northwintraders.onmicrosoft.com                                                                                    |
    | PrimarySmtpAddress    | Lara.Newton@northwind.com                                                                                                |
    | ExternalEmailAddress  | SMTP:LaraN@contoso.onmicrosoft.com                                                                                       |
    | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                     |
    | LegacyExchangeDN      | /o=First Organization/ou=Exchange Administrative Group                                                                   |
    |                       | (FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara                                                  |
    | EmailAddresses        | x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190  |
    |                       | 7273f1f9-Lara                                                                                                            |
    |                       | smtp:LaraN@northwindtraders.onmicrosoft.com                                                                              |
    |                       | SMTP:Lara.Newton@northwind.com                                                                                           |
    |||

   ソース **メールボックス オブジェクト** の例:

   | 属性             | 値                                                                    |
   |-----------------------|--------------------------------------------------------------------------|
   | エイリアス                 | Laran                                                                    |
   | RecipientType         | UserMailbox                                                              |
   | RecipientTypeDetails  | UserMailbox                                                              |
   | UserPrincipalName     | LaraN@contoso.onmicrosoft.com                                            |
   | PrimarySmtpAddress    | Lara.Newton@contoso.com                                                  |
   | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                     |
   | LegacyExchangeDN      | /o=First Organization/ou=Exchange Administrative Group                   |
   |                       | (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  |
   | EmailAddresses        | smtp:LaraN@contoso.onmicrosoft.com 
   |                       | SMTP:Lara.Newton@contoso.com          |
   |||

   - 追加の属性は、既に Exchange ハイブリッド 書き戻しに含まれている可能性があります。 含まれていない場合は、含める必要があります。 
   - msExchBlockedSendersHash – クライアントからオンプレミスの Active Directory にオンラインの安全な送信者データとブロックする差出人データを書き戻します。
   - msExchSafeRecipientsHash – クライアントからオンプレミスの Active Directory にオンラインの安全な送信者データとブロックする差出人データを書き戻します。
   - msExchSafeSendersHash – クライアントからオンプレミスの Active Directory にオンラインの安全な送信者データとブロックする差出人データを書き戻します。

2. 移動元メールボックスが訴訟ホールドの対象であり、移動元メールボックスの回復可能なアイテムのサイズがデータベースの既定値 (30 GB) より大きい場合、移動先のクォータがソース メールボックスのサイズより小さいので、移動は続行されません。 ターゲット MailUser オブジェクトを更新して、ELC メールボックス フラグをソース環境からターゲットに移行できます。これにより、ターゲット システムは MailUser のクォータを 100 GB に拡張し、ターゲットに移動できます。 これらの手順は、Azure AD Connect を実行しているハイブリッド ID でのみ機能します。ELC フラグをスタンプするコマンドはテナント管理者に公開されません。

    >[!Note]
    > サンプル – 現在、保証なし<br/>このスクリプトは、ソース メールボックス (ソース値を取得する) とターゲットのオンプレミス Active Directory (ADUser オブジェクトにスタンプを付け) の両方への接続を前提としています。 ソースで訴訟または単一アイテムの回復が有効になっている場合は、コピー先アカウントでこれを設定します。  これにより、宛先アカウントの削除のサイズが 100 GB に増加します。

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. 非ハイブリッド ターゲット テナントは、次のコマンドを実行して MailUser オブジェクトの訴訟ホールドを有効にし、クォータを 100 GB に増やして、移行前に MailUsers の [回復可能なアイテム] フォルダーのクォータを変更できます。 `Set-MailUser -EnableLitigationHoldForMigration $TRUE` これはハイブリッドのテナントでは機能しません。

4. ターゲット組織のユーザーには、組織に適用可能な適切な Exchange Online サブスクリプションのライセンスが必要です。 メールボックスの移動の前にライセンスを適用できますが、ターゲット MailUser が ExchangeGUID とプロキシ アドレスで適切にセットアップされた後にのみ適用できます。 ExchangeGUID を適用する前にライセンスを適用すると、ターゲット組織で新しいメールボックスがプロビジョニングされます。 

    > [!Note]
    > Mailbox オブジェクトまたは MailUser オブジェクトにライセンスを適用すると、すべての SMTP タイプの proxyAddresses がスクラブされ、確認済みのドメインだけが Exchange EmailAddresses 配列に含まれる必要があります。 

5. 移動先の MailUser に、ソース ExchangeGuid と一致しない以前の ExchangeGuid が存在しない必要があります。 これは、ターゲット MEU が以前に Exchange Online のライセンスを取得し、メールボックスをプロビジョニングした場合に発生する可能性があります。 ターゲット MailUser が以前に ExchangeGuid に対してライセンスを付与されている場合、またはソース ExchangeGuid と一致しない ExchangeGuid を持っていた場合は、クラウド MEU のクリーンアップを実行する必要があります。 これらのクラウド MEUs では、コマンドを実行 `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` できます。  

    > [!Caution]
    > このプロセスは取り返しができません。 オブジェクトに softDeleted メールボックスがある場合、この時点以降は復元できません。 ただし、クリアすると、正しい ExchangeGuid をターゲット オブジェクトに同期できます。MRS は、移動元メールボックスを新しく作成したターゲット メールボックスに接続します。 (新しいパラメーターに関する EHLO ブログを参照してください。  

    このコマンドを使用して、以前メールボックスだったオブジェクトを検索します。

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -a**.
    ```

    次に例を示します。 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    このコマンドを使用して、回復可能な削除によって削除されたメールボックスをクリアします。

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    次に例を示します。

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a>メールボックスの移行を実行する

テナント間の Exchange メールボックスの移行は、移行先のテナントから開始された移行バッチとして送信されます。 これは、オンプレミスの Exchange から Microsoft 365 に移行する場合の移行バッチの動作と似ています。 

### <a name="create-migration-batches"></a>移行バッチを作成する

移動を開始する移行バッチ コマンドレットの例を次に示します。

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> CSV ファイルの電子メール アドレスは、ソース テナントではなく、ターゲット テナントで指定されたアドレスである必要があります。

移行バッチの送信は、テナント間オプションを選択するときに、新しい Exchange 管理センターでもサポートされます。

#### <a name="update-on-premises-mailusers"></a>オンプレミスの MailUsers を更新する

メールボックスがソースからターゲットに移動したら、オンプレミスのメール ユーザー (ソースとターゲットの両方) が新しい targetAddress で更新される必要があります。 例では、移動で使用される targetDeliveryDomain **がcontoso.onmicrosoft.com。** この targetAddress でメール ユーザーを更新します。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**移行後にオンプレミスのソースで RemoteMailboxes を更新する必要がありますか?**

はい。ソース テナント メールボックスがターゲット テナントに移動するときに、ソースのオンプレミス ユーザーの targetAddress (RemoteRoutingAddress/ExternalEmailAddress) を更新する必要があります。  メール ルーティングは、異なる targetAddresses を持つ複数のメール ユーザー間の紹介に従う可能性があります。メール ユーザーの空き時間情報の参照はメールボックス ユーザーの場所をターゲットとする必要があります。 空き時間情報の参照では、複数のリダイレクトを追跡する必要があります。 

**Teams チャット フォルダーのコンテンツはテナント間で移行されますか?**  

いいえ、Teams チャット フォルダーのコンテンツはテナント間を移行されません。  

**オンボーディングとオフボーディングの移動ではなく、テナント間の移動である移動を確認するにはどうすれば良いでしょうか。**

パラメーターを使用 `-flags` します。 次に例を示します。

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

**テストで使用する属性をコピーするためのサンプル スクリプトを提供できますか。**

> [!Note]
> サンプル – 現在、保証なし<br/>このスクリプトは、ソース メールボックス (ソース値を取得する) と、ターゲットのオンプレミスの Active Directory ドメイン サービス (ADUser オブジェクトにスタンプを付け) の両方への接続を前提としています。 ソースで訴訟または単一アイテムの回復が有効になっている場合は、コピー先アカウントでこれを設定します。  これにより、宛先アカウントの削除のサイズが 100 GB に増加します。

```powershell
#Dumps out the test mailboxes from SourceTenant 
#Note, the filter applied on GetMailbox is for an attribute set on CA1 = “ProjectKermit” 
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################  
$outFile = "$home\desktop\UserListToImport.csv" 
$outArray = @() 
#output the test objects 
$Mailboxes = get-mailbox -filter "CustomAttribute1 -like ‘ProjectKermit'" -resultsize unlimited  
#created these mailboxes in adv using separate scripts but you get the idea on how to define the user list to move 
Foreach ($i in $Mailboxes)  
{ 
    $user = get-Recipient $i.alias 
    $myobj = New-Object System.Object 
    $myObj | Add-Member -type NoteProperty -name primarysmtpaddress -value $i.PrimarySMTPAddress 
    $myObj | Add-Member -type NoteProperty -name alias -value $i.alias 
    $myObj | Add-Member -type NoteProperty -name FirstName -value $User.FirstName 
    $myObj | Add-Member -type NoteProperty -name LastName -value $User.LastName 
    $myObj | Add-Member -type NoteProperty -name DisplayName -value $User.DisplayName 
    $myObj | Add-Member -type NoteProperty -name Name -value $i.Name 
    $myObj | Add-Member -type NoteProperty -name SamAccountName -value $i.SamAccountName 
    $myObj | Add-Member -type NoteProperty -name legacyExchangeDN -value $i.legacyExchangeDN    $myObj | Add-Member -type NoteProperty -name ExchangeGuid -value $i.ExchangeGuid 
    $outArray += $myObj 
} 
$outArray | Export-CSV $outfile -notypeinformation  
################################################################# 
#Copy the file $outfile to the desktop of the target on-premises 
#then run the below to create MEU in Target 
#################################################################  
$ImportUserList = import-csv "$home\desktop\UserListToImport.csv" 
$pwstr = "Something 98053 Random!!"; 
$pw = new-object "System.Security.SecureString"; 
for ($i=0; $i -lt $pwstr.Length; $i++) {$pw.AppendChar($pwstr[$i])} foreach ($user in $ImportUserList) { 
     $tmpUser = $null 
    $UPNSuffix = "@northwindtraders.com"    $UPN = $user.Alias+$upnsuffix 
    $tmpUser = New-MailUser -organization -UserPrincipalName $upn -ExternalEmailAddress $user.primarysmtpaddress -FirstName $user.FirstName ` 
                 -LastName $user.LastName -SamAccountName $user.SamAccountName -ResetPasswordOnNextLogon $false ` 
                 -Alias $user.alias -PrimarySmtpAddress $UPN -Name $User.Name -DisplayName $user.DisplayName ` 
                 -OrganizationalUnit "OU=ContosoUsers,OU=MLB,DC=ContosoLab,DC=net" -Password $pw       $x500 = "x500:" + $user.legacyExchangeDN 
    $tmpUser | Set-MailUser -ExchangeGuid $user.ExchangeGuid -EmailAddresses @{Add=$x500} -CustomAttribute1 "ProjectKermit" 
}  
################################################################# 
# On AADSync machine, run AADSync 
#################################################################  
Start-ADSyncSyncCycle 
 
#AADSync and FWDSync will create the target MEUs in the Target tenant 
```
**使用メールボックスを移動した後、1 日目に Outlook にアクセスする方法**

ドメインを所有できるのは 1 つのテナントだけのため、メールボックスの移動が完了すると、以前のプライマリ SMTPAddress はターゲット テナント内のユーザーに関連付けされません。新しいテナントに関連付けられているドメインのみ。 Outlook はユーザーの新しい UPN を使用してサービスに対する認証を行い、Outlook プロファイルはターゲット システム内のメールボックスと一致する従来のプライマリ SMTPAddress を検索する必要があります。 レガシ アドレスがターゲット システムに含ではなされていないので、Outlook プロファイルは接続して新しく移動したメールボックスを見つけることはありません。 

この初期展開では、ユーザーは新しい UPN、プライマリ SMTP アドレスを使用してプロファイルを再構築し、OST コンテンツを再同期する必要があります。 

> [!Note]
> ユーザーのバッチ処理を完了に合わせて計画します。 Outlook クライアント プロファイルを作成し、それ以降の OST ファイルと OAB ファイルをクライアントにダウンロードする場合は、ネットワークの使用率と容量を考慮する必要があります。 
 
**テナント間の移動を設定または完了するには、どのような Exchange RBAC の役割のメンバーである必要がありますか。**
 
メールボックス移動を実行する際の委任された職務の前提に基づく役割のマトリックスがあります。 現在、2 つの役割が必要です。  

- 1 つ目の役割は、テナント/組織の境界内または組織の境界にコンテンツを移動する承認を確立する 1 回設定タスクです。 組織の制御からデータを移動する操作は、すべての企業にとって重要な懸念事項です。組織管理者 (OrgAdmin) の最高の役割を割り当てました。 この役割は、リモート組織での -MailboxMoveCapability を定義する新しい OrganizationRelationship を変更またはセットアップする必要があります。 OrganizationRelationhip の他の属性はフェデレーション共有管理者が管理できるのに対し、OrgAdmin だけが MailboxMoveCapability 設定を変更できます。 
 
- 実際の移動コマンドを実行する役割は、下位レベルの関数に委任できます。 メールボックスの移動の役割には、パラメーターを使用してメールボックスを組織内外に移動する機能が割り当 `-RemoteTenant` てられます。  

**変換されたメールボックスの targetAddress (TargetDeliveryDomain) に対して選択されている SMTP アドレスをターゲットにする方法 (MailUser 変換へ)**
 
移動先オブジェクトの電子メール アドレス (proxyAddress) と一致して MailUser に変換する場合、MRS を使用して移動する Exchange メールボックスは、元のソース メールボックスで targetAddress を作成します。 このプロセスは、move コマンドに渡された -TargetDeliveryDomain 値を受け取り、ターゲット側のそのドメインに対応するプロキシを確認します。 一致が見つけると、対応する proxyAddress を使用して、変換されたメールボックス (現在の MailUser) オブジェクトに ExternalEmailAddress (targetAddress) を設定します。
 
**メールボックスのアクセス許可の移行方法**

メールボックスのアクセス許可には、代理送信とメールボックス アクセスが含まれます。 

- 代理人として送信 (AD:publicDelegates) は、ユーザーのメールボックスへのアクセス権を持つ受信者の DN を代理人として格納します。 この値は Active Directory に格納され、現在、メールボックスの移行の一部として移動されません。 ソース メールボックスに publicDelegates が設定されている場合は、コマンドを使用してターゲット環境で MEU からメールボックスへの変換が完了したら、ターゲット メールボックスの publicDelegates を再サンプリングする必要があります。 `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` 
 
- メールボックスに格納されているメールボックスのアクセス許可は、プリンシパルと代理人の両方がターゲット システムに移動された場合にメールボックスと共に移動します。 たとえば、ユーザーは、TestUser_7内のメールボックス に FullAccess TestUser_8付与SourceCompany.onmicrosoft.com。 メールボックスの移動が完了TargetCompany.onmicrosoft.com、ターゲット ディレクトリに同じアクセス許可が設定されます。 ソース テナントとターゲット テナントの両方TestUser_7に *Get-MailboxPermission* を使用する例を以下に示します。 Exchange コマンドレットには、ソースとターゲットのプレフィックスが付いて表示されます。 
 
移動前のメールボックスアクセス許可の出力の例を次に示します。 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
移動後のメールボックスアクセス許可の出力の例を次に示します。 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> テナント間のメールボックスと予定表のアクセス許可はサポートされていません。 プリンシパルと代理人を統合移動バッチに整理して、接続されたメールボックスが移行元テナントから同時に移行される必要があります。 

**移行を有効にするには、どの X500 プロキシをターゲットの MailUser プロキシ アドレスに追加する必要がありますか。**  

テナント間メールボックスの移行では、移動元メールボックス オブジェクトの LegacyExchangeDN 値が、移動先の MailUser オブジェクトの x500 電子メール アドレスとしてスタンプされる必要があります。  

例:   
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> この X500 プロキシに加えて、ソース内のメールボックスからターゲット内のメールボックスに、すべての X500 プロキシをコピーする必要があります。  

**Azure Key Vault は必要ですか。また、いつトランザクションが行われたか。**  

はい。移行を承認する証明書を保存するには、Key Vault を使用する Azure サブスクリプションが必要です。 ユーザー名 & パスワードを使用して移行元への認証を行うオンボード移行とは異なり、テナント間メールボックスの移行では OAuth とこの証明書をシークレット/資格情報として使用します。 Key Vault へのアクセスは、移行の開始時と終了時に 1 回、増分同期時に 24 時間ごとに 1 回アクセスされるのと同様に、すべてのメールボックス移行を通じて維持する必要があります。 ARK のコストの詳細については、こちらを参照 [してください]( https://azure.microsoft.com/en-us/pricing/details/key-vault/)。  

**バッチ処理に関する推奨事項はありますか?**  

バッチあたり 2,000 のメールボックスを超えないようにしてください。 同期中にエンド ユーザーに影響が出ない場合は、カットオーバー日の 2 週間前にバッチを送信することを強く推奨します。50,000 を超えるメールボックスの数量に関するガイダンスが必要な場合は、次のページでエンジニアリング フィードバック配布リストcrosstenantmigrationpreview@service.microsoft.com。

**顧客キーでサービスの暗号化を使用する場合**

メールボックスは移動前に復号化されます。 引き続き必要な場合は、ターゲット テナントで顧客キーが構成されていることを確認します。 詳細 [については、](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) こちらを参照してください。  

**推定移行時間は何時ですか?**

移行を計画する際に役立つ、次[](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times)の表に、一括メールボックスの移行または個々の移行が完了すると予想される場合のガイドラインを示します。 これらの見積もりは、以前の顧客移行のデータ分析に基づいて行います。 どの環境も一意なので、移行の正確な速度は異なる場合があります。  

この機能は現在プレビュー段階であり、SLA および該当するサービス レベルは、この機能のプレビュー状態中のパフォーマンスまたは可用性の問題には適用されません。

## <a name="known-issues"></a>既知の問題  

-  **問題: 自動拡張アーカイブを移行できません。** テナント間の移行機能は、特定のユーザーのプライマリ メールボックスとアーカイブ メールボックスの移行をサポートします。 ただし、ソース内のユーザーが自動拡張アーカイブ (複数のアーカイブ メールボックスを意味する) を持つ場合、この機能は追加のアーカイブを移行できません。

- **問題: 所有されていない smtp proxyAddress ブロック MRS を持つクラウド MailUsers がバックグラウンドで移動します。** ターゲット テナントの MailUser オブジェクトを作成する場合は、すべての SMTP プロキシ アドレスがターゲット テナント組織に属している必要があります。 ローカル テナントに属さないターゲット メール ユーザーに SMTP proxyAddress が存在する場合、MailUser から Mailbox への変換は防止されます。 これは、メールボックス オブジェクトが、テナントが権限を持つドメイン (テナントによって要求されたドメイン) からのみメールを送信できるという保証のためです。 

   - Azure AD Connect を使用してオンプレミスからユーザーを同期する場合、メールボックスが存在するソース テナント (laran@contoso.onmicrosoft.com) を指す ExternalEmailAddress を使用してオンプレミスの MailUser オブジェクトをプロビジョニングし、PrimarySMTPAddress をターゲット テナント (Lara.Newton@northwind.com) に存在するドメインとしてスタンプします。 これらの値はテナントに同期され、適切なメール ユーザーがプロビジョニングされ、移行の準備が整います。 オブジェクトの例を次に示します。
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > 電子 *contoso.onmicrosoft.com**アドレスが* EmailAddresses / proxyAddresses 配列に存在しない。

- **問題: "外部" プライマリ SMTP アドレスを持つ MailUser オブジェクトが、"内部" の会社が要求したドメインに変更またはリセットされる**

   MailUser オブジェクトは、ローカル以外のメールボックスへのポインターです。 テナント間のメールボックス移行の場合は、MailUser オブジェクトを使用して、移動元メールボックス (ターゲット組織の観点から) またはターゲット メールボックス (移行元組織の観点から) を表します。 MailUsers には、ディレクトリ内のメールボックス ユーザーの表示 SMTP アドレスを表す、実際のメールボックス (ProxyTest@fabrikam.onmicrosoft.com) の smtp アドレスと primarySMTP アドレスをポイントする ExternalEmailAddress (targetAddress) があります。 一部の組織では、プライマリ SMTP アドレスを外部 SMTP アドレスとして表示し、ローカル テナントによって所有/検証されるアドレス (fabrikam.com など、 contoso.com など) として表示しない場合があります。  ただし、ライセンス操作によって Exchange サービス プラン オブジェクトが MailUser に適用されると、プライマリ SMTP アドレスが変更され、ローカル組織 (contoso.com) によって確認されたドメインとして表示されます。 次の 2 つの潜在的な理由があります。
   
   - Exchange サービス プランが MailUser に適用されると、Azure AD プロセスはプロキシ スクラブの適用を開始し、ローカル組織が別のテナントからメールを送信、スプーフィング、またはメールを送信できないか確認します。 これらのサービス プランを持つ受信者オブジェクトの SMTP アドレスは、そのアドレスがローカル組織によって確認されていない場合に削除されます。 例の場合と同様に、Fabikam.com ドメインは contoso.onmicrosoft.com テナントによって検証されないので、スクラブによってそのドメインfabrikam.comされます。 移行前または移行後にこれらの外部ドメインを MailUser に保持する場合は、移行が完了した後、または移行前にライセンスを削除して、ユーザーに予期される外部ブランド化が適用されるかどうかを確認するために、移行プロセスを変更する必要があります。 メール サービスに影響を与えずに、メールボックス オブジェクトが適切にライセンスされていることを確認する必要があります。<br/><br/>テナント内の MailUser のサービス プランを削除するスクリプトContoso.onmicrosoft.com次に示します。

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       割り当てられた ServicePlans のセットの結果を次に示します。

    ```powershell
    (Get-MsolUser -UserPrincipalName proxytest@contoso.com).licenses |select 
    -ExpandProperty servicestatus |sort ProvisioningStatus -Descending   
    ServicePlan           ProvisioningStatus 
    -----------           ------------------ 
    ATP_ENTERPRISE        PendingProvisioning 
    MICROSOFT_SEARCH      PendingProvisioning 
    INTUNE_O365           PendingActivation 
    PAM_ENTERPRISE        Disabled 
    EXCHANGE_ANALYTICS    Disabled 
    EQUIVIO_ANALYTICS     Disabled 
    THREAT_INTELLIGENCE   Disabled 
    LOCKBOX_ENTERPRISE    Disabled 
    PREMIUM_ENCRYPTION    Disabled 
    EXCHANGE_S_ENTERPRISE Disabled 
    INFORMATION_BARRIERS  Disabled 
    MYANALYTICS_P2        Disabled 
    MIP_S_CLP1            Disabled 
    MIP_S_CLP2            Disabled 
    ADALLOM_S_O365        PendingInput 
    RMS_S_ENTERPRISE      Success 
    YAMMER_ENTERPRISE     Success 
    PROJECTWORKMANAGEMENT Success 
    BI_AZURE_P2           Success 
    WHITEBOARD_PLAN3      Success 
    SHAREPOINTENTERPRISE  Success 
    SHAREPOINTWAC         Success 
    KAIZALA_STANDALONE    Success 
    OFFICESUBSCRIPTION    Success 
    MCOSTANDARD           Success 
    Deskless              Success 
    STREAM_O365_E5        Success 
    FLOW_O365_P3          Success 
    POWERAPPS_O365_P3     Success 
    TEAMS1                Success 
    MCOEV                 Success 
    MCOMEETADV            Success 
    BPOS_S_TODO_3         Success 
    FORMS_PLAN_E5         Success 
    SWAY                  Success 

    ```
 
       ユーザーの PrimarySMTPAddress がスクラブされなくなりました。 ドメインfabrikam.comは、contoso.onmicrosoft.com テナントによって所有されていないので、ディレクトリに表示されるプライマリ SMTP アドレスとして保持されます。

       次に例を示します。

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - msExchRemoteRecipientType が 8 (DeprovisionMailbox) に設定されている場合、ターゲット テナントに移行されるオンプレミスの MailUser の場合、Azure のプロキシ スクラブ ロジックは、所有されていないドメインを削除し、primarySMTP を所有ドメインにリセットします。 オンプレミスの MailUser で msExchRemoteRecipientType をクリアすると、プロキシ スクラブ ロジックは適用されなくなりました。 <br/><br>以下に、Exchange Online を含む、可能なサービス プランの完全なセットを示します。

   | 名前                                              |
   |---------------------------------------------------|
   | Advanced eDiscovery Storage (500GB)               |
   | 顧客ロックボックス                                  |
   | データ損失防止                              |
   | Exchange Enterprise CAL サービス (EOP、DLP)       |
   | Exchange Essentials                               |
   | Exchange Foundation                               |
   | Exchange Online (P1)                              |
   | Exchange Online (プラン 1)                          |
   | Exchange Online (プラン 2)                          |
   | Exchange Online 用の Exchange Online Archiving     |
   | Exchange Server 用の Exchange Online Archiving     |
   | Exchange Online 非アクティブユーザー アドオン              |
   | Exchange Online Kiosk                             |
   | Exchange Online Multi-Geo                         |
   | Exchange Online プラン 1                            |
   | Exchange Online POP                               |
   | Exchange Online Protection                        |
   | 情報バリア                              |
   | Information Protection for Office 365 - Premium   |
   | Information Protection for Office 365 - Standard  |
   | MyAnalytics による分析情報                           |
   | Microsoft 365 Advanced Auditing                   |
   | Microsoft Bookings                                |
   | Microsoft Business Center                         |
   | Microsoft MyAnalytics (フル機能)                      |
   | Office 365 Advanced eDiscovery                    |
   | Microsoft Defender for Office 365 (プラン 1)    |
   | Microsoft Defender for Office 365 (プラン 2)    |
   | Office 365 Privileged Access Management           |
   | Office 365 でのプレミアム暗号化                  |
    