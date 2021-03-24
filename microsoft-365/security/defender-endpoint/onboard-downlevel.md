---
title: Microsoft Defender ATP で以前のバージョンの Windows をオンボードする
description: センサー データを Microsoft Defender ATP センサーに送信できるよう、オンボードでサポートされている以前のバージョンの Windows デバイス
keywords: オンボード、Windows、7、81、oms、sp1、enterprise、pro、down level
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a70826ee6e245f6744d8fc64eaf06e8cd1bdb265
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061122"
---
# <a name="onboard-previous-versions-of-windows"></a>以前のバージョンの Windows のオンボード

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**プラットフォーム**
- Windows 7 SP1エンタープライズ
- Windows 7 SP1 Pro
- Windows 8.1 Pro
- Windows 8.1 Enterprise


>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink)。

Defender for Endpoint では、サポートを拡張して、ダウンレベルのオペレーティング システムを含め、サポートされている Windows バージョンで高度な攻撃検出と調査機能を提供します。

ダウンレベルの Windows クライアント エンドポイントを Defender for Endpoint にオンボードするには、次の必要があります。
- System Center Endpoint Protection クライアントを構成および更新します。
- 以下の指示に従って、センサー データを Defender for Endpoint に報告するように Microsoft Monitoring Agent (MMA) をインストールして構成します。

> [!TIP]
> デバイスのオンボード後、検出テストを実行して、サービスに適切にオンボードされていることを確認できます。 詳細については、「新しくオンボードされた Defender for Endpoint エンドポイントで検出テストを実行 [する」を参照してください](run-detection-test.md)。

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>System Center Endpoint Protection クライアントの構成と更新
> [!IMPORTANT]
> この手順は、組織で System Center Endpoint Protection (SCEP) を使用している場合にのみ必要です。

Defender for Endpoint は System Center Endpoint Protection と統合され、マルウェア検出を可視化し、悪意のある可能性のあるファイルや疑わしいマルウェアを禁止することで、組織内の攻撃の伝達を停止します。 

この統合を有効にするには、次の手順が必要です。 
- エンドポイント保護 [クライアント用の 2017 年 1 月のマルウェア対策プラットフォーム更新プログラムをインストールする](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie) 
- SCEP クライアント Cloud Protection Service メンバーシップを詳細設定に **構成** する
- Microsoft Defender ウイルス対策クラウドへの接続を許可するネットワークを構成します。 詳細については [、「Microsoft Defender ウイルス対策クラウドへの接続を許可する」を参照してください。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>センサー データを Microsoft Defender for Endpoint に報告する Microsoft Monitoring Agent (MMA) をインストールして構成する

### <a name="before-you-begin"></a>はじめに
最小システム要件を確認するには、次の詳細を確認します。
- [2018 年 2 月の更新プログラムのロールアップをインストールする](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
  
  > [!NOTE]
  > エンタープライズ および Windows 7 SP1 Pro にのみWindows 7 SP1適用されます。 

- カスタマー エクスペリエンス [と診断テレメトリの更新プログラムをインストールする](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

- [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (以降) または[KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)のいずれかをインストールする

    > [!NOTE]
    > エンタープライズ および Windows 7 SP1 Pro にのみWindows 7 SP1適用されます。
    > 上記のインストールを.NET Framework 4.0.x にはインストールしない。

- Azure Log Analytics エージェントの最小システム要件を満たします。 詳細については、「Log Analytics を使用して環境内のコンピューターからデータ [を収集する」を参照してください。](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)



1. エージェント セットアップ ファイルをダウンロードします [。Windows 64 ビット エージェントまたは](https://go.microsoft.com/fwlink/?LinkId=828603) [Windows 32 ビット エージェント](https://go.microsoft.com/fwlink/?LinkId=828604)。

2. ワークスペース ID を取得します。
   - [Defender for Endpoint] ナビゲーション ウィンドウで、[デバイス **管理] ウィンドウの [>オンボーディング>選択します。**
   - オペレーティング **Windows 7 SP1 8.1 を** 選択します。
   - ワークスペース ID とワークスペース キーをコピーする

3. Workspace ID と Workspace キーを使用して、次のインストール方法を選択してエージェントをインストールします。
    - [セットアップを使用してエージェントを手動でインストールします](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)。 <br>
      [エージェントの **セットアップ オプション] ページ** で、[ **エージェントを Azure Log Analytics (OMS) に接続する] を選択します。**
    - [コマンド ラインを使用してエージェントをインストールします](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)。
    - [スクリプトを使用してエージェントを構成します](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)。

   > [!NOTE]
   > 米国政府機関のお客様[](gov.md)の場合は、[Azure Cloud] の下で、セットアップ ウィザードを使用する場合は "Azure US Government" を選択するか、コマンド ラインまたはスクリプトを使用する場合は、"OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" パラメーターを 1 に設定する必要があります。

4. プロキシを使用してインターネットに接続する場合は、「プロキシ設定の構成」セクションを参照してください。

完了すると、1 時間以内にポータルにオンボード エンドポイントが表示されます。

### <a name="configure-proxy-and-internet-connectivity-settings"></a>プロキシとインターネット接続の設定を構成する
 
- 各 Windows エンドポイントは、HTTPS を使用してインターネットに接続できる必要があります。 この接続は、直接、プロキシを使用するか [、OMS ゲートウェイを介して行います](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway)。
- プロキシまたはファイアウォールが既定ですべてのトラフィックをブロックしており、特定のドメインのみを許可している場合や HTTPS スキャン (SSL 検査) が有効になっている場合は [、Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)Service URL へのアクセスを有効にしてください。

## <a name="offboard-client-endpoints"></a>オフボード クライアント エンドポイント
オフボードには、エンドポイントから MMA エージェントをアンインストールするか、レポートから Defender for Endpoint ワークスペースに切り離します。 エージェントのオフボード後、エンドポイントはセンサー データを Defender for Endpoint に送信しなくなりました。 

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink)。

