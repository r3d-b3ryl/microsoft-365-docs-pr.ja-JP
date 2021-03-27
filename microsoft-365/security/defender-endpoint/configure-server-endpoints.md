---
title: Windows サーバーを Microsoft Defender for Endpoint サービスにオンボードする
description: センサー データを Microsoft Defender for Endpoint センサーに送信できるよう、Windows サーバーをオンボードします。
keywords: オンボード サーバー、サーバー、2012r2、2016、2019、サーバーオンボーディング、デバイス管理、Windows ATP サーバーの構成、Microsoft Defender for Endpoint サーバーのオンボード、Microsoft Defender for Endpoint サーバーのオンボード
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5013d94277eeba7d1df100d2850cb950fe2e0742
ms.sourcegitcommit: a965c498e6b3890877f895d5197898b306092813
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51379351"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a>Windows サーバーを Microsoft Defender for Endpoint サービスにオンボードする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- Windows Server 2008 R2 SP1
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server (SAC) バージョン 1803 以降
- Windows Server 2019 以降
- Windows Server 2019 Core Edition

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)


Defender for Endpoint は、Windows Server オペレーティング システムも含むサポートを拡張します。 このサポートは、Microsoft Defender セキュリティ センター コンソールを通じて、高度な攻撃検出および調査機能をシームレスに提供します。

ライセンスとインフラストラクチャに必要な機能に関する実践的なガイダンスについては、「Defender for Endpoint を使用して Windows サーバーを保護する [」を参照してください](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128)。

Windows サーバーの Windows セキュリティ ベースラインをダウンロードして使用する方法のガイダンスについては [、「Windows セキュリティ ベースライン」を参照してください](https://docs.microsoft.com/windows/device-security/windows-security-baselines)。

<br>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a>Windows Server 2008 R2 SP1、Windows Server 2012 R2、および Windows Server 2016

次のオプションWindows Server 2008 R2使用して、SP1、Windows Server 2012 R2、Windows Server 2016 を Defender for Endpoint にオンボードできます。

- **オプション 1**: [Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)のインストールと構成によるオンボード
- **オプション 2**: [Azure セキュリティ センター経由でオンボードする](#option-2-onboard-windows-servers-through-azure-security-center)
- **オプション 3**: [Microsoft Endpoint Manager バージョン 2002](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)以降のオンボード


指定されたオプションを使用してオンボーディング手順を完了した後、System Center Endpoint Protection クライアントを構成および [更新する必要があります](#configure-and-update-system-center-endpoint-protection-clients)。


> [!NOTE]
> Microsoft Monitoring Agent (オプション 1) または Microsoft Endpoint Manager (オプション 3) を介して Windows サーバーをオンボードするには、ノードごとに Defender for Endpoint スタンドアロン サーバー ライセンスが必要です。 または、Azure セキュリティ センター (オプション 2) を介して Windows サーバーをオンボードするには、ノードごとに Azure Defender for Servers ライセンスが必要です [。「Azure](https://docs.microsoft.com/azure/security-center/security-center-services)Security Center で利用可能なサポートされる機能」を参照してください。


### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a>オプション 1: Microsoft 監視エージェント (MMA) のインストールと構成によるオンボード
センサー データを Defender for Endpoint に報告するには、Windows サーバー用の MMA をインストールして構成する必要があります。 詳細については [、「Azure Log Analytics エージェントを使用してログ データを収集する」を参照してください](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)。

System Center Operations Manager (SCOM) または Azure Monitor (以前は Operations Management Suite (OMS) と呼ばれる) を既に使用している場合は、Microsoft Monitoring Agent (MMA) を接続して、マルチホミング サポートを通じて Defender for Endpoint ワークスペースに報告します。

一般に、次の手順を実行する必要があります。
1. 「始める前に」で説明されているオンボーディング要件 **を満た** します。
2. Microsoft Defender セキュリティ センターからサーバーの監視を有効にします。
3. センサー データを Defender for Endpoint に報告するサーバーの MMA をインストールして構成します。
4. System Center Endpoint Protection クライアントを構成および更新します。


> [!TIP]
> デバイスのオンボード後、検出テストを実行して、サービスに適切にオンボードされていることを確認できます。 詳細については、「新しくオンボードされた Defender for Endpoint エンドポイントで検出テストを実行 [する」を参照してください](run-detection-test.md)。


#### <a name="before-you-begin"></a>はじめに 
オンボーディング要件を満たすために、次の手順を実行します。

 - SP1 Windows Server 2008 R2 R2 Windows Server 2012、次の修正プログラムをインストールしてください。
    - [カスタマー エクスペリエンスと診断テレメトリの更新](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

 - さらに、SP1 のWindows Server 2008 R2、次の要件を満たしていることを確認します。
    - 2 [月の月次更新プログラムのロールアップをインストールする](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
    - [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (以降) または[KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)のいずれかをインストールする
   
   > [!NOTE]
    > SCCM を使用して SP1 Windows Server 2008 R2管理している場合、SCCM クライアント エージェントは .Net Framework 4.5.2 をインストールします。 そのため、.NET framework 4.5 (以降) をインストールする必要はないので、
   
 - SP1 Windows Server 2008 R2 R2 のWindows Server 2012: System Center Endpoint Protection クライアント [を構成および更新します](#configure-and-update-system-center-endpoint-protection-clients)。

    > [!NOTE]
    > この手順は、組織で System Center Endpoint Protection (SCEP) を使用し、SP1 および R2 のオンボーディングWindows Server 2008 R2必要Windows Server 2012です。


<span id="server-mma"/>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>センサー データを Microsoft Defender for Endpoint に報告する Microsoft Monitoring Agent (MMA) をインストールして構成する

1. エージェント セットアップ ファイル [(Windows 64 ビット](https://go.microsoft.com/fwlink/?LinkId=828603)エージェント) をダウンロードします。

2. 前の手順で取得した Workspace ID と Workspace キーを使用して、Windows サーバーにエージェントをインストールするには、次のインストール方法を選択します。
    - [セットアップを使用してエージェントを手動でインストールします](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)。 <br>
    [エージェントの **セットアップ オプション] ページ** で、[ **エージェントを Azure Log Analytics (OMS)** に接続する] を選択します。
    - [コマンド ラインを使用してエージェントをインストールします](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)。
    - [スクリプトを使用してエージェントを構成します](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)。

> [!NOTE]
> 米国政府機関のお客様[](gov.md)の場合は、[Azure Cloud] の下で、セットアップ ウィザードを使用する場合は "Azure US Government" を選択するか、コマンド ラインまたはスクリプトを使用する場合は、"OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" パラメーターを 1 に設定する必要があります。


<span id="server-proxy"/>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a>必要に応じて Windows サーバー プロキシとインターネット接続の設定を構成する
サーバーが Defender for Endpoint と通信するためにプロキシを使用する必要がある場合は、次のいずれかの方法を使用して、プロキシ サーバーを使用する MMA を構成します。


- [プロキシ サーバーを使用する MMA を構成する](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [すべての接続にプロキシ サーバーを使用する Windows を構成する](configure-proxy-internet.md)

プロキシまたはファイアウォールが使用されている場合は、サーバーが SSL インターセプトなしで直接 Microsoft Defender for Endpoint サービス URL にアクセスできます。 詳細については、「Defender for Endpoint Service URL へのアクセス [を有効にする」を参照してください](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。 SSL インターセプトを使用すると、システムは Defender for Endpoint サービスと通信できません。 

完了すると、1 時間以内にポータルにオンボード Windows サーバーが表示されます。

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a>オプション 2: Azure セキュリティ センターを介して Windows サーバーをオンボードする
1. Microsoft Defender Security Center ナビゲーションウィンドウで、[設定] [  >  **デバイス管理オン** ボーディング]  >  **を選択します**。

2. オペレーティング **Windows Server 2008 R2 SP1、2012 R2、2016 を** 選択します。

3. **[Azure セキュリティ センターのオンボード サーバー] をクリックします**。

4. Microsoft Defender for Endpoint with [Azure Security Center のオンボーディング手順に従います](https://docs.microsoft.com/azure/security-center/security-center-wdatp)。

オンボーディングの手順を完了した後、System Center [Endpoint Protection クライアントを構成および更新する必要があります](#configure-and-update-system-center-endpoint-protection-clients)。

> [!NOTE]
> - Azure Defender for Servers (以前の Azure Security Center Standard Edition) によるオンボーディングが期待通り動作するには、サーバーが Microsoft Monitoring Agent (MMA) 設定内で適切なワークスペースとキーを構成している必要があります。
> - 構成が完了すると、適切なクラウド管理パックがコンピューターに展開され、センサー プロセス (MsSenseS.exe) が展開され、開始されます。 
> - これは、サーバーが OMS ゲートウェイ サーバーをプロキシとして使用するように構成されている場合にも必要です。

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a>オプション 3: Microsoft Endpoint Manager バージョン 2002 以降の Windows サーバーをオンボードする
Microsoft Endpoint Manager Windows Server 2012 2002 以降を使用して、R2 および Windows Server 2016 をオンボードできます。 詳細については [、「Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch」を参照してください](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)。

オンボーディングの手順を完了した後、System Center [Endpoint Protection クライアントを構成および更新する必要があります](#configure-and-update-system-center-endpoint-protection-clients)。

<br>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a>Windows Server (SAC) バージョン 1803、Windows Server 2019、および Windows Server 2019 Core Edition
次の展開方法を使用して、Windows Server (SAC) バージョン 1803、Windows Server 2019、または Windows Server 2019 Core Edition をオンボードできます。

- [ローカル スクリプト](configure-endpoints-script.md) 
- [グループ ポリシー](configure-endpoints-gp.md)
- [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [System Center Configuration Manager 2012 / 2012 R2 1511 / 1602](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [永続的でないデバイスの VDI オンボーディング スクリプト](configure-endpoints-vdi.md)

> [!NOTE]
> - Microsoft Endpoint Manager を介した Windows Server 2019 のオンボーディング パッケージには、現在スクリプトが含まれています。 Configuration Manager でスクリプトを展開する方法の詳細については、「Configuration Manager の [パッケージとプログラム」を参照してください](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)。
> - ローカル スクリプトは概念実証に適していますが、実稼働展開には使用できません。 実稼働展開の場合は、グループ ポリシーまたは Microsoft Endpoint Configuration Manager を使用することをお勧めします。

Windows Server のサポートは、サーバーアクティビティ、カーネル攻撃とメモリ攻撃検出の範囲に関するより深い洞察を提供し、応答アクションを有効にします。

1. Windows 10 デバイス用の同じツールとメソッドを使用して、Windows サーバーの Defender for Endpoint オンボーディング設定を構成します。 詳細については、「オンボード [Windows 10 デバイス」を参照してください](configure-endpoints.md)。

2. サードパーティのマルウェア対策ソリューションを実行している場合は、次の Microsoft Defender AV パッシブ モード設定を適用する必要があります。 正しく構成されていることを確認します。

    1. 次のレジストリ エントリを設定します。
       - パス: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
       - 名前: ForceDefenderPassiveMode
       - 種類: REG_DWORD
       - Value: 1

    1. 次の PowerShell コマンドを実行して、パッシブ モードが構成されていることを確認します。

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. パッシブ モード イベントを含む最近のイベントが見つかったこと確認します。

       ![パッシブ モード検証結果のイメージ](images/atp-verify-passive-mode.png)

3. 次のコマンドを実行して、Microsoft Defender AV がインストールされていることを確認します。

   ```sc.exe query Windefend```

    結果が '指定されたサービスがインストールされたサービスとして存在しない' の場合は、Microsoft Defender AV をインストールする必要があります。 詳細については [、「Microsoft Defender Antivirus in Windows 10」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)。
    
    Windows サーバーでグループ ポリシーを使用して Microsoft Defender ウイルス対策を構成および管理する方法については、「グループ ポリシー設定を使用して Microsoft Defender ウイルス対策を構成および管理する」 [を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)。

<br>

## <a name="integration-with-azure-security-center"></a>Azure セキュリティ センターとの統合
Defender for Endpoint は、Azure Security Center と統合して、包括的な Windows サーバー保護ソリューションを提供できます。 この統合により、Azure Security Center は Defender for Endpoint の機能を使用して、Windows サーバーの脅威検出を強化できます。

この統合には、次の機能が含まれています。
- 自動オンボーディング - Defender for Endpoint センサーは、Azure セキュリティ センターにオンボードされている Windows サーバーで自動的に有効になります。 Azure Security Center オンボーディングの詳細については、「強化されたセキュリティのための Azure Security Center Standard へのオンボーディング」 [を参照してください](https://docs.microsoft.com/azure/security-center/security-center-onboarding)。

    > [!NOTE]
    > 自動オンボーディングは、SP1、Windows Server 2008 R2 R2、Windows Server 2012 Windows Server 2016 にのみ適用されます。

- Azure Security Center によって監視される Windows サーバーは、Defender for Endpoint - Azure Security Center で Defender for Endpoint テナントにシームレスに接続し、クライアントとサーバー全体で 1 つのビューを提供します。  さらに、Defender for Endpoint アラートは Azure Security Center コンソールで利用できます。
- サーバー調査 - Azure Security Center のお客様は、Microsoft Defender Security Center にアクセスして詳細な調査を実行して、潜在的な侵害の範囲を明らかにできます。

> [!IMPORTANT]
> - Azure Security Center を使用してサーバーを監視すると、Defender for Endpoint テナントが自動的に作成されます (米国のユーザーは米国、EU ではヨーロッパおよび英国のユーザー)。<br>
Defender for Endpoint によって収集されたデータは、プロビジョニング中に特定されたテナントの地理的位置に格納されます。
> - Azure Security Center を使用する前に Defender for Endpoint を使用する場合、後で Azure Security Center と統合した場合でも、テナントの作成時に指定した場所にデータが格納されます。
> - 構成が完了すると、データの保存場所を変更できません。 データを別の場所に移動する必要がある場合は、Microsoft サポートに問い合わせ、テナントをリセットする必要があります。 <br>
この統合を利用したサーバー エンドポイントの監視は、365 GCC のお客様Office無効になっています。

<br>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>System Center Endpoint Protection クライアントの構成と更新

Defender for Endpoint は、System Center Endpoint Protection と統合されます。 この統合により、マルウェアの検出を可視化し、悪意のある可能性のあるファイルや疑わしいマルウェアを禁止することで、組織内の攻撃の伝達を停止できます。

この統合を有効にするには、次の手順が必要です。
- Endpoint [Protection クライアント用の 2017 年 1 月のマルウェア対策プラットフォーム更新プログラムをインストールします](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)。

- [SCEP クライアント Cloud Protection Service メンバーシップを Advanced](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 設定に **構成** します。

<br>

## <a name="offboard-windows-servers"></a>オフボード Windows サーバー
Windows Server (SAC)、Windows Server 2019、および Windows Server 2019 Core Edition は、Windows 10 クライアント デバイスで使用できるのと同じ方法で実行できます。

その他の Windows サーバー バージョンでは、サービスから Windows サーバーをオフボードする 2 つのオプションがあります。
- MMA エージェントのアンインストール
- Defender for Endpoint ワークスペース構成を削除する

> [!NOTE]
> オフボードにより、Windows サーバーはポータルへのセンサー データの送信を停止しますが、Windows サーバーからのデータ (それが持っていたアラートへの参照を含む) は最大 6 か月間保持されます。

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a>MMA エージェントをアンインストールして Windows サーバーをアンインストールする
Windows サーバーをオフボードするには、WINDOWS サーバーから MMA エージェントをアンインストールするか、レポートから Defender for Endpoint ワークスペースに切り離します。 エージェントのオフボード後、Windows サーバーは Defender for Endpoint にセンサー データを送信しなくなりました。
詳細については、「エージェントを無効 [にするには」を参照してください](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)。

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a>Defender for Endpoint ワークスペース構成を削除する
Windows サーバーをオフボードするには、次のいずれかの方法を使用できます。

- DEFENDER for Endpoint ワークスペース構成を MMA エージェントから削除する
- PowerShell コマンドを実行して構成を削除する

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a>DEFENDER for Endpoint ワークスペース構成を MMA エージェントから削除する

1. **[Microsoft 監視エージェントのプロパティ] で****、[Azure Log Analytics (OMS) ] タブを選択** します。

2. [Defender for Endpoint] ワークスペースを選択し、[削除] を **クリックします**。

    ![Microsoft Monitoring Agent のプロパティのイメージ](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a>PowerShell コマンドを実行して構成を削除する

1. ワークスペース ID を取得します。

   1. ナビゲーション ウィンドウで、[設定オンボーディング]  >  **を選択します**。

   1. オペレーティング **Windows Server 2008 R2 SP1、2012 R2、2016** を選択し、ワークスペース ID を取得します。

      ![Windows サーバーオンボーディングのイメージ](images/atp-server-offboarding-workspaceid.png)

2. 管理者特権の PowerShell を開き、次のコマンドを実行します。 取得して置き換えたワークスペース ID を使用します `WorkspaceID` 。

    ```powershell
    $ErrorActionPreference = "SilentlyContinue"
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace("WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

<br>

## <a name="related-topics"></a>関連項目
- [オンボード Windows 10 デバイス](configure-endpoints.md)
- [Windows 以外のデバイスをオンボードする](configure-endpoints-non-windows.md)
- [プロキシとインターネット接続の設定を構成する](configure-proxy-internet.md)
- [新しくオンボードされた Defender for Endpoint デバイスで検出テストを実行する](run-detection-test.md)
- [Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング](troubleshoot-onboarding.md)
