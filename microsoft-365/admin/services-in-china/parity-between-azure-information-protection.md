---
title: 21Vianet が運用Office 365 に対する Azure Information Protection のサポート
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
description: 21Vianet が運用している Office 365 の Azure Information Protection (AIP) と、中国のお客様向け構成方法について説明します。
monikerRange: o365-21vianet
ms.openlocfilehash: 300e7633237511fb9de64199ae7cf54594f2239e
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099680"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>21Vianet が運用Office 365 に対する Azure Information Protection のサポート

この記事では、21Vianet が運用している Office 365 の Azure Information Protection (AIP) サポートと商用製品の違い、および AIP オンプレミス スキャナーのインストール方法やコンテンツ スキャン ジョブの管理方法など、中国のお客様向け AIP を構成する具体的な手順について説明します。 &mdash;

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>21Vianet が運用Office 365 の AIP と商用製品の相違点

この目標は、21Vianet が運用している Office 365 用の AIP を使用して、中国のお客様にすべての商用機能を提供することで実現しますが、強調表示する機能が不足しています。

以下に、21Vianet が運用している Office 365 用の AIP と、2021 年 1 月の商用サービスの間の既存のギャップを示します。

- Information Rights Management (IRM) は、Microsoft 365 Apps for enterprise (ビルド 11731.10000 以上) でのみサポートされます。 Office 2010、Office 2013、その他の Office 2016 バージョンはサポートされていません。

- 現在、Active Directory Rights Management サービス (AD RMS) から AIP への移行は使用できません。
  
- 商用クラウドのユーザーとの保護されたメールの共有がサポートされています。
  
- 現在、商用クラウドのユーザーとのドキュメントとメールの添付ファイルの共有は利用できません。 これには、商用クラウドで 21Vianet ユーザーが運用している Office 365、商用クラウドの 21Vianet ユーザーが運用している Office 365 以外のユーザー、および個人向け RMS ライセンスを持つユーザーが含まれます。
  
- 現在、SharePoint での IRM (IRM で保護されたサイトとライブラリ) は使用できません。
  
- 現在、RMS 用モバイル AD拡張機能は使用できません。

- モバイル [ビューアーは](/azure/information-protection/rms-client/mobile-app-faq) 、Azure China 21Vianet ではサポートされていません。

- Azure ポータルの AIP 領域は、中国のお客様は利用できません。 オンプレミス スキャナーのインストールやコンテンツ スキャン ジョブの管理など、ポータルでアクションを実行する代わりに [PowerShell](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) コマンドを使用します。

## <a name="configure-aip-for-customers-in-china"></a>中国のお客様向け AIP の構成

中国のお客様向け AIP を構成するには:
1. [テナントの Rights Management を有効にします](#step-1-enable-rights-management-for-the-tenant)。

2. [DNS 暗号化を構成します](#step-2-configure-dns-encryption)。

3. [AIP 統合ラベル付けクライアントをインストールして構成します](#step-3-install-and-configure-the-aip-unified-labeling-client)。

4. [Windows で AIP アプリを構成します](#step-4-configure-aip-apps-on-windows)。

5. [AIP オンプレミス スキャナーをインストールし、コンテンツ スキャン ジョブを管理します](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)。 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>手順 1: テナントの Rights Management を有効にする

暗号化が正しく機能するには、テナントに対して RMS を有効にする必要があります。

1. RMS が有効になっているか確認します。

    1. 管理者として PowerShell を起動します。
    2. AIPService モジュールがインストールされていない場合は、実行します `Install-Module AipService` 。
    3. を使用してモジュールをインポートします `Import-Module AipService` 。
    4. を使用してサービスに接続します `Connect-AipService -environmentname azurechinacloud` 。
    5. 状態 `(Get-AipServiceConfiguration).FunctionalState` が次の場合は、実行して確認します `Enabled` 。

2. 機能状態が次の場合 `Disabled` は、実行します `Enable-AipService` 。

### <a name="step-2-configure-dns-encryption"></a>手順 2: DNS 暗号化を構成する

暗号化を正しく機能Officeクライアント アプリケーションは、サービスの中国のインスタンスに接続し、そこからブートストラップする必要があります。 クライアント アプリケーションを適切なサービス インスタンスにリダイレクトするには、テナント管理者が Azure RMS URL に関する情報を含む DNS SRV レコードを構成する必要があります。 DNS SRV レコードがない場合、クライアント アプリケーションは既定でパブリック クラウド インスタンスへの接続を試み、失敗します。

また、ユーザーは、ユーザー名ではなく、テナント所有のドメインに基づくユーザー名 (たとえば、) を使用してログインすると想定 `joe@contoso.cn` `onmschina` しています `joe@contoso.onmschina.cn` 。 ユーザー名のドメイン名は、正しいサービス インスタンスへの DNS リダイレクトに使用されます。

#### <a name="configure-dns-encryption---windows"></a>DNS 暗号化の構成 - Windows

1. RMS ID を取得します。

    1. 管理者として PowerShell を起動します。
    2. AIPService モジュールがインストールされていない場合は、実行します `Install-Module AipService` 。
    3. を使用してサービスに接続します `Connect-AipService -environmentname azurechinacloud` 。
    4. RMS `(Get-AipServiceConfiguration).RightsManagementServiceId` ID を取得するために実行します。

2. DNS プロバイダーにログインし、ドメインの DNS 設定に移動して、新しい SRV レコードを追加します。

    - サービス = `_rmsredir`
    - プロトコル = `_http`
    - Name = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (GUID は RMS ID)
    - Priority、Weight、Seconds、TTL = 既定値

3. Azure portal でカスタム ドメインをテナントに [関連付ける](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)。 これにより、DNS にエントリが追加されます。DNS 設定に値を追加した後、検証に数分かかる場合があります。

4. 対応するグローバル管理者の資格情報を使用して Microsoft 365 管理センターにログインし、ユーザー作成用のドメイン (たとえば `contoso.cn` ) を追加します。 検証プロセスでは、追加の DNS 変更が必要になる場合があります。 確認が完了すると、ユーザーを作成できます。

#### <a name="configure-dns-encryption---mac-ios-android"></a>DNS 暗号化の構成 - Mac、iOS、Android

DNS プロバイダーにログインし、ドメインの DNS 設定に移動して、新しい SRV レコードを追加します。

- サービス = `_rmsdisco`
- プロトコル = `_http`
- Name = `_tcp`
- Target = `api.aadrm.cn`
- ポート = `80`
- Priority、Weight、Seconds、TTL = 既定値

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a>手順 3: AIP 統合ラベル付けクライアントをインストールおよび構成する

Microsoft ダウンロード センターから AIP 統合ラベル付け [クライアントをダウンロードします](https://www.microsoft.com/download/details.aspx?id=53018)。

詳しくは、以下を参照してください。

- [AIP ドキュメント](/azure/information-protection/)
- [AIP バージョン履歴とサポート ポリシー](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [AIP システム要件](/azure/information-protection/requirements)
- [AIP クイック スタート: AIP クライアントを展開する](/azure/information-protection/quickstart-deploy-client)
- [AIP 管理者ガイド](/azure/information-protection/rms-client/clientv2-admin-guide)
- [AIP ユーザー ガイド](/azure/information-protection/rms-client/clientv2-user-guide)
- [Microsoft 365 の感度ラベルについて](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a>手順 4: Windows で AIP アプリを構成する

Windows 上の AIP アプリは、Azure China の正しい主権クラウドを指し示す次のレジストリ キーを必要とします。

- レジストリ ノード = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Name = `CloudEnvType`
- 値 = `6` (既定値 = 0)
- Type = `REG_DWORD`

> [!IMPORTANT]
> アンインストール後にレジストリ キーが削除されるのを確認してください。 キーが空、正しくない、または存在しない場合、機能は既定値として動作します (商用クラウドの既定値は 0 です)。 キーが空または正しくない場合は、印刷エラーもログに追加されます。

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>手順 5: AIP オンプレミス スキャナーをインストールし、コンテンツ スキャン ジョブを管理する

AIP オンプレミス スキャナーをインストールして、ネットワークとコンテンツ共有で機密データをスキャンし、組織のポリシーで構成されている分類ラベルと保護ラベルを適用します。

スキャナーをインストールしてコンテンツ スキャン ジョブを管理する場合は、商用製品で使用される Azure ポータル インターフェイスの代わりに、次のコマンドレットを使用します。<br><br>

| コマンドレット | 説明 |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | コンテンツ スキャン ジョブに新しいリポジトリを追加します。 |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | コンテンツ スキャン ジョブに関する詳細を取得します。 |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | コンテンツ スキャン ジョブに対して定義されているリポジトリに関する詳細を取得します。 |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | コンテンツ スキャン ジョブを削除します。 |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | コンテンツ スキャン ジョブからリポジトリを削除します。 |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | コンテンツ スキャン ジョブの設定を定義します。 |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | コンテンツ スキャン ジョブの既存のリポジトリの設定を定義します。 |

詳細については [、「Azure Information Protection](/azure/information-protection/deploy-aip-scanner) 統合ラベルスキャナーとは」および [「PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)のみを使用してコンテンツ スキャン ジョブを管理する」を参照してください。
