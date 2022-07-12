---
title: Microsoft Defender for Endpointに切り替える - オンボード
description: Microsoft Defender for Endpointに切り替えます。 デバイスをオンボードし、Microsoft 以外のソリューションをアンインストールします。
keywords: 移行、Microsoft Defender for Endpoint、edr
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.custom:
- migrationguides
- admindeeplinkDEFENDER
ms.topic: article
ms.date: 04/01/2022
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: d927f1a5972e24c3bae0329bd866a4b56b0a5d95
ms.sourcegitcommit: c314e989202dc1c9c260fffd459d53bc1f08514e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2022
ms.locfileid: "66717252"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>Microsoft Defender for Endpointに切り替える - フェーズ 3: オンボード

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![フェーズ 1: Prepare3。](images/phase-diagrams/prepare.png#lightbox)](switch-to-mde-phase-1.md)<br/>[フェーズ 1: 準備](switch-to-mde-phase-1.md) | [![フェーズ 2: 設定](images/phase-diagrams/setup.png#lightbox)](switch-to-mde-phase-2.md)<br/>[フェーズ 2: 設定](switch-to-mde-phase-2.md) | ![フェーズ 3: オンボード](images/phase-diagrams/onboard.png#lightbox)<br/>フェーズ 3: オンボード |
|--|--|--|
|| |*お客様はここにいます。* |

**[Defender for Endpoint への切り替え](switch-to-mde-overview.md#the-migration-process)のフェーズ 3 へようこそ**。 この移行フェーズには、次の手順が含まれます。

1. [Defender for Endpoint にデバイスをオンボードします](#onboard-devices-to-microsoft-defender-for-endpoint)。
2. [検出テストを実行します](#run-a-detection-test)。
3. [Microsoft Defender ウイルス対策がエンドポイントでパッシブ モードになっていることを確認します](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints)。
4. [Microsoft Defender ウイルス対策の更新プログラムを取得します](#get-updates-for-microsoft-defender-antivirus)。
5. [Microsoft 以外のソリューションをアンインストールします](#uninstall-your-non-microsoft-solution)。
6. [Defender for Endpoint が正しく動作していることを確認します](#make-sure-defender-for-endpoint-is-working-correctly)。

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>デバイスを Microsoft Defender for Endpoint にオンボードする

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. [設定 **エンドポイントの** \> **オンボード****]** \> を選択します (**[デバイス管理]** の下)。

3. [ **オンボード プロセスを開始するオペレーティング システムの選択] ボックスの** 一覧で、オペレーティング システムを選択します。

4. **[展開方法]** で、オプションを選択します。 リンクとプロンプトに従って、組織のデバイスをオンボードします。 お困りの際は、 [オンボード方法 (](#onboarding-methods)この記事では) を参照してください。

> [!NOTE]
> オンボード中に問題が発生した場合は、「オンボードの[問題Microsoft Defender for Endpointトラブルシューティング](troubleshoot-onboarding.md)する」を参照してください。 この記事では、オンボードの問題とエンドポイントに関する一般的なエラーを解決する方法について説明します。

### <a name="onboarding-methods"></a>オンボードメソッド

> [!IMPORTANT]
> Microsoft Defender for Cloud を使用している場合は、「 [Microsoft Defender for Cloud との統合」を](configure-server-endpoints.md#integration-with-microsoft-defender-for-cloud)参照してください。

展開方法は、オペレーティング システムと推奨される方法によって異なります。 次の表に、Defender for Endpoint へのオンボードに役立つリソースを示します。

|オペレーティング システム  |メソッド  |
|---------|---------|
|Windows 10 以降<br/><br/>Windows Server 2019 以降。<br/><br/>Windows Server バージョン 1803 以降<br/><br/>Windows Server 2012 R2 と 2016<sup>[[1](#fn1)]<sup>  |   [ローカル スクリプト (最大 10 台のデバイス)](configure-endpoints-script.md)<br><br/>   [グループ ポリシー](configure-endpoints-gp.md)<br/><br/>[Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)<br/><br/>[Microsoft エンドポイント マネージャー/ Mobile デバイス管理 (Intune)](configure-endpoints-mdm.md)<br>    [VDI スクリプト](configure-endpoints-vdi.md) <br><br> **注**: ローカル スクリプトは概念実証に適していますが、運用環境のデプロイには使用しないでください。 運用環境の展開では、グループ ポリシー、Microsoft Endpoint Configuration Manager、またはIntuneを使用することをお勧めします。 |
|Windows Server 2008 R2 SP1 | [Microsoft Monitoring Agent (MMA)](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma)  または [Microsoft Defender for Cloud](/azure/security-center/security-center-wdatp) <br><br> **注**: Microsoft Monitoring Agent は Azure Log Analytics エージェントになりました。 詳細については、 [Log Analytics エージェントの概要に関する](/azure/azure-monitor/platform/log-analytics-agent)ページを参照してください。  |
|Windows 8.1 Enterprise<br/><br/>Windows 8.1 Pro<br/><br/>Windows 7 SP1 Pro<br/><br/>Windows 7 SP1| [Microsoft Monitoring Agent (MMA)](onboard-downlevel.md) <br><br> **注**: Microsoft Monitoring Agent は Azure Log Analytics エージェントになりました。 詳細については、 [Log Analytics エージェントの概要に関する](/azure/azure-monitor/platform/log-analytics-agent)ページを参照してください。  
| macOS ([システム要件を](microsoft-defender-endpoint-mac.md)参照してください) | [ローカル スクリプト](mac-install-manually.md)<br/><br/>[Microsoft エンドポイント マネージャー](mac-install-with-intune.md)<br/><br/>[JAMF Pro](mac-install-with-jamf.md)<br/><br/>[モバイル デバイス管理](mac-install-with-other-mdm.md)   |
| Linux ( [システム要件を](microsoft-defender-endpoint-linux.md#system-requirements)参照) |  [ローカル スクリプト](linux-install-manually.md) <br><br/> [人形](linux-install-with-puppet.md) <br><br/> [アンシブル](linux-install-with-ansible.md)|  
| iOS | [Microsoft エンドポイント マネージャー](ios-install.md)     |
|Android  | [Microsoft エンドポイント マネージャー](android-intune.md)  | 

(<a id="fn1">1</a>) Windows Server 2016 と Windows Server 2012 R2 は、[Windows サーバーのオンボード](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)の手順に従ってオンボードする必要があります。

## <a name="run-a-detection-test"></a>検出テストの実行

オンボードされたデバイスが Defender for Endpoint に正しく接続されていることを確認するには、検出テストを実行します。

|オペレーティング システム|ガイダンス|
|---|---|
|Windows 10 以降<br/><br/>Windows Server 2022<br/><br/>Windows Server 2019<br/><br/>Windows Server バージョン 1803 以降<br/><br/>Windows Server 2016<br/><br/>Windows Server 2012 R2|[「検出テストを実行する」を](run-detection-test.md)参照してください。|
|macOS ([システム要件を](microsoft-defender-endpoint-mac.md)参照してください)|で DIY アプリ <https://aka.ms/mdatpmacosdiy>をダウンロードして使用します。 <br/><br/> 詳細については、「 [macOS 上の Defender for Endpoint」](microsoft-defender-endpoint-mac.md)を参照してください。|
|Linux ( [システム要件を](microsoft-defender-endpoint-linux.md#system-requirements)参照)|1. 次のコマンドを実行し、 **1** の結果を探します `mdatp health --field real_time_protection_enabled`。<br/><br/>2. ターミナル ウィンドウを開き、次のコマンドを実行します `curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`。<br/><br/>3. 次のコマンドを実行して、検出された脅威を一覧表示します `mdatp threat list`。<br/><br/>詳細については、「 [Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)」を参照してください。|

## <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints"></a>Microsoft Defender ウイルス対策がエンドポイントでパッシブ モードになっていることを確認する

エンドポイントが Defender for Endpoint にオンボードされたので、次の手順は、Microsoft Defender ウイルス対策がパッシブ モードで実行されていることを確認することです。 次の表に示すように、いくつかのメソッドのいずれかを使用できます。

|メソッド|操作|
|---|---|
|コマンド プロンプト|1. Windows デバイスで、コマンド プロンプトを開きます。<br/><br/>2. 「`sc query windefend`」と入力し、Enter キーを押します。<br/><br/>3. 結果を確認して、Microsoft Defender ウイルス対策がパッシブ モードで実行されていることを確認します。|
|PowerShell|1. Windows デバイスで、管理者としてWindows PowerShellを開きます。<br/><br/>2. 次の PowerShell コマンドレットを実行します `Get-MpComputerStatus|select AMRunningMode`。 <br/><br/>3. 結果を確認します。 **パッシブ モード** が表示されます。|
|Windows セキュリティ アプリを開きます。|1. Windows デバイスで、Windows セキュリティ アプリを開きます。<br/><br/>2. [**ウイルスと脅威の防止**] を選択します。<br/><br/>3. "**自分を保護している人**" の下で [**プロバイダーの管理**] を選択します。<br/><br/>4. [ **セキュリティ プロバイダー** ] ページの [ **ウイルス対策**] で、 **Microsoft Defender ウイルス対策がオンになっていることを** 確認します。|
|タスク マネージャー|1. Windows デバイスで、タスク マネージャー アプリを開きます。<br/><br/>2. [ **詳細** ] タブを選択します。一覧で **MsMpEng.exe** を探します。|

> [!NOTE]
> 一部のバージョンの Windows では *、Microsoft Defender ウイルス対策* の代わりに *Windows Defender ウイルス対策* が表示される場合があります。
> パッシブ モードとアクティブ モードの詳細については、「 [Microsoft Defender ウイルス対策の状態の詳細](microsoft-defender-antivirus-compatibility.md#more-details-about-microsoft-defender-antivirus-states)」を参照してください。

### <a name="set-microsoft-defender-antivirus-on-windows-server-to-passive-mode-manually"></a>Windows Server で Microsoft Defender ウイルス対策をパッシブ モードに手動で設定する

Windows Server、バージョン 1803 以降、または Windows Server 2019 または Windows Server 2022 で Microsoft Defender ウイルス対策をパッシブ モードに設定するには、次の手順に従います。

1. レジストリ エディターを開き、次に `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`移動します。

2. **ForceDefenderPassiveMode** という DWORD エントリを編集 (または作成) し、次の設定を指定します。

   - DWORD の値を 1 に設定 **します**。

   - [ **基本**] で 、[ **16 進数**] を選択します。

> [!NOTE]
> 他のメソッドを使用して、次のようなレジストリ キーを設定できます。
>
> - [グループ ポリシー環境設定](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
> - [ローカル グループ ポリシー オブジェクト ツール](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
> - [Configuration Managerのパッケージ](/mem/configmgr/apps/deploy-use/packages-and-programs)

### <a name="start-microsoft-defender-antivirus-on-windows-server-2016"></a>Windows Server 2016で Microsoft Defender ウイルス対策を開始する

Windows Server 2016を使用している場合は、Microsoft Defender ウイルス対策を手動で開始する必要がある場合があります。 このタスクは、デバイスの PowerShell コマンドレット `mpcmdrun.exe -wdenable` を使用して実行できます。

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策の更新プログラムを取得する

Microsoft Defender ウイルス対策がパッシブ モードで実行されている場合でも、新しいマルウェアや攻撃手法から保護するために必要な最新のテクノロジと機能をデバイスに確実に提供するには、Microsoft Defender ウイルス対策を最新の状態に保つことが重要です。 ( [Microsoft Defender ウイルス対策の互換性](microsoft-defender-antivirus-compatibility.md)に関するページを参照してください)。

Microsoft Defender ウイルス対策を最新の状態に保つことに関連する更新プログラムには、次の 2 種類があります。

- セキュリティ インテリジェンスの更新プログラム

- 製品の更新プログラム

更新プログラムを取得するには、「Microsoft Defender ウイルス対策更新プログラムの管理」のガイダンスに従い [、ベースラインを適用します](manage-updates-baselines-microsoft-defender-antivirus.md)。

## <a name="uninstall-your-non-microsoft-solution"></a>Microsoft 以外のソリューションをアンインストールする

この時点で次の操作が行われます。

- 組織のデバイスを Defender for Endpoint にオンボードし、

- Microsoft Defender ウイルス対策がインストールされ、有効になっています。

次に、Microsoft 以外のウイルス対策、マルウェア対策、エンドポイント保護ソリューションをアンインストールします。 Microsoft 以外のソリューションをアンインストールすると、Microsoft Defender ウイルス対策はパッシブ モードからアクティブ モードに切り替わります。 ほとんどの場合、これは自動的に発生します。 

> [!IMPORTANT]
> Microsoft 以外のウイルス対策/マルウェア対策ソリューションをアンインストールした後、何らかの理由で Microsoft Defender ウイルス対策がアクティブ モードに移行しない場合は、「 [Microsoft Defender ウイルス対策がパッシブ モードで停止しているようです](switch-to-mde-troubleshooting.md#microsoft-defender-antivirus-seems-to-be-stuck-in-passive-mode)」を参照してください。

Microsoft 以外のソリューションのアンインストールに関するヘルプを表示するには、テクニカル サポート チームにお問い合わせください。

## <a name="make-sure-defender-for-endpoint-is-working-correctly"></a>Defender for Endpoint が正しく動作していることを確認する

Defender for Endpoint にオンボードし、以前の Microsoft 以外のソリューションをアンインストールしたので、次の手順は Defender for Endpoint が正しく動作していることを確認することです。 

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ナビゲーション ウィンドウで、[**Endpoints** Device inventory]\(エンドポイント **デバイス インベントリ**\ > ) を選択します。 そこでは、デバイスの保護状態を確認できます。

詳細については、「 [デバイス インベントリ](machines-view-overview.md)」を参照してください。

## <a name="next-steps"></a>次の手順

**おめでとうございます**。 [Defender for Endpoint への移行](switch-to-mde-overview.md#the-migration-process)が完了しました。

- Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) で[セキュリティ操作ダッシュボードにアクセスします](security-operations-dashboard.md)。

- [Defender for Endpoint を管理し、移行後に行います](manage-mde-post-migration.md)。
