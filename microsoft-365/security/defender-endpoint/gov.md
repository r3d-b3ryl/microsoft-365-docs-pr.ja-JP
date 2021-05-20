---
title: 米国政府のお客様向けの Microsoft Defender for Endpoint
description: 米国政府の顧客の要件と利用可能な機能のエンドポイントのマイクロソフト ディフェンダーについて学びます
keywords: 政府, gcc, 高, 要件, 能力, ディフェンダー, エンドポイント用のマイクロソフトディフェンダー, エンドポイント, dod
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
ms.openlocfilehash: 0276f0464f898d3675e4cc1d6b69185e7e390a87
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572671"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>米国政府のお客様向けの Microsoft Defender for Endpoint

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Azure の米国政府環境で構築された米国政府の顧客のエンドポイントのマイクロソフト Defender は、Azure コマーシャルのエンドポイントの Defender と同じ基盤テクノロジを使用します。

この製品は、GCC、GCC高、および DoD のお客様が利用でき、商用バージョンと同じ予防、検出、調査、および修復に基づいています。 ただし、このオファリングの機能の可用性にはいくつかの違いがあります。

> [!NOTE]
> 商用でエンドポイント用の Defender を使用しているGCCの顧客の場合は、公開ドキュメントページを参照してください。

## <a name="licensing-requirements"></a>ライセンスの要件
米国政府のお客様のエンドポイントのマイクロソフトディフェンダーには、次のマイクロソフトボリューム ライセンスの提供のいずれかを必要があります。

### <a name="desktop-licensing"></a>デスクトップ ライセンス
GCC | GCC High | DoD
:---|:---|:---
Windows 10 EnterpriseE5 GCC | Windows 10 EnterpriseE5 GCCハイ | Windows 10 EnterpriseDoD 用 E5
| | GCC高のMicrosoft 365 E5 | Microsoft 365DoD 用 G5
| | Microsoft 365G5 高GCCセキュリティ | Microsoft 365DoD のための G5 セキュリティ
エンドポイントのマイクロソフトディフェンダー - GCC | GCC高のエンドポイントのマイクロソフトディフェンダー | DOD のエンドポイント用のマイクロソフト ディフェンダー

### <a name="server-licensing"></a>サーバー ライセンス
GCC | GCC High | DoD
:---|:---|:---
エンドポイント サーバー GCC用のマイクロソフト ディフェンダー | エンドポイント サーバーのマイクロソフト ディフェンダー (GCC 高) | DOD のエンドポイント サーバーのマイクロソフト ディフェンダー
サーバー用 Azure Defender | サーバー用の Azure Defender - 政府 | サーバー用の Azure Defender - 政府

<br />

## <a name="portal-urls"></a>ポータル URL
次に、米国政府のお客様のエンドポイント ポータル URL 用の Microsoft Defender を示します。

お客様の種類 | ポータル URL
:---|:---
GCC | https://gcc.securitycenter.microsoft.us
GCC High | https://securitycenter.microsoft.us
DoD | https://securitycenter.microsoft.us

<br />

## <a name="endpoint-versions"></a>エンドポイントのバージョン

### <a name="standalone-os-versions"></a>スタンドアロン OS のバージョン
次の OS バージョンがサポートされています。

OS バージョン | GCC | GCC High | DoD
:---|:---|:---|:---
Windows 10、バージョン 20H2 [(KB4586853)](https://support.microsoft.com/help/4586853) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg)
Windows 10、バージョン 2004 [(KB4586853)](https://support.microsoft.com/help/4586853) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg)
Windows 10、バージョン 1909 [(KB4586819)](https://support.microsoft.com/help/4586819) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg)
Windows 10、バージョン 1903 [(KB4586819)](https://support.microsoft.com/help/4586819) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg)
Windows 10、バージョン 1809 [(KB4586839)](https://support.microsoft.com/help/4586839) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg)
Windows 10、バージョン 1803 [(KB4598245)](https://support.microsoft.com/help/4598245) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg)
Windows 10、バージョン 1709 | ![いいえ](images/svg/check-no.svg)<br />注: サポートされません。 | ![](images/svg/check-yes.svg) [KB4499147](https://support.microsoft.com/help/4499147)ではい<br />注意: [非推奨](/lifecycle/announcements/revised-end-of-service-windows-10-1709)の をアップグレードしてください。 | ![いいえ](images/svg/check-no.svg)<br />注: サポートされません。
Windows 10、バージョン 1703 以前 | ![いいえ](images/svg/check-no.svg)<br />注: サポートされません。 | ![いいえ](images/svg/check-no.svg)<br />注: サポートされません。 | ![いいえ](images/svg/check-no.svg)<br />注: サポートされません。
Windowsサーバー 2019 [(KB4586839)](https://support.microsoft.com/help/4586839) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg)
Windows Server 2016 | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg)
Windows 8.1 Enterprise | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg)
Windows 8 Pro | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg)
Windows 7 SP1 Enterprise | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg)
Windows 7 SP1 Pro | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg)
Linux | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg)
macOS | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg)
Android | ![いいえ](images/svg/check-no.svg) エンジニアリングバックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリングバックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリングバックログについて
iOS | ![いいえ](images/svg/check-no.svg) エンジニアリングバックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリングバックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリングバックログについて

> [!NOTE]
> パッチを指定する場合は、正しい環境に Endpoint の Defender を設定するために、デバイスオンボーディングの前に展開する必要があります。

> [!NOTE]
> [Microsoft Monitoring Agent](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)を使用して、Windows 10 または server 2019 Windowsより古いWindowsデバイスをオンボードしようとしています。 [セットアップ ウィザード](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)を使用する場合は、[Azure Cloud] の下にある [Azure US 政府][](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)を選択する必要[](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPEがあります。

### <a name="os-versions-when-using-azure-defender-for-servers"></a>サーバー用の Azure Defender を使用する場合の OS バージョン
[サーバー用 Azure Defender](/azure/security-center/security-center-wdatp)を使用する場合は、次の OS バージョンがサポートされます。

OS バージョン | GCC | GCC High | DoD
:---|:---|:---|:---
Windows Server 2019 | ![いいえ](images/svg/check-no.svg) 開発中 | ![いいえ](images/svg/check-no.svg) 開発中 | ![いいえ](images/svg/check-no.svg) 開発中
Windows Server 2016 | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg)

<br />

## <a name="required-connectivity-settings"></a>必要な接続設定
プロキシまたはファイアウォールが既定ですべてのトラフィックをブロックし、特定のドメインの通過だけを許可している場合は、ダウンロード可能シートに記載されているドメインを許可ドメインのリストに追加します。

次のダウンロード可能なスプレッドシートには、ネットワークが接続できる必要があるサービスと関連付けられた URL が一覧表示されます。 これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルタリングルールがないことを確認するか、 *許可ルールを* 作成します。

ドメインのスプレッドシート一覧 | 説明
:-----|:-----
![エンドポイント URL スプレッドシート用の Microsoft Defender 用のサム イメージ](images/mdatp-urls.png)<br/> | サービスの場所、地理的な場所、および OS に関する特定の DNS レコードのスプレッドシート。 <br /><br />[スプレッドシートはこちらからダウンロードできます。](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

詳細については、「デバイス [プロキシとインターネット接続の設定を構成する](configure-proxy-internet.md)」を参照してください。

> [!NOTE]
> スプレッドシートには商用 URL も含まれていますが、必ず "米国政府" タブを確認してください。
> 
> フィルター処理の場合は、"US Gov" と表示されたレコードと、地理列の下の特定のクラウドを探します。

### <a name="service-backend-ip-ranges"></a>サービス バックエンド IP 範囲

ネットワーク デバイスが DNS ベースのルールをサポートしていない場合は、代わりに IP 範囲を使用します。

米国政府のお客様のエンドポイントの Defender は、Azure の米国政府環境に構築され、次のリージョンにデプロイされています。

- アズクラウド.usgovテキサス州
- アズクラウド.usgovバージニア州

Azure の IP 範囲は、 [Azure の IP 範囲とサービス タグ – 米国政府機関クラウド で](https://www.microsoft.com/download/details.aspx?id=57063)検索できます。

> [!NOTE]
> クラウドベースのソリューションとして、IP アドレスの範囲が変更される可能性があります。 DNS ベースのルールに移行することをお勧めします。

<br />

## <a name="api"></a>API
[API ドキュメント](apis-intro.md)に記載されているパブリック URI の代わりに、次の URI を使用する必要があります。

エンドポイントの種類 | GCC | GCCハイ&ドッド
:---|:---|:---
ログイン | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
エンドポイント API の擁護者 | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
SIEM | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br />

## <a name="feature-parity-with-commercial"></a>コマーシャルとの機能パリティ
米国政府のお客様向けのエンドポイントの擁護者は、商用製品と完全に同等ではありません。 私たちの目標は、米国政府のお客様にすべての商用機能を提供することですが、まだ利用できない機能がいくつかあります。

既知のギャップは次のとおりです。

フィーチャー名 | GCC | GCC High | DoD
:---|:---|:---|:---
管理と API: ストリーミング API | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg)
Web コンテンツ フィルタリング | ![いいえ](images/svg/check-no.svg) 開発中 | ![いいえ](images/svg/check-no.svg) 開発中 | ![いいえ](images/svg/check-no.svg) 開発中
統合: Azure センチネル | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) アラート <br /> ![いいえ](images/svg/check-no.svg) インシデント&生データ: 開発中 | ![はい](images/svg/check-yes.svg) アラート <br /> ![いいえ](images/svg/check-no.svg) インシデント&生データ: 開発中
統合: Microsoft Cloud App Security | ![いいえ](images/svg/check-no.svg) 開発中 | ![いいえ](images/svg/check-no.svg) 開発中 | ![いいえ](images/svg/check-no.svg) 開発中
統合: マイクロソフト コンプライアンス マネージャー | ![いいえ](images/svg/check-no.svg) 開発中 | ![いいえ](images/svg/check-no.svg) 開発中 | ![いいえ](images/svg/check-no.svg) 開発中
統合: マイクロソフトの ID の擁護者 | ![いいえ](images/svg/check-no.svg) 開発中 | ![いいえ](images/svg/check-no.svg) 開発中 | ![いいえ](images/svg/check-no.svg) 開発中
統合: マイクロソフト エンドポイント DLP | ![いいえ](images/svg/check-no.svg) 開発中 | ![いいえ](images/svg/check-no.svg) 開発中 | ![いいえ](images/svg/check-no.svg) 開発中
統合: Microsoft Intune | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg) | ![はい](images/svg/check-yes.svg)
統合: マイクロソフト Power Automate & Azure Logic Apps | ![はい](images/svg/check-yes.svg) | ![いいえ](images/svg/check-no.svg) 開発中 | ![いいえ](images/svg/check-no.svg) 開発中
Microsoft 脅威エキスパート | ![いいえ](images/svg/check-no.svg) エンジニアリングバックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリングバックログについて | ![いいえ](images/svg/check-no.svg) エンジニアリングバックログについて
