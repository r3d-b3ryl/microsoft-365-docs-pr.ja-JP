---
title: 21Vianet によって運用されるOffice 365の Azure Information Protection サポート
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
description: 21Vianet によって運用されるOffice 365用の Azure Information Protection (AIP) と、中国のお客様向けに Azure Information Protection (AIP) を構成する方法について説明します。
monikerRange: o365-21vianet
ms.openlocfilehash: 80cd8d9b848235fc3486ad1952fa58f9d7d1570d
ms.sourcegitcommit: c6f1486617b39565bfd8f662ee6ad65a9cefd3e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66530170"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>21Vianet によって運用されるOffice 365の Azure Information Protection サポート

この記事では、21Vianet が運用するOffice 365に対する Azure Information Protection (AIP) のサポートと、中国&mdash;のお客様向けに AIP を構成する具体的な手順について説明します。これには、AIP オンプレミス スキャナーをインストールしてコンテンツ スキャン ジョブを管理する方法が含まれます。

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>21Vianet によって運用されるOffice 365の AIP と商用オファリングの違い

目標は、21Vianet オファーによって運用されている AIP Office 365を使用して、中国のお客様にすべての商用機能と機能を提供することですが、特に強調したい機能がいくつかあります。

次の一覧には、21Vianet によって運用されているOffice 365の AIP と、2021 年 1 月の時点での商用オファリングの間の既存のギャップが含まれています。

- Active Directory Rights Management Services (AD RMS) 暗号化は、Microsoft 365 Apps for enterprise (ビルド 11731.10000 以降) でのみサポートされます。 Office Professional Plusは AD RMS をサポートしていません。

- AD RMS から AIP への移行は現在使用できません。
  
- 商用クラウド内のユーザーとの保護された電子メールの共有がサポートされています。
  
- 現在、商用クラウド内のユーザーとのドキュメントと電子メールの添付ファイルの共有は利用できません。 これには、商用クラウド内の 21Vianet ユーザー、商用クラウド内の 21Vianet ユーザーが運用する非Office 365、個人向け RMS ライセンスを持つユーザーが運用するOffice 365が含まれます。
  
- SharePoint を使用した IRM (IRM で保護されたサイトとライブラリ) は現在使用できません。
  
- AD RMS のモバイル デバイス拡張機能は現在使用できません。

- [モバイル ビューアー](/azure/information-protection/rms-client/mobile-app-faq)は、Azure China 21Vianet ではサポートされていません。

- Azure portalの AIP 領域は、中国のお客様には使用できません。 コンテンツ スキャン ジョブの管理や実行など、ポータルでアクションを実行する代わりに [PowerShell コマンド](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) を使用します。

- 21Vianet によって運用Office 365の AIP エンドポイントは、他のクラウド サービスに必要なエンドポイントとは異なります。 クライアントから次のエンドポイントへのネットワーク接続が必要です。
    - ラベル ポリシーとラベル ポリシーをダウンロードする: `*.protection.partner.outlook.cn`
    - Azure Rights Management サービス: `*.aadrm.cn`

## <a name="configure-aip-for-customers-in-china"></a>中国のお客様向けに AIP を構成する

中国のお客様向けに AIP を構成するには:
1. [テナントの Rights Management を有効にします](#step-1-enable-rights-management-for-the-tenant)。

1. [Microsoft Information Protection Sync Service サービス プリンシパルを追加します](#step-2-add-the-microsoft-information-protection-sync-service-service-principal)。

1. [DNS 暗号化を構成します](#step-3-configure-dns-encryption)。

1. [AIP 統合ラベル付けクライアントをインストールして構成します](#step-4-install-and-configure-the-aip-unified-labeling-client)。

1. [Windows で AIP アプリを構成します](#step-5-configure-aip-apps-on-windows)。

1. [AIP オンプレミス スキャナーをインストールし、コンテンツ スキャン ジョブを管理](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)します。 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>手順 1: テナントの Rights Management を有効にする

暗号化を正しく機能させるには、テナントに対して RMS を有効にする必要があります。

1. RMS が有効になっているかどうかを確認します。

    1. 管理者として PowerShell を起動します。
    2. AIPService モジュールがインストールされていない場合は、実行 `Install-Module AipService`します。
    3. を使用してモジュールを `Import-Module AipService`インポートします。
    4. を使用して `Connect-AipService -environmentname azurechinacloud`サービスに接続します。
    5. 実行 `(Get-AipServiceConfiguration).FunctionalState` し、状態が `Enabled`.

2. 機能状態が次の場合は `Disabled`、実行します `Enable-AipService`。

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a>手順 2: Microsoft Information Protection Sync Service サービス プリンシパルを追加する

**Microsoft Information Protection Sync Service サービス** プリンシパルは、既定では Azure China テナントでは使用できず、Azure Information Protectionに必要です。 Azure Az PowerShell モジュールを使用して、このサービス プリンシパルを手動で作成します。

1. Azure Az モジュールがインストールされていない場合は、Azure Az モジュールをインストールするか、Azure Cloud Shellなどの Azure Az モジュールがプレインストールされているリソース[を使用します](/azure/cloud-shell/overview)。 詳細については、「 [Azure Az PowerShell モジュールのインストール](/powershell/azure/install-az-ps)」を参照してください。

1. [Connect-AzAccount](/powershell/module/az.accounts/Connect-AzAccount) コマンドレットと環境名を使用してサービスに`azurechinacloud`接続します。

    ```powershell
    Connect-azaccount -environmentname azurechinacloud
    ```

1. [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) コマンドレットと `870c4f2e-85b6-4d43-bdda-6ed9a579b725` **Microsoft Purview 情報保護 Sync Service** のアプリケーション ID を使用して、Microsoft Information Protection Sync Service サービス プリンシパルを手動で作成します。

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. サービス プリンシパルを追加した後、サービスに必要な関連するアクセス許可を追加します。

### <a name="step-3-configure-dns-encryption"></a>手順 3: DNS 暗号化を構成する

暗号化を正しく機能させるには、Office クライアント アプリケーションがサービスの中国インスタンスに接続し、そこからブートストラップする必要があります。 クライアント アプリケーションを適切なサービス インスタンスにリダイレクトするには、テナント管理者は、Azure RMS URL に関する情報を使用して DNS SRV レコードを構成する必要があります。 DNS SRV レコードがない場合、クライアント アプリケーションは既定でパブリック クラウド インスタンスへの接続を試み、失敗します。

また、ユーザーは、テナント所有のドメイン (たとえば) に基づくユーザー名を使用してログインし、ユーザー名 (たとえば、`joe@contoso.cn``joe@contoso.onmschina.cn`ユーザー名) ではなく`onmschina`ログインすることを前提としています。 ユーザー名のドメイン名は、正しいサービス インスタンスへの DNS リダイレクトに使用されます。

#### <a name="configure-dns-encryption---windows"></a>DNS 暗号化の構成 - Windows

1. RMS ID を取得します。

    1. 管理者として PowerShell を起動します。
    2. AIPService モジュールがインストールされていない場合は、実行 `Install-Module AipService`します。
    3. を使用して `Connect-AipService -environmentname azurechinacloud`サービスに接続します。
    4. RMS ID を取得するために実行 `(Get-AipServiceConfiguration).RightsManagementServiceId` します。

2. DNS プロバイダーにログインし、ドメインの DNS 設定に移動して、新しい SRV レコードを追加します。

    - サービス = `_rmsredir`
    - プロトコル = `_http`
    - Name = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (GUID が RMS ID である場合)
    - 優先度、重み、秒、TTL = 既定値

3. カスタム ドメインを[Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)のテナントに関連付けます。 これにより、DNS にエントリが追加されます。DNS 設定に値を追加した後、確認に数分かかる場合があります。

4. 対応するグローバル管理者資格情報を使用してMicrosoft 365 管理センターにログインし、ユーザー作成用のドメイン (たとえば) `contoso.cn`を追加します。 確認プロセスでは、追加の DNS 変更が必要になる場合があります。 確認が完了したら、ユーザーを作成できます。

#### <a name="configure-dns-encryption---mac-ios-android"></a>DNS 暗号化の構成 - Mac、iOS、Android

DNS プロバイダーにログインし、ドメインの DNS 設定に移動して、新しい SRV レコードを追加します。

- サービス = `_rmsdisco`
- プロトコル = `_http`
- Name = `_tcp`
- ターゲット = `api.aadrm.cn`
- ポート = `80`
- 優先度、重み、秒、TTL = 既定値


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a>手順 4: AIP 統合ラベル付けクライアントをインストールして構成する

[Microsoft ダウンロード センター](https://www.microsoft.com/download/details.aspx?id=53018)から AIP 統合ラベル付けクライアントをダウンロードしてインストールします。

詳細については、以下を参照してください。

- [AIP のドキュメント](/azure/information-protection/)
- [AIP バージョン履歴とサポート ポリシー](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [AIP システム要件](/azure/information-protection/requirements)
- [AIP クイック スタート: AIP クライアントをデプロイする](/azure/information-protection/quickstart-deploy-client)
- [AIP 管理者ガイド](/azure/information-protection/rms-client/clientv2-admin-guide)
- [AIP ユーザー ガイド](/azure/information-protection/rms-client/clientv2-user-guide)
- [Microsoft 365 の秘密度ラベルについて学習する](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a>手順 5: Windows で AIP アプリを構成する

Windows 上の AIP アプリでは、Azure China の正しいソブリン クラウドを指すために、次のレジストリ キーが必要です。

- レジストリ ノード = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Name = `CloudEnvType`
- 値 = `6` (既定値 = 0)
- 型 = `REG_DWORD`

> [!IMPORTANT]
> アンインストール後にレジストリ キーを削除しないようにしてください。 キーが空、正しくない、または存在しない場合、機能は既定値として動作します (商用クラウドの場合は既定値 = 0)。 キーが空または正しくない場合は、印刷エラーもログに追加されます。

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>手順 6: AIP オンプレミス スキャナーをインストールし、コンテンツ スキャン ジョブを管理する

AIP オンプレミス スキャナーをインストールして、機密データのネットワークとコンテンツ共有をスキャンし、組織のポリシーで構成されている分類ラベルと保護ラベルを適用します。

コンテンツ スキャン ジョブを構成および管理する場合は、商用サービスで使用される[Azure portal インターフェイス](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only)の代わりに、次の手順を使用します。

詳細については、「[Azure Information Protection統合ラベル付けスキャナーとは」](/azure/information-protection/deploy-aip-scanner)と「[PowerShell のみを使用したコンテンツ スキャン ジョブの管理](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)」を参照してください。

**スキャナーをインストールして構成するには**:

1. スキャナーを実行する Windows Server コンピューターにサインインします。 ローカル管理者権限を持ち、SQL Server マスター データベースに書き込むアクセス許可を持つアカウントを使用します。

1. PowerShell を閉じてから開始します。 以前に AIP クライアントとスキャナーをインストールしたことがある場合は、 **AIPScanner** サービスが停止していることを確認します。

1. **[管理者として実行**] オプションを使用してWindows PowerShell セッションを開きます。

1. [Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) コマンドレットを実行し、Azure Information Protection スキャナーのデータベースを作成するSQL Server インスタンスと、スキャナー クラスターのわかりやすい名前を指定します。

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) コマンドで同じクラスター名を使用して、複数のスキャナー ノードを同じクラスターに関連付けることができます。 複数のスキャナー ノードに同じクラスターを使用すると、複数のスキャナーを連携してスキャンを実行できます。
    > 

1. **管理ツール** >  サービスを使用して、サービスがインストールされていることを確認 **します**。

    インストールされているサービスは **Azure Information Protection スキャナー** という名前で、作成したスキャナー サービス アカウントを使用して実行するように構成されています。

1. スキャナーで使用する Azure トークンを取得します。 Azure AD トークンを使用すると、スキャナーは Azure Information Protection サービスに対して認証を行い、スキャナーを非対話型で実行できます。 

    1. Azure portalを開き、認証用のアクセス トークンを指定する Azure AD アプリケーションを作成します。 詳細については、「[Azure Information Protection の非対話型ファイルにラベルを付ける方法」を](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)参照してください。
    
        > [!TIP]
        > [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) コマンド用に Azure AD アプリケーションを作成して構成する場合、[**Api アクセス許可の要求**] ウィンドウに、Microsoft API タブの代わりに **組織が使用** する API タブ **が** 表示されます。組織が **Azure Rights Management Services** を選択するために **使用する API を** 選択します。 
        >

    1. Windows Server コンピューターから、スキャナー サービス アカウントにインストールに対して **ローカルでログオン** が許可されている場合は、このアカウントでサインインし、PowerShell セッションを開始します。 
    
        スキャナー サービス アカウントにインストールに対して **ローカルでログオン** を許可できない場合は、「[Azure Information Protection のファイルに非対話型でラベルを付ける方法](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)」で説明されているように、*OnBehalfOf* パラメーターと [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) を使用します。

    1. [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) を実行し、Azure AD アプリケーションからコピーされた値を指定します。

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      次に例を示します。

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    スキャナーに、Azure AD に対して認証するトークンが含まれるようになりました。 このトークンは、Azure AD の **Web アプリ /API** クライアント シークレットの構成に従って、1 年間、2 年間、または決して有効ではありません。 トークンの有効期限が切れた場合は、この手順を繰り返す必要があります。

1. [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) コマンドレットを実行して、スキャナーをオフライン モードで機能するように設定します。 実行：

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) コマンドレットを実行して、既定のコンテンツ スキャン ジョブを作成します。

    **Set-AIPScannerContentScanJob** コマンドレットで必要な唯一のパラメーターは **、適用です**。 ただし、この時点で、コンテンツ スキャン ジョブの他の設定を定義することもできます。 次に例を示します。

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    上記の構文は、構成を続行するときに、次の設定を構成します。

    - スキャナーの実行スケジュールを *手動* で保持する
    - 秘密度ラベル付けポリシーに基づいて検出される情報の種類を設定します
    - 秘密度ラベル付けポリシーを適用 *しません*
    - 機密ラベル付けポリシーに定義されている既定のラベルを使用して、コンテンツに基づいてファイルに自動的にラベルを付ける
    - ファイルのラベル変更を許可 *しない*
    - 値 *によって* 変更、*最終更新日*、変更 *された日付* など、スキャン中と自動ラベル付け中にファイルの詳細を保持します
    - 実行中に .msg ファイルと .tmp ファイルを除外するようにスキャナーを設定します
    - スキャナーの実行時に使用するアカウントに既定の所有者を設定します。

1. [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) コマンドレットを使用して、コンテンツ スキャン ジョブでスキャンするリポジトリを定義します。 たとえば、以下を実行します。

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    追加するリポジトリの種類に応じて、次のいずれかの構文を使用します。

    - ネットワーク共有の場合は、.`\\Server\Folder`
    - SharePoint ライブラリの場合は、 `http://sharepoint.contoso.com/Shared%20Documents/Folder`.
    - ローカル パスの場合: `C:\Folder`
    - UNC パスの場合: `\\Server\Folder`

    > [!NOTE]
    > ワイルドカードはサポートされておらず、WebDav の場所はサポートされていません。
    >
    > 後でリポジトリを変更するには、代わりに [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) コマンドレットを使用します。 


必要に応じて、次の手順に進みます。

- [検出サイクルを実行して、スキャナーのレポートを表示する](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [PowerShell を使用して、分類と保護を適用するようにスキャナーを構成する](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [PowerShell を使用してスキャナーで DLP ポリシーを構成する](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

次の表に、スキャナーのインストールとコンテンツ スキャン ジョブの管理に関連する PowerShell コマンドレットを示します。

| コマンドレット | 説明 |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | コンテンツ スキャン ジョブに新しいリポジトリを追加します。 |
| [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|クラスターに関する詳細を返します。 |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | コンテンツ スキャン ジョブの詳細を取得します。 |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | コンテンツ スキャン ジョブに定義されているリポジトリの詳細を取得します。 |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | コンテンツ スキャン ジョブを削除します。 |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | コンテンツ スキャン ジョブからリポジトリを削除します。 |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | コンテンツ スキャン ジョブの設定を定義します。 |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | コンテンツ スキャン ジョブ内の既存のリポジトリの設定を定義します。 |
| | |

詳細については、以下を参照してください。

- [Azure Information Protection統合ラベル付けスキャナーとは](/azure/information-protection/deploy-aip-scanner)
- [Azure Information Protection (AIP) 統合ラベル付けスキャナーの構成とインストール](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- [PowerShell のみを使用してコンテンツ スキャン ジョブを管理します](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。
