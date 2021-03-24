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
ms.openlocfilehash: 31928deddc2a504cc0b6c91af287e4977791c920
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065868"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>米国政府機関のお客様向けエンドポイント向け Microsoft Defender

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint for US Government の顧客は、米国 Azure Government 環境で構築され、Azure Commercial の Defender for Endpoint と同じ基になるテクノロジを使用します。

この製品は、GCC、GCC High、DoD のお客様が利用できる製品で、商用バージョンと同じ予防、検出、調査、修復に基づいて提供されます。 ただし、このサービスの機能の可用性にはいくつかの違いがあります。

> [!NOTE]
> 商用で Defender for Endpoint を使用している GCC のお客様は、パブリック ドキュメント ページを参照してください。

## <a name="licensing-requirements"></a>ライセンスの要件
Microsoft Defender for Endpoint for US Government のお客様には、次のいずれかの Microsoft ボリューム ライセンスオファーが必要です。

### <a name="desktop-licensing"></a>デスクトップ ライセンス
GCC | GCC High | DoD
:---|:---|:---
Windows 10 Enterprise E5 GCC | Windows 10 Enterprise E5 for GCC High | Windows 10 Enterprise E5 for DOD
| | Microsoft 365 E5 for GCC High | 
| | Microsoft 365 G5 Security for GCC High | 
エンドポイント用 Microsoft Defender - GCC | Microsoft Defender for Endpoint for GCC High | Microsoft Defender for Endpoint for DOD

### <a name="server-licensing"></a>サーバー ライセンス
GCC | GCC High | DoD
:---|:---|:---
Microsoft Defender for Endpoint Server GCC | Microsoft Defender for Endpoint Server for GCC High | Microsoft Defender for Endpoint Server for DOD
サーバー用 Azure Defender | サーバー用 Azure Defender - Government | サーバー用 Azure Defender - Government

> [!NOTE]
> DoD ライセンスは、DoD の一般提供でのみ利用できます。

<br>

## <a name="portal-urls"></a>ポータル URL
米国政府機関のお客様向け Microsoft Defender for Endpoint ポータル URL を次に示します。

お客様の種類 | ポータル URL
:---|:---
GCC | https://gcc.securitycenter.microsoft.us
GCC High | https://securitycenter.microsoft.us
DoD (PREVIEW) | https://securitycenter.microsoft.us

<br>

## <a name="endpoint-versions"></a>エンドポイントのバージョン

### <a name="standalone-os-versions"></a>スタンドアロン OS のバージョン
次の OS バージョンがサポートされています。

OS のバージョン | GCC | GCC High | DoD (PREVIEW)
:---|:---|:---|:---
Windows 10 バージョン 20H2 [(KB4586853 )](https://support.microsoft.com/help/4586853) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg)
Windows 10 バージョン 2004 [(KB4586853 )](https://support.microsoft.com/help/4586853) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)
Windows 10 バージョン 1909 [(KB4586819](https://support.microsoft.com/help/4586819)) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)
Windows 10 バージョン 1903 [(KB4586819](https://support.microsoft.com/help/4586819)) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)
Windows 10 バージョン 1809 [(KB4586839](https://support.microsoft.com/help/4586839)) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)
Windows 10 バージョン 1803 [(KB4598245 )](https://support.microsoft.com/help/4598245) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)
Windows 10 バージョン 1709 | ![いいえ](/security/defender-endpoint/images/svg/check-no)<br>注: サポートされません | ![は ](/security/defender-endpoint/images/svg/check-yes) い [KB4499147](https://support.microsoft.com/help/4499147)<br>注: [非推奨 、](https://docs.microsoft.com/lifecycle/announcements/revised-end-of-service-windows-10-1709)アップグレードしてください | ![いいえ](/security/defender-endpoint/images/svg/check-no)<br>注: サポートされません
Windows 10 バージョン 1703 以前 | ![いいえ](/security/defender-endpoint/images/svg/check-no)<br>注: サポートされません | ![いいえ](/security/defender-endpoint/images/svg/check-no)<br>注: サポートされません | ![いいえ](/security/defender-endpoint/images/svg/check-no)<br>注: サポートされません
Windows Server 2019 [(KB4586839](https://support.microsoft.com/help/4586839)を使用) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)
Windows Server 2016 | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)
Windows Server 2012 R2 | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)
Windows Server 2008 R2 SP1 | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)
Windows 8.1 Enterprise | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)
Windows 8 Pro | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)
Windows 7 SP1エンタープライズ | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)
Windows 7 SP1 Pro | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)
Linux | ![いいえ](/security/defender-endpoint/images/svg/check-no) 開発中 | ![いいえ](/security/defender-endpoint/images/svg/check-no) 開発中 | ![いいえ](/security/defender-endpoint/images/svg/check-no) 開発中
macOS | ![いいえ](/security/defender-endpoint/images/svg/check-no) 開発中 | ![いいえ](/security/defender-endpoint/images/svg/check-no) 開発中 | ![いいえ](/security/defender-endpoint/images/svg/check-no) 開発中
Android | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて
iOS | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて

> [!NOTE]
> パッチが指定されている場合、Defender for Endpoint を正しい環境に構成するには、デバイスオンボーディングの前に展開する必要があります。

> [!NOTE]
> Microsoft Monitoring Agent を使用して Windows 10 または Windows Server 2019 より古い Windows デバイス[をオンボードしようとしている場合](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma) セットアップ ウィザードを使用する場合、またはコマンド ラインまたはスクリプトを使用する場合は、[Azure Cloud] で[](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)[Azure [](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) US Government] を選択する必要があります。"OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" パラメーターを 1 に設定します。 [](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)

### <a name="os-versions-when-using-azure-defender-for-servers"></a>Azure Defender for Servers を使用する場合の OS のバージョン
Azure Defender for Servers を使用する場合は、次の [OS バージョンがサポートされます](https://docs.microsoft.com/azure/security-center/security-center-wdatp)。

OS のバージョン | GCC | GCC High | DoD (PREVIEW)
:---|:---|:---|:---
Windows Server 2016 | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)
Windows Server 2012 R2 | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)
Windows Server 2008 R2 SP1 | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)

<br>

## <a name="required-connectivity-settings"></a>必須の接続設定
プロキシまたはファイアウォールが既定ですべてのトラフィックをブロックし、特定のドメインの通過だけを許可している場合は、ダウンロード可能シートに記載されているドメインを許可ドメインのリストに追加します。

次のダウンロード可能なスプレッドシートには、ネットワークが接続できる必要があるサービスと関連付けられている URL が一覧表示されます。 これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルター ルールが存在しないか、またはそれらの URL 専用の許可ルールを作成します。

ドメインリストのスプレッドシート | 説明
:-----|:-----
![Microsoft Defender for Endpoint URL スプレッドシートのサム イメージ](images/mdatp-urls.png)<br/> | サービスの場所、地理的な場所、および OS の特定の DNS レコードのスプレッドシート。 <br><br>[ここにスプレッドシートをダウンロードします。](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

詳細については、「デバイス プロキシと [インターネット接続の設定を構成する」を参照してください](configure-proxy-internet.md)。

> [!NOTE]
> スプレッドシートには商用 URL も含まれています。必ず [US Gov] タブを確認してください。 <br> フィルター処理を行う場合は、"US Gov" というラベルが付いたレコードと、地理列の下にある特定のクラウドを探します。

<br>

## <a name="api"></a>API
API ドキュメントに記載されているパブリック URI の代わりに、次の [URI](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/apis-intro)を使用する必要があります。

エンドポイントの種類 | GCC | GCC High & DoD (PREVIEW)
:---|:---|:---
ログイン | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
Defender for Endpoint API | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
SIEM | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br>

## <a name="feature-parity-with-commercial"></a>商用機能と機能のパリティ
Defender for Endpoint は、商用サービスと完全なパリティを持つ必要があります。 すべての商用機能と機能を米国政府機関のお客様に提供しますが、まだ利用できない機能がいくつか用意されています。

これらは、2021 年 2 月の既知のギャップです。

フィーチャー名 | GCC | GCC High | DoD (PREVIEW)
:---|:---|:---|:---
自動調査と修復: ライブ応答 | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)
自動調査と修復: 365 Officeへの応答 | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて
メール通知 | ![いいえ](/security/defender-endpoint/images/svg/check-no) ロール アウト | ![いいえ](/security/defender-endpoint/images/svg/check-no) ロール アウト | ![いいえ](/security/defender-endpoint/images/svg/check-no) ロール アウト
評価ラボ | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)
管理と API: デバイスの正常性とコンプライアンス レポート | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)
管理と API: サードパーティ製品との統合 | ![いいえ](/security/defender-endpoint/images/svg/check-no) 開発中 | ![いいえ](/security/defender-endpoint/images/svg/check-no) 開発中 | ![いいえ](/security/defender-endpoint/images/svg/check-no) 開発中
管理と API: ストリーミング API | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![いいえ](/security/defender-endpoint/images/svg/check-no) 開発中 | ![いいえ](/security/defender-endpoint/images/svg/check-no) 開発中
管理と API: 脅威保護レポート | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)
脅威&の管理 | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)
脅威の分析 | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)
Web コンテンツ のフィルター処理 | ![いいえ](/security/defender-endpoint/images/svg/check-no) 開発中 | ![いいえ](/security/defender-endpoint/images/svg/check-no) 開発中 | ![いいえ](/security/defender-endpoint/images/svg/check-no) 開発中
統合: Azure Sentinel | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![いいえ](/security/defender-endpoint/images/svg/check-no) 開発中 | ![いいえ](/security/defender-endpoint/images/svg/check-no) 開発中
統合: Microsoft Cloud App Security | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて
統合: Microsoft コンプライアンス マネージャー | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて
統合: Microsoft Defender for Identity | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて
統合: Microsoft Defender for Office 365 | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて
統合: Microsoft Endpoint DLP | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて
統合: Microsoft Intune | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![いいえ](/security/defender-endpoint/images/svg/check-no) 開発中 | ![いいえ](/security/defender-endpoint/images/svg/check-no) 開発中
統合: Microsoft Power Automate & Azure Logic Apps | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![いいえ](/security/defender-endpoint/images/svg/check-no) 開発中 | ![いいえ](/security/defender-endpoint/images/svg/check-no) 開発中
統合: Skype for Business / Teams | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes) | ![はい](/security/defender-endpoint/images/svg/check-yes)
Microsoft 脅威エキスパート | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて | ![いいえ](/security/defender-endpoint/images/svg/check-no) エンジニアリング バックログについて
