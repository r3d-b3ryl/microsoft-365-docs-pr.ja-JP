---
title: 以前のバージョンの Windows をMicrosoft Defender for Endpointにオンボードする
description: サポートされている以前のバージョンの Windows デバイスをオンボードして、センサー データをMicrosoft Defender for Endpoint センサーに送信できるようにします
keywords: onboard, windows, 7, 81, oms, sp1, enterprise, pro, down level
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
ms.openlocfilehash: c330d3c8210ea0c83605a2b5e9f9f43d1c930442
ms.sourcegitcommit: bc35c7826e3403f259725ac72cca5bafd36aa56a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2022
ms.locfileid: "66554425"
---
# <a name="onboard-previous-versions-of-windows"></a>以前のバージョンの Windows をオンボードする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**プラットフォーム**

- Windows 7 SP1 Enterprise
- Windows 7 SP1 Pro
- Windows 8.1 Pro
- Windows 8.1 Enterprise
- Windows Server 2008 R2 SP1

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-downlevel-abovefoldlink)

Defender for Endpoint では、下位レベルのオペレーティング システムを含めるサポートが拡張され、サポートされている Windows バージョンで高度な攻撃の検出と調査機能が提供されます。

ダウンレベルの Windows クライアント エンドポイントを Defender for Endpoint にオンボードするには、次のことを行う必要があります。

- [System Center Endpoint Protection クライアントの構成と更新](#configure-and-update-system-center-endpoint-protection-clients)
- [センサー データを報告する Microsoft Monitoring Agent (MMA) をインストールして構成する](#install-and-configure-microsoft-monitoring-agent-mma)

Windows Server 2008 R2 SP1 の場合は、 [Microsoft Defender for Cloud を使用してオンボードすることもできます](#onboard-windows-servers-through-microsoft-defender-for-cloud)。

> [!NOTE]
> Microsoft Monitoring Agent を使用して Windows サーバーをオンボードするには、ノードごとに Defender for Endpoint スタンドアロン サーバー ライセンスが必要です (オプション 1)。 または、Microsoft Defender for Cloud を使用して Windows サーバーをオンボードするには、ノードごとに Microsoft Defender for servers ライセンスが必要です (オプション 2)、 [Microsoft Defender for Cloud で使用可能なサポートされている機能に関するページを](/azure/defender-for-cloud/supported-machines-endpoint-solutions-clouds-servers)参照してください。

> [!TIP]
> デバイスをオンボードした後、検出テストを実行して、サービスに適切にオンボードされていることを確認できます。 詳細については、「 [新しくオンボードされた Defender for Endpoint エンドポイントで検出テストを実行する」を参照してください](run-detection-test.md)。

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>System Center Endpoint Protection クライアントの構成と更新

> [!IMPORTANT]
> この手順は、組織で System Center Endpoint Protection (SCEP) を使用している場合にのみ必要です。

Defender for Endpoint はSystem Center Endpoint Protectionと統合され、マルウェア検出の可視性を提供し、悪意のある可能性のあるファイルや疑わしいマルウェアを禁止することで、組織内の攻撃の伝達を停止します。

この統合を有効にするには、次の手順が必要です。

- [Endpoint Protection クライアント用に 2017 年 1 月のマルウェア対策プラットフォーム更新プログラムを](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)インストールする
- SCEP クライアント Cloud Protection Service メンバーシップを **詳細設定** に構成する
- Microsoft Defender ウイルス対策クラウドへの接続を許可するようにネットワークを構成します。 詳細については、「[Microsoft Defender ウイルス対策ネットワーク接続の構成と検証](/microsoft-365/security/defender-endpoint/configure-network-connections-microsoft-defender-antivirus)」を参照してください。

## <a name="install-and-configure-microsoft-monitoring-agent-mma"></a>Microsoft Monitoring Agent (MMA) をインストールして構成する

### <a name="before-you-begin"></a>はじめに

次の詳細を確認して、最小システム要件を確認します。

- [2018 年 2 月の月次更新プログラムロールアップを](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)インストールする

  > [!NOTE]
  > Windows Server 2008 R2、Windows 7 SP1 Enterprise、および Windows 7 SP1 Pro にのみ適用されます。

- [カスタマー エクスペリエンスと診断テレメトリ用の更新プログラムをインストールする](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

- [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (またはそれ以降) または [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework) をインストールする

    > [!NOTE]
    > Windows Server 2008 R2、Windows 7 SP1 Enterprise、および Windows 7 SP1 Pro にのみ適用されます。
    >
    > 4.0.x .NET Frameworkインストールしないでください。これは、上記のインストールを無効にするためです。
    >
    > .NET 4.5 のインストールでは、インストール後にコンピューターの再起動が必要になる場合があります。

- Azure Log Analytics エージェントの最小システム要件を満たします。 詳細については、「[Log Analytics を使用して環境内のコンピューターからデータを収集する](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)」を参照してください。

### <a name="installation-steps"></a>インストールの手順

1. エージェント セットアップ ファイル ( [Windows 64 ビット エージェント](https://go.microsoft.com/fwlink/?LinkId=828603) または [Windows 32 ビット エージェント) をダウンロードします](https://go.microsoft.com/fwlink/?LinkId=828604)。

    >[!NOTE]
    >[MMA エージェントによる SHA-1 サポートが廃止されたため、MMA エージェント](/azure/azure-monitor/agents/agent-windows#sha-2-code-signing-support-requirement)はバージョン 10.20.18029 以降である必要があります。
    

2. ワークスペース ID を取得します。
   - Defender for Endpoint ナビゲーション ウィンドウで、[**設定] > [デバイス管理] > [オンボード**] を選択します。
   - オペレーティング システムを選択する
   - ワークスペース ID とワークスペース キーをコピーする

3. ワークスペース ID とワークスペース キーを使用して、次のいずれかのインストール方法を選択してエージェントをインストールします。
    - [セットアップを使用してエージェントを手動でインストールします](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)。

      [**エージェントのセットアップ オプション]** ページで、[**エージェントを Azure Log Analytics (OMS) に接続** する] を選択します。

    - [コマンド ラインを使用してエージェントをインストールします](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)。
    - [スクリプトを使用してエージェントを構成します](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)。

   > [!NOTE]
   > [米国政府機関のお客様](gov.md)の場合は、[Azure Cloud] でセットアップ ウィザードを使用するか、コマンド ラインまたはスクリプトを使用する場合は [Azure US Government] を選択する必要があります。"OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" パラメーターを 1 に設定します。

4. プロキシを使用してインターネットに接続する場合は、「プロキシとインターネット接続の設定の構成」セクションを参照してください。

完了すると、1 時間以内にポータルにオンボードされたエンドポイントが表示されます。

## <a name="configure-proxy-and-internet-connectivity-settings"></a>プロキシとインターネット接続の設定を構成する
サーバーが Defender for Endpoint と通信するためにプロキシを使用する必要がある場合は、次のいずれかの方法を使用して、プロキシ サーバーを使用するように MMA を構成します。

- [プロキシ サーバーを使用するように MMA を構成する](/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [すべての接続にプロキシ サーバーを使用するように Windows を構成する](configure-proxy-internet.md)

プロキシまたはファイアウォールが使用されている場合は、サーバーが SSL インターセプトなしですべてのMicrosoft Defender for Endpoint サービス URL に直接アクセスできることを確認してください。 詳細については、「 [Defender for Endpoint サービス URL へのアクセスを有効にする」を](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)参照してください。 SSL インターセプトを使用すると、システムが Defender for Endpoint サービスと通信できなくなります。

完了すると、1 時間以内にオンボードされた Windows サーバーがポータルに表示されます。

## <a name="onboard-windows-servers-through-microsoft-defender-for-cloud"></a>Microsoft Defender for Cloud を使用して Windows サーバーをオンボードする

1. Microsoft 365 Defenderナビゲーション ウィンドウで、[**デバイス管理** > **のオンボード****の設定]** >  を選択します。

2. オペレーティング システムとして **Windows Server 2008 R2 SP1** を選択します。

3. **Microsoft Defender for Cloud で [サーバーのオンボード**] をクリックします。

4. [Microsoft Defender for Cloud のMicrosoft Defender for Endpoint](/azure/security-center/security-center-wdatp)のオンボード手順に従い、Azure ARC を使用している場合は、「[Microsoft Defender for Endpoint統合を有効にする」](/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration)のオンボード手順に従います。

オンボード手順を完了したら、[System Center Endpoint Protection クライアントを構成して更新](#configure-and-update-system-center-endpoint-protection-clients)する必要があります。

> [!NOTE]
>
> - Microsoft Defender を介したオンボードでサーバーが期待どおりに機能するには、サーバーに Microsoft Monitoring Agent (MMA) 設定内で適切なワークスペースとキーが構成されている必要があります。
> - 構成が完了すると、適切なクラウド管理パックがマシンにデプロイされ、センサー プロセス (MsSenseS.exe) がデプロイされて開始されます。
> - これは、OMS ゲートウェイ サーバーをプロキシとして使用するようにサーバーが構成されている場合にも必要です。



## <a name="verify-onboarding"></a>オンボードを確認する

Microsoft Defender AV とMicrosoft Defender for Endpointが実行されていることを確認します。 

> [!NOTE]
> Microsoft Defender AV の実行は必須ではありませんが、推奨されます。 別のウイルス対策ベンダー製品が主要なエンドポイント保護ソリューションである場合は、パッシブ モードで Defender ウイルス対策を実行できます。 パッシブ モードがオンになっていることを確認できるのは、Microsoft Defender for Endpoint センサー (SENSE) が実行されていることを確認した後のみです。 

1. 次のコマンドを実行して、Microsoft Defender AV がインストールされていることを確認します。

   ```sc.exe query Windefend```

    結果が "指定されたサービスがインストール済みサービスとして存在しない" 場合は、Microsoft Defender AV をインストールする必要があります。 詳細については、「[Windows 10の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-windows.md)」を参照してください。

    グループ ポリシーを使用して Windows サーバーのMicrosoft Defender ウイルス対策を構成および管理する方法については、「[グループ ポリシー設定を使用してMicrosoft Defender ウイルス対策を構成および管理する方法](use-group-policy-microsoft-defender-antivirus.md)」 を参照してください。


2. 次のコマンドを実行して、Microsoft Defender for Endpoint が実行されていることを検証します。

    ```sc.exe query sense```
    
    結果には、実行中であることが示されます。 オンボーディングで問題が発生した場合は、「[オンボードのトラブルシューティング](troubleshoot-onboarding.md)」 を参照してください。

## <a name="run-a-detection-test"></a>検出テストの実行
[［新しくオンボードされたデバイスで検出テストを実行する］](run-detection-test.md) の手順に従って、サーバーが Defender for the Endpoint サービスに報告していることを検証します。





## <a name="onboarding-endpoints-with-no-management-solution"></a>管理ソリューションを使用せずにエンドポイントをオンボードする 

### <a name="using-group-policy"></a>グループ ポリシーの使用

**手順 1: エンドポイントに対応する更新プログラムをダウンロードします。**

1. c:\windows\sysvol\domain\scripts に移動します (ドメイン コントローラーのいずれかで変更制御が必要になる場合があります)。
1. MMA という名前のフォルダーを作成します。
1. 次をダウンロードし、MMA フォルダーに配置します。
   
    - カスタマー エクスペリエンスと診断テレメトリの更新:
      - [Windows Server 2008 R2 x64 の場合](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)
     
    Windows Server 2008 R2 SP1 の場合は、次の更新プログラムも必要です。

    2018 年 2 月の月次ロールアップ - KB4074598 (Windows Server 2008 R2)

    [Microsoft Update カタログ](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4074598)<br>
    Windows Server 2008 R2 x64 の更新プログラムをダウンロードする
    
    .NET Framework 3.5.1 (KB315418)<br>
    [Windows Server 2008 R2 x64 の場合](/iis/install/installing-iis-7/install-windows-server-2008-and-windows-server-2008-r2)
    
    >[!NOTE]
    > この記事では、x64 ベースのサーバー (MMA エージェント .exe x64 新しい SHA-2 準拠バージョン) を使用していることを前提としています。


**手順 2: ファイル名 DeployMMA.cmd を作成する (メモ帳を使用)** cmd ファイルに次の行を追加します。 ワークスペース ID とキーが必要であることに注意してください。

次のコマンドは例です。 次の値を置き換えます。
- KB - オンボードするエンドポイントに関連する該当する KB を使用する
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
"c:\windows\MMA\MMASetup-AMD64.exe" /c /t:"C:\Windows\MMA"
c:\windows\MMA\setup.exe /qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1 OPINSIGHTS_WORKSPACE_ID="<your workspace ID>" OPINSIGHTS_WORKSPACE_KEY="<your workspace key>" AcceptEndUserLicenseAgreement=1

) 
```





### <a name="group-policy-configuration"></a>グループ ポリシー構成

"Microsoft Defender for Endpointオンボード" などのデバイスのオンボード専用の新しいグループ ポリシーを作成します。

- "c:\windows\MMA" という名前のグループ ポリシー フォルダーを作成する

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="フォルダーの場所" lightbox="images/grppolicyconfig1.png":::

    **これにより、MMA と呼ばれる GPO が適用され、c:\windows に格納されるすべてのサーバーに新しいフォルダーが追加されます。これには、MMA のインストール ファイル、前提条件、およびインストール スクリプトが含まれます。**

- Net ログオンに格納されている各ファイルに対して、グループ ポリシー ファイルの基本設定を作成します。

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="グループ ポリシー - 1" lightbox="images/grppolicyconfig2.png":::

DOMAIN\NETLOGON\MMA\filename から C:\windows\MMA\filename にファイルがコピー **されるため、インストール ファイルはサーバーにローカル** になります。

:::image type="content" source="images/deploymma.png" alt-text="デプロイ mma cmd プロパティ" lightbox="images/deploymma.png":::

プロセスを繰り返しますが、[共通] タブでアイテム レベルのターゲットを作成するため、ファイルはスコープ内の適切なプラットフォーム/オペレーティング システムのバージョンにのみコピーされます。

:::image type="content" source="images/targeteditor.png" alt-text="ターゲット エディター" lightbox="images/targeteditor.png":::

Windows Server 2008 R2 の場合は、次のものが必要です (コピーダウンのみ)。
- Windows6.1-KB3080149-x64.msu
- Windows6.1-KB3154518-x64.msu
- Windows6.1-KB4075598-x64.msu


これが完了したら、スタートアップ スクリプト ポリシーを作成する必要があります。

:::image type="content" source="images/startupprops.png" alt-text="スタートアップ プロパティ" lightbox="images/startupprops.png":::

ここで実行するファイルの名前は c:\windows\MMA\DeployMMA.cmd です。
起動プロセスの一環としてサーバーを再起動すると、カスタマー エクスペリエンスと診断テレメトリ KB 用の更新プログラムがインストールされ、MMA エージェントがインストールされ、ワークスペース ID とキーが設定されると、サーバーがオンボードされます。

すべてのサーバーを再起動しない場合は、 **即時タスク** を使用して deployMMA.cmd を実行することもできます。

これは 2 つのフェーズで実行できます。 最初 **に GPO でファイルとフォルダーを** 作成します。GPO が適用され、すべてのサーバーにインストール ファイルがあることをシステムに確認する時間を与えます。 次に、即時タスクを追加します。 これにより、再起動を必要とせずに同じ結果が得られます。

スクリプトには終了メソッドがあり、MMA がインストールされている場合は再実行されないため、毎日スケジュールされたタスクを使用して同じ結果を得ることもできます。 Configuration Managerコンプライアンス ポリシーと同様に、MMA が存在することを確認するために毎日チェックされます。

:::image type="content" source="images/schtask.png" alt-text="タスクをスケジュールする" lightbox="images/schtask.png":::

:::image type="content" source="images/newtaskprops.png" alt-text="新しいタスクプロパティ" lightbox="images/newtaskprops.png":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="デプロイ mma のダウンロード プロパティ" lightbox="images/deploymmadowmload.png":::

:::image type="content" source="images/tasksch.png" alt-text="タスク スケジューラ" lightbox="images/tasksch.png":::

Server 2008 R2 のオンボードドキュメントで説明されているように、以下を参照してください:Windows Server 2008 R2 SP1 の場合は、次の要件を満たしていることを確認してください。

- [2018 年 2 月の月次更新プログラムロールアップを](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)インストールする
- [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (またはそれ以降) または [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework) をインストールする

Windows Server 2008 R2 をオンボードする前に、KB が存在することを確認してください。 このプロセスでは、サーバーを管理するConfiguration Managerがない場合は、すべてのサーバーをオンボードできます。


## <a name="offboard-endpoints"></a>オフボード エンドポイント

サービスから Windows エンドポイントをオフボードするには、次の 2 つのオプションがあります。

- MMA エージェントをアンインストールする
- Defender for Endpoint ワークスペースの構成を削除する

> [!NOTE]
> オフボーディングにより、Windows エンドポイントはポータルへのセンサー データの送信を停止しますが、エンドポイントからのデータ (アラートへの参照を含む) は最大 6 か月間保持されます。

### <a name="uninstall-the-mma-agent"></a>MMA エージェントをアンインストールする

Windows エンドポイントをオフボードするには、MMA エージェントをアンインストールするか、レポートから Defender for Endpoint ワークスペースにデタッチします。 エージェントのオフボード後、エンドポイントは Defender for Endpoint にセンサー データを送信しなくなります。
詳細については、「 [エージェントを無効にするには」を](/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)参照してください。

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a>Defender for Endpoint ワークスペースの構成を削除する

次のいずれかの方法を使用できます。

- MMA エージェントから Defender for Endpoint ワークスペースの構成を削除する
- PowerShell コマンドを実行して構成を削除する

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a>MMA エージェントから Defender for Endpoint ワークスペースの構成を削除する

1. **Microsoft Monitoring Agent のプロパティ** で、**Azure Log Analytics (OMS)** タブを選択します。

2. Defender for Endpoint ワークスペースを選択し、[ **削除**] をクリックします。

    :::image type="content" source="images/atp-mma.png" alt-text="[ワークスペース] ウィンドウ" lightbox="images/atp-mma.png":::

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a>PowerShell コマンドを実行して構成を削除する

1. ワークスペース ID を取得します。

   1. ナビゲーション ウィンドウで、[オン **ボーディング****の設定]** >  を選択します。

   1. 関連するオペレーティング システムを選択し、ワークスペース ID を取得します。

    
2. 管理者特権の PowerShell を開き、次のコマンドを実行します。 取得したワークスペース ID を使用して、次の値を `WorkspaceID`置き換えます。

    ```   
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace("WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```
