---
title: 米国政府のお客様向けの Microsoft Defender for Endpoint
description: 利用可能な米国政府機関Microsoft Defender for Endpoint要件と機能の概要
keywords: government, gcc, high, requirements, capabilitis, defender, Microsoft Defender for Endpoint, エンドポイント, dod
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b6c9594112e347439945d3c21f61f9272edb935f
ms.sourcegitcommit: bcbcbd4ddc72ad2fed629619d23fac5827d072bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2022
ms.locfileid: "64507369"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>米国政府のお客様向けの Microsoft Defender for Endpoint

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft Defender for Endpoint米国政府機関環境で構築された米国政府機関のお客様は、Azure Commercial の Defender for Endpoint と同じ基になるテクノロジを使用します。

この製品は、GCC、GCC、DoD のお客様に提供され、商用バージョンと同じ予防、検出、調査、修復に基づいて提供されます。 ただし、このサービスの機能の可用性にはいくつかの違いがあります。

> [!NOTE]
> 商用で Defender for Endpoint をGCCするユーザーの場合は、パブリック ドキュメント ページを参照してください。

## <a name="licensing-requirements"></a>ライセンスの要件

Microsoft Defender for Endpointのお客様には、次のいずれかの Microsoft ボリューム ライセンスオファーが必要です。

### <a name="desktop-licensing"></a>デスクトップ ライセンス

<br />

****

|GCC|GCC High|DoD|
|---|---|---|
|Microsoft 365 GCC G5|Microsoft 365 E5 High のGCC|Microsoft 365 G5 for DOD|
|Microsoft 365 G5 セキュリティ GCC|Microsoft 365 G5 Security for GCC High|Microsoft 365 G5 Security for DOD|
|Microsoft Defender for Endpoint - GCC|Microsoft Defender for Endpoint High のGCC|Microsoft Defender for Endpoint DOD の詳細|
|Windows 10 Enterprise E5 GCC|Windows 10 Enterprise E5 for GCC High|Windows 10 Enterprise E5 for DOD|
|

### <a name="server-licensing"></a>サーバー ライセンス

<br />

****

|GCC|GCC High|DoD|
|---|---|---|
|Microsoft Defender for Endpoint サーバー GCC|Microsoft Defender for Endpoint サーバー for GCC High|Microsoft Defender for Endpoint サーバー for DOD|
|サーバー用 Microsoft Defender|Microsoft Defender for servers - Government|Microsoft Defender for servers - Government|
|

## <a name="portal-urls"></a>ポータル URL

米国政府機関のお客様向Microsoft Defender for Endpointポータル URL を次に示します。

<br />

****

|お客様の種類|ポータル URL|
|---|---|
|GCC|<https://security.microsoft.com>|
|GCC High|<https://security.microsoft.us>|
|DoD|<https://security.microsoft.us>|
|
> [!NOTE]
> お客様がGCCの顧客でありhttps://transition.security.microsoft.com、商用からMicrosoft Defender for Endpointに移行するGCC、商用データにアクセスMicrosoft Defender for Endpoint使用します。

## <a name="endpoint-versions"></a>エンドポイントのバージョン

### <a name="standalone-os-versions"></a>スタンドアロン OS のバージョン

次の OS バージョンがサポートされています。

<br />

****

OS のバージョン|GCC|GCC High|DoD
:---|:---:|:---:|:---:
Windows 11|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 10バージョン 21H1 以上|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 10バージョン 20H2 ([KB4586853](https://support.microsoft.com/help/4586853) <sup>1)</sup>|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 10バージョン 2004 ([KB4586853](https://support.microsoft.com/help/4586853) <sup>1)</sup>|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 10バージョン 1909 ([KB4586819](https://support.microsoft.com/help/4586819) <sup>1)</sup>|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 10バージョン 1903 ([KB4586819](https://support.microsoft.com/help/4586819) <sup>1)</sup>|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 10 Version 1809 ([KB4586839](https://support.microsoft.com/help/4586839) <sup>1)</sup>|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 10バージョン 1803 ([KB4598245](https://support.microsoft.com/help/4598245) <sup>1)</sup>|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 10バージョン 1709|![いいえ。](images/svg/check-no.svg) <br /> 注: サポートされません|![は](images/svg/check-yes.svg) い [KB4499147](https://support.microsoft.com/help/4499147) <sup>1</sup> <br /> 注: [非推奨、](/lifecycle/announcements/revised-end-of-service-windows-10-1709)アップグレードしてください|![いいえ](images/svg/check-no.svg) <br /> 注: サポートされません
Windows 10バージョン 1703 以前|![いいえ。](images/svg/check-no.svg) <br /> 注: サポートされません|![いいえ](images/svg/check-no.svg) <br /> 注: サポートされません|![不要](images/svg/check-no.svg) <br /> 注: サポートされません
Windows Server 2022|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows Server 2019 ([KB4586839](https://support.microsoft.com/help/4586839) <sup>1)</sup>|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows Server 2016 (モダン) <sup>2</sup>|![はい。](images/svg/check-yes.svg) <br /> パブリック プレビュー|![はい](images/svg/check-yes.svg) <br /> パブリック プレビュー|![はい](images/svg/check-yes.svg) <br /> パブリック プレビュー
Windows Server 2012 R2 (モダン) <sup>2</sup>|![はい。](images/svg/check-yes.svg) <br /> パブリック プレビュー|![はい](images/svg/check-yes.svg) <br /> パブリック プレビュー|![はい](images/svg/check-yes.svg) <br /> パブリック プレビュー
Windows Server 2016 (レガシ) <sup>3</sup>|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows Server 2012 R2 (Legacy) <sup>3</sup>|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 (Legacy) <sup>3</sup>|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 8.1 Enterprise (レガシ) <sup>3</sup>|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 8 Pro (レガシ) <sup>3</sup>|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 7 SP1 Enterprise (Legacy) <sup>3</sup>|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 7 SP1 Pro (Legacy) <sup>3</sup>|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Linux|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
macOS|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Android|![はい。](images/svg/check-yes.svg) <br /> パブリック プレビュー|![はい](images/svg/check-yes.svg) <br /> パブリック プレビュー|![はい](images/svg/check-yes.svg) <br /> パブリック プレビュー
iOS|![はい。](images/svg/check-yes.svg) <br /> パブリック プレビュー|![はい](images/svg/check-yes.svg) <br /> パブリック プレビュー|![はい](images/svg/check-yes.svg) <br /> パブリック プレビュー
|

> [!NOTE]
> <sup>1</sup> Defender for Endpoint を正しい環境に構成するには、デバイスオンボーディングの前にパッチを展開する必要があります。
>
> <sup>2</sup> [2016 および 2012 R2](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution-preview) の統合モダン Windowsについて学習します。 以前に MMA を使用してサーバーをオンボードした場合は、「 [Server migration](server-migration.md) 」のガイダンスに従って新しいソリューションに移行します。
>
> <sup>3</sup> [Microsoft Monitoring Agent](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma) を使用する場合は、セットアップ ウィザードを使用する場合、またはコマンド ラインまたはスクリプトを使用する場合は、[Azure Cloud] で [Azure US Government[](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)] を選択する[](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)必要があります。"OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" パラメーターを 1 に設定します。[](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard) <br /> サポートされる最小 MMA バージョンは 10.20.18029 (2020 年 3 月) です。

### <a name="os-versions-when-using-microsoft-defender-for-servers"></a>サーバーに Microsoft Defender を使用する場合の OS のバージョン

Microsoft Defender をサーバーに使用する場合は、次の [OS バージョンがサポートされます](/azure/security-center/security-center-wdatp)。

<br />

****

OS のバージョン|GCC|GCC High|DoD
:---|:---:|:---:|:---:
Windows Server 2022|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows Server 2019|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows Server 2016|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows Server 2012 R2|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
|

## <a name="required-connectivity-settings"></a>必須の接続設定

プロキシまたはファイアウォールが既定ですべてのトラフィックをブロックし、特定のドメインの通過だけを許可している場合は、ダウンロード可能シートに記載されているドメインを許可ドメインのリストに追加します。

次のダウンロード可能なスプレッドシートには、ネットワークが接続できる必要があるサービスと関連付けられている URL が一覧表示されます。 これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルタールールが存在しないか、許可ルールを作成します。

|ドメインリストのスプレッドシート| 説明|
|---|---|
|Microsoft Defender for Endpointの URL リスト| 商用顧客向けサービスの場所、地理的な場所、OS に関する特定の DNS レコードのスプレッドシート。 <p> [ここにスプレッドシートをダウンロードします。](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)
| Microsoft Defender for Endpoint/Gov/GCC/DoD の URL リスト | Gov/GCC/DoD のお客様向けサービスの場所、地理的な場所、OS の特定の DNS レコードのスプレッドシート。 <p> [ここにスプレッドシートをダウンロードします。](https://download.microsoft.com/download/6/a/0/6a041da5-c43b-4f17-8167-79dfdc10507f/mde-urls-gov.xlsx)

詳細については、「デバイス プロキシと [インターネット接続の設定を構成する」を参照してください](configure-proxy-internet.md)。

> [!NOTE]
> スプレッドシートには商用 URL も含まれています。必ず [US Gov] タブを確認してください。
>
> フィルター処理を行う場合は、"US Gov" というラベルが付いたレコードと、地理列の下にある特定のクラウドを探します。

## <a name="api"></a>API

API ドキュメントに記載されているパブリック URI の代わりに、次の [URI](apis-intro.md) を使用する必要があります。

<br />

****

|エンドポイントの種類|GCC|GCC高& DoD|
|---|---|---|
|ログイン|`https://login.microsoftonline.com`|`https://login.microsoftonline.us`|
|Defender for Endpoint API|`https://api-gcc.securitycenter.microsoft.us`|`https://api-gov.securitycenter.microsoft.us`|
|SIEM|`https://wdatp-alertexporter-us.gcc.securitycenter.windows.us`|`https://wdatp-alertexporter-us.securitycenter.windows.us`|
|

## <a name="feature-parity-with-commercial"></a>商用機能と機能のパリティ

米国政府機関のお客様向けエンドポイントの Defender は、商用サービスと完全に同一性を持つ必要があります。 すべての商用機能と機能を米国政府機関のお客様に提供しますが、まだ利用できない機能がいくつか用意されています。

既知のギャップは次のとおりです。

<br />

****

|フィーチャー名|GCC|GCC High|DoD|
|---|:---:|:---:|:---:|
|ネットワーク評価|![不要](images/svg/check-no.svg) 開発中|![不要](images/svg/check-no.svg) 開発中|![不要](images/svg/check-no.svg) 開発中|
|ネットワーク検出|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|
|レポート: デバイス制御、デバイスの正常性、ファイアウォール|![不要](images/svg/check-no.svg) 開発中|![不要](images/svg/check-no.svg) 開発中|![不要](images/svg/check-no.svg) 開発中|
|Web コンテンツ フィルタリング|![不要](images/svg/check-no.svg) 開発中|![不要](images/svg/check-no.svg) 開発中|![不要](images/svg/check-no.svg) 開発中|
  

Mobile Threat Defense の機能と既知のギャップを次に示します [(Android Microsoft Defender for Endpoint iOS &)](mtd.md)

<br />

****

|フィーチャー名|GCC|GCC High|DoD|
|---|:---:|:---:|:---:|
|Web 保護 (フィッシング対策とカスタム インジケーター)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|
|マルウェア保護 (Android-Only)|![不要](images/svg/check-no.svg) 開発中|![不要](images/svg/check-no.svg) 開発中|![不要](images/svg/check-no.svg) 開発中|
|脱獄検出 (iOS-Only)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|
|条件付きアクセス/条件付き起動|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|
|MAM のサポート|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|
|プライバシーコントロール|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|
|脅威と脆弱性の管理 (TVM)|![いいえ](images/svg/check-no.svg) 開発中|![不要](images/svg/check-no.svg) 開発中|![不要](images/svg/check-no.svg) 開発中|
|Web コンテンツ フィルタリング|![いいえ](images/svg/check-no.svg) 開発中|![不要](images/svg/check-no.svg) 開発中|![不要](images/svg/check-no.svg) 開発中|
  

