---
title: テナント間でのメールボックスの移行
description: テナント間でメールボックスを移動Microsoft 365またはOffice 365方法。
ms.author: kvice
author: kelleyvice-msft
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: 09/21/2020
ms.reviewer: georgiah
ms.custom:
- it-pro
- admindeeplinkMAC
- admindeeplinkEXCHANGE
ms.collection:
- M365-subscription-management
ms.openlocfilehash: e9ec5c27f5dabfa2df0f12ca6daecfcef860547c
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2022
ms.locfileid: "64499377"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>テナント間メールボックスの移行 (プレビュー)

一般的に、合併や売却の際には、ユーザーのメールボックスを新しいテナントにExchange Onlineする機能が必要です。 テナント間メールボックスの移行により、テナント管理者はリモート PowerShell や MRS のような既知のインターフェイスを使用して、ユーザーを新しい組織に移行できます。

管理者は、メールボックスの移動New-MigrationBatch役割を使用して、テナント間の移動を実行するために使用できる、New-MigrationBatch コマンドレットを使用できます。

移行するユーザーは、移行先のテナント Exchange Online MailUsers として存在し、テナント間の移動を有効にするには、特定の属性でマークされている必要があります。 ターゲット テナントで適切に設定されていないユーザーの移動はシステムによって失敗します。

移動が完了すると、移動元のユーザー メールボックスが MailUser に変換され、targetAddress (Exchange の ExternalEmailAddress として表示) が宛先テナントへのルーティング アドレスでスタンプされます。 このプロセスは、従来の MailUser をソース テナントに残し、共存とメール ルーティングを可能にします。 ビジネス プロセスで許可されている場合、ソース テナントはソース MailUser を削除するか、メール連絡先に変換できます。

ハイブリッドまたはクラウドExchange、または 2 つの任意の組み合わせのテナントに対して、複数テナント間のメールボックス移行がサポートされます。

この記事では、テナント間のメールボックス移動のプロセスについて説明し、メールボックス コンテンツの移動に対してソース テナントとターゲット テナントを準備する方法Exchange Online示します。

   > [!NOTE]
   > Azure Key Vault を不要にするように、テナント間メールボックスの移行を有効にするためのセットアップ手順が最近更新されました。 このプレビューに初めてオンボーディングを行う場合は、アクションは必要ありません。このドキュメントで説明されている手順に従ってください。 以前の AKV メソッドを使用してテナントの構成を開始した場合は、この新しい方法の使用を開始するために、その構成を停止または削除することを強くお勧めします。 以前の AKV メソッドでメールボックスの移行が進行中の場合は、既存の移行が完了するまで待ち、以下の手順に従って新しい簡略化された方法を有効にしてください。 Azure Key Vault に必要なセットアップ手順はアーカイブされますが、参照 **[のためにここで確認](https://github.com/microsoft/cross-tenant/wiki/V1-Content#cross-tenant-mailbox-migration-preview)** できます。

## <a name="preparing-source-and-target-tenants"></a>ソーステナントとターゲット テナントの準備

### <a name="prerequisites-for-source-and-target-tenants"></a>ソーステナントとターゲット テナントの前提条件

開始する前に、Azure、EXO 移行エンドポイント、EXO 組織の関係でメールボックスの移動アプリケーションを構成するために必要なアクセス許可を持っている必要があります。

さらに、ソース テナント内のメールが有効なセキュリティ グループが少なくとも 1 つ必要です。 これらのグループは、ソース (またはリソースとも呼ばれる) テナントからターゲット テナントに移動できるメールボックスの一覧の範囲を指定するために使用されます。 これにより、移行元テナント管理者は、移動する必要があるメールボックスの特定のセットを制限または範囲指定し、意図しないユーザーが移行されるのを防ぐことが可能になります。 入れ子になったグループはサポートされていません。

また、信頼できるパートナー企業 (メールボックスを移動する相手) と通信して、テナント ID を取得Microsoft 365必要があります。 このテナント ID は、[組織リレーションシップ ドメイン名] フィールドで使用されます。

サブスクリプションのテナント ID を取得するには、サブスクリプションに[サインインMicrosoft 365 管理センターに](https://go.microsoft.com/fwlink/p/?linkid=2024339)移動します[https://aad.portal.azure.com/\#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。 Tenant ID プロパティのコピー アイコンをクリックしてクリップボードにコピーします。

### <a name="configuration-steps-to-enable-your-tenants-for-cross-tenant-mailbox-migrations"></a>テナント間のメールボックス移行を有効にする構成手順

   > [!NOTE]
   > ターゲット (宛先) を最初に構成する必要があります。 これらの手順を完了するには、ソース テナントとターゲット テナントの両方のテナント管理者資格情報を持っている必要はありません。また、テナント管理者の資格情報を知る必要はありません。 手順は、異なる管理者によってテナントごとに個別に実行できます。

### <a name="prepare-the-target-destination-tenant-by-creating-the-migration-application-and-secret"></a>移行アプリケーションとシークレットを作成してターゲット (移行先) テナントを準備する

1. ターゲット テナント管理者資格情報Azure ADポータル (<https://portal.azure.com>) にログインします。

   ![Azure Logon](../media/tenant-to-tenant-mailbox-move/74f26681e12df3308c7823ee7d527587.png)

2. [管理] の下の [表示Azure Active Directory。

   ![Azure Active Directory ボタン](../media/tenant-to-tenant-mailbox-move/109ac3dfbac2403fb288f085767f393b.png)

3. 左側のナビゲーション バーで、[アプリの登録] を選択します。

4. [新しい登録] を選択する

   ![新しいアプリケーション](../media/tenant-to-tenant-mailbox-move/b36698df128e705eacff4bff7231056a.png)

5. [アプリケーションの登録] ページの [サポートされているアカウントの種類] で、[任意の組織ディレクトリのアカウント] を選択します (Any Azure AD - Multitenant)。 次に、[リダイレクト URI ](オプション)で、[Web] を選択し、と入力します <https://office.com>。 最後に、[登録] を選択します。

   ![アプリケーション登録](../media/tenant-to-tenant-mailbox-move/edcdf18b9f504c47284fe4afb982c433.png)

6. ページの右上隅に、アプリが正常に作成されたことを示す通知ポップアップが表示されます。

7. [ホーム] に戻り、[アプリAzure Active Directory] をクリックします。

8. [所有アプリケーション] で、作成したアプリを見つけてクリックします。

9. ^Essentials では、ターゲット テナントの URL を作成するために後で必要なアプリケーション (クライアント) ID をコピーダウンする必要があります。

10. 次に、左側のナビゲーション バーで[API のアクセス許可] をクリックして、アプリに割り当てられたアクセス許可を表示します。

11. 既定では、ユーザーです。 読み取りアクセス許可は、作成したアプリに割り当てられますが、メールボックスの移行には読み取りアクセス許可は必要としません。そのアクセス許可を削除できます。

    ![アプリケーション アクセス許可](../media/tenant-to-tenant-mailbox-move/6a8c13a36cb3e10964a6920b8138e12b.png)

12. メールボックスの移行に対するアクセス許可を追加する必要があります。[アクセス許可の追加] を選択します。

13. [API アクセス許可の要求] ウィンドウで、組織で使用する API を選択し、Office 365 Exchange Onlineして選択します。

    ![[API の選択]](../media/tenant-to-tenant-mailbox-move/0b4dc1eea3910e9c475724d9473aca58.png)

14. 次に、[アプリケーションのアクセス許可] を選択します。

15. 次に、[アクセス許可の選択] で [メールボックス] を展開し、[Mailbox.Migration] をオンにし、画面の下部にある [アクセス許可の追加] をオンにします。

    ![API の設定](../media/tenant-to-tenant-mailbox-move/0038a4cf74bb13de0feb51800e078803.png)

16. 次に、アプリケーション&左側のナビゲーション バーで [証明書とシークレット] を選択します。

17. [クライアント シークレット] で、[新しいクライアント シークレット] を選択します。

    ![クライアント シークレット](../media/tenant-to-tenant-mailbox-move/273dafd5e6c6455695f9baf35ef9977a.png)

18. [クライアント シークレットの追加] ウィンドウで説明を入力し、必要な有効期限設定を構成します。

      > [!NOTE]
      > これは、移行エンドポイントの作成時に使用されるパスワードです。 このパスワードをクリップボードにコピーするか、このパスワードを安全/秘密のパスワード安全な場所にコピーすることが非常に重要です。 このパスワードを確認できるのは、これが唯一の時間です。 何らかの方法で紛失したり、リセットする必要がある場合は、Azure portal にログインし、アプリ登録に移動し、移行アプリを見つけて、[Secrets & 証明書] を選択し、アプリの新しいシークレットを作成できます。

19. 移行アプリケーションとシークレットが正常に作成されたので、アプリケーションに同意する必要があります。 アプリケーションに同意するには、Azure Active Directory ランディング ページに戻り、左側のナビゲーションで Enterprise アプリケーションをクリックし、作成した移行アプリを見つけて選択し、左側のナビゲーションで [アクセス許可] を選択します。

20. [テナント] ボタンの [管理者の同意を許可する] をクリックします。

21. 新しいブラウザー ウィンドウが開き、[承諾] を選択します。

22. ポータル ウィンドウに戻り、[更新] を選択して受け入れを確認できます。

23. 信頼できるパートナー (ソース テナント管理者) に送信する URL を策定して、メールボックスの移行を有効にするためのアプリケーションを受け入れすることもできます。 作成したアプリのアプリケーション ID が必要な URL の例を次に示します。

    ```powershell
    https://login.microsoftonline.com/sourcetenant.onmicrosoft.com/adminconsent?client_id=[application_id_of_the_app_you_just_created]&redirect_uri=https://office.com
    ```

    > [!NOTE]
    > 作成したメールボックス移行アプリのアプリケーション ID が必要です。
    >
    > 上記の例の sourcetenant.onmicrosoft.com ソース テナントに正しい名前を onmicrosoft.com があります。
    >
    > [application_id_of_the_app_you_just_created] を、作成したメールボックス移行アプリのアプリケーション ID に置き換える必要があります。

### <a name="prepare-the-target-tenant-by-creating-the-exchange-online-migration-endpoint-and-organization-relationship"></a>移行エンドポイントと組織の関係を作成してExchange Onlineテナントを準備する

1. ターゲット テナントへのリモート PowerShell 接続Exchange Onlineします。

2. テナント間メールボックスの移動用に新しい移行エンドポイントを作成する

   > [!NOTE]
   > 作成したメールボックス移行アプリのアプリケーション ID と、このプロセス中に構成したパスワード (シークレット) が必要です。 また、エンドポイントを使用Microsoft 365クラウド インスタンスの種類によっては、異なる場合があります。 [エンドポイントのMicrosoft 365[]](/microsoft-365/enterprise/microsoft-365-endpoints) ページを参照し、テナントの適切なインスタンスを選択し、[必須アドレスの最適化] Exchange Onlineを確認し、必要に応じて置き換える必要があります。

   ```powershell
   
   # Enable customization if tenant is dehydrated
     $dehydrated=Get-OrganizationConfig | fl isdehydrated
     if ($dehydrated -eq $true) {Enable-OrganizationCustomization}
     
   $AppId = "[guid copied from the migrations app]"

   $Credential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $AppId, (ConvertTo-SecureString -String "[this is your secret password you saved in the previous steps]" -AsPlainText -Force)

   New-MigrationEndpoint -RemoteServer outlook.office.com -RemoteTenant "sourcetenant.onmicrosoft.com" -Credentials $Credential -ExchangeRemoteMove:$true -Name "[the name of your migration endpoint]" -ApplicationId $AppId
   ```

3. ソース テナントに対して、既存の組織リレーションシップ オブジェクトを作成または編集します。

   ```powershell
   $sourceTenantId="[tenant id of your trusted partner, where the source mailboxes are]"
   $orgrels=Get-OrganizationRelationship
   $existingOrgRel = $orgrels | ?{$_.DomainNames -like $sourceTenantId}
   If ($null -ne $existingOrgRel)
   {
       Set-OrganizationRelationship $existingOrgRel.Name -Enabled:$true -MailboxMoveEnabled:$true -MailboxMoveCapability Inbound
   }
   If ($null -eq $existingOrgRel)
   {
       New-OrganizationRelationship "[name of the new organization relationship]" -Enabled:$true -MailboxMoveEnabled:$true -MailboxMoveCapability Inbound -DomainNames $sourceTenantId
   }
   ```

### <a name="prepare-the-source-current-mailbox-location-tenant-by-accepting-the-migration-application-and-configuring-the-organization-relationship"></a>移行アプリケーションを受け入れ、組織の関係を構成して、移行元 (現在のメールボックスの場所) テナントを準備する

1. ブラウザーから、信頼できるパートナーが提供する URL リンクに移動して、メールボックス移行アプリケーションに同意します。 URL は次のように表示されます。

   ```powershell
   https://login.microsoftonline.com/sourcetenant.onmicrosoft.com/adminconsent?client_id=[application_id_of_the_app_you_just_created]&redirect_uri=https://office.com
   ```

   > [!NOTE]
   > 作成したメールボックス移行アプリのアプリケーション ID が必要です。
   > 上記の例の sourcetenant.onmicrosoft.com ソース テナントに正しい名前を onmicrosoft.com があります。
   > [application_id_of_the_app_you_just_created] を、作成したメールボックス移行アプリのアプリケーション ID に置き換える必要があります。

2. ポップアップが表示されたら、アプリケーションを受け入れます。 ポータルにログインして、Azure Active Directoryアプリケーションの下にあるアプリケーションEnterpriseすることもできます。

3. リモート PowerShell ウィンドウから、既存の組織リレーションシップ オブジェクトをターゲット (宛先) テナントに対してExchange Online編集します。

   ```powershell
   $targetTenantId="[tenant id of your trusted partner, where the mailboxes are being moved to]"
   $appId="[application id of the mailbox migration app you consented to]"
   $scope="[name of the mail enabled security group that contains the list of users who are allowed to migrate]"
   $orgrels=Get-OrganizationRelationship
   $existingOrgRel = $orgrels | ?{$_.DomainNames -like $targetTenantId}
   If ($null -ne $existingOrgRel)
   {
       Set-OrganizationRelationship $existingOrgRel.Name -Enabled:$true -MailboxMoveEnabled:$true -MailboxMoveCapability RemoteOutbound -OAuthApplicationId $appId -MailboxMovePublishedScopes $scope
   }
   If ($null -eq $existingOrgRel)
   {
       New-OrganizationRelationship "[name of your organization relationship]" -Enabled:$true -MailboxMoveEnabled:$true -MailboxMoveCapability RemoteOutbound -DomainNames $targetTenantId -OAuthApplicationId $appId -MailboxMovePublishedScopes $scope
   }
   ```
   
> [!NOTE]
> テナントドメイン名として入力した$sourceTenantId ID $targetTenantId GUID であり、テナント ドメイン名ではありません。 テナント ID の例とテナント ID の検索に関する情報については、「[Find your your Microsoft 365テナント ID」を参照してください](/onedrive/find-your-office-365-tenant-id)。
   
### <a name="how-do-i-know-this-worked"></a>設定が適用されたことを確認する方法

ターゲット テナントで作成したクロステナント移行エンドポイントに対して [Test-MigrationServerAvailability](/powershell/module/exchange/Test-MigrationServerAvailability) コマンドレットを実行することで、テナント間メールボックスの移行構成を確認できます。

   > [!NOTE]
   >
   > - ターゲット テナント:
   > 
   > Test-MigrationServerAvailability -Endpoint "[クロステナント移行エンドポイントの名前]"
   >
   > Get-OrganizationRelationship |fl 名、DomainNames、MailboxMoveEnabled、MailboxMoveCapability
   >
   > - ソース テナント:
   > 
   > Get-OrganizationRelationship |fl 名、DomainNames、MailboxMoveEnabled、MailboxMoveCapability 

### <a name="move-mailboxes-back-to-the-original-source"></a>メールボックスを元のソースに戻す

メールボックスを元のソース テナントに戻す必要がある場合は、新しいソース テナントと新しいターゲット テナントの両方で同じ手順とスクリプトを実行する必要があります。 既存の Organization Relationship オブジェクトは更新または追加され、再作成されません。

## <a name="prepare-target-user-objects-for-migration"></a>移行用にターゲット ユーザー オブジェクトを準備する

移行するユーザーは、ターゲット テナントに存在し、Exchange Onlineシステム (MailUsers) に特定の属性でマークを付け、テナント間の移動を有効にする必要があります。 ターゲット テナントで適切に設定されていないユーザーの移動はシステムによって失敗します。 次のセクションでは、ターゲット テナントの MailUser オブジェクト要件について説明します。

### <a name="prerequisites-for-target-user-objects"></a>ターゲット ユーザー オブジェクトの前提条件

次のオブジェクトと属性がターゲット組織で設定されている必要があります。

1. 移行元組織から移動するメールボックスの場合は、ターゲット組織で MailUser オブジェクトを準備する必要があります。

   - ターゲット MailUser には、ソース メールボックスからの属性、または新しい User オブジェクトが割り当てられている必要があります。
      - ExchangeGUID (ソースからターゲットへの直接フロー): メールボックス GUID が一致している必要があります。 移動プロセスは、ターゲット オブジェクトに存在しない場合は続行できません。
      - ArchiveGUID (ソースからターゲットへの直接フロー): アーカイブ GUID が一致している必要があります。 移動プロセスは、ターゲット オブジェクトに存在しない場合は続行できません。 (これは、ソース メールボックスがアーカイブが有効になっている場合にのみ必要です)。
      - LegacyExchangeDN (flow as proxyAddress, "x500:\<LegacyExchangeDN>"): LegacyExchangeDN は、ターゲット MailUser に x500: proxyAddress として存在する必要があります。 さらに、ソース メールボックスからターゲット メール ユーザーにすべての x500 アドレスをコピーする必要があります。 移動プロセスは、ターゲット オブジェクトに存在しない場合は続行できません。
      - UserPrincipalName: UPN は、ユーザーの新しい ID またはターゲット企業 (たとえば、ユーザーの ID) に user@northwindtraders.onmicrosoft.com。
      - プライマリ SMTPAddress: プライマリ SMTP アドレスは、ユーザーの新しい会社 (たとえば、user@northwind.com) に合 user@northwind.com。
      - TargetAddress/ExternalEmailAddress: MailUser は、ソース テナントでホストされているユーザーの現在のメールボックスを参照します (たとえば、user@contoso.onmicrosoft.com)。 この値を割り当てる場合は、PrimarySMTPAddress を割り当てまたは割り当て中か、この値によって PrimarySMTPAddress が設定され、移動エラーが発生します。
      - 移行元メールボックスからターゲット MailUser に従来の smtp プロキシ アドレスを追加することはできません。 たとえば、テナント オブジェクトの MEU contoso.com を維持 fabrikam.onmicrosoft.com できません)。 ドメインは、1 つのテナントAzure ADまたはExchange Online関連付けられる。

     MailUser **オブジェクト** の例:

     | 属性            | 値                                                                                                                   |
     | -------------------- | ----------------------------------------------------------------------------------------------------------------------- |
     | Alias                | LaraN                                                                                                                   |
     | RecipientType        | MailUser                                                                                                                |
     | RecipientTypeDetails | MailUser                                                                                                                |
     | UserPrincipalName    | LaraN@northwintraders.onmicrosoft.com                                                                                   |
     | PrimarySmtpAddress   | Lara.Newton@northwind.com                                                                                               |
     | ExternalEmailAddress | SMTP:LaraN@contoso.onmicrosoft.com                                                                                      |
     | ExchangeGuid         | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                    |
     | LegacyExchangeDN     | /o=First Organization/ou=Exchangeグループ                                                                  |
     |                      | (FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara                                                 |
     | EmailAddresses       | x500:/o=First Organization/ou=Exchange 管理グループ (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190 |
     |                      | 7273f1f9-Lara                                                                                                           |
     |                      | smtp:LaraN@northwindtraders.onmicrosoft.com                                                                             |
     |                      | SMTP:Lara.Newton@northwind.com                                                                                          |
     |                      |                                                                                                                         |

     ソース **メールボックス オブジェクト** の例:

     | 属性            | 値                                                                   |
     | -------------------- | ----------------------------------------------------------------------- |
     | Alias                | LaraN                                                                   |
     | RecipientType        | UserMailbox                                                             |
     | RecipientTypeDetails | UserMailbox                                                             |
     | UserPrincipalName    | LaraN@contoso.onmicrosoft.com                                           |
     | PrimarySmtpAddress   | Lara.Newton@contoso.com                                                 |
     | ExchangeGuid         | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                    |
     | LegacyExchangeDN     | /o=First Organization/ou=Exchangeグループ                  |
     |                      | (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara |
     | EmailAddresses       | smtp:LaraN@contoso.onmicrosoft.com                                      |
     |                      | SMTP:Lara.Newton@contoso.com                                            |
     |                      |                                                                         |

   - ハイブリッドライトバックに追加の属性Exchange含まれている場合があります。 含まれていない場合は、含める必要があります。
   - msExchBlockedSendersHash – クライアントからオンプレミスの Active Directory にオンラインセーフでブロックされた送信者データを書き込みます。
   - msExchSafeRecipientsHash – クライアントからオンプレミスの Active Directory にオンラインセーフでブロックされた送信者データを書き込みます。
   - msExchSafeSendersHash – クライアントからオンプレミスの Active Directory にオンラインセーフでブロックされた送信者データを書き込みます。

2. ソース メールボックスが LitigationHold に設定され、ソース メールボックスの回復可能なアイテムのサイズがデータベースの既定値 (30 GB) よりも大きい場合、ターゲット クォータがソース メールボックスのサイズより小さいので、移動は続行されません。 ターゲット MailUser オブジェクトを更新して、ELC メールボックス フラグをソース環境からターゲットに移行できます。これにより、ターゲット システムは MailUser のクォータを 100 GB に拡張し、ターゲットへの移動を許可します。 これらの手順は、ELC フラグをスタンプするコマンドがテナント管理者に公開されないので、Azure AD Connect を実行しているハイブリッド ID でのみ機能します。

    > [!NOTE]
    > サンプル – 現在、保証なし
    >
    > このスクリプトは、ソース メールボックス (ソース値を取得する) とターゲットのオンプレミス Active Directory (ADUser オブジェクトにスタンプを押す) の両方への接続を前提としています。 ソースで訴訟または単一アイテムの回復が有効になっている場合は、コピー先アカウントでこれを設定します。  これにより、宛先アカウントのゴミ箱のサイズが 100 GB に増加します。

    ```powershell
    $ELCValue = 0
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}}
    ```

3. ハイブリッド以外のターゲット テナントは、次のコマンドを実行して MailUser オブジェクトの訴訟ホールドを有効にし、クォータを 100 GB `Set-MailUser -EnableLitigationHoldForMigration`に増やして、移行前に MailUsers の回復可能なアイテム フォルダーのクォータを変更できます。 これは、ハイブリッドのテナントでは機能しません。

4. ターゲット組織のユーザーは、組織に適用可能な適切なサブスクリプションExchange Onlineライセンスを受け取る必要があります。 メールボックスの移動の前にライセンスを適用できますが、対象の MailUser が ExchangeGUID とプロキシ アドレスで適切に設定されている場合にのみ適用できます。 ExchangeGUID を適用する前にライセンスを適用すると、新しいメールボックスがターゲット組織にプロビジョニングされます。

    > [!NOTE]
    > Mailbox オブジェクトまたは MailUser オブジェクトにライセンスを適用すると、すべての SMTP タイプの proxyAddresses がスクラブされ、確認済みのドメインだけが Exchange EmailAddresses 配列に含まれるか確認されます。

5. ターゲットの MailUser に、ソース ExchangeGuid と一致しない以前の ExchangeGuid が存在しなかっている必要があります。 これは、ターゲット MEU が以前にメールボックスのライセンスを取得し、Exchange Onlineされている場合に発生する可能性があります。 ターゲットの MailUser が以前に ExchangeGuid のライセンスを取得していたか、ソース ExchangeGuid と一致しない ExchangeGuid を持っていた場合は、クラウド MEU のクリーンアップを実行する必要があります。 これらのクラウド MEUs では、実行できます `Set-User <identity> -PermanentlyClearPreviousMailboxInfo`。

    > [!CAUTION]
    > このプロセスは不可逆的です。 オブジェクトに softDeleted メールボックスがある場合、この時点以降は復元できません。 ただし、クリアすると、正しい ExchangeGuid をターゲット オブジェクトに同期し、MRS は新しく作成されたターゲット メールボックスにソース メールボックスを接続します。 (新しいパラメーターに関する EHLO ブログを参照してください)。

    このコマンドを使用して、以前メールボックスだったオブジェクトを検索します。

    ```powershell
    Get-User <identity> | select Name, *recipient* | Format-Table -AutoSize
    ```

    次に例を示します。

    ```powershell
    Get-User John@northwindtraders.com |select name, *recipient*| Format-Table -AutoSize

    Name       PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails
    ----       ---------------------------- ------------- --------------------
    John       UserMailbox                  MailUser      MailUser
    ```

    このコマンドを使用して、削除済みメールボックスを消去します。

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    次に例を示します。

    ```powershell
    Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo -Confirm
    
    Are you sure you want to perform this action?
    Delete all existing information about user "John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.
    Do you want to continue?
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y
    ```

### <a name="perform-mailbox-migrations"></a>メールボックスの移行を実行する

移行バッチとしてExchangeテナント間の移行がターゲット テナントから開始されます。 これは、オンプレミスからオンプレミスへの移行時にオンボーディング移行バッチExchange動作する方法Microsoft 365。

### <a name="create-migration-batches"></a>移行バッチの作成

移動を開始する移行バッチ コマンドレットの例を次に示します。

```powershell
New-MigrationBatch -Name T2Tbatch -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain target.onmicrosoft.com

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch                   Syncing ExchangeRemoteMove 1
```

> [!NOTE]
> CSV ファイルの電子メール アドレスは、ソース テナントではなく、ターゲット テナントで指定された電子メール アドレスである必要があります。
>
> [コマンドレットの詳細については、こちらをクリックしてください。](/powershell/module/exchange/new-migrationbatch)
>
> [CSV ファイルの例については、ここをクリックしてください](/exchange/csv-files-for-mailbox-migration-exchange-2013-help)

移行バッチの申請は、クロステナント オプションを選択Exchange<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">管理センター</a>からサポートされます。

### <a name="update-on-premises-mailusers"></a>オンプレミスの MailUsers を更新する

メールボックスがソースからターゲットに移動したら、ソースとターゲットの両方で、オンプレミスのメール ユーザーが新しい targetAddress で更新されます。 例では、移動で使用される targetDeliveryDomain **が contoso.onmicrosoft.com**。 この targetAddress を使用してメール ユーザーを更新します。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**移動後に、オンプレミスのソースで RemoteMailboxes を更新する必要がありますか?**

はい、ソース テナント メールボックスがターゲット テナントに移動するときに、ソースのオンプレミス ユーザーの targetAddress (RemoteRoutingAddress/ExternalEmailAddress) を更新する必要があります。  メール ルーティングは、異なる targetAddresses を持つ複数のメール ユーザー間の参照に従う場合があります。メール ユーザーの空き時間情報の参照はメールボックス ユーザーの場所をターゲットにしている必要があります。 空き時間情報の参照は、複数のリダイレクトを追跡しない。

**会議Teamsテナント間で移行しますか?**

会議は移動しますが、アイテムがクロステナントTeams移行しても、会議の URL は更新されません。 URL はターゲット テナントで無効になりますので、会議を削除して再作成Teamsがあります。

**チャット フォルダー Teamsクロステナントを移行しますか?**

いいえ、Teamsフォルダーのコンテンツはクロステナントを移行できません。

**オンボーディングとオフボーディングの移動ではなく、テナント間の移動である移動を確認する方法**

Flags パラメーター _を使用_ します。 次に例を示します。

```powershell
Get-MoveRequest -Flags "CrossTenant"
```

**テストで使用する属性をコピーするためのスクリプトの例を提供できますか?**

> [!NOTE]
> SAMPLE – AS IS, NO WARRANTY このスクリプトは、ソース メールボックス (ソース値を取得する) とターゲットのオンプレミス Active Directory ドメイン サービス (ADUser オブジェクトにスタンプを押す) の両方への接続を前提としています。 ソースで訴訟または単一アイテムの回復が有効になっている場合は、コピー先アカウントでこれを設定します。  これにより、宛先アカウントのゴミ箱のサイズが 100 GB に増加します。



   ```powershell
   # This will export users from the source tenant with the CustomAttribute1 = "Cross-Tenant-Project"
   # These are the 'target' users to be moved to the Northwind org tenant
   $outFileUsers = "$home\desktop\UsersToMigrate.txt"
   $outFileUsersXML = "$home\desktop\UsersToMigrate.xml"
   Get-Mailbox -Filter "CustomAttribute1 -like 'Cross-Tenant-Project'" -ResultSize Unlimited | Select-Object -ExpandProperty  Alias | Out-File $outFileUsers
   $mailboxes = Get-Content $outFileUsers
   $mailboxes | ForEach-Object {Get-Mailbox $_} | Select-Object PrimarySMTPAddress,Alias,SamAccountName,FirstName,LastName,DisplayName,Name,ExchangeGuid,ArchiveGuid,LegacyExchangeDn,EmailAddresses | Export-Clixml $outFileUsersXML
   ```

   ```powershell
   # Copy the file $outfile to the desktop of the target on-premises then run the below to create MEU in Target
   $mailboxes = Import-Clixml $home\desktop\UsersToMigrate.xml
   add-type -AssemblyName System.Web
   foreach ($m in $mailboxes) {
       $organization = "@contoso.onmicrosoft.com"
       $mosi = $m.Alias+$organization
       $Password = [System.Web.Security.Membership]::GeneratePassword(16,4) | ConvertTo-SecureString -AsPlainText -Force
       $x500 = "x500:" +$m.LegacyExchangeDn
       $tmpUser = New-MailUser -MicrosoftOnlineServicesID $mosi -PrimarySmtpAddress $mosi -ExternalEmailAddress $m.PrimarySmtpAddress -FirstName $m.FirstName -LastName $m.LastName -Name $m.Name -DisplayName $m.DisplayName -Alias $m.Alias -Password $Password
       $tmpUser | Set-MailUser -EmailAddresses @{add=$x500} -ExchangeGuid $m.ExchangeGuid -ArchiveGuid $m.ArchiveGuid -CustomAttribute1 "Cross-Tenant-Project"
       $tmpx500 = $m.EmailAddresses | ?{$_ -match "x500"}
       $tmpx500 | %{Set-MailUser $m.Alias -EmailAddresses @{add="$_"}}
       }
   ```

   ```powershell
   # Now sync the changes from On-Premises to Azure and Exchange Online in the Target tenant
   # This action should create the target mail enabled users (MEUs) in the Target tenant
   Start-ADSyncCycle
   ```

**使用メールボックスを移動Outlook 1 日目にアクセスする方法**

1 つのテナントだけがドメインを所有できるので、メールボックスの移動が完了すると、以前のプライマリ SMTPAddress はターゲット テナントのユーザーに関連付けされません。新しいテナントに関連付けられているドメインのみ。 Outlook新しい UPN を使用してサービスに対する認証を行い、Outlook プロファイルは、ターゲット システム内のメールボックスに一致するレガシ プライマリ SMTPAddress を見つける必要があります。 従来のアドレスがターゲットシステムに含されていないので、Outlook プロファイルは新しく移動されたメールボックスを見つけるために接続されません。

この初期展開では、ユーザーは新しい UPN、プライマリ SMTP アドレス、および再同期 OST コンテンツを使用してプロファイルを再構築する必要があります。

> [!NOTE]
> 完了のためにユーザーをバッチ処理する場合は、必要に応じて計画します。 クライアント プロファイルが作成され、後続の OST および OAB ファイルがクライアントにダウンロードOutlookネットワーク使用率と容量を考慮する必要があります。

**テナント間Exchangeを設定または完了するには、RBAC の役割のメンバーである必要がある役割を説明します。**

メールボックスの移動を実行する際の委任された職務の前提に基づく役割のマトリックスがあります。 現在、2 つの役割が必要です。

- 最初の役割は、テナント/組織の境界にコンテンツを移動または外に移動する権限を確立する 1 回のセットアップ タスクです。 組織の管理からデータを移動すると、すべての企業にとって重要な懸念事項となります。組織管理者 (OrgAdmin) の最も高い割り当てられた役割を選択しました。 この役割は、リモート組織で -MailboxMoveCapability を定義する新しい OrganizationRelationship を変更または設定する必要があります。 MailboxMoveCapability 設定を変更できるのは OrgAdmin のみですが、OrganizationRelationship の他の属性はフェデレーション共有管理者が管理できます。

- 実際の移動コマンドを実行する役割は、下位レベルの関数に委任できます。 メールボックスの移動の役割は、組織内または組織外でメールボックスを移動する機能に割り当てられます。

**変換されたメールボックスの targetAddress (TargetDeliveryDomain) に選択されている SMTP アドレスを (MailUser 変換に) ターゲットにする方法を説明します。**

Exchangeのメール アドレス (proxyAddress) を照合して MailUser に変換するときに、MRS を使用して移動する場合は、元のソース メールボックスの targetAddress を作成します。 このプロセスは、move コマンドに渡される -TargetDeliveryDomain 値を受け取り、ターゲット側のそのドメインの一致するプロキシをチェックします。 一致を見つけると、一致する proxyAddress を使用して、変換されたメールボックス (現在の MailUser) オブジェクトに ExternalEmailAddress (targetAddress) を設定します。

**メールボックスのアクセス許可の移行方法**

メールボックスのアクセス許可には、代理送信とメールボックス アクセスが含まれます。

- Send On Behalf Of (AD:publicDelegates) は、代理人としてユーザーのメールボックスにアクセスできる受信者の DN を格納します。 この値は Active Directory に格納され、現在はメールボックスの移行の一部として移動されません。 ソース メールボックスに publicDelegates が設定されている場合は、MEU からメールボックスへの変換が実行によってターゲット環境で完了したら、ターゲット メールボックスの publicDelegates を再サンプリングする必要があります `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>`。

- メールボックスに格納されているメールボックスのアクセス許可は、プリンシパルと代理人の両方がターゲット システムに移動すると、メールボックスと共に移動します。 たとえば、ユーザーがTestUser_7に FullAccess が付与TestUser_8メールボックスにアクセス SourceCompany.onmicrosoft.com。 メールボックスの移動が完了すると、TargetCompany.onmicrosoft.com ディレクトリに同じアクセス許可が設定されます。 ソース テナントとターゲット テナントの両方TestUser_7 *Get-MailboxPermission* を使用する例を以下に示します。 Exchangeコマンドレットには、ソースとターゲットのプレフィックスが付けされます。

移動前のメールボックスアクセス許可の出力例を次に示します。

```powershell
Get-SourceMailboxPermission TestUser_7 | Format-Table -AutoSize User, AccessRights, IsInherited, Deny

User                                             AccessRights                         IsInherited Deny
----                                             ------------                         ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}         False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                         False       False
```

移動後のメールボックスアクセス許可の出力例を次に示します。

```powershell
Get-TargetMailboxPermission TestUser_7 | Format-Table -AutoSize User, AccessRights, IsInherited, Deny

User                                             AccessRights                         IsInherited Deny
----                                             ------------                         ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}         False       False
TestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                         False       False
```

> [!NOTE]
> テナント間のメールボックスと予定表のアクセス許可はサポートされていません。 プリンシパルと代理人を統合移動バッチに整理して、接続されているこれらのメールボックスがソース テナントから同時に移行される必要があります。

**移行を有効にするには、どの X500 プロキシをターゲットの MailUser プロキシ アドレスに追加する必要がありますか?**

テナント間メールボックスの移行では、ソース メールボックス オブジェクトの LegacyExchangeDN 値を、ターゲット MailUser オブジェクトの x500 メール アドレスとしてスタンプする必要があります。

例:

```powershell
LegacyExchangeDN value on source mailbox is:
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara

so, the x500 email address to be added to target MailUser object would be:
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara
```

> [!NOTE]
> この X500 プロキシに加えて、ソース内のメールボックスからすべての X500 プロキシをターゲットのメールボックスにコピーする必要があります。

**ソーステナントとターゲット テナントは同じドメイン名を使用できますか?**

いいえ。 ソーステナントとターゲットテナントのドメイン名は一意である必要があります。 たとえば、ドメインのソース ドメインと contoso.com のターゲット ドメイン fourthcoffee.com。

**共有メールボックスは移動し、引き続き機能しますか?**

はい、ただし、次の記事の説明に従ってストアのアクセス許可のみを保持します。

- [Microsoft Docs |ユーザーの受信者のアクセス許可を管理Exchange Online](/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [Microsoft サポート |専用のメールボックスExchangeアクセスOutlookを付与するOffice 365方法](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

**バッチに関する推奨事項はありますか?**

バッチあたりのメールボックス数は 2000 を超えないようにしてください。 同期中にエンド ユーザーに影響が出ない場合は、カットオーバー日の 2 週間前にバッチを送信することを強く推奨します。 50,000 を超えるメールボックスの数量に関するガイダンスが必要な場合は、次のページでエンジニアリング フィードバック配布リストに crosstenantmigrationpreview@service.microsoft.com。

**顧客キーでサービス暗号化を使用する場合は、**

メールボックスは移動前に復号化されます。 顧客キーがまだ必要な場合は、ターゲット テナントで顧客キーが構成されていることを確認します。 詳細 [については、](/microsoft-365/compliance/customer-key-overview) こちらを参照してください。

**推定移行時間は何ですか?**

移行を計画する際に役立つ、次[](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times)の表に、メールボックスの一括移行または個々の移行が完了すると予想される場合のガイドラインを示します。 これらの見積もりは、以前の顧客移行のデータ分析に基づいて行います。 すべての環境が一意なので、正確な移行速度は異なる場合があります。

この機能は現在プレビュー中であり、SLA であり、該当するサービス レベルは、この機能のプレビュー状態の間、パフォーマンスや可用性の問題には適用されません。

**ソース テナント内のドキュメントを、コピー先テナントのユーザーが使用できる保護します。**

テナント間の移行では、メールボックス データだけが移行され、それ以外は移行されません。 他にも複数のオプションがあります。これは、次のブログ投稿に記載されています。 <https://techcommunity.microsoft.com/t5/security-compliance-and-identity/mergers-and-spinoffs/ba-p/910455>

**移行先テナント内のラベルは、組織間の配置に応じて、移行されたユーザーのラベルのセットまたは追加のラベルのセットとして、移行元テナントと同じラベルを作成できます。**

クロステナント移行ではラベルがエクスポートされないので、テナント間でラベルを共有する方法はありません。これは、移行先テナントでラベルを再作成することでのみ実現できます。

**グループの移動をMicrosoft 365しますか?**

現在、テナント間メールボックスの移行機能では、グループ間の移行Microsoft 365されていません。

**移行元テナント管理者は、メールボックスが新しい/ターゲット テナントに移行された後、メールボックスに対して電子情報開示検索を実行できますか?**

いいえ、テナント間メールボックスの移行後、移行元の移行済みユーザーのメールボックスに対する電子情報開示は機能しません。 これは、メールボックスがターゲット テナントに移行され、ターゲット テナントに属している間に、検索対象のメールボックスがソースに存在しなくなったためです。 電子情報開示では、メールボックスの移行後は、ターゲット テナント (メールボックスが現在存在する場所) でのみ実行できます。 移行後にソース メールボックスのコピーをソース テナントに保持する必要がある場合、ソースの管理者は、データに対する将来の電子情報開示操作のために、移行前の代替メールボックスにコンテンツをコピーできます。

## <a name="known-issues"></a>既知の問題

- **問題: 移行後Teamsテナントの機能が制限されます。** メールボックスがターゲット テナントに移行された後、Teamsテナント内のユーザーがユーザーのメールボックスにアクセスできなくなりました。 そのため、ユーザーがソース テナント資格情報を使用して Teams にログインすると、プロファイル画像を更新する機能が失われる、予定表アプリケーションがない、パブリック チームを検索して参加できません。

- **問題: 自動拡張アーカイブを移行できません。** テナント間移行機能は、特定のユーザーのプライマリ メールボックスとアーカイブ メールボックスの移行をサポートします。 ただし、ソース内のユーザーが自動拡張アーカイブ (複数のアーカイブ メールボックスを意味する) を持つ場合、この機能は追加のアーカイブを移行できず、失敗する必要があります。

- **問題: 所有されていない smtp proxyAddress ブロック MRS がバックグラウンドを移動するクラウド MailUsers。** ターゲット テナントの MailUser オブジェクトを作成する場合は、すべての SMTP プロキシ アドレスがターゲット テナント組織に属している必要があります。 ローカル テナントに属していないターゲット メール ユーザーに SMTP proxyAddress が存在する場合、MailUser からメールボックスへの変換は防止されます。 これは、メールボックス オブジェクトが、テナントが権限を持つドメイン (テナントが要求するドメイン) からのみメールを送信できるという保証が原因です。

  - Azure AD Connect を使用してオンプレミスからユーザーを同期する場合は、メールボックスが存在するソース テナント (LaraN@contoso.onmicrosoft.com) を指す ExternalEmailAddress を使用してオンプレミスの MailUser オブジェクトをプロビジョニングし、PrimarySMTPAddress をターゲット テナント (Lara.Newton@northwind.com) に存在するドメインとしてスタンプします。 これらの値はテナントに同期され、適切なメール ユーザーがプロビジョニングされ、移行の準備が整います。 オブジェクトの例を次に示します。

    ```powershell
    Get-MailUser LaraN | select ExternalEmailAddress, EmailAddresses

    ExternalEmailAddress               EmailAddresses
    --------------------               --------------
    SMTP:LaraN@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com}
    ```

   > [!NOTE]
   > 電子 *contoso.onmicrosoft.com* アドレス *が* EmailAddresses/proxyAddresses 配列に存在しない。

- **問題: "外部" プライマリ SMTP アドレスを持つ MailUser オブジェクトが変更/リセットされ、"内部" の会社が要求したドメインにリセットされる**

  MailUser オブジェクトは、ローカル以外のメールボックスへのポインターです。 テナント間メールボックスの移行の場合、MailUser オブジェクトを使用して、ソース メールボックス (ターゲット組織の観点から) またはターゲット メールボックス (ソース組織の観点から) を表します。 MailUsers には、ディレクトリ内のメールボックス ユーザーの表示される SMTP アドレスを表す、実際のメールボックス (ProxyTest@fabrikam.onmicrosoft.com) の smtp アドレスと primarySMTP アドレスをポイントする ExternalEmailAddress (targetAddress) があります。 一部の組織では、プライマリ SMTP アドレスを外部 SMTP アドレスとして表示し、ローカル テナントが所有/検証したアドレス (fabrikam.com など)として表示 contoso.com。  ただし、Exchange サービスプラン オブジェクトがライセンス操作を介して MailUser に適用されると、プライマリ SMTP アドレスが変更され、ローカル組織 (contoso.com) によって確認されたドメインとして表示されます。 次の 2 つの潜在的な理由があります。

  - Exchange サービス プランが MailUser に適用されると、Azure AD プロセスはプロキシ スクラブの適用を開始して、ローカル組織が別のテナントからメールを送信、スプーフィング、またはメールを送信できないか確認します。 これらのサービス プランを持つ受信者オブジェクト上の SMTP アドレスは、ローカル組織によってアドレスが確認されていない場合は削除されます。 例の場合と同様に、Fabikam.com ドメインは contoso.onmicrosoft.com テナントによって検証されないので、スクラブによってそのドメイン fabrikam.com されます。 移行前または移行後にこれらの外部ドメインを MailUser に保持する場合は、移行が完了した後、または移行前に移行プロセスを変更してライセンスを削除し、ユーザーが予期した外部ブランド化を適用する必要があります。 メールボックス オブジェクトがメール サービスに影響を与えずに適切にライセンスされていることを確認する必要があります。
  - テナント内の MailUser のサービス プランを削除するスクリプト contoso.onmicrosoft.com 次に示します。

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTELLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION"
    Set-MsolUserLicense -UserPrincipalName ProxyTest@contoso.com LicenseOptions $lo
    ```

       割り当てられた ServicePlans のセットの結果を次に示します。

    ```powershell
    (Get-MsolUser -UserPrincipalName ProxyTest@contoso.com).licenses | Select-Object -ExpandProperty ServiceStatus |sort ProvisioningStatus -Descending

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

    ユーザーの PrimarySMTPAddress がスクラブされなくなりました。 ドメイン fabrikam.com はテナントが所有 contoso.onmicrosoft.com、ディレクトリに表示されるプライマリ SMTP アドレスとして保持されます。

    次に例を示します。

    ```powershell
    Get-Recipient ProxyTest | Format-Table -AutoSize UserPrincipalName, PrimarySmtpAddress, ExternalEmailAddress, ExternalDirectoryObjectId
    UserPrincipalName               PrimarySmtpAddress              ExternalEmailAddress                 ExternalDirectoryObjectId
    -----------------               ------------------              --------------------                 -------------------------
    ProxyTest@fabrikam.com          ProxyTest@fabrikam.com          SMTP:ProxyTest@fabrikam.com          e2513482-1d5b-4066-936a-cbc7f8f6f817
    ```

    - msExchRemoteRecipientType が 8 (DeprovisionMailbox) に設定されている場合、ターゲット テナントに移行されるオンプレミスの MailUser の場合、Azure のプロキシ スクラブ ロジックは所有されていないドメインを削除し、primarySMTP を所有ドメインにリセットします。 オンプレミスの MailUser で msExchRemoteRecipientType をクリアすると、プロキシ スクラブ ロジックは適用されなくなりました。

      以下に、現在のサービス プランの完全なセットを示Exchange Online。

      | 名前                                             |
      | ------------------------------------------------ |
      | Advanced eDiscovery Storage (500 GB)              |
      | 顧客ロックボックス                                 |
      | データ損失防止                             |
      | Exchange Enterprise CAL サービス (EOP、DLP)      |
      | Exchange Essentials                              |
      | Exchange財団                              |
      | Exchange Online (P1)                             |
      | Exchange Online (プラン 1)                         |
      | Exchange Online (プラン 2)                         |
      | Exchange Online 用の Exchange Online Archiving    |
      | Exchange Server 用の Exchange Online Archiving    |
      | Exchange Online非アクティブ ユーザー アドオン             |
      | Exchange Online Kiosk                            |
      | Exchange Online Multi-Geo                        |
      | Exchange Online プラン 1                           |
      | Exchange Online POP                              |
      | Exchange Online Protection                       |
      | 情報バリア                             |
      | Information Protection for Office 365 - Premium  |
      | Information Protection for Office 365 - Standard |
      | インサイト By MyAnalytics                          |
      | Microsoft 365高度な監査                  |
      | Microsoft Bookings                               |
      | Microsoft Business Center                        |
      | Microsoft MyAnalytics (フル機能)                     |
      | Office 365 Advanced eDiscovery                   |
      | Microsoft Defender for Office 365 (プラン 1)       |
      | Microsoft Defender for Office 365 (プラン 2)       |
      | Office 365 Privileged Access Management          |
      | プレミアムの暗号化Office 365                 |
      |                                                  |
