---
title: 21Vianet が運用している Office 365 の Azure Information Protection 間のパリティ
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
description: 21Vianet が運用している Office 365 の Azure Information Protection と、中国のお客様に対して構成する方法について説明します。
monikerRange: o365-21vianet
ms.openlocfilehash: ad3420483701c83ffef65994996047de56a7085c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644665"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>21Vianet が運用している Office 365 の Azure Information Protection 間のパリティ

21Vianet が運用している Office 365 の Azure Information Protection を使用して、中国のお客様にすべての商用機能と機能を提供することを目標としていますが、いくつかの不足している機能を強調したいと考えています。

次の一覧には、21Vianet が運用している Office 365 用の Azure Information Protection と、2007 2019 年7月の商用オファーリングの間の既存のギャップが記載されています。

- Information Rights Management (IRM) は、Microsoft 365 Apps for enterprise (ビルド11731.10000 以降) に対してのみサポートされています。 Office 2010、Office 2013、およびその他の Office 2016 バージョンはサポートされていません。

- Active Directory Rights Management サービス (AD RMS) から Azure Information Protection への移行は現在使用できません。
  
- 保護された電子メールを商用クラウド内のユーザーに共有することがサポートされています。
  
- ドキュメントと電子メールの添付ファイルを商用クラウドのユーザーに共有することは現在使用できません。 これには、商用クラウドの21Vianet ユーザーが運用している Office 365、商用クラウドの21Vianet ユーザーが運用している非 Office 365、および個人ライセンスの RMS を使用するユーザーが含まれます。
  
- SharePoint を使用した IRM (IRM で保護されたサイトおよびライブラリ) は現在使用できません。
  
- Rights Management コネクタは現在使用できません。
  
- AD RMS のモバイルデバイス拡張機能は現在使用できません。

## <a name="configuring-azure-information-protection-for-customers-in-china"></a>中国のお客様向けに Azure Information Protection を構成する

### <a name="enable-rights-management-for-the-tenant"></a>テナントの Rights Management を有効にする

暗号化を正しく動作させるには、テナントに対して RMS を有効にする必要があります。

- RMS が有効になっているかどうかを確認します。
  1. PowerShell を管理者として起動します。
  2. AIPService モジュールがインストールされていない場合は、を実行 `Install-Module AipService` します。
  3. を使用してモジュールをインポートし `Import-Module AipService` ます。
  4. を使用してサービスに接続し `Connect-AipService -environmentname azurechinacloud` ます。
  5. を実行 `(Get-AipServiceConfiguration).FunctionalState` し、状態がであるかどうかを確認し `Enabled` ます。

- 機能状態がの場合は `Disabled` 、を実行 `Enable-AipService` します。

### <a name="dns-configuration-for-encryption-windows"></a>暗号化の DNS 構成 (Windows)

暗号化が正常に機能するためには、Office クライアントアプリケーションは、サービスの中国のインスタンスと、そこからブートストラップに接続する必要があります。 クライアントアプリケーションを適切なサービスインスタンスにリダイレクトするには、テナント管理者が Azure RMS URL に関する情報を使用して DNS SRV レコードを構成する必要があります。 DNS SRV レコードがない場合、クライアントアプリケーションは既定でパブリッククラウドインスタンスへの接続を試行しますが、失敗します。

また、ユーザーはテナント所有のドメイン (たとえば、) ではなく、ユーザー名を使用してログインすることを前提としています (例:) `joe@contoso.cn` `onmschina` `joe@contoso.onmschina.cn` 。 Username のドメイン名は、適切なサービスインスタンスへの DNS リダイレクトに使用されます。

- RMS ID を取得します。
  1. PowerShell を管理者として起動します。
  2. AIPService モジュールがインストールされていない場合は、を実行 `Install-Module AipService` します。
  3. を使用してサービスに接続し `Connect-AipService -environmentname azurechinacloud` ます。
  4. を実行し `(Get-AipServiceConfiguration).RightsManagementServiceId` て RMS ID を取得します。

- DNS プロバイダーにログインし、ドメインの DNS 設定に移動して、新しい SRV レコードを追加します。
  - サービス = `_rmsredir`
  - Protocol = `_http`
  - Name = `_tcp`
  - Target = `[GUID].rms.aadrm.cn` (GUID は RMS ID です)
  - Priority、Weight、Seconds、TTL = 既定値

- [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)のテナントにカスタムドメインを関連付けます。 DNS にエントリが追加されます。これにより、DNS 設定に値を追加した後に、確認に数分かかる場合があります。

- 対応するグローバル管理者の資格情報を使用して Microsoft 365 管理センターにログインし、ドメインを追加します (例: `contoso.cn` )。 検証プロセスでは、追加の DNS 変更が必要になることがあります。 確認が完了したら、ユーザーを作成できます。

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>暗号化の DNS 構成 (Mac、iOS、Android)

- DNS プロバイダーにログインし、ドメインの DNS 設定に移動して、新しい SRV レコードを追加します。
  - サービス = `_rmsdisco`
  - Protocol = `_http`
  - Name = `_tcp`
  - Target = `api.aadrm.cn`
  - ポート = `80`
  - Priority、Weight、Seconds、TTL = 既定値
