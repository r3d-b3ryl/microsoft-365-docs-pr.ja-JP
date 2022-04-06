---
title: '[スイッチ] Microsoft Defender for Endpoint - オンボード'
description: スイッチを [Microsoft Defender for Endpoint] にMicrosoft Defender for Endpoint。 デバイスをオンボードし、Microsoft 以外のソリューションをアンインストールします。
keywords: 移行、 Microsoft Defender for Endpoint、edr
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
ms.openlocfilehash: 4f387ae01af51292667f810176970f3607b489b3
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634407"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>[スイッチ] Microsoft Defender for Endpoint - フェーズ 3: オンボード

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![フェーズ 1: Prepare3。](images/phase-diagrams/prepare.png#lightbox)](switch-to-mde-phase-1.md)<br/>[フェーズ 1: 準備](switch-to-mde-phase-1.md) | [![フェーズ 2: 設定](images/phase-diagrams/setup.png#lightbox)](switch-to-mde-phase-2.md)<br/>[フェーズ 2: 設定](switch-to-mde-phase-2.md) | ![フェーズ 3: オンボード](images/phase-diagrams/onboard.png#lightbox)<br/>フェーズ 3: オンボード |
|--|--|--|
|| |*お前はここにいる!* |

**エンドポイントの Defender への切り [替えのフェーズ 3 へようこそ](switch-to-mde-overview.md#the-migration-process)**。 この移行フェーズには、次の手順が含まれます。

1. [デバイスを Defender for Endpoint にオンボードします](#onboard-devices-to-microsoft-defender-for-endpoint)。
2. [検出テストを実行します](#run-a-detection-test)。
3. [エンドポイントでMicrosoft Defender ウイルス対策パッシブ モードに切り替わります](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints)。
4. [ユーザーの更新プログラムをMicrosoft Defender ウイルス対策](#get-updates-for-microsoft-defender-antivirus)。
5. [Microsoft 以外のソリューションをアンインストールします](#uninstall-your-non-microsoft-solution)。
6. [Defender for Endpoint が正しく動作するようにします](#make-sure-defender-for-endpoint-is-working-correctly)。

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>デバイスを Microsoft Defender for Endpoint にオンボードする

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. [**設定** \> **オンボーディング]** \> **を選択します** ([デバイス **の管理] の下)。**

3. [オンボード **プロセスを開始するオペレーティング システムの選択] ボックスの一覧で** 、オペレーティング システムを選択します。

4. [ **展開方法] で**、オプションを選択します。 リンクとプロンプトに従って、組織のデバイスをオンボードします。 お困りの際は、 「 [Onboarding メソッド (この](#onboarding-methods) 記事)」を参照してください。

> [!NOTE]
> オンボーディング中に問題が発生した場合は、「[オンボードに関する問題Microsoft Defender for Endpointトラブルシューティング」を参照してください](troubleshoot-onboarding.md)。 この記事では、オンボーディングの問題とエンドポイントの一般的なエラーを解決する方法について説明します。

### <a name="onboarding-methods"></a>オンボーディングメソッド

> [!IMPORTANT]
> この機能を使用している場合Microsoft Defender for Cloud、「[統合と統合」を参照Microsoft Defender for Cloud](configure-server-endpoints.md#integration-with-microsoft-defender-for-cloud)。

展開方法は、オペレーティング システムと優先する方法によって異なります。 次の表に、Defender for Endpoint へのオンボードに役立つリソースの一覧を示します。

|オペレーティング システム  |メソッド  |
|---------|---------|
|Windows 10以降<br/><br/>Windows Server 2019 以降。<br/><br/>Windows Server バージョン 1803 以降<br/><br/>Windows Server 2012 R2 および 2016<sup>[[1](#fn1)]<sup>  |   [ローカル スクリプト (最大 10 台のデバイス)](configure-endpoints-script.md)<br><br/>   [グループ ポリシー](configure-endpoints-gp.md)<br/><br/>[Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)<br/><br/>[Microsoft エンドポイント マネージャー/ Mobile デバイス管理 (Intune)](configure-endpoints-mdm.md)<br>    [VDI スクリプト](configure-endpoints-vdi.md) <br><br> **注**: ローカル スクリプトは概念実証に適していますが、実稼働環境の展開には使用できません。 実稼働展開の場合は、グループ ポリシー、Microsoft Endpoint Configuration Manager、またはIntune。 |
|Windows Server 2008 R2 SP1 | [Microsoft Monitoring Agent (MMA)](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma) [または Microsoft Defender for Cloud](/azure/security-center/security-center-wdatp) <br><br> **注**: Microsoft Monitoring Agent Azure Log Analytics エージェントです。 詳細については、「 [Log Analytics エージェントの概要」を参照してください](/azure/azure-monitor/platform/log-analytics-agent)。  |
|Windows 8.1 Enterprise<br/><br/>Windows 8.1 Pro<br/><br/>Windows 7 SP1 Pro<br/><br/>Windows 7 SP1| [Microsoft Monitoring Agent (MMA)](onboard-downlevel.md) <br><br> **注**: Microsoft Monitoring Agent Azure Log Analytics エージェントです。 詳細については、「 [Log Analytics エージェントの概要」を参照してください](/azure/azure-monitor/platform/log-analytics-agent)。  
| macOS (「 [システム要件」を参照)](microsoft-defender-endpoint-mac.md) | [ローカル スクリプト](mac-install-manually.md)<br/><br/>[Microsoft エンドポイント マネージャー](mac-install-with-intune.md)<br/><br/>[JAMF Pro](mac-install-with-jamf.md)<br/><br/>[モバイル デバイス管理](mac-install-with-other-mdm.md)   |
| Linux (「 [システム要件」を参照](microsoft-defender-endpoint-linux.md#system-requirements)) |  [ローカル スクリプト](linux-install-manually.md) <br><br/> [Puppet](linux-install-with-puppet.md) <br><br/> [Ansible](linux-install-with-ansible.md)|  
| iOS | [Microsoft エンドポイント マネージャー](ios-install.md)     |
|Android  | [Microsoft エンドポイント マネージャー](android-intune.md)  | 

(<a id="fn1">1</a>) Windows Server 2016および Windows Server 2012 R2 は、オンボード サーバーの指示に従ってオンボード[Windowsがあります](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)。

## <a name="run-a-detection-test"></a>検出テストの実行

オンボードデバイスが Defender for Endpoint に正しく接続されていることを確認するには、検出テストを実行できます。

|オペレーティング システム|ガイダンス|
|---|---|
|Windows 10以降<br/><br/>Windows Server 2022<br/><br/>Windows Server 2019<br/><br/>Windows Server バージョン 1803 以降<br/><br/>Windows Server 2016<br/><br/>Windows Server 2012 R2|「 [検出テストを実行する」を参照してください](run-detection-test.md)。<br/><br/>Defender for Endpoint デモ シナリオ サイト (<https://demo.wd.microsoft.com>) にアクセスし、1 つ以上のシナリオを試してください。 たとえば、クラウド配信の **保護デモ シナリオを** 試してみてください。|
|macOS (「 [システム要件」を参照)](microsoft-defender-endpoint-mac.md)|で DIY アプリをダウンロードして使用します <https://aka.ms/mdatpmacosdiy>。 <br/><br/> 詳細については、「 [Defender for Endpoint on macOS」を参照してください](microsoft-defender-endpoint-mac.md)。|
|Linux (「 [システム要件」を参照](microsoft-defender-endpoint-linux.md#system-requirements))|1. 次のコマンドを実行し、1 の結果 **を探します**。 `mdatp health --field real_time_protection_enabled`<br/><br/>2. ターミナル ウィンドウを開き、次のコマンドを実行します。 `curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`<br/><br/>3. 次のコマンドを実行して、検出された脅威を一覧表示します。 `mdatp threat list`<br/><br/>詳細については、「 [Defender for Endpoint on Linux」を参照してください](microsoft-defender-endpoint-linux.md)。|

> [!NOTE]
> demo.wd.microsoft.com の Defender for Endpoint デモ サイトは推奨されません。今後削除される予定です。

## <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints"></a>エンドポイントでMicrosoft Defender ウイルス対策パッシブ モードの状態を確認する

エンドポイントが Defender for Endpoint にオンボードされたので、次の手順では、パッシブ モードでMicrosoft Defender ウイルス対策を確認します。 次の表で説明するように、いくつかの方法のいずれかを使用できます。

|メソッド|操作|
|---|---|
|コマンド プロンプト|1. Windows デバイスで、コマンド プロンプトを開きます。<br/><br/>2. 「`sc query windefend`」と入力し、Enter キーを押します。<br/><br/>3. 結果を確認して、Microsoft Defender ウイルス対策がパッシブ モードで実行されていることを確認します。|
|PowerShell|1. デバイスでWindows管理者としてWindows PowerShell開きます。<br/><br/>2. 次の PowerShell コマンドレットを実行します。 `Get-MpComputerStatus|select AMRunningMode` <br/><br/>3. 結果を確認します。 パッシブ モードが **表示されます**。|
|Windows セキュリティ アプリを開きます。|1. Windows デバイスで、Windows セキュリティ アプリを開きます。<br/><br/>2. [**ウイルスと脅威の防止**] を選択します。<br/><br/>3. "**自分を保護している人**" の下で [**プロバイダーの管理**] を選択します。<br/><br/>4. [セキュリティ **プロバイダー] ページの** [ウイルス対策] で、有効になっているMicrosoft Defender ウイルス対策 **を探します**。|
|タスク マネージャー|1. Windows デバイスで、タスク マネージャー アプリを開きます。<br/><br/>2. [詳細] タブ **を選択** します。リストで **MsMpEng.exe** を探します。|

> [!NOTE]
> 一部の *バージョンの**Windows Defender ウイルス対策のMicrosoft Defender ウイルス対策* の代わりに、Windows。
> パッシブ モードとアクティブ モードの詳細については、「パッシブ モードとアクティブ モードの詳細[Microsoft Defender ウイルス対策参照してください](microsoft-defender-antivirus-compatibility.md#more-details-about-microsoft-defender-antivirus-states)。

### <a name="set-microsoft-defender-antivirus-on-windows-server-to-passive-mode-manually"></a>サーバー Microsoft Defender ウイルス対策をWindowsパッシブ モードに手動で設定する

Windows Server、バージョン 1803 以降、または Windows Server 2019、または Windows Server 2022 で Microsoft Defender ウイルス対策 をパッシブ モードに設定するには、次の手順を実行します。

1. レジストリ エディターを開き、に移動します `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`。

2. **ForceDefenderPassiveMode** という DWORD エントリを編集 (または作成) し、次の設定を指定します。

   - DWORD の値を **1 に設定します**。

   - [基本 **] で**、[16 進数] **を選択します**。

> [!NOTE]
> 他のメソッドを使用して、次のようなレジストリ キーを設定できます。
>
> - [グループ ポリシー基本設定](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
> - [ローカル グループ ポリシー オブジェクト ツール](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
> - [パッケージのConfiguration Manager](/mem/configmgr/apps/deploy-use/packages-and-programs)

### <a name="start-microsoft-defender-antivirus-on-windows-server-2016"></a>Microsoft Defender ウイルス対策からWindows Server 2016

ユーザー設定を使用しているWindows Server 2016、手動で開始するMicrosoft Defender ウイルス対策があります。 このタスクは、デバイスで PowerShell コマンドレットを使用 `mpcmdrun.exe -wdenable` して実行できます。

## <a name="get-updates-for-microsoft-defender-antivirus"></a>ユーザーの更新プログラムを取得Microsoft Defender ウイルス対策

Microsoft Defender ウイルス対策モードで実行されている場合でも、新しいマルウェアや攻撃の手法から保護するために必要な最新のテクノロジと機能をデバイスに提供するには、最新のMicrosoft Defender ウイルス対策を維持する必要があります。 (「互換性[Microsoft Defender ウイルス対策」を](microsoft-defender-antivirus-compatibility.md)参照してください)。

Microsoft Defender ウイルス対策を最新の状態に保つことに関連する更新プログラムには、次の 2 種類があります。

- セキュリティ インテリジェンスの更新プログラム

- 製品の更新プログラム

更新プログラムを取得するには、「更新プログラムの管理」のガイダンス[にMicrosoft Defender ウイルス対策ベースラインを適用します](manage-updates-baselines-microsoft-defender-antivirus.md)。

## <a name="uninstall-your-non-microsoft-solution"></a>Microsoft 以外のソリューションをアンインストールする

この時点で、次の情報を使用できます。

- 組織のデバイスを Defender for Endpoint にオンボードし、

- Microsoft Defender ウイルス対策がインストールされ、有効になっている場合

次に、Microsoft 以外のウイルス対策、マルウェア対策、エンドポイント保護ソリューションをアンインストールします。 Microsoft 以外のソリューションをアンインストールすると、Microsoft Defender ウイルス対策モードからアクティブ モードに切り替わります。 ほとんどの場合、これは自動的に行われます。 

> [!IMPORTANT]
> Microsoft 以外のウイルス対策/マルウェア対策ソリューションをアンインストールした後に何らかの理由で Microsoft Defender ウイルス対策 がアクティブ モードに入らない場合は、「[Microsoft Defender ウイルス対策](switch-to-mde-troubleshooting.md#microsoft-defender-antivirus-seems-to-be-stuck-in-passive-mode) がパッシブ モードでスタックしているようです」を参照してください。

Microsoft 以外のソリューションのアンインストールに関するヘルプを入手するには、テクニカル サポート チームにお問い合わせください。

## <a name="make-sure-defender-for-endpoint-is-working-correctly"></a>Defender for Endpoint が正しく動作するようにする

Defender for Endpoint にオンボードし、以前の Microsoft 以外のソリューションをアンインストールしたので、次の手順では、Defender for Endpoint が正しく動作することを確認します。 このタスクを実行する優れた方法の 1 つは、Defender for Endpoint デモ シナリオ サイト ([https://demo.wd.microsoft.com](https://demo.wd.microsoft.com)) にアクセスすることです。 少なくとも次を含む、そのページで 1 つ以上のデモ シナリオを試してみてください。

- クラウドによる保護

- 望ましくない可能性のあるアプリケーション (PUA)

- ネットワーク保護 (NP)

> [!NOTE]
> demo.wd.microsoft.com の Defender for Endpoint デモ サイトは推奨されません。今後削除される予定です。

## <a name="next-steps"></a>次の手順

**おめでとう** ございます! Defender [for Endpoint への移行が完了しました](switch-to-mde-overview.md#the-migration-process)。

- [ポータル () のセキュリティ](security-operations-dashboard.md)操作ダッシュボードMicrosoft 365 Defenderアクセスします[https://security.microsoft.com](https://security.microsoft.com)。

- [Defender for Endpoint の管理、移行後](manage-mde-post-migration.md)。
