---
title: 21Vianet が運用している Office 365 向け Azure Information Protection と商用サービスの間のパリティ
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
ms.reviewer: arthurj
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
ms.openlocfilehash: 50269749b5f4e544263f790ec9c7e4474af57219
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840303"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>21Vianet が運用している Office 365 向け Azure Information Protection と商用サービスの間のパリティ

この目標は、21Vianet が運用している Office 365 向け Azure Information Protection (AIP) が提供する中国のお客様に、すべての商用機能を提供することで実現しますが、強調表示する機能が不足しています。

次の一覧には、21Vianet が運用している Office 365 向け Azure Information Protection と 2021 年 1 月の商用サービスの間の既存のギャップが含まれています。

- Information Rights Management (IRM) は、Microsoft 365 Apps for enterprise (ビルド 11731.10000 以上) でのみサポートされます。 Office 2010、Office 2013、その他の Office 2016 バージョンはサポートされていません。

- 現在、Active Directory Rights Management サービス (AD RMS) から Azure Information Protection への移行は利用できません。
  
- 商用クラウド内のユーザーへの保護された電子メールの共有がサポートされています。
  
- 現在、商用クラウド内のユーザーへのドキュメントとメールの添付ファイルの共有は利用できません。 これには、商用クラウドで 21Vianet ユーザーが運用している Office 365、商用クラウドの 21Vianet ユーザーが運用している Office 365 以外のユーザー、および個人向け RMS ライセンスを持つユーザーが含まれます。
  
- 現在、SharePoint での IRM (IRM で保護されたサイトとライブラリ) は使用できません。
  
- 現在、RMS 用モバイル AD拡張機能は使用できません。

- モバイル [ビューアーは](/azure/information-protection/rms-client/mobile-app-faq) 、Azure China 21Vianet ではサポートされていません。

## <a name="configuring-azure-information-protection-for-customers-in-china"></a>中国のお客様向け Azure Information Protection の構成

### <a name="enable-rights-management-for-the-tenant"></a>テナントの Rights Management を有効にする

暗号化が正しく機能するには、テナントに対して RMS を有効にする必要があります。

- RMS が有効になっているか確認します。
  1. 管理者として PowerShell を起動します。
  2. AIPService モジュールがインストールされていない場合は、実行します `Install-Module AipService` 。
  3. を使用してモジュールをインポートします `Import-Module AipService` 。
  4. を使用してサービスに接続します `Connect-AipService -environmentname azurechinacloud` 。
  5. 状態 `(Get-AipServiceConfiguration).FunctionalState` が次の場合は、実行して確認します `Enabled` 。

- 機能状態が次の場合 `Disabled` は、実行します `Enable-AipService` 。

### <a name="dns-configuration-for-encryption-windows"></a>暗号化用の DNS 構成 (Windows)

暗号化を正しく機能Officeクライアント アプリケーションは、サービスの中国のインスタンスに接続し、そこからブートストラップする必要があります。 クライアント アプリケーションを適切なサービス インスタンスにリダイレクトするには、テナント管理者が Azure RMS URL に関する情報を含む DNS SRV レコードを構成する必要があります。 DNS SRV レコードがない場合、クライアント アプリケーションは既定でパブリック クラウド インスタンスへの接続を試み、失敗します。

また、ユーザーは、ユーザー名ではなく、テナント所有のドメインに基づくユーザー名 (たとえば、) を使用してログインすると想定 `joe@contoso.cn` `onmschina` しています `joe@contoso.onmschina.cn` 。 ユーザー名のドメイン名は、正しいサービス インスタンスへの DNS リダイレクトに使用されます。

- RMS ID を取得します。
  1. 管理者として PowerShell を起動します。
  2. AIPService モジュールがインストールされていない場合は、実行します `Install-Module AipService` 。
  3. を使用してサービスに接続します `Connect-AipService -environmentname azurechinacloud` 。
  4. RMS `(Get-AipServiceConfiguration).RightsManagementServiceId` ID を取得するために実行します。

- DNS プロバイダーにログインし、ドメインの DNS 設定に移動して、新しい SRV レコードを追加します。
  - サービス = `_rmsredir`
  - プロトコル = `_http`
  - Name = `_tcp`
  - Target = `[GUID].rms.aadrm.cn` (GUID は RMS ID)
  - Priority、Weight、Seconds、TTL = 既定値

- Azure portal でカスタム ドメインをテナントに [関連付ける](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)。 これにより、DNS にエントリが追加されます。DNS 設定に値を追加した後、検証に数分かかる場合があります。

- 対応するグローバル管理者の資格情報を使用して Microsoft 365 管理センターにログインし、ユーザー作成用のドメイン (たとえば `contoso.cn` ) を追加します。 検証プロセスでは、追加の DNS 変更が必要になる場合があります。 確認が完了すると、ユーザーを作成できます。

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>暗号化用の DNS 構成 (Mac、iOS、Android)

DNS プロバイダーにログインし、ドメインの DNS 設定に移動して、新しい SRV レコードを追加します。

- サービス = `_rmsdisco`
- プロトコル = `_http`
- Name = `_tcp`
- Target = `api.aadrm.cn`
- ポート = `80`
- Priority、Weight、Seconds、TTL = 既定値

### <a name="aip-client-configuration"></a>AIP クライアント構成

統合 AIP クライアントは、Microsoft ダウンロード センター [からダウンロードできます](https://www.microsoft.com/download/details.aspx?id=53018)。

詳しくは、以下を参照してください。

- [Azure Information Protection のドキュメント](/azure/information-protection/)
- [AIP バージョン履歴とサポート ポリシー](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [AIP システム要件](/azure/information-protection/requirements)
- [AIP クイック スタート: AIP クライアントを展開する](/azure/information-protection/quickstart-deploy-client)
- [AIP 管理者ガイド](/azure/information-protection/rms-client/clientv2-admin-guide)
- [AIP ユーザー ガイド](/azure/information-protection/rms-client/clientv2-user-guide)
- [Microsoft 365 の感度ラベルについて](/microsoft-365/compliance/sensitivity-labels)

### <a name="aip-apps-configuration-unified-labeling-client-only"></a>AIP アプリの構成 (統合ラベル付けクライアントのみ)

統合ラベル付けソリューションでは、Windows 上の AIP アプリが Azure China 用の正しい主権クラウドを指し示す次のレジストリ キーを必要とします。

- レジストリ ノード = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Name = `CloudEnvType`
- 値 = `6` (既定値 = 0)
- Type = `REG_DWORD`

> [!IMPORTANT]
> アンインストール後にレジストリ キーが削除されるのを確認してください。 キーが空、正しくない、または存在しない場合、機能は既定値として動作します (商用クラウドの既定値は 0 です)。 キーが空または正しくない場合は、印刷エラーもログに追加されます。

### <a name="manage-azure-information-protection-content-scan-jobs"></a>Azure Information Protection コンテンツ スキャン ジョブを管理する

Azure Information Protection コンテンツ スキャン ジョブを Azure China スキャナー サーバーで管理するには、Azure Portal の代わりに次のコマンドレットを使用します。<br><br>

| コマンドレット | 説明 |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | コンテンツ スキャン ジョブに新しいリポジトリを追加します。 |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | コンテンツ スキャン ジョブに関する詳細を取得します。 |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | コンテンツ スキャン ジョブに対して定義されているリポジトリに関する詳細を取得します。 |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | コンテンツ スキャン ジョブを削除します。 |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | コンテンツ スキャン ジョブからリポジトリを削除します。 |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | コンテンツ スキャン ジョブの設定を定義します。 |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | コンテンツ スキャン ジョブの既存のリポジトリの設定を定義します。 |

詳細については [、「PowerShell のみを使用してコンテンツ スキャン ジョブを管理する」を参照してください](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。