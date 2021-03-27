---
title: 米国政府機関のお客様向けエンドポイント向け Microsoft Defender
description: Microsoft Defender for Endpoint for US Government のお客様の要件と利用可能な機能について説明します。
keywords: government, gcc, high, requirements, capabilitis, defender, defender atp, mdatp, endpoint, dod
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 089614fab57950af5f60181ce7ed2116046ad347
ms.sourcegitcommit: a965c498e6b3890877f895d5197898b306092813
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51379372"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>米国政府機関のお客様向けエンドポイント向け Microsoft Defender

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint for US Government のお客様は、Azure US Government 環境で構築され、Azure Commercial の Defender for Endpoint と同じ基礎テクノロジを使用します。

この製品は、GCC、GCC High、DoD のお客様が利用できる製品で、商用バージョンと同じ予防、検出、調査、修復に基づいて提供されます。 ただし、このサービスの機能の可用性にはいくつかの違いがあります。

> [!NOTE]
> 商用で Defender for Endpoint を使用している GCC のお客様は、パブリック ドキュメント ページを参照してください。

## <a name="licensing-requirements"></a>ライセンスの要件
Microsoft Defender for Endpoint for US Government のお客様には、次のいずれかの Microsoft ボリューム ライセンスオファーが必要です。

### <a name="desktop-licensing"></a>デスクトップ ライセンス
GCC | GCC High | DoD
:---|:---|:---
Windows 10 Enterprise E5 GCC | Windows 10 Enterprise E5 for GCC High | Windows 10 Enterprise E5 for DOD
| | Microsoft 365 E5 for GCC High | Microsoft 365 G5 for DOD
| | Microsoft 365 G5 Security for GCC High | Microsoft 365 G5 Security for DOD
エンドポイント用 Microsoft Defender - GCC | Microsoft Defender for Endpoint for GCC High | Microsoft Defender for Endpoint for DOD

### <a name="server-licensing"></a>サーバー ライセンス
GCC | GCC High | DoD
:---|:---|:---
Microsoft Defender for Endpoint Server GCC | Microsoft Defender for Endpoint Server for GCC High | Microsoft Defender for Endpoint Server for DOD
サーバー用 Azure Defender | サーバー用 Azure Defender - Government | サーバー用 Azure Defender - Government

<br />

## <a name="portal-urls"></a>ポータル URL
米国政府機関のお客様向け Microsoft Defender for Endpoint ポータル URL を次に示します。

お客様の種類 | ポータル URL
:---|:---
GCC | https://gcc.securitycenter.microsoft.us
GCC High | https://securitycenter.microsoft.us
DoD | https://securitycenter.microsoft.us

<br />

## <a name="endpoint-versions"></a>エンドポイントのバージョン

### <a name="standalone-os-versions"></a>スタンドアロン OS のバージョン
次の OS バージョンがサポートされています。

OS のバージョン | GCC | GCC High | DoD
:---|:---|:---|:---
Windows 10 バージョン 20H2 [(KB4586853 )](https://support.microsoft.com/help/4586853) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
Windows 10 バージョン 2004 [(KB4586853 )](https://support.microsoft.com/help/4586853) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
Windows 10 バージョン 1909 [(KB4586819](https://support.microsoft.com/help/4586819)) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
Windows 10 バージョン 1903 [(KB4586819](https://support.microsoft.com/help/4586819)) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
Windows 10 バージョン 1809 [(KB4586839](https://support.microsoft.com/help/4586839)) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
Windows 10 バージョン 1803 [(KB4598245 )](https://support.microsoft.com/help/4598245) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
Windows 10 バージョン 1709 | ![いいえ](images/svg/check-no.svg)<br />注: サポートされません | ![は ](images/svg/check-yes.svg) い [KB4499147](https://support.microsoft.com/help/4499147)<br />注: [非推奨 、](https://docs.microsoft.com/lifecycle/announcements/revised-end-of-service-windows-10-1709)アップグレードしてください | ![いいえ](images/svg/check-no.svg)<br />注: サポートされません
Windows 10 バージョン 1703 以前 | ![いいえ](images/svg/check-no.svg)<br />注: サポートされません | ![いいえ](images/svg/check-no.svg)<br />注: サポートされません | ![いいえ](images/svg/check-no.svg)<br />注: サポートされません
Windows Server 2019 [(KB4586839](https://support.microsoft.com/help/4586839)を使用) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
Windows Server 2016 | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
Windows 8.1 Enterprise | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
Windows 8 Pro | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
Windows 7 SP1エンタープライズ | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
Windows 7 SP1 Pro | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
Linux | ![必要](images/svg/check-yes.svg) プレビューで<br />以下のメモを参照してください。 | ![必要](images/svg/check-yes.svg) プレビューで<br />以下のメモを参照してください。 | ![必要](images/svg/check-yes.svg) プレビューで<br />以下のメモを参照してください。
macOS | ![必要](images/svg/check-yes.svg) プレビューで<br />以下のメモを参照してください。 | ![必要](images/svg/check-yes.svg) プレビューで<br />以下のメモを参照してください。 | ![必要](images/svg/check-yes.svg) プレビューで<br />以下のメモを参照してください。
Android | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて
iOS | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて

> [!NOTE]
> パッチが指定されている場合、Defender for Endpoint を正しい環境に構成するには、デバイスオンボーディングの前に展開する必要があります。

> [!NOTE]
> Microsoft Monitoring Agent を使用して Windows 10 または Windows Server 2019 より古い Windows デバイス[をオンボードしようとしている場合](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma) セットアップ ウィザードを使用する場合、またはコマンド ラインまたはスクリプトを使用する場合は、[Azure Cloud] で[](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)[Azure [](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) US Government] を選択する必要があります。"OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" パラメーターを 1 に設定します。 [](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)

> [!NOTE]
> Linux ではバージョン 101.25.72 以上、macOS ではバージョン 101.25.69 以上が必要です。 プレビュー中は、これらのバージョンは "Insider Fast" チャネルでのみ利用可能です。 手順 [については、「Linux ソフトウェア リポジトリを構成](linux-install-manually.md#configure-the-linux-software-repository) する」または [「チャネル名を設定する (macOS)」](mac-updates.md#set-the-channel-name) を参照してください。

### <a name="os-versions-when-using-azure-defender-for-servers"></a>Azure Defender for Servers を使用する場合の OS のバージョン
Azure Defender for Servers を使用する場合は、次の [OS バージョンがサポートされます](https://docs.microsoft.com/azure/security-center/security-center-wdatp)。

OS のバージョン | GCC | GCC High | DoD
:---|:---|:---|:---
Windows Server 2016 | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)

<br />

## <a name="required-connectivity-settings"></a>必須の接続設定
プロキシまたはファイアウォールが既定ですべてのトラフィックをブロックし、特定のドメインの通過だけを許可している場合は、ダウンロード可能シートに記載されているドメインを許可ドメインのリストに追加します。

次のダウンロード可能なスプレッドシートには、ネットワークが接続できる必要があるサービスと関連付けられている URL が一覧表示されます。 これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルター ルールが存在しないか、またはそれらの URL 専用の許可ルールを作成します。

ドメインリストのスプレッドシート | 説明
:-----|:-----
![Microsoft Defender for Endpoint URL スプレッドシートのサム イメージ](images/mdatp-urls.png)<br/> | サービスの場所、地理的な場所、および OS の特定の DNS レコードのスプレッドシート。 <br /><br />[ここにスプレッドシートをダウンロードします。](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

詳細については、「デバイス プロキシと [インターネット接続の設定を構成する」を参照してください](configure-proxy-internet.md)。

> [!NOTE]
> スプレッドシートには商用 URL も含まれています。必ず [US Gov] タブを確認してください。
> 
> フィルター処理を行う場合は、"US Gov" というラベルが付いたレコードと、地理列の下にある特定のクラウドを探します。

### <a name="service-backend-ip-ranges"></a>サービス バックエンドの IP 範囲

ネットワーク デバイスが DNS ベースのルールをサポートしない場合は、代わりに IP 範囲を使用します。

米国政府機関のお客様向けエンドポイントの Defender は、Azure US Government 環境に構築され、次の地域に展開されます。

- AzureCloud.usgovtexas
- AzureCloud.usgovvirginia

Azure IP 範囲とサービス タグ – US Government Cloud で Azure IP 範囲 [を確認できます](https://www.microsoft.com/download/details.aspx?id=57063)。

> [!NOTE]
> クラウドベースのソリューションとして、IP アドレス範囲が変更される可能性があります。 DNS ベースのルールに移動する必要があります。

<br />

## <a name="api"></a>API
API ドキュメントに記載されているパブリック URI の代わりに、次の [URI](apis-intro.md)を使用する必要があります。

エンドポイントの種類 | GCC | GCC High & DoD
:---|:---|:---
ログイン | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
Defender for Endpoint API | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
SIEM | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br />

## <a name="feature-parity-with-commercial"></a>商用機能と機能のパリティ
米国政府機関のお客様向けエンドポイントの Defender は、商用サービスと完全に同一性を持つ必要があります。 すべての商用機能と機能を米国政府機関のお客様に提供しますが、まだ利用できない機能がいくつか用意されています。

これらは、2021 年 3 月の既知のギャップです。

フィーチャー名 | GCC | GCC High | DoD
:---|:---|:---|:---
自動調査と修復: ライブ応答 | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
自動調査と修復: 365 Officeへの応答 | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて
メール通知 | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
評価ラボ | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
管理と API: デバイスの正常性とコンプライアンス レポート | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
管理と API: サードパーティ製品との統合 | ![いいえ](images/svg/check-no.svg) ロール アウト | ![いいえ](images/svg/check-no.svg) ロール アウト | ![いいえ](images/svg/check-no.svg) ロール アウト
管理と API: ストリーミング API | ![必要](images/svg/check-yes.svg) | ![いいえ](images/svg/check-no.svg) 開発中 | ![いいえ](images/svg/check-no.svg) 開発中
管理と API: 脅威保護レポート | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
脅威&の管理 | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
脅威の分析 | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
Web コンテンツ のフィルター処理 | ![いいえ](images/svg/check-no.svg) 開発中 | ![いいえ](images/svg/check-no.svg) 開発中 | ![いいえ](images/svg/check-no.svg) 開発中
統合: Azure Sentinel | ![必要](images/svg/check-yes.svg) | ![いいえ](images/svg/check-no.svg) 開発中 | ![いいえ](images/svg/check-no.svg) 開発中
統合: Microsoft Cloud App Security | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて
統合: Microsoft コンプライアンス マネージャー | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて
統合: Microsoft Defender for Identity | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて
統合: Microsoft Defender for Office 365 | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて
統合: Microsoft Endpoint DLP | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて
統合: Microsoft Intune | ![必要](images/svg/check-yes.svg) | ![いいえ](images/svg/check-no.svg) 開発中 | ![いいえ](images/svg/check-no.svg) 開発中
統合: Microsoft Power Automate & Azure Logic Apps | ![必要](images/svg/check-yes.svg) | ![いいえ](images/svg/check-no.svg) 開発中 | ![いいえ](images/svg/check-no.svg) 開発中
統合: Skype for Business / Teams | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![必要](images/svg/check-yes.svg)
Microsoft 脅威エキスパート | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリング バックログについて
