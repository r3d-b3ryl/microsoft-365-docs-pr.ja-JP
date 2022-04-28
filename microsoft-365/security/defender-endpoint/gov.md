---
title: 米国政府のお客様向けの Microsoft Defender for Endpoint
description: 利用可能な米国政府機関のお客様の要件と機能のMicrosoft Defender for Endpointについて説明します
keywords: government, gcc, high, requirements, capabilities, defender, Microsoft Defender for Endpoint, endpoint, dod
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
ms.openlocfilehash: 51f9c373a68e34ffafa5c3763b8efe77fa2c6146
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65098738"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>米国政府のお客様向けの Microsoft Defender for Endpoint

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Azure US Government 環境に組み込まれている米国政府機関のお客様向けのMicrosoft Defender for Endpointは、Azure Commercial の Defender for Endpoint と同じ基盤となるテクノロジを使用します。

このオファリングは、GCC、GCC High、DoD のお客様が利用でき、商用バージョンと同じ防止、検出、調査、修復に基づいています。 ただし、このオファリングの機能の可用性にはいくつかの違いがあります。

> [!NOTE]
> コマーシャルで Defender for Endpoint を使用しているGCCのお客様は、パブリック ドキュメント ページを参照してください。

## <a name="licensing-requirements"></a>ライセンスの要件

米国政府機関のお客様向けのMicrosoft Defender for Endpointには、次のいずれかの Microsoft ボリューム ライセンス オファーが必要です。

### <a name="desktop-licensing"></a>デスクトップ ライセンス

<br />

****

|GCC|GCC High|DoD|
|---|---|---|
|Microsoft 365 GCC G5|GCC High のMicrosoft 365 E5|MICROSOFT 365 G5 for DOD|
|Microsoft 365 G5 セキュリティ GCC|Microsoft 365 G5 Security for GCC High|MICROSOFT 365 G5 Security for DOD|
|Microsoft Defender for Endpoint - GCC|GCC High のMicrosoft Defender for Endpoint|DOD のMicrosoft Defender for Endpoint|
|E5 GCCをWindows 10 Enterpriseする|Windows 10 Enterprise E5 for GCC High|DOD の E5 のWindows 10 Enterprise|
|

### <a name="server-licensing"></a>サーバー ライセンス

<br />

****

|GCC|GCC High|DoD|
|---|---|---|
|Microsoft Defender for Endpoint サーバー GCC|GCC High 用Microsoft Defender for Endpoint サーバー|MICROSOFT DEFENDER FOR ENDPOINT サーバー for DOD|
|Microsoft Defender for servers|Microsoft Defender for servers - Government|Microsoft Defender for servers - Government|
|

## <a name="portal-urls"></a>ポータル URL

米国政府機関のお客様向けのMicrosoft Defender for Endpoint ポータル URL を次に示します。

<br />

****

|お客様の種類|ポータル URL|
|---|---|
|GCC|<https://security.microsoft.com>|
|GCC High|<https://security.microsoft.us>|
|DoD|<https://security.apps.mil>|
|
> [!NOTE]
> GCC顧客であり、Microsoft Defender for EndpointコマーシャルからGCCに移行する過程にある場合は、Microsoft Defender for Endpoint商用データにアクセスするために使用https://transition.security.microsoft.comします。

## <a name="endpoint-versions"></a>エンドポイントのバージョン

### <a name="standalone-os-versions"></a>スタンドアロン OS バージョン

次の OS バージョンがサポートされています。

<br />

****

OS のバージョン|GCC|GCC High|DoD
:---|:---:|:---:|:---:
Windows 11|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 10バージョン 21H1 以降|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 10バージョン 20H2 ([KB4586853](https://support.microsoft.com/help/4586853) <sup>1</sup>)|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 10バージョン 2004 ([KB4586853](https://support.microsoft.com/help/4586853) <sup>1</sup>)|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 10バージョン 1909 ([KB4586819](https://support.microsoft.com/help/4586819) <sup>1</sup>)|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 10バージョン 1903 ([KB4586819](https://support.microsoft.com/help/4586819) <sup>1</sup>)|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 10 Version 1809 ([KB4586839](https://support.microsoft.com/help/4586839) <sup>1</sup>)|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 10バージョン 1803 ([KB4598245](https://support.microsoft.com/help/4598245) <sup>1</sup>)|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 10バージョン 1709|![その必要はありません。](images/svg/check-no.svg) <br /> 注: サポートされません|![[KB4499147](https://support.microsoft.com/help/4499147) <sup>1</sup> ではい](images/svg/check-yes.svg) <br /> 注: [非推奨、](/lifecycle/announcements/revised-end-of-service-windows-10-1709)アップグレードしてください|![なし](images/svg/check-no.svg) <br /> 注: サポートされません
Windows 10バージョン 1703 以前|![その必要はありません。](images/svg/check-no.svg) <br /> 注: サポートされません|![いいえ](images/svg/check-no.svg) <br /> 注: サポートされません|![いいえ](images/svg/check-no.svg) <br /> 注: サポートされません
Windows Server 2022|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows Server 2019 ([KB4586839](https://support.microsoft.com/help/4586839) <sup>1</sup>)|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows Server 2016 (モダン) <sup>2</sup>|![はい。](images/svg/check-yes.svg) <br /> パブリック プレビュー|![はい](images/svg/check-yes.svg) <br /> パブリック プレビュー|![はい](images/svg/check-yes.svg) <br /> パブリック プレビュー
Windows Server 2012 R2 (モダン) <sup>2</sup>|![はい。](images/svg/check-yes.svg) <br /> パブリック プレビュー|![はい](images/svg/check-yes.svg) <br /> パブリック プレビュー|![はい](images/svg/check-yes.svg) <br /> パブリック プレビュー
Windows Server 2016 (レガシ) <sup>3</sup>|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows Server 2012 R2 (レガシ) <sup>3</sup>|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 (レガシ) <sup>3</sup>|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 8.1 Enterprise (レガシ) <sup>3</sup>|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 8 Pro (レガシ) <sup>3</sup>|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 7 SP1 Enterprise (レガシ) <sup>3</sup>|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Windows 7 SP1 Pro (レガシ) <sup>3</sup>|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Linux|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
macOS|![はい。](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)
Android|![はい。](images/svg/check-yes.svg) <br /> パブリック プレビュー|![はい](images/svg/check-yes.svg) <br /> パブリック プレビュー|![はい](images/svg/check-yes.svg) <br /> パブリック プレビュー
iOS|![はい。](images/svg/check-yes.svg) <br /> パブリック プレビュー|![はい](images/svg/check-yes.svg) <br /> パブリック プレビュー|![はい](images/svg/check-yes.svg) <br /> パブリック プレビュー
|

> [!NOTE]
> <sup>1</sup> Defender for Endpoint を正しい環境に構成するには、デバイスオンボードの前にパッチを展開する必要があります。
>
> <sup>2</sup> [Windows 2016 および 2012 R2 の統合モダン ソリューション](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution)について説明します。 MMA を使用して以前にサーバーをオンボードしたことがある場合は、[［サーバーの移行］](server-migration.md) に記載されているガイダンスに従って、新しいソリューションに移行してください。
>
> <sup>3</sup> [Microsoft Monitoring Agent](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma)を使用する場合は、[セットアップ ウィザード](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)を使用する場合、または[コマンド ライン](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)またはスクリプトを使用する場合は、"Azure Cloud" で "Azure US Government" を選択する必要があります。コマンド ラインまたは[スクリプト](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)を使用する場合は、"OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" パラメーターを 1 に設定します。 <br /> MMA でサポートされている最小バージョンは 10.20.18029 (2020 年 3 月) です。

### <a name="os-versions-when-using-microsoft-defender-for-servers"></a>サーバーに Microsoft Defender を使用する場合の OS バージョン

[サーバーに Microsoft Defender](/azure/security-center/security-center-wdatp) を使用する場合は、次の OS バージョンがサポートされます。

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

## <a name="required-connectivity-settings"></a>必要な接続設定

プロキシまたはファイアウォールが既定ですべてのトラフィックをブロックし、特定のドメインの通過だけを許可している場合は、ダウンロード可能シートに記載されているドメインを許可ドメインのリストに追加します。

次のダウンロード可能なスプレッドシートには、ネットワークが接続できる必要があるサービスとその関連 URL が一覧表示されます。 これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルター規則がないことを確認するか、それらに対して特別に *許可* 規則を作成します。

|ドメイン リストのスプレッドシート| 説明|
|---|---|
|商用顧客向けの Microsoft Defender for Endpoint の URL リスト| 商用顧客向けサービスの場所、地理的な場所、OS に関する特定の DNS レコードのスプレッドシート。 <p> [ここにスプレッドシートをダウンロードします。](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)
| Gov/GCC/DoD 向けの Microsoft Defender for Endpoint の URL リスト | Gov/GCC/DoD のお客様向けのサービスの場所、地理的な場所、OS の特定の DNS レコードのスプレッドシート。 <p> [ここにスプレッドシートをダウンロードします。](https://download.microsoft.com/download/6/a/0/6a041da5-c43b-4f17-8167-79dfdc10507f/mde-urls-gov.xlsx)

詳細については、「 [デバイス プロキシとインターネット接続の設定を構成する](configure-proxy-internet.md)」を参照してください。

> [!NOTE]
> スプレッドシートには商用 URL も含まれています。必ず [US Gov] タブをオンにします。
>
> フィルター処理を行うときは、"US Gov" というラベルの付いたレコードと、地理列の下にある特定のクラウドを探します。

## <a name="api"></a>API

[API ドキュメント](apis-intro.md)に記載されているパブリック URI の代わりに、次の URI を使用する必要があります。

<br />

****

|エンドポイントの種類|GCC|GCC 高& DoD|
|---|---|---|
|ログイン|`https://login.microsoftonline.com`|`https://login.microsoftonline.us`|
|Defender for Endpoint API|`https://api-gcc.securitycenter.microsoft.us`|`https://api-gov.securitycenter.microsoft.us`|
|SIEM|`https://wdatp-alertexporter-us.gcc.securitycenter.windows.us`|`https://wdatp-alertexporter-us.securitycenter.windows.us`|
|

## <a name="feature-parity-with-commercial"></a>商用の機能パリティ

米国政府機関向け Defender for Endpoint のお客様は、商用サービスと完全な同等性を持っていません。 私たちの目標は、すべての商用機能と機能を米国政府機関のお客様に提供することですが、まだ利用できない機能がいくつかあります。

既知のギャップは次のとおりです。

<br />

****

|フィーチャー名|GCC|GCC High|DoD|
|---|:---:|:---:|:---:|
|ネットワーク評価|![なし](images/svg/check-no.svg) 開発中|![なし](images/svg/check-no.svg) 開発中|![いいえ](images/svg/check-no.svg) 開発中|
|ネットワーク検出|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|
|レポート: デバイス制御、デバイスの正常性、ファイアウォール|![いいえ](images/svg/check-no.svg) 開発中|![なし](images/svg/check-no.svg) 開発中|![いいえ](images/svg/check-no.svg) 開発中|
|Web コンテンツ フィルタリング|![いいえ](images/svg/check-no.svg) 開発中|![いいえ](images/svg/check-no.svg) 開発中|![いいえ](images/svg/check-no.svg) 開発中|
  

[Mobile Threat Defense (Android & iOS 上のMicrosoft Defender for Endpoint)](mtd.md) の機能と既知のギャップを次に示します。

<br />

****

|フィーチャー名|GCC|GCC High|DoD|
|---|:---:|:---:|:---:|
|Web Protection (フィッシング対策とカスタム インジケーター)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|
|Malware Protection (Android のみ)|![なし](images/svg/check-no.svg) 開発中|![なし](images/svg/check-no.svg) 開発中|![なし](images/svg/check-no.svg) 開発中|
|脱獄検出 (iOS のみ)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|
|条件付きアクセス/条件付き起動|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|
|MAM のサポート|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|
|プライバシー コントロール|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|![はい](images/svg/check-yes.svg)|
|脅威と脆弱性の管理 (TVM)|![いいえ](images/svg/check-no.svg) 開発中|![いいえ](images/svg/check-no.svg) 開発中|![いいえ](images/svg/check-no.svg) 開発中|
  

