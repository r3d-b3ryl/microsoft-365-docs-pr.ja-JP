---
title: エンドポイント用 Microsoft Defender に切り替える - セットアップ
description: これは、Microsoft Defender for Endpoint に切り替えるフェーズ 2 セットアップです。
keywords: 移行, Microsoft Defender for Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 656ee0bda769cb5ff2cdbe406db2a95e791210c1
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935559"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-2-setup"></a>エンドポイントの Microsoft Defender に切り替える - フェーズ 2: セットアップ

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![フェーズ 1: 準備](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[フェーズ 1: 準備](switch-to-microsoft-defender-prepare.md) |![フェーズ 2: 設定](images/phase-diagrams/setup.png)<br/>フェーズ 2: 設定 |[![フェーズ 3: Onboard3](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[フェーズ 3: オンボード](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
||*お前はここにいる!* | |

Microsoft Defender for Endpoint への切り **[替えのセットアップ フェーズへようこそ](switch-to-microsoft-defender-migration.md#the-migration-process)**。 このフェーズには、次の手順が含まれます。
1. [Microsoft Defender ウイルス対策を有効にして、パッシブ モードの状態を確認します](#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode)。
2. [Microsoft Defender ウイルス対策の更新プログラムを取得します](#get-updates-for-microsoft-defender-antivirus)。
3. [既存のエンドポイント ソリューションの除外リストに Microsoft Defender for Endpoint を追加します](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution)。
4. [Microsoft Defender ウイルス対策の除外リストに既存のソリューションを追加します](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus)。
5. [既存のソリューションを Microsoft Defender for Endpoint の除外リストに追加します](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-for-endpoint)。
6. [デバイス グループ、デバイス コレクション、および組織単位を設定します](#set-up-your-device-groups-device-collections-and-organizational-units)。
7. [マルウェア対策ポリシーとリアルタイム保護を構成します](#configure-antimalware-policies-and-real-time-protection)。

## <a name="enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode"></a>Microsoft Defender ウイルス対策を有効にし、パッシブ モードの状態を確認する

Windows Server などの特定のバージョンの Windows では、McAfee ソリューションのインストール時に Microsoft Defender ウイルス対策がアンインストールまたは無効になっている可能性があります。 これは、Microsoft Defender ウイルス対策は、McAfee などのサードパーティのウイルス対策製品をインストールするときにパッシブ モードまたは無効モードに入らないためです。 (この詳細については、「Microsoft Defender ウイルス対策の互換性 [」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。

移行プロセスのこの手順には、次のタスクが含まれます。
- [Windows Server で DisableAntiSpyware を false に設定する](#set-disableantispyware-to-false-on-windows-server)
- [Windows Server での Microsoft Defender ウイルス対策の再インストール](#reinstall-microsoft-defender-antivirus-on-windows-server)。
- [Windows Server で Microsoft Defender ウイルス対策をパッシブ モードに設定する](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)
- [Windows クライアント デバイスで Microsoft Defender ウイルス対策を有効にする](#enable-microsoft-defender-antivirus-on-your-windows-client-devices)。そして
- [Microsoft Defender ウイルス対策がパッシブ モードに設定されているのを確認します](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode)。  

### <a name="set-disableantispyware-to-false-on-windows-server"></a>Windows Server で DisableAntiSpyware を false に設定する

[DisableAntiSpyware](https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)レジストリ キーは、Microsoft Defender ウイルス対策を無効にし、McAfee などの別のウイルス対策製品を展開するために、過去に使用されています。 一般に、Windows デバイスとエンドポイントにこのレジストリ キーを持つ必要があります。ただし、構成済みの場合は、その値を false `DisableAntiSpyware` に設定する方法を次に示します。

1. Windows Server デバイスで、[レジストリ エディター] を開きます。
2. `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` に移動します。
3. そのフォルダーで **、DisableAntiSpyware** という DWORD エントリを探します。
   - そのエントリが表示されない場合は、すべて設定されます。
   - **DisableAntiSpyware が表示された場合は、** 手順 4 に進みます。
4. DisableAntiSpyware DWORD を右クリックし、[変更] を **選択します**。
5. に値を設定します `0` 。 (レジストリ キーの値を false に *設定します*。)

> [!TIP]
> このレジストリ キーの詳細については [、「DisableAntiSpyware」を参照してください](https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)。

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Windows Server に Microsoft Defender ウイルス対策を再インストールする

> [!NOTE]
> 次の手順は、次のバージョンの Windows を実行しているエンドポイントまたはデバイスにのみ適用されます。
> - Windows Server 2019
> - Windows Server バージョン 1803 (コア専用モード)
> - Windows Server 2016

1. エンドポイントまたはデバイスのローカル管理者として、デバイスを開Windows PowerShell。
2. 次の PowerShell コマンドレットを実行します。 <br/>   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <br/>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender` <br/>
   > [!NOTE]
   > PS を実行しているタスク シーケンス内で DISM コマンドを使用する場合は、次のパスを使用cmd.exe必要です。
   > 例:<br/>
   > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<br/>
   > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>
3. Microsoft Defender ウイルス対策が実行されているを確認するには、次の PowerShell コマンドレットを使用します。 <br/>
   `Get-Service -Name windefend`

#### <a name="are-you-using-windows-server-2016"></a>Windows Server 2016 を使用していますか?

Windows Server 2016 を使用している場合に Microsoft Defender ウイルス対策の有効化に問題がある場合は、次の PowerShell コマンドレットを使用します。

`mpcmdrun -wdenable`

> [!TIP]
> さらにサポートが必要な場合 「Microsoft [Defender Antivirus on Windows Server」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-on-windows-server-2016)。

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Windows Server で Microsoft Defender ウイルス対策をパッシブ モードに設定する

組織は既存のエンドポイント保護ソリューションを引き続き使用していますので、Microsoft Defender Antivirus をパッシブ モードに設定する必要があります。 そうすることで、既存のソリューションと Microsoft Defender Antivirus は、Microsoft Defender for Endpoint へのオンボーディングが完了するまで、並べて実行できます。

1. レジストリ エディターを開き、次に移動します。 <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.
2. **ForceDefenderPassiveMode** という DWORD エントリを編集 (または作成) し、次の設定を指定します。
   - DWORD の値を **1 に設定します**。
   - [基本 **] で**、[16 進数] **を選択します**。

> [!NOTE]
> 他のメソッドを使用して、次のようなレジストリ キーを設定できます。
>- [グループ ポリシーの基本設定](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [ローカル グループ ポリシー オブジェクト ツール](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Configuration Manager のパッケージ](https://docs.microsoft.com/mem/configmgr/apps/deploy-use/packages-and-programs)

### <a name="enable-microsoft-defender-antivirus-on-your-windows-client-devices"></a>Windows クライアント デバイスで Microsoft Defender ウイルス対策を有効にする

組織が Microsoft 以外のウイルス対策ソリューションを使用している場合、Microsoft Defender Antivirus は組織の Windows デバイスで無効になっている可能性が最も高い。 移行プロセスのこの手順では、Microsoft Defender ウイルス対策を有効にする必要があります。 

Microsoft Defender ウイルス対策を有効にするには、Intune を使用することをお勧めします。 ただし、次の表に示すメソッドを使用できます。

|メソッド  |操作  |
|---------|---------|
|[Intune](https://docs.microsoft.com/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**注**: Intune は現在 Microsoft エンドポイント マネージャーです。 |1. Microsoft Endpoint Manager 管理センターに [移動し、](https://go.microsoft.com/fwlink/?linkid=2109431) サインインします。<br/>2. [**デバイス**  >  **構成プロファイル] を選択** し、構成するプロファイルの種類を選択します。 デバイス制限プロファイルの種類をまだ作成していない場合、または新しいデバイス制限の種類を作成する場合は[、「Microsoft Intune](https://docs.microsoft.com/intune/device-restrictions-configure)でデバイス制限設定を構成する」を参照してください。<br/>3. [プロパティ] **を選択** し、[構成設定: **編集] を選択します**。<br/>4. **[Microsoft Defender ウイルス対策] を展開します**。 <br/>5. クラウド **による保護を有効にする**。<br/>6. [サンプル申請の前にユーザー **に確認** する] ドロップダウンで、[すべてのサンプルを **自動的に送信する] を選択します**。<br/>7. [望ましくない可能性 **のあるアプリケーションの** 検出] ドロップダウンで、[有効にする] または [**監査] を****選択します**。<br/>8. [確認] **+ [保存] を選択** し、[保存] を **選択します**。<br/>**ヒント**: Intune デバイス プロファイルの詳細 (設定の作成および構成方法など)については、「Microsoft Intune デバイス プロファイルとは」 [を参照してください](https://docs.microsoft.com/intune/device-profiles)。|
|Windows のコントロール パネル     |ここでのガイダンスに従います [。Microsoft Defender ウイルス対策を有効にする](https://docs.microsoft.com/mem/intune/user-help/turn-on-defender-windows)。 <br/>**注**: 一部の *バージョンの* Windows では *、Microsoft Defender ウイルス* Windows Defender代わりにウイルス対策ソフトウェアが表示される場合があります。        |
|[高度なグループ ポリシーの管理](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) <br/>or<br/>[グループ ポリシー管理コンソール](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  |1. [コンピューターの構成 **]**  >  **[管理用テンプレート**  >  **] Windows コンポーネント Microsoft** Defender Antivirus  >  **に移動します**。 <br/>2. [Microsoft Defender ウイルス対策を無効にする] という **ポリシーを探します**。<br/>3. [ポリシー **設定の編集] を選択** し、ポリシーが無効になっているか確認します。 これにより、Microsoft Defender ウイルス対策が有効です。 <br/>**注**: 一部の *バージョンの* Windows では *、Microsoft Defender ウイルス* Windows Defender代わりにウイルス対策ソフトウェアが表示される場合があります。 |

### <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode"></a>Microsoft Defender ウイルス対策がパッシブ モードにあるか確認する

Microsoft Defender ウイルス対策をパッシブ モードに設定すると、既存のエンドポイント保護ソリューションと共に実行できます。 次の表で説明するように、コマンド プロンプトまたは PowerShell を使用してこのタスクを実行できます。

|メソッド  |操作  |
|---------|---------|
|コマンド プロンプト     |1. Windows デバイスで、管理者としてコマンド プロンプトを開きます。 <br/>2. と `sc query windefend` 入力し、Enter キーを押します。<br/>3. 結果を確認して、Microsoft Defender Antivirus がパッシブ モードで実行されているのを確認します。         |
|PowerShell     |1. Windows デバイスで、管理者としてWindows PowerShellを開きます。<br/>2. [Get-MpComputerStatus コマンドレットを実行](https://docs.microsoft.com/powershell/module/defender/Get-MpComputerStatus) します。 <br/>3. 結果の一覧で **、AMRunningMode: パッシブ** モードまたは **AMRunningMode: SxS パッシブ** モードのいずれかを探します。          |

> [!NOTE]
> 一部の *バージョンの* Windows では *、Microsoft Defender ウイルス* Windows Defender代わりにウイルス対策ソフトウェアが表示される場合があります。

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策の更新プログラムを取得する

Microsoft Defender ウイルス対策をパッシブ モードで実行している場合でも、新しいマルウェアや攻撃の手法から保護するために必要な最新のテクノロジと機能をデバイスに提供するには、Microsoft Defender ウイルス対策を最新の状態に保つことが [重要です](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。

Microsoft Defender ウイルス対策を最新の状態に保つことに関連する更新プログラムには、次の 2 種類があります。
- セキュリティ インテリジェンスの更新プログラム
- 製品の更新

更新プログラムを取得するには、「Microsoft Defender ウイルス対策の更新プログラムの管理」のガイダンスに [従い、ベースラインを適用します](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)。

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution"></a>既存のソリューションの除外リストに Microsoft Defender for Endpoint を追加する

セットアップ プロセスのこの手順では、既存のエンドポイント保護ソリューションおよび組織が使用している他のセキュリティ製品の除外リストに Microsoft Defender for Endpoint を追加します。 

> [!TIP]
> 除外の構成に関するヘルプについては、ソリューション プロバイダーのドキュメントを参照してください。

構成する特定の除外は、実行しているエンドポイントまたはデバイスの Windows のバージョンによって異なるので、次の表に示します。

|OS |除外 |
|--|--|
|- Windows 10 [バージョン 1803](https://docs.microsoft.com/windows/release-health/status-windows-10-1803) 以降 [(Windows 10](https://docs.microsoft.com/windows/release-health/release-information)リリース情報を参照)<br/>- [KB4493441](https://support.microsoft.com/help/4493441)がインストールされている Windows 10 バージョン[1703 または 1709](https://docs.microsoft.com/windows/release-health/status-windows-10-1709) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server バージョン 1803](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/>  |
|- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <br/>- [Windows 7](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/>**注**: 監視ホスト一時ファイル 6\45 は、番号が異なるサブフォルダーを指定できます。<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策の除外リストに既存のソリューションを追加する

セットアップ プロセスのこの手順では、既存のソリューションを Microsoft Defender ウイルス対策除外リストに追加します。 

Microsoft Defender ウイルス対策 [スキャンに除外を追加する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)場合は、パスとプロセスの除外を追加する必要があります。 次の点に注意してください。
- パスの除外は、特定のファイルと、それらのファイルにアクセスするファイルを除外します。
- プロセスの除外は、プロセスが触れたものも除外しますが、プロセス自体は除外しません。
- 各実行可能ファイル (.exe) をパスの除外とプロセスの除外の両方として一覧表示すると、プロセスと、その実行可能ファイルに触れるものは除外されます。
- 完全なパスを使用してプロセスの除外をリストし、その名前でのみリストします。 (名前専用メソッドの安全性が低い)。

次の表に示す通り、いくつかの方法から除外を Microsoft Defender ウイルス対策に追加できます。

|メソッド | 操作|
|--|--|
|[Intune](https://docs.microsoft.com/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**注**: Intune は現在 Microsoft エンドポイント マネージャーです。 |1. Microsoft Endpoint Manager 管理センターに [移動し、](https://go.microsoft.com/fwlink/?linkid=2109431) サインインします。<br/>2. [**デバイス**  >  **構成プロファイル] を選択** し、構成するプロファイルを選択します。<br/>3. [管理] **で、[** プロパティ] を **選択します**。 <br/>4. [構成設定 **: 編集] を選択します**。<br/>5. **[Microsoft Defender ウイルス** 対策] を展開し **、[Microsoft Defender ウイルス対策の除外] を展開します**。<br/>6. Microsoft Defender ウイルス対策スキャンから除外するファイルとフォルダー、拡張機能、およびプロセスを指定します。 詳細については [、「Microsoft Defender ウイルス対策の除外」を参照してください](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)。<br/>7. [確認] **+ [保存] を選択** し、[保存] を **選択します**。  |
|[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/) |1. [Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/servers/manage/admin-console)コンソールを使用して、[アセットとコンプライアンス エンドポイント保護マルウェア対策ポリシー] に移動し、変更するポリシー  >    >  を選択します。 <br/>2. Microsoft Defender ウイルス対策スキャンから除外するファイルとフォルダー、拡張機能、およびプロセスの除外設定を指定します。 |
|[グループ ポリシー オブジェクト](https://docs.microsoft.com/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. グループ ポリシー管理コンピューターで、グループ [](https://technet.microsoft.com/library/cc731212.aspx)ポリシー管理コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。<br/>2. グループ ポリシー管理 **エディターで、[** コンピューターの構成] に移動し **、[管理用** テンプレート] **をクリックします**。<br/>3. ツリーを **Windows** コンポーネントの  >  **Microsoft Defender ウイルス対策除外に**  >  **展開します**。<br/>**注**: 一部の *バージョンの* Windows では *、Microsoft Defender ウイルス* Windows Defender代わりにウイルス対策ソフトウェアが表示される場合があります。<br/>4. [パスの除外] **設定を** ダブルクリックし、除外を追加します。<br/>- オプションを [有効] に **設定します**。<br/>- [オプション] **セクションで** 、[ **表示.... をクリックします**。<br/>- [値名] 列の下に、各フォルダー **を独自の行に指定** します。<br/>- ファイルを指定する場合は、ドライブ文字、フォルダー パス、ファイル名、拡張子など、ファイルへの完全修飾パスを入力してください。 [値 **] 列に「0」****と入力** します。<br/>5. **[OK] をクリックします**。<br/>6. [拡張機能の除外] **設定をダブルクリック** し、除外を追加します。<br/>- オプションを [有効] に **設定します**。<br/>- [オプション] **セクションで** 、[ **表示.... をクリックします**。<br/>- [値の名前] 列の下に、それぞれのファイル拡張子 **を独自の行に入力** します。  [値 **] 列に「0」****と入力** します。<br/>7. **[OK] をクリックします**。 |
|ローカル グループ ポリシー オブジェクト |1. エンドポイントまたはデバイスで、ローカル グループ ポリシー エディターを開きます。 <br/>2. [コンピューターの **構成] [**  >  **管理用テンプレート**]  >  **[Windows コンポーネント**  >  **] [Microsoft Defender ウイルス対策**  >  **の除外] に移動します**。 <br/>**注**: 一部の *バージョンの* Windows では *、Microsoft Defender ウイルス* Windows Defender代わりにウイルス対策ソフトウェアが表示される場合があります。<br/>3. パスとプロセスの除外を指定します。 |
|レジストリ キー |1. 次のレジストリ キーをエクスポートします `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` 。<br/>2. レジストリ キーをインポートします。 次に、2 つの例を紹介します。<br/>- ローカル パス: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- ネットワーク共有: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-for-endpoint"></a>既存のソリューションを Microsoft Defender for Endpoint の除外リストに追加する

エンドポイント用 Microsoft Defender に除外を追加するには、インジケーターを [作成します](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators#create-indicators-for-files)。

1. Microsoft Defender セキュリティ センター ( ) に移動 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) し、サインインします。
2. ナビゲーション ウィンドウで、[設定ルールインジケーター]  >  **を**  >  **選択します**。
3.  [ファイル ハッシュ **] タブで、[** インジケーターの追加] **を選択します**。
4. [インジケーター **] タブ** で、次の設定を指定します。
   - ファイル ハッシュ (ヘルプが必要ですか? この [記事の「CMPivot を使用してファイル ハッシュを検索](#find-a-file-hash-using-cmpivot) する」を参照してください。
   - [ **有効期限が切れる ] (UTC) で、[しない]** を **選択します**。
5. [アクション] **タブ** で、次の設定を指定します。
   - **応答アクション**: **許可**
   - タイトルと説明
6. [スコープ **] タブの**[デバイス グループ **]** で、[スコープ内のすべてのデバイス] または [リストから **選択] を選択します**。
7. [概要 **] タブで** 設定を確認し、[保存] を **クリックします**。

### <a name="find-a-file-hash-using-cmpivot"></a>CMPivot を使用してファイル ハッシュを検索する

CMPivot は、Configuration Manager のコンソール内ユーティリティです。 CMPivot は、環境内のデバイスのリアルタイム状態へのアクセスを提供します。 ターゲット コレクション内の現在接続されているデバイスすべてでクエリをすぐに実行し、結果を返します。 詳細については [、「CMPivot の概要」を参照してください](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot-overview)。

CMPivot を使用してファイル ハッシュを取得するには、次の手順を実行します。

1. 前提条件を [確認します](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot#prerequisites)。
2. [CMPivot を起動します](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot#start-cmpivot)。 
3. Configuration Manager ( ) に接続します `SCCM_ServerName.DomainName.com` 。
4. [クエリ] **タブを選択** します。
5. [デバイスコレクション **] リストで** 、[すべてのシステム] **(既定) を選択します**。
6. クエリ ボックスに、次のクエリを入力します。<br/>

   ```kusto
   File(c:\\windows\\notepad.exe)
   | project Hash
   ```
   
   > [!NOTE]
   > 上記のクエリで、サードパーティ *notepad.exe* 製品プロセス名に置き換える必要があります。 

## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>デバイス グループ、デバイス コレクション、および組織単位を設定する

| コレクションの種類 | 操作 |
|--|--|
|[デバイス グループ](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups) (以前はコンピューター グループと呼ばば) を使用すると、セキュリティ運用チームは、自動調査や修復などのセキュリティ機能を構成できます。<br/> デバイス グループは、セキュリティ運用チームが必要に応じて修復アクションを実行できるよう、これらのデバイスへのアクセスを割り当てる場合にも役立ちます。 <br/>デバイス グループは、Microsoft Defender セキュリティ センターで作成されます。 |1. Microsoft Defender セキュリティ センター ( ) に移動します [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 。<br/>2. 左側のナビゲーション ウィンドウで、[設定] [アクセス許可  >  **] [デバイス グループ]**  >  **を選択します**。  <br/>3. **[+ デバイス グループの追加] を選択します**。<br/>4. デバイス グループの名前と説明を指定します。<br/>5. [オートメーション レベル **] ボックスの一覧** で、オプションを選択します。 (Full - **脅威を自動的に修復することをお勧めします**。)さまざまなオートメーション レベルの詳細については、「脅威を修復する方法 [」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)。<br/>6. 一致するルールの条件を指定して、デバイス グループに属するデバイスを特定します。 たとえば、ドメイン、OS のバージョンを選択したり、デバイス タグを [使用することもできます](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags)。 <br/>7. [ユーザー アクセス **] タブ** で、デバイス グループに含まれるデバイスにアクセスできる役割を指定します。 <br/>8. [完了] **を選択します**。 |
|[デバイス コレクションを使用](https://docs.microsoft.com/mem/configmgr/core/clients/manage/collections/introduction-to-collections) すると、セキュリティ運用チームは、アプリケーションの管理、コンプライアンス設定の展開、または組織内のデバイスへのソフトウェア更新プログラムのインストールを行えます。 <br/>デバイス コレクションは、Configuration Manager を使用 [して作成されます](https://docs.microsoft.com/mem/configmgr/)。 |「コレクションを作成する [」の手順に従います](https://docs.microsoft.com/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create)。 |
|[組織単位](https://docs.microsoft.com/azure/active-directory-domain-services/create-ou) を使用すると、ユーザー アカウント、サービス アカウント、コンピューター アカウントなどのオブジェクトを論理的にグループ化できます。 その後、管理者を特定の組織単位に割り当て、グループ ポリシーを適用して対象の構成設定を適用できます。<br/> 組織単位は Azure [Active Directory ドメイン サービスで定義されます](https://docs.microsoft.com/azure/active-directory-domain-services)。 | 「Azure Active Directory Domain Services マネージ ドメインで組織単位を作成する [」の手順に従います](https://docs.microsoft.com/azure/active-directory-domain-services/create-ou)。 |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>マルウェア対策ポリシーとリアルタイム保護を構成する

Configuration Manager とデバイス コレクションを使用して、マルウェア対策ポリシーを構成します。
- 「Configuration [Manager でエンドポイント保護用のマルウェア対策ポリシーを作成して展開する」を参照してください](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)。
- マルウェア対策ポリシーを作成して構成する場合は、リアルタイムの保護設定を確認[](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings)し、一目でブロック[を有効にします](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)。

> [!TIP]
> オンボーディング時に組織のデバイスの前にポリシーを展開できます。

## <a name="next-step"></a>次の手順

**おめでとう** ございます! Microsoft Defender for Endpoint への切り替えの [セットアップ フェーズが完了しました](switch-to-microsoft-defender-migration.md#the-migration-process)。

- [フェーズ 3: エンドポイント用 Microsoft Defender にオンボードするに進む](switch-to-microsoft-defender-onboard.md)
