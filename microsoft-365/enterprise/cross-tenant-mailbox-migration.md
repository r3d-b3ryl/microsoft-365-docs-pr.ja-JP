---
title: テナント間でのメールボックスの移行
description: Microsoft 365 または Office 365 テナント間でメールボックスを移動する方法について説明します。
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
ms.openlocfilehash: 06a82fda31e602ed2feb53d00e8839daf801bf7e
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277484"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>テナント間のメールボックスの移行 (プレビュー)

以前は、Exchange Online テナントが同じ Exchange Online サービスの別のテナントにメールボックスを移動する必要がある場合、それらを完全にオンプレミスにして、新しいテナントに移行する必要があります。 新しいクロステナントメールボックス移行機能を使用すると、ソーステナントとターゲットテナントの両方のテナント管理者は、オンプレミスシステムのインフラストラクチャの依存関係を持つテナント間でメールボックスを移動することができます。 これにより、オフボードおよびオンボードメールボックスに対する必要性がなくなります。

一般に、合併または divestitures では、ユーザーとコンテンツを新しいテナントに移動する機能が必要です。 ターゲットのテナント管理者が移動を実行すると、オンプレミスとクラウドのオンボード移行のようなプル移動と呼ばれます。

テナント間の Exchange メールボックスの移動は、テナント管理者が完全にサービスを提供し、ユーザーを新しい組織に移行するために必要なより大きなワークフローにスクリプト化できる既知のインターフェイスを使用しています。 管理者は、 `New-MigrationBatch` Move メールボックス管理役割で使用可能なコマンドレットを使用して、テナント間の移動を実行できます。 移動プロセスには、メールボックスの同期および終了の際にテナントの承認チェックが含まれます。 
 
移行するユーザーは、テナントユーザーとしてターゲットテナントの Exchange Online システムに存在する必要があります。これは、テナント間の移動を有効にするために特定の属性でマークされています。 ターゲットテナントに正しく設定されていないユーザーの場合、システムは移動に失敗します。 

移動が完了すると、移行元システムのメールボックスは MailUser に変換され、targetAddress (Exchange の ExternalEmailAddress として表示される) には、ルーティングアドレスが宛先のテナントにスタンプされます。 このプロセスでは、従来の MailUser をソーステナントに残して、共存とメールルーティングの期間を可能にします。 ビジネスプロセスが許可されている場合、ソーステナントは移動元の MailUser を削除するか、メール連絡先に変換することができます。 

テナント間の Exchange メールボックスの移行は、ハイブリッドまたはクラウドのみのテナント、またはその2つの組み合わせでサポートされています。

この記事では、テナント間でのメールボックスの移動のプロセスについて説明し、コンテンツの移動用にソースおよびターゲットテナントを準備する方法についてのガイダンスを提供します。 

## <a name="preparing-source-and-target-tenants"></a>ソースおよびターゲットテナントの準備

テナント間の Exchange メールボックスの移行機能には、テナント間の移行の承認とスコープが必要です。 Azure エンタープライズアプリケーションとキーヴォールトストレージソリューションを使用すると、テナント管理者は、1つのテナントから別のテナントへの Exchange Online メールボックスの移行の承認およびスコープの管理を行うことができるようになります。 テナント間のメールボックスの移動は、招待と同意モデルをサポートして、テナントのペア間の認証に使用される Azure Active Directory (Azure AD) アプリケーションを確立します。 組織上の関係や移行エンドポイントなど、追加のコンポーネントも必要です。

このセクションには、ターゲットディレクトリで MailUser ユーザーオブジェクトを準備するために必要な特定の手順は含まれません。また、移行バッチを送信するためのサンプルコマンドも含まれていません。 この情報については、「 [移行先ユーザーオブジェクトの移行を準備する](#prepare-target-user-objects-for-migration) 」を参照してください。

## <a name="prerequisites"></a>前提条件

テナント間のメールボックス移動機能では、テナント間でのメールボックスの移行を認証および承認するために使用される証明書とシークレットに安全に格納してアクセスするために、 [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) が必要になります。 

開始する前に、Azure Key Vault、Move Mailbox application、EXO Migration Endpoint、および EXO 組織上の関係を構成するために、展開スクリプトを実行するために必要なアクセス許可があることを確認してください。 通常、グローバル管理者には、すべての構成手順を実行する権限があります。

さらに、セットアップを実行する前に、ソーステナント内のメールが有効なセキュリティグループが必要です。 これらのグループは、ソース (またはリソースとも呼ばれる) テナントからターゲットテナントに移動できるメールボックスの一覧のスコープに使用されます。 これにより、移動する必要のある特定のメールボックスのセットをソーステナント管理者が制限または範囲設定でき、意図しないユーザーが移行されるのを防ぐことができます。 ネストされたグループはサポートされていません。

また、(メールボックスを移動する相手となる) 信頼できるパートナー企業と連絡して、Microsoft 365 テナント ID を入手する必要があります。 このテナント ID は、組織の関係フィールドで使用され `DomainName` ます。

サブスクリプションのテナント ID を取得するには、Microsoft 365 管理センターにサインインして、に移動し [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) ます。 テナント ID プロパティの [コピー] アイコンをクリックして、クリップボードにコピーします。

プロセスのしくみを次に示します。

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="メールボックスの移行のテナントの準備。":::

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)

[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).
--> 

### <a name="prepare-tenants"></a>テナントの準備

高レベルでは、セットアップスクリプトを実行するときに、次の構成操作が行われます。

ターゲットテナントを準備します。

1. 既存の Azure リソースグループが指定されていない場合は、新しいものが作成されます (スクリプト)。
2. 既存のキーボルトが指定されていない場合は、新しいコンテナーが作成されます (スクリプト)。
3. Office 365 Exchange Online メールボックス移行アプリケーション (スクリプト) 用の新しいアクセスポリシーが作成されます。
4. 移行アプリケーション (スクリプト) に対するシークレットを保持するために、新しい証明書が作成されます (指定されている場合は、既存の証明書がある場合)。
5. 新しい Azure AD アプリケーションが作成されます (スクリプト)。
6. 証明書/シークレットは、移行アプリケーション (スクリプト) にアップロードされます。
7. メールボックスの移行アクセス許可は、アプリケーション (スクリプト) に割り当てられます。
8. 展開スクリプトは、ターゲットの管理者が自身のアプリケーション (スクリプト) を同意するまで停止します。
9. ターゲットのテナント管理者は、アプリケーションに与えられたアクセス許可 (手動) に同意します。
10. ターゲットテナント (スクリプト) に対して組織上の関係が作成されます。
11. 移行エンドポイントが作成され、メールボックスがターゲットテナント (スクリプト) にプルされます。

ソーステナントを準備します。

1. ソーステナント管理者は、ターゲットテナント (手動) からメールボックス移行アプリケーションへの招待に対する同意を受け入れます。
2. 移行元のテナント管理者は、テナント内にメールが有効なセキュリティグループを作成して、移行アプリケーションによる移動が許可されたメールボックスのリストを格納します (手動)。
3. メールボックス移行アプリケーションを指定するターゲットテナントに対して組織上の関係が作成され、移動要求 (スクリプト) を受け入れるために、OAuth の検証に使用する必要があります。

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>ターゲットテナント管理者のためのステップごとの手順

1. [GitHub リポジトリ](https://github.com/microsoft/cross-tenant/releases/tag/Preview)からターゲットテナントのセットアップの SetupCrossTenantRelationshipForTargetTenant.ps1 スクリプトをダウンロードします。 
2. スクリプトを実行するコンピューターにスクリプト (SetupCrossTenantRelationshipForTargetTenant.ps1) を保存します。
3. Exchange Online ターゲットテナントへのリモート PowerShell 接続を作成します。 この場合も、Azure Key Vault storage and certificate、Move Mailbox application、EXO Migration Endpoint、および EXO 組織の関係を構成するために、展開スクリプトを実行するために必要なアクセス許可があることを確認してください。
4. ファイルフォルダーディレクトリをスクリプトの場所に変更するか、現在リモート PowerShell セッションにある場所にスクリプトが保存されていることを確認します。
5. 次のパラメーターと値を使用して、スクリプトを実行します。

    | パラメーター | 値 | 必須またはオプション
    |---------------------------------------------|-----------------|--------------|
    | -ResourceTenantDomain                       | ソーステナントドメイン (fabrikam onmicrosoft.com など) \. 。 | 必須 |
    | -ResourceTenantAdminEmail                   | 送信元テナント管理者の電子メールアドレス。 これは、ターゲット管理者から送信されたメールボックス移行アプリケーションの使用に同意するソーステナント管理者です。これは、アプリケーションの電子メールの招待を受信する管理者です。 | 必須 |
    | -TargetTenantDomain                         | 宛先のテナントドメイン (contoso onmicrosoft.com など) \. 。 | 必須 |
    | -ResourceTenantId                           | 送信元テナントの組織 ID (GUID)。 | 必須 |
    | -SubscriptionId                             | リソースの作成に使用する Azure サブスクリプション。 | 必須 |
    | -ResourceGroup                              | キーのコンテナーを含む、または含む Azure リソースグループの名前。 | 必須 |
    | -KeyVaultName                               | メールボックス移行アプリケーション証明書/シークレットを格納する Azure Key Vault インスタンス。 | 必須 |
    | -任意の Ename                            | キーコンテナーで証明書を生成または検索するときの証明書の名前。 | 必須 |
    | -CertificateSubject                         | Azure Key Vault 証明書のサブジェクト名 (CN = contoso_fabrikam など)。 | 必須 |
    | -ExistingApplicationId                      | メール移行アプリケーションが既に作成されている場合に使用します。 | 省略可能 |
    | -AzureAppPermissions                        | メールボックス移行アプリケーションに必要なアクセス許可 (Exchange または MSGraph (メールボックスを移動するための Exchange) など)。また、このアプリケーションを使用して、リソーステナントへの同意リンクの招待を送信するための MSGraph を提供します。 | 必須 |
    | -UseAppAndCertGeneratedForSendingInvitation | 移行用に作成されたアプリケーションを使用して、ソーステナントの管理者に同意リンクの招待状を送信するために使用するパラメーター。このパラメーターを指定しない場合、Azure に接続するためのターゲット管理者の資格情報を求めるメッセージが表示され、招待を対象の管理者として送信します。 | オプション |
    | -KeyVaultAuditStorageAccountName            | キーヴォールトの監査ログが格納されるストレージアカウント。 | 省略可能 |
    | -KeyVaultAuditStorageResourceGroup          | キーコンテナーの監査ログを格納するためのストレージアカウントを含むリソースグループ。 | 省略可能 |
    ||||

6. このスクリプトは一時停止して、このプロセス中に作成された Exchange メールボックス移行アプリケーションを受け入れるか、または同意するように求められます。 次に例を示します。

    ```powershell
    PS C:\Users\Admin\scripts\T2TMovesV2> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

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

7. URL がリモート PowerShell セッションに表示されます。 テナントの同意のために提供されたリンクをコピーして、Web ブラウザーに貼り付けます。

8. グローバル管理者の資格情報を使用してサインインします。 次の画面が表示されたら、[ **同意**する] を選択します。

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="[アクセス許可の承諾] ダイアログボックス":::
    
9. リモート PowerShell セッションに戻り、Enter キーを押して続行します。

10. スクリプトは、残りのセットアップオブジェクトを構成します。 次に例を示します。

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

これで、ターゲットの管理者セットアップが完了しました。

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>ソーステナント管理者のためのステップごとの手順

1.  セットアップ時に、ターゲット管理者によって指定された ResourceTenantAdminEmail として、メールボックスにサインインします。 ターゲットテナントから電子メール招待状を検索し、[ **開始** ] ボタンを選択します。

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="[招待されました] ダイアログボックス":::

2. [ **承諾** ] を選択して招待状を承諾します。

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="アクセス許可を受け入れるためのダイアログボックス":::

   > [!NOTE]
   > このメールを受信できない場合、または見つからない場合は、ターゲットテナント管理者に対して、招待を受け入れるために付与される直接 URL が提供されています。 URL は、ターゲットテナント管理者のリモート PowerShell セッションの「トランスクリプト」に記載されている必要があります。

3. Microsoft 365 管理センターまたはリモート PowerShell セッションのいずれかで、1つまたは複数のメールが有効なセキュリティグループを作成して、移動元のテナントからターゲットテナントにプル (移動) する目的のテナントによって許可されるメールボックスの一覧を制御します。 このグループを事前に設定する必要はありませんが、セットアップ手順 (スクリプト) を実行するには、少なくとも1つのグループを指定する必要があります。 グループのネストはサポートされていません。 

4. [ここで](https://github.com/microsoft/cross-tenant/releases/tag/Preview)、GitHub リポジトリからソーステナントのセットアップの SetupCrossTenantRelationshipForTargetResource.ps1 スクリプトをダウンロードします。 

5. Exchange 管理者のアクセス許可を使用して、ソーステナントへのリモート PowerShell 接続を作成します。 グローバル管理者のアクセス許可は、ソーステナントのみを構成する必要はありません。これは、Azure アプリケーションの作成プロセスのためです。

6. ディレクトリをスクリプトの場所に変更するか、現在リモート PowerShell セッションにある場所にスクリプトが保存されていることを確認してください。

7. 次の必要なパラメーターと値を使用して、スクリプトを実行します。

    | パラメーター | 値 |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | 移行の対象となる id またはメールボックスのソーステナントによって作成された、メールが有効なセキュリティグループ。 |
    | -ResourceTenantDomain | ソーステナントのドメイン名 (fabrikam onmicrosoft.com など) \. 。 |
    | -TargetTenantDomain | 宛先のテナントのドメイン名 (contoso \. onmicrosoft.com など)。 |
    | -ApplicationId | 移行に使用するアプリケーションの Azure アプリケーション ID (GUID)。 Azure ポータル (Azure AD、エンタープライズアプリケーション、アプリ名、アプリケーション ID) 経由で利用可能なアプリケーション ID。または、招待メールに含まれています。  |
    | -TargetTenantId | ターゲットテナントのテナント ID。 たとえば、contoso onmicrosoft.com テナントの Azure AD テナント ID \. 。 |
    |||
    
    次に例を示します。
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

これで、ソース管理者のセットアップが完了しました。

### <a name="verify-setup"></a>セットアップを確認する

ターゲットのソースとターゲットのテナントと移行エンドポイントの組織上の関係が正常に作成されていることを確認します。

#### <a name="target-tenant"></a>ターゲットテナント

**組織の関係**

このコマンドを使用して、組織の関係オブジェクトが作成され、構成されていることを確認します。

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
次に例を示します：

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

**移行エンドポイント**

このコマンドを使用して、移行エンドポイントオブジェクトが作成され、構成されていることを確認します。

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

次に例を示します。

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a>ソーステナント

**組織の関係**

このコマンドを使用して、組織の関係オブジェクトが作成され、構成されていることを確認します。

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```
次に例を示します。

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a>メールボックスを元のソースに戻す

メールボックスが元のソーステナントに戻る必要がある場合は、同じ手順とスクリプトのセットを新しいソーステナントと新しいターゲットテナントの両方で実行する必要があります。 既存の組織の関係オブジェクトは、再作成されるのではなく、更新または追加されます。

## <a name="prepare-target-user-objects-for-migration"></a>移行先のユーザーオブジェクトの準備

移行するユーザーは、テナント間の移動を有効にするために特定の属性でマークされたターゲットテナントおよび Exchange Online システム (MailUsers として) に存在する必要があります。 ターゲットテナントに正しく設定されていないユーザーの場合、システムは移動に失敗します。 次のセクションでは、ターゲットテナントの MailUser オブジェクトの要件について詳しく説明します。

### <a name="prerequisites"></a>前提条件
  
次のオブジェクトと属性が移動先の組織に設定されていることを確認する必要があります。  

1. 送信元組織から移動するメールボックスの場合は、移動先の組織で MailUser オブジェクトを準備する必要があります。 
   - 移動先の MailUser は、移動元のメールボックスからこれらの属性を持っているか、または新しいユーザーオブジェクトで割り当てられている必要があります。
      - ExchangeGUID (ソースからターゲットへの直接フロー) –メールボックスの GUID は一致する必要があります。 移動先のオブジェクトにこのパラメーターが存在しない場合、移動プロセスは続行されません。 
      - アーカイブ Guid (ソースからターゲットへの直接フロー) –アーカイブ GUID は一致する必要があります。 移動プロセスは、ターゲットオブジェクトに存在しない場合は続行されません。 (これは、移動元のメールボックスのアーカイブが有効になっている場合にのみ必要です)。 
      - LegacyExchangeDN (proxyAddress, "x500: <LegacyExchangeDN> ") – legacyexchangedn は、対象の MailUser に x500: proxyAddress として存在している必要があります。 移動プロセスは、ターゲットオブジェクトに存在しない場合は続行されません。 
      - UserPrincipalName – UPN は、ユーザーの新しい id または対象となる会社 (たとえば、user@northwindtraders.onmicrosoft.com) に揃えられます。 
      - プライマリ SMTPAddress –プライマリ SMTP アドレスは、ユーザーの新しい会社 (たとえば、user@northwind.com) に揃えられます。 
      - TargetAddress/ExternalEmailAddress – MailUser は、ソーステナントでホストされているユーザーの現在のメールボックスを参照します (たとえば、user@contoso.onmicrosoft.com)。 この値を割り当てるときは、PrimarySMTPAddress も割り当てられているか、またはこの値によって PrimarySMTPAddress が設定され、移動エラーが発生します。 
      - 移行元メールボックスからメールユーザーを移動するために従来の smtp プロキシアドレスを追加することはできません。 たとえば、fabrikam.onmicrosoft.com テナントオブジェクトの MEU で contoso.com を管理することはできません。 ドメインは、1つの Azure AD または Exchange Online テナントにのみ関連付けられます。
 
    **ターゲット**mailuser オブジェクトの例:
 
    | 属性             | 値                                                                                                                    |
    |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
    | エイリアス                 | LaraN                                                                                                                    |
    | RecipientType         | Enable-mailuser                                                                                                                 |
    | RecipientTypeDetails  | Enable-mailuser                                                                                                                 |
    | UserPrincipalName     | LaraN@northwintraders \. onmicrosoft.com                                                                                    |
    | PrimarySmtpAddress    | Lara \. Newton@northwind.com                                                                                                |
    | ExternalEmailAddress  | SMTP: LaraN@contoso \. onmicrosoft.com                                                                                       |
    | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                     |
    | LegacyExchangeDN      | /o = First Organization/ou = Exchange 管理グループ                                                                   |
    |                       | (FYDIBOHF23SPDLT)/cn = Recipients/cn = 74e5385fce4b46d19006876949855035Lara                                                  |
    | EmailAddresses        | x500:/o = First Organization/ou = Exchange 管理グループ (FYDIBOHF23SPDLT)/cn = Recipients/cn = d11ec1a2cacd4f81858c8190  |
    |                       | 72Lara f1f9-                                                                                                            |
    |                       | smtp: LaraN@northwindtraders \. onmicrosoft.com                                                                              |
    |                       | SMTP: Lara \. Newton@northwind.com                                                                                           |
    |||

   **ソース**メールボックスオブジェクトの例:

   | 属性             | 値                                                                    |
   |-----------------------|--------------------------------------------------------------------------|
   | エイリアス                 | LaraN                                                                    |
   | RecipientType         | UserMailbox                                                              |
   | RecipientTypeDetails  | UserMailbox                                                              |
   | UserPrincipalName     | LaraN@contoso \. onmicrosoft.com                                            |
   | PrimarySmtpAddress    | Lara \. Newton@contoso.com                                                  |
   | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                     |
   | LegacyExchangeDN      | /o = First Organization/ou = Exchange 管理グループ                   |
   |                       | (FYDIBOHF23SPDLT)/cn = Recipients/cn = d11ec1a2cacd4f81858c81907273f1f9Lara  |
   | EmailAddresses        | smtp: LaraN@contoso \. onmicrosoft.com 
   |                       | SMTP: Lara \. Newton@contoso.com          |
   |||

   - その他の属性は、既に Exchange ハイブリッドの書き戻しに含めることができます。 含まれていない場合は、それらを含める必要があります。 
   - msExchBlockedSendersHash –オンラインセーフおよびブロックされた送信者データをクライアントからオンプレミスの Active Directory に書き戻します。
   - Msexchsaferecipientshash ユーザー–オンラインセーフおよびブロックされた送信者データをクライアントからオンプレミスの Active Directory に書き戻します。
   - Msexchsafesendershash ユーザー–オンラインセーフおよびブロックされた送信者データをクライアントからオンプレミスの Active Directory に書き戻します。

2. ソースメールボックスが LitigationHold 上にあり、ソースメールボックスの回復可能なアイテムのサイズがデータベースの既定値 (30 GB) より大きい場合、移動先のクォータがソースメールボックスのサイズより小さいため、移動は続行されません。 ターゲットの MailUser オブジェクトを更新して、ソース環境からターゲットに移動することによって、ターゲットシステムで MailUser のクォータを 100 GB に拡張し、ターゲットへの移動を許可することができます。 これらの手順は、ELC フラグをスタンプするコマンドがテナント管理者に公開されていないため、Azure AD Connect を実行しているハイブリッド id に対してのみ機能します。

    >[!Note]
    > サンプル–これと同様に、保証なし<br/>このスクリプトでは、ソースのメールボックス (ソースの値を取得する場合) と、ターゲットのオンプレミスの Active Directory (ADUser オブジェクトにスタンプする) の両方への接続が想定されています。 ソースに訴訟または単一アイテムの回復が有効になっている場合は、これを移行先のアカウントで設定します。  これにより、移行先アカウントのサイズが 100 GB に増加します。

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```
3. 非ハイブリッドターゲットテナントは、次のコマンドを実行して、Mailusers オブジェクトに対する訴訟ホールドを有効にし、クォータを 100 GB に増やすことにより、メールを移行する前に、MailUsers の回復可能なアイテムフォルダーのクォータを変更することができ `Set-MailUser -EnableLitigationHoldForMigration $TRUE` ます。 注これはハイブリッドのテナントでは機能しません。

4. 移行先組織のユーザーには、組織に適用できる適切な Exchange Online サブスクリプションのライセンスが付与されている必要があります。 メールボックスの移動の前にライセンスを適用することができますが、移動先の MailUser が ExchangeGUID とプロキシアドレスを使用して適切に設定されている場合に限られます。 ExchangeGUID が適用される前にライセンスを適用すると、移動先の組織でプロビジョニングされた新しいメールボックスになります。 

    > [!Note]
    > メールボックスまたは MailUser オブジェクトにライセンスを適用すると、すべての SMTP タイプ proxyAddresses が scrubbed になり、確認済みのドメインのみが Exchange EmailAddresses アレイに含まれるようになります。 

5. 移動先の MailUser に、ソース ExchangeGuid と一致しない以前の ExchangeGuid がないことを確認する必要があります。 これは、ターゲット MEU が以前 Exchange Online 用にライセンスされていて、メールボックスがプロビジョニングされている場合に発生する可能性があります。 移動先のメールユーザーが以前にライセンスされていたか、またはソース ExchangeGuid と一致しない ExchangeGuid がある場合は、クラウド MEU のクリーンアップを実行する必要があります。 これらの cloud MEUs では、コマンドを実行でき `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` ます。 

    > [!Caution]
    > この処理は、取り消すことができません。 オブジェクトに softDeleted メールボックスがある場合は、この時点以降は復元できません。 ただし、オフにした場合は、正しい ExchangeGuid をターゲットオブジェクトに同期させることができます。また、新しく作成したターゲットメールボックスにソースメールボックスを接続します。 (新しいパラメーターで EHLO ブログを参照してください)。 
 
    このコマンドを使用して、以前のメールボックスであったオブジェクトを検索します。

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
 
    このコマンドを使用して、削除済みメールボックスの回復可能な削除

    ````
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```` 

    次に例を示します。

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY. 
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y 
    ```

## <a name="perform-mailbox-migrations"></a>メールボックスの移行を実行する

テナント間の Exchange メールボックスの移行は、ターゲットテナントから開始された移行バッチとして送信されます。 これは、Exchange オンプレミスから Microsoft 365 に移行する際に、移行バッチを処理する方法に似ています。 

### <a name="create-migration-batches"></a>移行バッチを作成する

や議 off 移動の移行バッチコマンドレットの例を次に示します。

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> CSV ファイルの電子メールアドレスは、ターゲットテナントで指定されたものである必要があります。ソーステナントでは指定されていません。

クロステナントオプションを選択する場合は、新しい Exchange 管理センターから移行バッチの送信もサポートされます。
 
#### <a name="update-on-premises-mailusers"></a>オンプレミスのメールユーザーを更新する

メールボックスが移行元から移行先に移動したら、ソースとターゲットの両方の社内メールユーザーが新しい targetAddress で更新されるようにする必要があります。 この例では、移動で使用される targetDeliveryDomain は **contoso \. onmicrosoft.com**です。 この targetAddress を使用してメールユーザーを更新します。
 
## <a name="frequently-asked-questions"></a>よく寄せられる質問
 
**移行後に、オンプレミスのソースで Remotemックスを更新する必要がありますか?**
 
はい。ソーステナントメールボックスをターゲットテナントに移動するときに、ソースの targetAddress (RemoteRoutingAddress/ExternalEmailAddress) を更新する必要があります。  メールルーティングは、異なる targetAddresses を持つ複数のメールユーザーにわたる参照に従うことができますが、メールユーザーの空き時間情報の検索では、メールボックスユーザーの場所を対象とする必要があります。 空き時間情報の参照では、複数のリダイレクトは追跡されません。 
 
**Teams のチャットフォルダーコンテンツはテナント間で移行しますか?** 

いいえ。 Teams のチャットフォルダーのコンテンツは、クロステナントを移行しません。 
 
**オンボードとオフボードの移動ではなく、テナント間の移動のみを表示するには、どうすればよいですか?**

パラメーターを使用 `-flags` します。 次に例を示します。

```powershell
Get-MoveRequest -Flags "CrossTenant" 
```
 
**テストで使用される属性をコピーするためのスクリプトの例を提供できますか。**

> [!Note]
> サンプル–これと同様に、保証なし<br/>このスクリプトでは、ソースのメールボックス (ソースの値を取得する場合) と、ターゲットのオンプレミスの Active Directory ドメインサービス (ADUser オブジェクトにスタンプする) の両方への接続を想定しています。 ソースに訴訟または単一アイテムの回復が有効になっている場合は、これを移行先のアカウントで設定します。  これにより、移行先アカウントのサイズが 100 GB に増加します。

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
**使用メールボックスを移動した後、1日目に Outlook にアクセスするにはどうすればよいですか。**

ドメインを所有できるテナントは1つだけなので、メールボックスの移動が完了したときに、以前のプライマリ SMTPAddress はターゲットテナントのユーザーに関連付けられません。新しいテナントに関連付けられているドメインのみ。 Outlook では、ユーザーの新しい UPN を使用してサービスに対して認証を行い、Outlook プロファイルは、ターゲットシステムのメールボックスに一致する従来のプライマリ SMTPAddress を検索することを想定しています。 従来のアドレスはターゲットシステムには含まれていないため、outlook プロファイルは新たに移動されたメールボックスを検索するために接続されません。 

この初期展開では、ユーザーは新しい UPN、プライマリ SMTP アドレスを使用してプロファイルを再構築し、OST コンテンツを再同期する必要があります。 

> [!Note]
> ユーザーの完了をバッチ処理する際には、適宜計画してください。 Outlook クライアントプロファイルを作成するときには、ネットワークの使用率と容量を考慮する必要があります。その後、OST および OAB ファイルがクライアントにダウンロードされます。 
 
**テナント間の移動をセットアップまたは完了するには、どのような Exchange RBAC の役割をメンバーにする必要がありますか。**
 
メールボックスの移動を実行する際に委任された業務の前提に基づいて、役割のマトリックスが用意されています。 現時点では、次の2つの役割が必要です。  

- 最初の役割は、テナントまたは組織の境界からコンテンツを移動する承認を確立する1回限りのセットアップタスクです。 組織の管理からデータを移動することは、すべての企業にとって重要な問題であるため、組織の管理者 (OrgAdmin) の中で最も割り当てられている役割を使用しています。 この役割では、リモート組織で-MailboxMoveCapability を定義する新しい組織関係を変更またはセットアップする必要があります。 MailboxMoveCapability の設定を変更できるのは OrgAdmin ですが、OrganizationRelationhip のその他の属性はフェデレーション共有の管理者が管理できます。 
 
- 実際の移動コマンドを実行する役割は、下位レベルの関数に委任できます。 移動メールボックスの役割には、パラメーターを使用して、組織内または組織外にメールボックスを移動する機能が割り当てられ `-RemoteTenant` ます。  

**変換されたメールボックスのどの SMTP アドレスが targetAddress (TargetDeliveryDomain) に対して選択されるのか (MailUser conversion への移行)。**
 
Exchange メールボックスの移動先オブジェクトの電子メールアドレス (proxyAddress) を照合することによって、MailUser に変換するときに、targetAddress を使用して移動元のメールボックスに移動します。 このプロセスは、移動コマンドに渡された TargetDeliveryDomain の値を取得し、そのドメインに対応するプロキシがターゲット側にあるかどうかを確認します。 一致するものが見つかった場合は、一致した proxyAddress を使用して、変換されたメールボックス (現在は MailUser) オブジェクトの ExternalEmailAddress (targetAddress) を設定します。
 
**メールボックスのアクセス許可はどのように移行しますか?**

メールボックスのアクセス許可には、代理人としてのメールボックスアクセスが含まれています。 

- 代理人として送信 (AD: publicDelegates) は、代理人としてユーザーのメールボックスにアクセスできる受信者の DN を格納します。 この値は Active Directory に格納され、現在、メールボックスの移行の一部としては移動しません。 送信元メールボックスに publicDelegates が設定されている場合は、コマンドを使用して、対象の環境で MEU からメールボックスへの変換が完了した後、宛先メールボックスに対して publicDelegates を再度スタンプする必要があり `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` ます。 
 
- メールボックスに格納されているメールボックスのアクセス許可は、プリンシパルと代理人の両方が移動先のシステムに移動されたときに、メールボックスと共に移動します。 たとえば、ユーザー TestUser_7 には、テナント SourceCompany.onmicrosoft.com の TestUser_8 メールボックスに対する FullAccess が許可されています。 メールボックスの移動が TargetCompany.onmicrosoft.com に完了すると、ターゲットディレクトリにも同じアクセス許可が設定されます。 *Add-mailboxpermission*を使用したソースおよびターゲットテナントの TestUser_7 の例を次に示します。 Exchange コマンドレットの先頭には、source と target が付けられます。 
 
移動前のメールボックスアクセス許可の出力例を次に示します。 

```powershell
PS C:\DEMO Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
移動後のメールボックスのアクセス許可の出力例を次に示します。 

```powershell
C:\DEMO> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> テナント間メールボックスおよび予定表へのアクセス許可はサポートされていません。 これらの接続されたメールボックスがソーステナントから同時に遷移するように、プリンシパルとデリゲートを統合された移動バッチに整理する必要があります。 
 
## <a name="known-issues"></a>既知の問題 

-  **問題: 自動拡張アーカイブを移行できません。** テナント間の移行機能は、特定のユーザーのプライマリメールボックスとアーカイブメールボックスの移行をサポートしています。 ただし、ソース内のユーザーが自動拡張アーカイブを持っている場合 (複数のアーカイブメールボックスを対象としている場合)、追加のアーカイブを移行することはできません。

- **問題: 非所有の smtp proxyAddress ブロックを持つクラウドメールユーザーが背景を移動します。** ターゲットテナントの MailUser オブジェクトを作成する場合は、すべての SMTP プロキシアドレスがターゲットテナントの組織に属していることを確認する必要があります。 ローカルテナントに属していない宛先メールユーザーに SMTP proxyAddress が存在する場合、MailUser から Mailbox への変換は行われません。 これは、microsoft がメールボックスオブジェクトが権限を持つ (テナントによって要求された) ドメインからメールを送信できることを保証するためです。 
- 
   - Azure AD Connect を使用してオンプレミスのユーザーを同期する場合は、ExternalEmailAddress を使用してオンプレミスの MailUser オブジェクトをプロビジョニングします。これには、メールボックスが存在するソーステナント (laran@contoso \. onmicrosoft.com) を指定し、PrimarySMTPAddress をターゲットテナント (Newton@northwind Lara com) に存在するドメインとしてスタンプし \. ます。 これらの値は、テナントに同期し、適切なメールユーザーがプロビジョニングされ、移行の準備ができています。 オブジェクトの例を次に示します。
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > EmailAddresses/proxyAddresses 配列に *contoso. onmicrosoft \. com* アドレスが存在し *ません* 。

- **問題: "external" プライマリ SMTP アドレスを持つ MailUser オブジェクトが変更され、"内部" 企業の要求ドメインにリセットされる**

   MailUser オブジェクトは、ローカル以外のメールボックスへのポインターです。 テナント間のメールボックスの移行の場合、MailUser オブジェクトを使用して、ソースのメールボックス (ターゲット組織の観点から) またはターゲットメールボックス (送信元組織の観点) を表します。 MailUsers には、実際のメールボックスの smtp アドレス (ProxyTest \@ fabrikam \. onmicrosoft.com) と、ディレクトリ内のメールボックスユーザーの表示された smtp アドレスを表す primarysmtp アドレスをポイントする ExternalEmailAddress (targetAddress) があります。 一部の組織では、プライマリ SMTP アドレスを外部の SMTP アドレスとして表示することを選択します。これは、ローカルテナントが所有/確認したアドレス (contoso.com としてではなく fabrikam.com など) では表示されません。  ただし、ライセンス操作によって Exchange サービスプランオブジェクトが MailUser に適用されると、プライマリ SMTP アドレスが変更され、ローカル組織 (contoso.com) によって確認されたドメインとして表示されるようになります。 次の2つの理由が考えられます。
   
   - いずれかの Exchange サービスプランが MailUser に適用されると、ローカル組織が別のテナントからメールの送信、スプーフィング、またはメールを送信できないようにするために、Azure AD プロセスがプロキシスクラブの強制が開始されます。 このようなサービスプランを持つ受信者オブジェクトのすべての SMTP アドレスは、アドレスがローカル組織によって確認されていない場合は削除されます。 この例の場合と同様に、Fabikam \. com ドメインは contoso onmicrosoft.com テナントによって検証されないため、スクラブにより \. fabrikam com ドメインが削除され \. ます。 これらの外部ドメインを MailUser で保持する場合は、移行の前または移行後に、移行の完了後または移行後に、ライセンスを削除するように移行プロセスを変更する必要があります。これにより、ユーザーが期待する外部ブランドを適用していることを確認できます。 メールサービスに影響を与えないように、メールボックスオブジェクトが適切にライセンスされていることを確認する必要があります。<br/><br/>Contoso onmicrosoft.com テナントの MailUser のサービスプランを削除するスクリプトの例 \. を次に示します。

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       指定された ServicePlans のセットの結果をここに示します。

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
 
       ユーザーの PrimarySMTPAddress は scrubbed れなくなりました。 Fabrikam.com ドメインは contoso.onmicrosoft.com テナントによって所有されておらず、ディレクトリに表示されるプライマリ SMTP アドレスとして保持されます。

       次に例を示します。

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - MsexchremoterDeprovisionMailbox Pienttype が 8 () に設定されている場合、ターゲットテナントに移行されるオンプレミスのメールユーザーの場合、Azure のプロキシのスクラブロジックによって、所有されていないドメインが削除され、primarySMTP が所有ドメインにリセットされます。 オンプレミスのメールユーザーの Msexchenttype をオフにすると、プロキシスクラブロジックは適用されなくなります。 <br/><br>以下は、Exchange Online を含むサービスプランの完全なセットです。

   | 名前                                              |
   |---------------------------------------------------|
   | 高度な電子情報開示ストレージ (500 GB)               |
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
   | Exchange Online の非アクティブなユーザーアドオン              |
   | Exchange Online Kiosk                             |
   | Exchange Online Multi-Geo                         |
   | Exchange Online プラン 1                            |
   | Exchange Online POP                               |
   | Exchange Online Protection                        |
   | 情報の障壁                              |
   | Information Protection for Office 365 - Premium   |
   | Information Protection for Office 365 - Standard  |
   | MyAnalytics による洞察                           |
   | Microsoft 365 Advanced Auditing                   |
   | Microsoft Bookings                                |
   | Microsoft Business Center                         |
   | Microsoft MyAnalytics (フル機能)                      |
   | Office 365 Advanced eDiscovery                    |
   | Office 365 Advanced Threat Protection (プラン 1)    |
   | Office 365 Advanced Threat Protection (プラン 2)    |
   | Office 365 Privileged Access Management           |
   | Outlook Customer Manager                          |
   | Office 365 でのプレミアム暗号化                  |
   || 
 
