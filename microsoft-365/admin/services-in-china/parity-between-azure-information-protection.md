---
title: 21Vianet がOffice 365 に対する Azure Information Protection のサポート
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: 21Vianet が運用する 365 Office Azure Information Protection (AIP) の詳細と、中国の顧客向け構成方法について説明します。
monikerRange: o365-21vianet
ms.openlocfilehash: bddba69ecc8b7b80d2b2c7c48d820ec22d293362
ms.sourcegitcommit: b56a8ff9bb496bf2bc1991000afca3d251f45b72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418034"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>21Vianet がOffice 365 に対する Azure Information Protection のサポート

この記事では、21Vianet と商用製品が運用する Office 365 の Azure Information Protection (AIP) サポートの違い、および AIP オンプレミス スキャナーをインストールしてコンテンツ スキャン ジョブを管理する方法など、中国の顧客向け AIP を構成するための具体的な手順について説明します。 &mdash;

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>21Vianet Office 365 の AIP と商用サービスの違い

21Vianet オファーが運営する Office 365 の AIP を使用して、中国のすべての商用機能と機能を中国のお客様に提供しますが、強調表示する機能が不足しています。

次の一覧には、21Vianet が運営する Office 365 の AIP と 2021 年 1 月の商用製品の間の既存のギャップが含まれます。

- Information Rights Management (IRM) は、Microsoft 365 Apps for enterprise (ビルド 11731.100000 以上) でのみサポートされます。 Office 2010、Office 2013、その他Office 2016 バージョンはサポートされていません。

- 現在、Active Directory Rights Management サービス (AD RMS) から AIP への移行は使用できません。
  
- 商用クラウド内のユーザーとの保護されたメールの共有がサポートされています。
  
- 現在、商用クラウド内のユーザーとのドキュメントと電子メールの添付ファイルの共有は利用できません。 これには、商用クラウドOffice 21Vianet ユーザーが運用する Office 365、商用クラウドで 21Vianet ユーザーが運用する非 Office 365、個人向け RMS ライセンスを持つユーザーが含まれます。
  
- 現在、SharePoint を使用した IRM (IRM で保護されたサイトとライブラリ) は使用できません。
  
- 現在、RMS のモバイル AD拡張機能は使用できません。

- モバイル [ビューアーは](/azure/information-protection/rms-client/mobile-app-faq) Azure China 21Vianet ではサポートされていません。

- Azure ポータルの AIP 領域は、中国のお客様が利用できません。 [オンプレミス スキャナーの](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)インストールやコンテンツ スキャン ジョブの管理など、ポータルでアクションを実行する代わりに PowerShell コマンドを使用します。

## <a name="configure-aip-for-customers-in-china"></a>中国の顧客向け AIP の構成

中国の顧客向け AIP を構成するには、次の手順を行います。
1. [テナントの権限管理を有効にします](#step-1-enable-rights-management-for-the-tenant)。

2. [DNS 暗号化を構成します](#step-2-configure-dns-encryption)。

3. [AIP 統合ラベル 付けクライアントをインストールして構成します](#step-3-install-and-configure-the-aip-unified-labeling-client)。

4. [Windows で AIP アプリを構成します](#step-4-configure-aip-apps-on-windows)。

5. [AIP オンプレミス スキャナーをインストールし、コンテンツ スキャン ジョブを管理します](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)。 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>手順 1: テナントの権限管理を有効にする

暗号化が正しく機能するには、テナントで RMS を有効にする必要があります。

1. RMS が有効になっているか確認します。

    1. 管理者として PowerShell を起動します。
    2. AIPService モジュールがインストールされていない場合は、実行します `Install-Module AipService` 。
    3. を使用してモジュールをインポート `Import-Module AipService` します。
    4. を使用してサービスに接続します `Connect-AipService -environmentname azurechinacloud` 。
    5. 状態 `(Get-AipServiceConfiguration).FunctionalState` が . `Enabled`

2. 機能状態がである場合は `Disabled` 、実行します `Enable-AipService` 。

### <a name="step-2-configure-dns-encryption"></a>手順 2: DNS 暗号化を構成する

暗号化が正しく動作するにはOfficeクライアント アプリケーションは、サービスの中国インスタンスに接続し、そこからブートストラップする必要があります。 クライアント アプリケーションを適切なサービス インスタンスにリダイレクトするには、テナント管理者が Azure RMS URL に関する情報を含む DNS SRV レコードを構成する必要があります。 DNS SRV レコードがない場合、クライアント アプリケーションは既定でパブリック クラウド インスタンスへの接続を試み、失敗します。

また、テナントが所有するドメイン (たとえば) に基づいてユーザー名を使用してログインし、ユーザー名 (たとえば) でログインしないという前提 `joe@contoso.cn` `onmschina` があります `joe@contoso.onmschina.cn` 。 ユーザー名のドメイン名は、正しいサービス インスタンスへの DNS リダイレクトに使用されます。

#### <a name="configure-dns-encryption---windows"></a>DNS 暗号化の構成 - Windows

1. RMS ID を取得します。

    1. 管理者として PowerShell を起動します。
    2. AIPService モジュールがインストールされていない場合は、実行します `Install-Module AipService` 。
    3. を使用してサービスに接続します `Connect-AipService -environmentname azurechinacloud` 。
    4. RMS `(Get-AipServiceConfiguration).RightsManagementServiceId` ID を取得するために実行します。

2. DNS プロバイダーにログインし、ドメインの DNS 設定に移動し、新しい SRV レコードを追加します。

    - サービス = `_rmsredir`
    - プロトコル = `_http`
    - Name = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (GUID は RMS ID)
    - 優先度、重み、秒、TTL = 既定値

3. Azure portal のテナントにカスタム ドメインを関連 [付ける](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)。 これにより、DNS のエントリが追加され、DNS 設定に値を追加した後に検証に数分かかる場合があります。

4. 対応するグローバル管理者資格情報を使用して Microsoft 365 管理センターにログインし、ユーザー作成用のドメイン (たとえば `contoso.cn` ) を追加します。 検証プロセスでは、追加の DNS 変更が必要になる場合があります。 検証が完了すると、ユーザーを作成できます。

#### <a name="configure-dns-encryption---mac-ios-android"></a>DNS 暗号化の構成 - Mac、iOS、Android

DNS プロバイダーにログインし、ドメインの DNS 設定に移動し、新しい SRV レコードを追加します。

- サービス = `_rmsdisco`
- プロトコル = `_http`
- Name = `_tcp`
- Target = `api.aadrm.cn`
- Port = `80`
- 優先度、重み、秒、TTL = 既定値

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a>手順 3: AIP 統合ラベル 付けクライアントをインストールして構成する

AIP 統合ラベル 付けクライアントを Microsoft ダウンロード センター [からダウンロードします](https://www.microsoft.com/download/details.aspx?id=53018)。

詳細については、以下を参照してください。

- [AIP ドキュメント](/azure/information-protection/)
- [AIP バージョンの履歴とサポート ポリシー](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [AIP システム要件](/azure/information-protection/requirements)
- [AIP クイック スタート: AIP クライアントを展開する](/azure/information-protection/quickstart-deploy-client)
- [AIP 管理者ガイド](/azure/information-protection/rms-client/clientv2-admin-guide)
- [AIP ユーザー ガイド](/azure/information-protection/rms-client/clientv2-user-guide)
- [Microsoft 365 の感度ラベルの詳細](../../compliance/sensitivity-labels.md)

### <a name="step-4-configure-aip-apps-on-windows"></a>手順 4: Windows で AIP アプリを構成する

Windows 上の AIP アプリでは、Azure China の正しいソブリン クラウドをポイントするために、次のレジストリ キーが必要です。

- レジストリ ノード = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Name = `CloudEnvType`
- 値 = `6` (既定値 = 0)
- Type = `REG_DWORD`

> [!IMPORTANT]
> アンインストール後にレジストリ キーを削除しない必要があります。 キーが空、正しくない、または存在しない場合、機能は既定値 (商用クラウドの既定値 = 0) として動作します。 キーが空または正しくない場合は、印刷エラーもログに追加されます。

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>手順 5: AIP オンプレミス スキャナーをインストールし、コンテンツ スキャン ジョブを管理する

AIP オンプレミス スキャナーをインストールして、ネットワークとコンテンツ共有の機密データをスキャンし、組織のポリシーで構成されている分類ラベルと保護ラベルを適用します。

- [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication)コマンド用に Azure AD アプリケーションを作成および構成する場合、[API のアクセス許可の要求] ウィンドウには **、[Microsoft** **API]** タブではなく [組織で使用する API] タブが表示されます。組織が **使用する API を選択し、[Azure** **Rights Management Services] を選択します**。

- スキャナーをインストールしてコンテンツ スキャン ジョブを管理する場合は、商用製品で使用される Azure ポータル インターフェイスではなく、次のコマンドレットを使用します。<br><br>

    | コマンドレット | 説明 |
    |--|--|
    | [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | コンテンツ スキャン ジョブに新しいリポジトリを追加します。 |
    | [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | コンテンツ スキャン ジョブの詳細を取得します。 |
    | [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | コンテンツ スキャン ジョブに定義されているリポジトリの詳細を取得します。 |
    | [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | コンテンツ スキャン ジョブを削除します。 |
    | [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | コンテンツ スキャン ジョブからリポジトリを削除します。 |
    | [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | コンテンツ スキャン ジョブの設定を定義します。 |
    | [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | コンテンツ スキャン ジョブの既存のリポジトリの設定を定義します。 |
    | | |

> [!TIP]
> スキャナー[をインストールする場合は](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner)[、Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner)コマンドで同じクラスター名を使用して、複数のスキャナー ノードを同じクラスターに関連付ける必要があります。 複数のスキャナー ノードに同じクラスターを使用すると、複数のスキャナーを組み合わせてスキャンを実行できます。
> 
> [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)コマンドレットを使用して、クラスターに関する詳細を返します。
> 
詳細については、「Azure Information Protection 統合ラベル スキャナーとは」および [「PowerShell](/azure/information-protection/deploy-aip-scanner) のみを使用してコンテンツ スキャン ジョブを管理する」 [を参照してください](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。