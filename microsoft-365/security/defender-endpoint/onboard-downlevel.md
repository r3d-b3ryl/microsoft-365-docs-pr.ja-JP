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
ms.openlocfilehash: f17f8fe3ccb659f04ab5acac9108d4151a5d1769
ms.sourcegitcommit: be095345257225394674698beb3feeb0696ec86d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2021
ms.locfileid: "60240526"
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
- Windows Server 2008 R2 SP1

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-downlevel-abovefoldlink)

Defender for Endpoint は、ダウンレベルのオペレーティング システムを含むサポートを拡張し、サポートされているバージョンの高度な攻撃検出と調査Windowsします。



クライアント エンドポイントのダウンレベル Windows Defender for Endpoint にオンボードするには、次の必要があります。


- [クライアントの構成と更新System Center Endpoint Protectionする](#configure-and-update-system-center-endpoint-protection-clients)
- [センサー データをMicrosoft Monitoring Agentレポートするコンピューター (MMA) のインストールと構成](#install-and-configure-microsoft-monitoring-agent-mma)


サーバー 2008 R2 SP1 Windows、Azure Defender を使用してオン[ボーディングを行うオプションがあります](#onboard-windows-servers-through-azure-defender)。


> [!NOTE]
> Defender for Endpoint スタンドアロン サーバー ライセンスは、ノードごとに必要です(オプション 1) Windowsサーバー Microsoft Monitoring Agentオンボーディングします。 または、Azure Defender (オプション 2) を使用して Windows サーバーをオンボードするには、ノードごとに Azure Defender for Servers ライセンスが必要です[。「Azure Defender](/azure/security-center/security-center-services)で利用可能なサポートされる機能」を参照してください。



> [!TIP]
> デバイスのオンボード後、検出テストを実行して、サービスに適切にオンボードされていることを確認できます。 詳細については、「新しくオンボードされた Defender for Endpoint エンドポイントで検出テストを実行 [する」を参照してください](run-detection-test.md)。

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>クライアントの構成と更新System Center Endpoint Protectionする

> [!IMPORTANT]
> この手順は、組織が SCEP (SCEP) System Center Endpoint Protection必要です。

Defender for Endpoint は System Center Endpoint Protection と統合し、マルウェアの検出を可視化し、悪意のある可能性のあるファイルや疑わしいマルウェアを禁止することで、組織内の攻撃の伝達を停止します。

この統合を有効にするには、次の手順が必要です。

- [2017 年 1](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)月のマルウェア対策プラットフォーム更新プログラムをクライアントEndpoint Protectionする
- SCEP クライアント Cloud Protection Service メンバーシップを詳細設定に **構成** する
- クラウドへの接続を許可するネットワークMicrosoft Defender ウイルス対策します。 詳細については、「ネットワーク接続の[構成と検証Microsoft Defender ウイルス対策参照してください。](/microsoft-365/security/defender-endpoint/configure-network-connections-microsoft-defender-antivirus)

## <a name="install-and-configure-microsoft-monitoring-agent-mma"></a>インストールと構成Microsoft Monitoring Agent (MMA) 

### <a name="before-you-begin"></a>開始する前に

最小システム要件を確認するには、次の詳細を確認します。

- [2018 年 2 月の更新プログラムのロールアップをインストールする](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)

  > [!NOTE]
  > 7 SP1 および 7 SP1 Windows 7 SP1 EnterpriseおよびWindowsにのみPro。

- カスタマー エクスペリエンス [と診断テレメトリの更新プログラムをインストールする](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

- [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (以降) または[KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)のいずれかをインストールする

    > [!NOTE]
    > 7 SP1 および 7 SP1 Windows 7 SP1 EnterpriseおよびWindowsにのみPro。
    > 上記のインストールを.NET Framework 4.0.x にはインストールしない。

- Azure Log Analytics エージェントの最小システム要件を満たします。 詳細については、「Log Analytics を使用して環境内のコンピューターからデータ [を収集する」を参照してください。](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)


### <a name="installation-steps"></a>インストールの手順

1. エージェント セットアップ ファイルをダウンロードします[Windows 64 ビット](https://go.microsoft.com/fwlink/?LinkId=828603)エージェントまたは[32 ビット Windowsエージェントをダウンロードします](https://go.microsoft.com/fwlink/?LinkId=828604)。

2. ワークスペース ID を取得します。
   - [Defender for Endpoint] ナビゲーション ウィンドウで、[デバイス設定 >**オンボーディング>選択します。**
   - オペレーティング システムを選択する
   - ワークスペース ID とワークスペース キーをコピーする

3. Workspace ID と Workspace キーを使用して、次のインストール方法を選択してエージェントをインストールします。
    - [セットアップを使用してエージェントを手動でインストールします](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)。

      [エージェント **のセットアップ オプション]** ページで、[エージェント **Connect Azure Log Analytics (OMS) に移動する] を選択します。**

    - [コマンド ラインを使用してエージェントをインストールします](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)。
    - [スクリプトを使用してエージェントを構成します](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)。

   > [!NOTE]
   > 米国政府機関のお客様[](gov.md)の場合は、[Azure Cloud] の下で、セットアップ ウィザードを使用する場合は "Azure US Government" を選択するか、コマンド ラインまたはスクリプトを使用する場合は、"OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" パラメーターを 1 に設定する必要があります。

4. プロキシを使用してインターネットに接続する場合は、「プロキシとインターネット接続の設定を構成する」セクションを参照してください。

完了すると、1 時間以内にポータルにオンボード エンドポイントが表示されます。

## <a name="configure-proxy-and-internet-connectivity-settings"></a>プロキシとインターネット接続の設定を構成する
サーバーが Defender for Endpoint と通信するためにプロキシを使用する必要がある場合は、次のいずれかの方法を使用して、プロキシ サーバーを使用する MMA を構成します。

- [プロキシ サーバーを使用する MMA を構成する](/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [すべてのWindowsプロキシ サーバーを使用するサーバーを構成する](configure-proxy-internet.md)

プロキシまたはファイアウォールが使用されている場合は、サーバーが SSL インターセプトなしで直接 Microsoft Defender for Endpoint サービス URL にアクセスできます。 詳細については、「Defender for Endpoint Service URL へのアクセス [を有効にする」を参照してください](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。 SSL インターセプトを使用すると、システムは Defender for Endpoint サービスと通信できません。

完了すると、1 時間以内にポータルにオンボード Windowsサーバーが表示されます。


## <a name="onboard-windows-servers-through-azure-defender"></a>Azure Defender Windowsサーバーのオンボード

1. [デバイス管理] Microsoft Defender セキュリティ センターで、[デバイス管理 **オン** ボーディング] 設定  >  **を**  >  **選択します**。

2. オペレーティング **Windowsサーバー 2008 R2 SP1 を** 選択します。

3. **[Azure セキュリティ センターのオンボード サーバー] をクリックします**。

4. Microsoft Defender for Endpoint with Azure Defender のオンボーディング手順に従い [、Azure](/azure/security-center/security-center-wdatp) ARC を使用している場合は、「Microsoft Defender for Endpoint 統合を有効にする」のオンボーディング手順に [従います](/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration)。

オンボーディングの手順を完了した後、クライアントの構成と[更新System Center Endpoint Protection必要があります](#configure-and-update-system-center-endpoint-protection-clients)。

> [!NOTE]
>
> - Azure Defender for Servers によるオンボーディングが期待通り動作するには、サーバーに適切なワークスペースとキーが構成されている必要があります。Microsoft Monitoring Agent (MMA) の設定で構成します。
> - 構成が完了すると、適切なクラウド管理パックがコンピューターに展開され、センサー プロセス (MsSenseS.exe) が展開され、開始されます。
> - これは、サーバーが OMS ゲートウェイ サーバーをプロキシとして使用するように構成されている場合にも必要です。



## <a name="verify-onboarding"></a>オンボーディングの確認

Microsoft Defender AV と Microsoft Defender for Endpoint が実行されているのを確認します。 

> [!NOTE]
> Microsoft Defender AV の実行は必要ありませんが、お勧めします。 別のウイルス対策ベンダー製品がプライマリ エンドポイント保護ソリューションである場合は、パッシブ モードで Defender ウイルス対策を実行できます。 パッシブ モードがオンの状態を確認できるのは、Microsoft Defender for Endpoint センサー (SENSE) が実行されている状態を確認した後のみです。 

1. 次のコマンドを実行して、Microsoft Defender AV がインストールされていることを確認します。

   ```sc.exe query Windefend```

    結果が '指定されたサービスがインストールされたサービスとして存在しない' の場合は、Microsoft Defender AV をインストールする必要があります。 詳細については[、「Microsoft Defender ウイルス対策」をWindows 10。](microsoft-defender-antivirus-windows.md)

    グループ ポリシーを使用 Microsoft Defender ウイルス対策して Windows サーバーでグループ ポリシーを構成および管理する方法については、「グループ ポリシー設定を使用してグループ ポリシーを構成および管理する」を参照[Microsoft Defender ウイルス対策。](use-group-policy-microsoft-defender-antivirus.md)


2. 次のコマンドを実行して、Microsoft Defender for Endpoint が実行されているのを確認します。

    ```sc.exe query sense```
    
    結果は、実行中を示す必要があります。 オンボーディングで問題が発生した場合は、「オンボードのトラブルシューティング [」を参照してください](troubleshoot-onboarding.md)。

## <a name="run-a-detection-test"></a>検出テストを実行する
「新しくオンボード[](run-detection-test.md)されたデバイスで検出テストを実行する」の手順に従って、サーバーが Defender for the Endpoint Service に対して報告を行っているのを確認します。





## <a name="onboarding-endpoints-with-no-management-solution"></a>管理ソリューションを使用してエンドポイントをオンボーディングする 

### <a name="using-group-policy"></a>グループ ポリシーの使用

**手順 1: エンドポイントに対応する udpate をダウンロードします。**

1. c:\windows\sysvol\domain\scripts に移動します (ドメイン コントローラーの 1 つで変更コントロールが必要になる場合があります)。
1. MMA という名前のフォルダーを作成します。
1. 次のファイルをダウンロードし、MMA フォルダーに配置します。
   
    - カスタマー エクスペリエンスと診断テレメトリの更新:
      - [For Windows Server 2008 R2 x64](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)
     
    サーバー Windows 2008 R2 SP1 では、次の更新プログラムも必要です。

    2018 年 2 月の月次ロールアップ - KB4074598 (Windows Server 2008 R2)

    [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4074598)<br>
    Windows Server 2008 R2 x64 の更新プログラムをダウンロードする
    
    .NET Framework 3.5.1 (KB315418)<br>
    [For Windows Server 2008 R2 x64](https://download.microsoft.com/download/6/8/0/680ee424-358c-4fdf-a0de-b45dee07b711/windows6.1-kb3154518-x64.msu)
    
    >[!NOTE]
    > この記事では、x64 ベースのサーバー (MMA Agent .exe X64 新しい SHA-2 準拠バージョン) を使用している必要があります。


**手順 2: ファイル名 DeployMMA.cmd を作成する (メモ帳を使用)** cmd ファイルに次の行を追加します。 ワークスペース ID と KEY が必要です。

次のコマンドは、例です。 次の値を置き換える。
- KB - オンボーディングするエンドポイントに関連する該当する KB を使用する
- ワークスペース ID と KEY - ID とキーを使用する


```dos
@echo off 
cd "C:"
IF EXIST "C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe" ( 
exit
) ELSE (

wusa.exe C:\Windows\MMA\Windows6.1-KB3080149-x64.msu /quiet /norestart
wusa.exe C:\Windows\MMA\Windows6.1-KB4074598-x64.msu /quiet /norestart
wusa.exe C:\Windows\MMA\Windows6.1-KB3154518-x64.msu /quiet /norestart
wusa.exe C:\Windows\MMA\Windows8.1-KB3080149-x64.msu /quiet /norestart
"c:\windows\MMA\MMASetup-AMD64.exe" /c /t: "C:\Windows\MMA"c:\windows\MMA\ setup.exe /qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1
OPINSIGHTS_WORKSPACE_ID="<your workspace ID>"
OPINSIGHTS_WORKSPACE_KEY="<your workspace key>" AcceptEndUserLicenseAgreement=1
)

)
```





### <a name="group-policy-configuration"></a>グループ ポリシーの構成

「Microsoft Defender for Endpoint Onboarding」などのオンボード デバイス専用の新しいグループ ポリシーを作成します。

- "c:\windows\MMA" という名前のグループ ポリシー フォルダーを作成する

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="フォルダー":::

    **これにより、GPO が適用され、MMA と呼ばれるすべてのサーバーに新しいフォルダーが追加され、c:\windows に格納されます。これには、MMA、前提条件、およびインストール スクリプトのインストール ファイルが含まれる。**

- Net ログオンに格納されている各ファイルのグループ ポリシー ファイルの基本設定を作成します。

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="グループ ポリシーイメージ1":::

DOMAIN\NETLOGON\MMA\filename から C:\windows\MMA\filename にファイルをコピー **します。**

:::image type="content" source="images/deploymma.png" alt-text="mma cmd を展開する":::

プロセスを繰り返しますが、[COMMON] タブでアイテム レベルのターゲット設定を作成します。そのため、ファイルはスコープ内の適切なプラットフォーム/オペレーティング システムバージョンにのみコピーされます。

:::image type="content" source="images/targeteditor.png" alt-text="ターゲット エディター":::

このWindows Server 2008 R2 では、次の情報が必要になります (コピーダウンのみ)。
- Windows6.1-KB3080149-x64.msu
- Windows6.1-KB3154518-x64.msu
- Windows6.1-KB4075598-x64.msu


これが完了したら、起動スクリプト ポリシーを作成する必要があります。

:::image type="content" source="images/startupprops.png" alt-text="プロパティの起動":::

ここで実行するファイルの名前は c:\windows\MMA\DeployMMA.cmd です。
サーバーが起動プロセスの一部として再起動すると、カスタマー エクスペリエンスと診断テレメトリ KB の更新プログラムがインストールされ、MMA エージェントがインストールされ、ワークスペース ID とキーが設定され、サーバーがオンボードされます。

すべてのサーバーを再起動 **しない** 場合は、即時タスクを使用して deployMMA.cmd を実行することもできます。

これは、2 つのフェーズで実行できます。 まず **、GPO でファイルと** フォルダーを作成します。 GPO が適用され、すべてのサーバーにインストール ファイルが含まれています。 次に、イミディエイト タスクを追加します。 これにより、再起動を必要とせずに同じ結果が得られます。

スクリプトは exit メソッドを持ち、MMA がインストールされている場合は再び実行されませんので、毎日スケジュールされたタスクを使用して同じ結果を得る場合も可能です。 Configuration Manager コンプライアンス ポリシーと同様に、MMA が存在しているのを確認するために毎日チェックされます。

:::image type="content" source="images/schtask.png" alt-text="スケジュール タスク":::

:::image type="content" source="images/newtaskprops.png" alt-text="新しいタスクのプロパティ":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="mma ダウンロード の小道具を展開する":::

:::image type="content" source="images/tasksch.png" alt-text="タスク スケジューラ":::

Server 2008 R2 のオンボーディングに関するドキュメントで説明したように、以下を参照してください。 Windows Server 2008 R2 SP1 の場合は、次の要件を満たしていることを確認してください。

- [2018 年 2 月の更新プログラムのロールアップをインストールする](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
- [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (以降) または[KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)のいずれかをインストールする

Server 2008 R2 のオンボード前に、KB がWindows確認してください。 このプロセスでは、Configuration Manager がサーバーを管理している必要がない場合は、すべてのサーバーをオンボードできます。


## <a name="offboard-endpoints"></a>オフボード エンドポイント

サービスからエンドポイントをオフボードWindows 2 つのオプションがあります。

- MMA エージェントのアンインストール
- Defender for Endpoint ワークスペース構成を削除する

> [!NOTE]
> オフボードにより、Windows エンドポイントはポータルへのセンサー データの送信を停止しますが、エンドポイントからのデータ (それが持っていたアラートへの参照を含む) は最大 6 か月間保持されます。

### <a name="uninstall-the-mma-agent"></a>MMA エージェントのアンインストール

このエンドポイントをオフWindows、MMA エージェントをアンインストールするか、レポートから Defender for Endpoint ワークスペースに切り離します。 エージェントのオフボード後、エンドポイントはセンサー データを Defender for Endpoint に送信しなくなりました。
詳細については、「エージェントを無効 [にするには」を参照してください](/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)。

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a>Defender for Endpoint ワークスペース構成を削除する

次のいずれかの方法を使用できます。

- DEFENDER for Endpoint ワークスペース構成を MMA エージェントから削除する
- PowerShell コマンドを実行して構成を削除する

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a>DEFENDER for Endpoint ワークスペース構成を MMA エージェントから削除する

1. [プロパティ **Microsoft Monitoring Agent] で****、[Azure Log Analytics (OMS) タブを選択** します。

2. [Defender for Endpoint] ワークスペースを選択し、[削除] を **クリックします**。

    ![プロパティのMicrosoft Monitoring Agent画像](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration&quot;></a>PowerShell コマンドを実行して構成を削除する

1. ワークスペース ID を取得します。

   1. ナビゲーション ウィンドウで、[オンボーディング]**設定**  >  **選択します**。

   1. 関連するオペレーティング システムを選択し、ワークスペース ID を取得します。

    
2. 管理者特権の PowerShell を開き、次のコマンドを実行します。 取得して置き換えたワークスペース ID を使用します `WorkspaceID` 。

    ```   
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace(&quot;WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```
