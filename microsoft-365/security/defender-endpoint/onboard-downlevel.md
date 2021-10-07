---
title: Microsoft Defender for Endpoint の以前Windowsバージョンのオンボード
description: センサー データを Microsoft Defender for Endpoint センサーに送信Windows以前のバージョンのデバイスをオンボードでサポート
keywords: オンボード、Windows、7、81、oms、sp1、enterprise、pro、down level
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: dcfbef4e728a3b29a2d23f55d5bd96aeffd19b00
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60206831"
---
# <a name="onboard-previous-versions-of-windows"></a>以前のバージョンの Windows をオンボードする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**プラットフォーム**
- Windows 7 SP1 Enterprise
- Windows 7 SP1 Pro
- Windows 8.1 Pro
- Windows 8.1 Enterprise

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-downlevel-abovefoldlink)

Defender for Endpoint は、ダウンレベルのオペレーティング システムを含むサポートを拡張し、サポートされているバージョンの高度な攻撃検出と調査Windowsします。

クライアント エンドポイントのダウンレベル Windows Defender for Endpoint にオンボードするには、次の必要があります。

- クライアントの構成と更新System Center Endpoint Protectionします。
- 以下に示すMicrosoft Monitoring Agent、センサー データを Defender for Endpoint に報告するように、センサー データ (MMA) をインストールして構成します。

> [!TIP]
> デバイスのオンボード後、検出テストを実行して、サービスに適切にオンボードされていることを確認できます。 詳細については、「新しくオンボードされた Defender for Endpoint エンドポイントで検出テストを実行 [する」を参照してください](run-detection-test.md)。

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>クライアントの構成と更新System Center Endpoint Protectionする

> [!IMPORTANT]
> この手順は、組織が SCEP (SCEP) System Center Endpoint Protection必要です。

Defender for Endpoint は System Center Endpoint Protection と統合し、マルウェアの検出を可視化し、悪意のある可能性のあるファイルや疑わしいマルウェアを禁止することで、組織内の攻撃の伝達を停止します。

この統合を有効にするには、次の手順が必要です。

- [2017 年 1](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)月のマルウェア対策プラットフォーム更新プログラムをクライアントEndpoint Protectionする
- SCEP クライアント Cloud Protection Service メンバーシップを詳細設定に **構成** する
- クラウドへの接続を許可するネットワークMicrosoft Defender ウイルス対策します。 詳細については、「Allow [connections to the Microsoft Defender ウイルス対策 クラウド」を参照してください。](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>センサー データを Microsoft Defender for Endpoint にMicrosoft Monitoring Agentレポートするデバイス (MMA) をインストールして構成する

### <a name="before-you-begin"></a>はじめに

最小システム要件を確認するには、次の詳細を確認します。

- [2018 年 2 月の更新プログラムのロールアップをインストールする](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)

  > [!NOTE]
  > 7 SP1 および 7 SP1 Windows 7 SP1 EnterpriseおよびWindowsにのみPro。

- カスタマー エクスペリエンス [と診断テレメトリの更新プログラムをインストールする](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

- [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (以降) または[KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)のいずれかをインストールする

    > [!NOTE]
    > 7 SP1 および 7 SP1 Windows 7 SP1 EnterpriseおよびWindowsにのみPro。
    > 上記のインストールを.NET Framework 4.0.x にはインストールしない。

- Azure Log Analytics エージェントの最小システム要件を満たします。 詳細については [、「Log Analytics を使用して環境内のコンピューターからデータを収集する」を参照してください](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)。

1. エージェント セットアップ ファイルをダウンロードします[Windows 64 ビット](https://go.microsoft.com/fwlink/?LinkId=828603)エージェントまたは[32 ビット Windowsエージェントをダウンロードします](https://go.microsoft.com/fwlink/?LinkId=828604)。

2. ワークスペース ID を取得します。
   - [Defender for Endpoint] ナビゲーション ウィンドウで、[デバイス設定 >**の>オンボーディング>選択します。**
   - オペレーティング **Windows 7 SP1 と 8.1** を選択する
   - ワークスペース ID とワークスペース キーをコピーする

3. Workspace ID と Workspace キーを使用して、次のインストール方法を選択してエージェントをインストールします。
    - [セットアップを使用してエージェントを手動でインストールします](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)。

      [エージェント **のセットアップ オプション]** ページで、[エージェント **Connect Azure Log Analytics (OMS) に移動する] を選択します。**

    - [コマンド ラインを使用してエージェントをインストールします](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)。
    - [スクリプトを使用してエージェントを構成します](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)。

   > [!NOTE]
   > 米国政府機関のお客様[](gov.md)の場合は、[Azure Cloud] の下で、セットアップ ウィザードを使用する場合は "Azure US Government" を選択するか、コマンド ラインまたはスクリプトを使用する場合は、"OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" パラメーターを 1 に設定する必要があります。

4. プロキシを使用してインターネットに接続する場合は、「プロキシ設定の構成」セクションを参照してください。

完了すると、1 時間以内にポータルにオンボード エンドポイントが表示されます。

### <a name="configure-proxy-and-internet-connectivity-settings"></a>プロキシとインターネット接続の設定を構成する

- 各Windows HTTPS を使用してインターネットに接続できる必要があります。 この接続は、直接、プロキシを使用するか [、OMS ゲートウェイを介して行います](/azure/log-analytics/log-analytics-oms-gateway)。
- プロキシまたはファイアウォールが既定ですべてのトラフィックをブロックしており、特定のドメインのみを許可している場合や HTTPS スキャン (SSL 検査) が有効になっている場合は [、Defender for Endpoint](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)Service URL へのアクセスを有効にしてください。

## <a name="run-a-detection-test-to-verify-onboarding"></a>検出テストを実行してオンボーディングを確認する

デバイスのオンボード後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認できます。 詳細については、「新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する [」を参照してください](run-detection-test.md)。

## <a name="offboard-client-endpoints"></a>オフボード クライアント エンドポイント

オフボードには、エンドポイントから MMA エージェントをアンインストールするか、レポートから Defender for Endpoint ワークスペースに切り離します。 エージェントのオフボード後、エンドポイントはセンサー データを Defender for Endpoint に送信しなくなりました。

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-downlevele-belowfoldlink)
