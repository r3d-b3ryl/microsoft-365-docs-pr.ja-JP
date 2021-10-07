---
title: 21Vianet がOffice 365 Azure Information Protection のサポート
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: 21Vianet が運用する 21Vianet Office 365 Azure Information Protection (AIP) の詳細と、中国の顧客向け構成方法について説明します。
monikerRange: o365-21vianet
ms.openlocfilehash: 3235bf77ec8cd7be96910614bdde41fb60f9f556
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60199239"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>21Vianet がOffice 365 Azure Information Protection のサポート

この記事では、21Vianet と商用製品が運用する Office 365 の Azure Information Protection (AIP) サポートの違い、および AIP オンプレミス スキャナーのインストール方法やコンテンツ スキャン ジョブの管理方法など、中国のお客様向け AIP を構成するための具体的な手順について説明します。 &mdash;

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>21Vianet がOffice 365する AIP と商用サービスの違い

21Vianet オファーが運用する Office 365 の AIP を使用して、中国のすべての商用機能と機能を中国のお客様に提供しますが、強調表示する機能が不足しています。

次の一覧には、21Vianet が運用する 2021 Office 365の AIP と 2021 年 1 月の商用製品との間の既存のギャップが含まれます。

- Information Rights Management (IRM) は、Microsoft 365 Apps for enterprise (ビルド 11731.10000 以上) でのみサポートされます。 Office 2010、Office 2013、その他Office 2016 バージョンはサポートされていません。

- 現在、Active Directory Rights Management サービス (AD RMS) から AIP への移行は使用できません。
  
- 商用クラウド内のユーザーとの保護されたメールの共有がサポートされています。
  
- 現在、商用クラウド内のユーザーとのドキュメントと電子メールの添付ファイルの共有は利用できません。 これには、Office 365クラウド内の 21Vianet ユーザーが運用するユーザー、商用クラウド内の 21Vianet ユーザーが運用する Office 365 以外のユーザー、および RMS for Individuals ライセンスを持つユーザーが含まれます。
  
- IRM と SharePoint (IRM で保護されたサイトとライブラリ) は現在使用できません。
  
- 現在、RMS のモバイル AD拡張機能は使用できません。

- モバイル [ビューアーは](/azure/information-protection/rms-client/mobile-app-faq) Azure China 21Vianet ではサポートされていません。

- Azure ポータルの AIP 領域は、中国のお客様が利用できません。 コンテンツ [スキャン ジョブの](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 管理や実行など、ポータルでアクションを実行する代わりに PowerShell コマンドを使用します。

## <a name="configure-aip-for-customers-in-china"></a>中国の顧客向け AIP の構成

中国の顧客向け AIP を構成するには、次の手順を行います。
1. [テナントの権限管理を有効にします](#step-1-enable-rights-management-for-the-tenant)。

1. [同期サービス Microsoft Information Protectionを追加します](#step-2-add-the-microsoft-information-protection-sync-service-service-principal)。

1. [DNS 暗号化を構成します](#step-3-configure-dns-encryption)。

1. [AIP 統合ラベル 付けクライアントをインストールして構成します](#step-4-install-and-configure-the-aip-unified-labeling-client)。

1. [アプリで AIP アプリを構成Windows。](#step-5-configure-aip-apps-on-windows)

1. [AIP オンプレミス スキャナーをインストールし、コンテンツ スキャン ジョブを管理します](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)。 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>手順 1: テナントの権限管理を有効にする

暗号化が正しく機能するには、テナントで RMS を有効にする必要があります。

1. RMS が有効になっているか確認します。

    1. 管理者として PowerShell を起動します。
    2. AIPService モジュールがインストールされていない場合は、実行します `Install-Module AipService` 。
    3. を使用してモジュールをインポート `Import-Module AipService` します。
    4. Connectを使用してサービスにアクセスします `Connect-AipService -environmentname azurechinacloud` 。
    5. 状態 `(Get-AipServiceConfiguration).FunctionalState` が . `Enabled`

2. 機能状態がである場合は `Disabled` 、実行します `Enable-AipService` 。

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a>手順 2: 同期サービス Microsoft Information Protectionを追加する

同期 **Microsoft Information Protectionサービス** プリンシパルは、Azure China テナントでは既定では使用できません。Azure Information Protection には必須です。

1. [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal)コマンドレットと同期サービスのアプリケーション ID を使用して、このサービス `870c4f2e-85b6-4d43-bdda-6ed9a579b725` プリンシパルMicrosoft Information Protection作成します。 

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. サービス プリンシパルを追加した後、サービスに必要な関連するアクセス許可を追加します。

### <a name="step-3-configure-dns-encryption"></a>手順 3: DNS 暗号化を構成する

暗号化が正しく動作するにはOfficeクライアント アプリケーションは、サービスの中国インスタンスに接続し、そこからブートストラップする必要があります。 クライアント アプリケーションを適切なサービス インスタンスにリダイレクトするには、テナント管理者が Azure RMS URL に関する情報を含む DNS SRV レコードを構成する必要があります。 DNS SRV レコードがない場合、クライアント アプリケーションは既定でパブリック クラウド インスタンスへの接続を試み、失敗します。

また、テナントが所有するドメイン (たとえば) に基づいてユーザー名を使用してログインし、ユーザー名 (たとえば) でログインしないという前提 `joe@contoso.cn` `onmschina` があります `joe@contoso.onmschina.cn` 。 ユーザー名のドメイン名は、正しいサービス インスタンスへの DNS リダイレクトに使用されます。

#### <a name="configure-dns-encryption---windows"></a>DNS 暗号化の構成 - Windows

1. RMS ID を取得します。

    1. 管理者として PowerShell を起動します。
    2. AIPService モジュールがインストールされていない場合は、実行します `Install-Module AipService` 。
    3. Connectを使用してサービスにアクセスします `Connect-AipService -environmentname azurechinacloud` 。
    4. RMS `(Get-AipServiceConfiguration).RightsManagementServiceId` ID を取得するために実行します。

2. DNS プロバイダーにログインし、ドメインの DNS 設定に移動し、新しい SRV レコードを追加します。

    - サービス = `_rmsredir`
    - プロトコル = `_http`
    - Name = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (GUID は RMS ID)
    - 優先度、重み、秒、TTL = 既定値

3. Azure portal のテナントにカスタム ドメインを関連 [付ける](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)。 これにより、DNS のエントリが追加され、DNS 設定に値を追加した後に検証に数分かかる場合があります。

4. 対応するグローバル管理者資格情報Microsoft 365 管理センターにログインし、ユーザー作成用のドメイン (たとえば `contoso.cn` ) を追加します。 検証プロセスでは、追加の DNS 変更が必要になる場合があります。 検証が完了すると、ユーザーを作成できます。

#### <a name="configure-dns-encryption---mac-ios-android"></a>DNS 暗号化の構成 - Mac、iOS、Android

DNS プロバイダーにログインし、ドメインの DNS 設定に移動し、新しい SRV レコードを追加します。

- サービス = `_rmsdisco`
- プロトコル = `_http`
- Name = `_tcp`
- Target = `api.aadrm.cn`
- Port = `80`
- 優先度、重み、秒、TTL = 既定値


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a>手順 4: AIP 統合ラベル 付けクライアントをインストールして構成する

Microsoft ダウンロード センターから AIP 統合ラベル 付けクライアントを [ダウンロードしてインストールします](https://www.microsoft.com/download/details.aspx?id=53018)。

詳細については、以下を参照してください。

- [AIP ドキュメント](/azure/information-protection/)
- [AIP バージョンの履歴とサポート ポリシー](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [AIP システム要件](/azure/information-protection/requirements)
- [AIP クイック スタート: AIP クライアントを展開する](/azure/information-protection/quickstart-deploy-client)
- [AIP 管理者ガイド](/azure/information-protection/rms-client/clientv2-admin-guide)
- [AIP ユーザー ガイド](/azure/information-protection/rms-client/clientv2-user-guide)
- [感度ラベルMicrosoft 365する](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a>手順 5: アプリで AIP アプリを構成Windows

Azure China のWindowsソブリン クラウドをポイントするには、次のレジストリ キーが必要です。

- レジストリ ノード = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Name = `CloudEnvType`
- 値 = `6` (既定値 = 0)
- Type = `REG_DWORD`

> [!IMPORTANT]
> アンインストール後にレジストリ キーを削除しない必要があります。 キーが空、正しくない、または存在しない場合、機能は既定値 (商用クラウドの既定値 = 0) として動作します。 キーが空または正しくない場合は、印刷エラーもログに追加されます。

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>手順 6: AIP オンプレミス スキャナーをインストールし、コンテンツ スキャン ジョブを管理する

AIP オンプレミス スキャナーをインストールして、ネットワークとコンテンツ共有の機密データをスキャンし、組織のポリシーで構成されている分類ラベルと保護ラベルを適用します。

コンテンツ スキャン ジョブを構成および管理する場合は、商用サービスで使用される [Azure ポータル](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) インターフェイスの代わりに、次の手順を使用します。

詳細については、「Azure Information Protection 統合ラベル スキャナーとは」および [「PowerShell](/azure/information-protection/deploy-aip-scanner) のみを使用してコンテンツ スキャン ジョブを管理する」 [を参照してください](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。

**スキャナーをインストールして構成するには、次の手順を実行します**。

1. スキャナーを実行するWindowsサーバー コンピューターにサインインします。 ローカル管理者権限を持ち、マスター データベースに書き込む権限を持つアカウントSQL Server使用します。

1. PowerShell を閉じた状態で開始します。 以前に AIP クライアントとスキャナーをインストールした場合は **、AIPScanner** サービスが停止されていることを確認します。

1. [管理者としてWindows PowerShell] オプションを使用して、**セッションを開** きます。

1. [Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner)コマンドレットを実行し、Azure Information Protection スキャナー用のデータベースを作成する SQL Server インスタンスと、スキャナー クラスターのわかりやすい名前を指定します。

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner)コマンドで同じクラスター名を使用して、複数のスキャナー ノードを同じクラスターに関連付けできます。 複数のスキャナー ノードに同じクラスターを使用すると、複数のスキャナーを組み合わせてスキャンを実行できます。
    > 

1. 管理ツール サービスを使用してサービスがインストール **されていることを確認**  >  **します**。

    インストールされているサービスの名前は **Azure Information Protection Scanner** で、作成したスキャナー サービス アカウントを使用して実行するように構成されています。

1. スキャナーで使用する Azure トークンを取得します。 Azure ADトークンを使用すると、スキャナーは Azure Information Protection サービスに対して認証を行い、スキャナーを非対話的に実行できます。 

    1. Azure portal を開き、Azure ADアプリケーションを作成して、認証用のアクセス トークンを指定します。 詳細については [、「Azure Information Protection 用に対話](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)的にファイルにラベルを付ける方法」を参照してください。
    
        > [!TIP]
        > [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication)コマンド用に Azure AD アプリケーションを作成および構成する場合、[API のアクセス許可の要求] ウィンドウには **、[Microsoft** **API]** タブではなく [組織で使用する API] タブが表示されます。組織が **使用する API を選択し、[Azure** **Rights Management Services] を選択します**。 
        >

    1. Windows サーバー コンピューターから、スキャナー サービス アカウントにインストールに対するローカルログオン権限が付与されている場合は、このアカウントでサインインし、PowerShell セッションを開始します。 
    
        スキャナー サービス アカウントにインストールに対してローカルにログオンする権限を付与できない場合は [、「Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)用に対話的にファイルにラベルを付ける方法」の説明に従って [、Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication)を使用して *OnBehalfOf* パラメーターを使用します。

    1. [Set-AIPAuthentication を実行](/powershell/module/azureinformationprotection/set-aipauthentication)し、Azure アプリケーションからコピーされた値ADします。

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      次に例を示します。

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    これで、スキャナーに Azure サーバーに対する認証トークンがAD。 このトークンは、Azure アプリの Web アプリ **/API** クライアント シークレットの構成に従って、1 年、2 年、または 2 年間有効AD。 トークンの有効期限が切れたら、この手順を繰り返す必要があります。

1. [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration)コマンドレットを実行して、スキャナーをオフライン モードで機能に設定します。 次を実行します: 

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob)コマンドレットを実行して、既定のコンテンツ スキャン ジョブを作成します。

    **Set-AIPScannerContentScanJob** コマンドレットで必要なパラメーターは、強制 **のみです**。 ただし、この時点でコンテンツ スキャン ジョブの他の設定を定義することもできます。 次に例を示します。

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    上記の構文は、構成を続行する間に次の設定を構成します。

    - スキャナーの実行スケジュールを手動に *保持する*
    - 感度ラベル付けポリシーに基づいて検出される情報の種類を設定します。
    - 感度 *ラベル* 付けポリシーを適用しない
    - 感度ラベル付けポリシーに定義されている既定のラベルを使用して、コンテンツに基づいてファイルに自動的にラベルを付ける
    - ファイル *の* 再ラベル付けは許可しない
    - 値によって変更された日付、最後に変更された日付、および変更を含む、スキャンと自動ラベル付け中にファイル *の詳細を保持* します
    - 実行中に .msg ファイルと .tmp ファイルを除外するスキャナーを設定します。
    - スキャナーの実行時に使用するアカウントに既定の所有者を設定します。

1. [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository)コマンドレットを使用して、コンテンツ スキャン ジョブでスキャンするリポジトリを定義します。 たとえば、以下を実行します。

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    追加するリポジトリの種類に応じて、次のいずれかの構文を使用します。

    - ネットワーク共有の場合は、 を使用します `\\Server\Folder` 。
    - ライブラリの場合SharePointを使用します `http://sharepoint.contoso.com/Shared%20Documents/Folder` 。
    - ローカル パスの場合: `C:\Folder`
    - UNC パスの場合: `\\Server\Folder`

    > [!NOTE]
    > ワイルドカードはサポートされていません。WebDav の場所はサポートされていません。
    >
    > 後でリポジトリを変更するには、代わりに [Set-AIPScannerRepository コマンドレット](/powershell/module/azureinformationprotection/set-aipscannerrepository) を使用します。 


必要に応じて、次の手順に進みます。

- [検出サイクルを実行して、スキャナーのレポートを表示する](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [PowerShell を使用して分類と保護を適用するスキャナーを構成する](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [PowerShell を使用してスキャナーで DLP ポリシーを構成する](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

次の表に、スキャナーのインストールとコンテンツ スキャン ジョブの管理に関連する PowerShell コマンドレットの一覧を示します。

| コマンドレット | 説明 |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | コンテンツ スキャン ジョブに新しいリポジトリを追加します。 |
| [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|クラスターに関する詳細を返します。 |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | コンテンツ スキャン ジョブの詳細を取得します。 |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | コンテンツ スキャン ジョブに定義されているリポジトリの詳細を取得します。 |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | コンテンツ スキャン ジョブを削除します。 |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | コンテンツ スキャン ジョブからリポジトリを削除します。 |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | コンテンツ スキャン ジョブの設定を定義します。 |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | コンテンツ スキャン ジョブの既存のリポジトリの設定を定義します。 |
| | |

詳細については、以下を参照してください。

- [Azure Information Protection 統合ラベル スキャナーとは](/azure/information-protection/deploy-aip-scanner)
- [Azure Information Protection (AIP) 統合ラベル スキャナーの構成とインストール](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- [PowerShell のみを使用してコンテンツ スキャン ジョブを管理します](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。
