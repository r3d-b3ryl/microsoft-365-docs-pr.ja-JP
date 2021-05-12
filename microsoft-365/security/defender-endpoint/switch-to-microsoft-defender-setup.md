---
title: エンドポイント用 Microsoft Defender に切り替える - セットアップ
description: フェーズ 2、セットアップ プロセス(Microsoft Defender for Endpoint に切り替える場合)。
keywords: 移行、Microsoft Defender for Endpoint、edr、Windows Defender
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
ms.date: 05/10/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 1047d39c70e230e2765f82da4d687b36c4719b3e
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327466"
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
5. [デバイス グループ、デバイス コレクション、および組織単位を設定します](#set-up-your-device-groups-device-collections-and-organizational-units)。
6. [マルウェア対策ポリシーとリアルタイム保護を構成します](#configure-antimalware-policies-and-real-time-protection)。

## <a name="enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode"></a>Microsoft Defender ウイルス対策を有効にし、パッシブ モードの状態を確認する

Windows Server などの特定のバージョンの Windows では、McAfee ソリューションのインストール時に Microsoft Defender ウイルス対策がアンインストールまたは無効になっている可能性があります。 エンドポイントを Defender for Endpoint にオンボードする準備が整った場合、Microsoft Defender Antivirus はパッシブ モードまたは無効モードに自動的には入らない。 また、Windows Server では、Microsoft Defender ウイルス対策をアクティブ モードにし、Microsoft 以外のウイルス対策/マルウェア対策ソリューション (マカフィー、シマンテックなど) と共に使用することはできません。 Defender for Endpoint およびウイルス対策ソリューションの詳細については、「Microsoft Defender ウイルス対策の互換性」 [を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。

Microsoft Defender ウイルス対策が有効でパッシブ モードで有効になっているのを確認するには、この記事で説明する次のタスクを実行します。
- [Windows Server で DisableAntiSpyware を false に設定する](#set-disableantispyware-to-false-on-windows-server)
- [Windows Server での Microsoft Defender ウイルス対策の再インストール](#reinstall-microsoft-defender-antivirus-on-windows-server)。
- [Windows Server で Microsoft Defender ウイルス対策をパッシブ モードに設定する](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)
- [Windows クライアント デバイスで Microsoft Defender ウイルス対策を有効にする](#enable-microsoft-defender-antivirus-on-your-windows-client-devices)。そして
- [Microsoft Defender ウイルス対策がパッシブ モードに設定されているのを確認します](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode)。  

### <a name="set-disableantispyware-to-false-on-windows-server"></a>Windows Server で DisableAntiSpyware を false に設定する

[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)レジストリ キーは、Microsoft Defender ウイルス対策を無効にし、McAfee などの別のウイルス対策製品を展開するために、過去に使用されています。 一般に、Windows デバイスとエンドポイントにこのレジストリ キーを持つ必要があります。ただし、構成済みの場合は、その値を false `DisableAntiSpyware` に設定する方法を次に示します。

1. Windows Server デバイスで、[レジストリ エディター] を開きます。

2. `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` に移動します。

3. そのフォルダーで **、DisableAntiSpyware** という DWORD エントリを探します。
   - そのエントリが表示されない場合は、すべて設定されます。
   - **DisableAntiSpyware が表示された場合は、** 手順 4 に進みます。

4. DisableAntiSpyware DWORD を右クリックし、[変更] を **選択します**。

5. に値を設定します `0` 。 (このアクションは、レジストリ キーの値を false に *設定* します。)

> [!TIP]
> このレジストリ キーの詳細については [、「DisableAntiSpyware」を参照してください](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)。

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Windows Server に Microsoft Defender ウイルス対策を再インストールする

> [!NOTE]
> 次の手順は、次のバージョンの Windows を実行しているエンドポイントまたはデバイスにのみ適用されます。
> - Windows Server 2019
> - Windows Server バージョン 1803 (コア専用モード)
> - Windows Server 2016 [(「Windows Server 2016](#are-you-using-windows-server-2016)を使用していますか」の重要な情報を参照してください)

1. エンドポイントまたはデバイスのローカル管理者として、デバイスを開Windows PowerShell。

2. 次の PowerShell コマンドレットを実行します。 <br/>   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <p>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender` <br/>
 
    > [!NOTE]
    > PS を実行しているタスク シーケンス内で DISM コマンドを使用する場合は、次のパスを使用cmd.exe必要です。
    > 例:<br/>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<p>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. Microsoft Defender ウイルス対策が実行されているを確認するには、次の PowerShell コマンドレットを使用します。 <br/>
   `Get-Service -Name windefend`

#### <a name="are-you-using-windows-server-2016"></a>Windows Server 2016 を使用していますか?

Windows Server 2016 を実行しているエンドポイントがある場合は、Microsoft 以外のウイルス対策/マルウェア対策ソリューションと共に Microsoft Defender ウイルス対策を実行できません。 Microsoft Defender ウイルス対策は、Windows Server 2016 のパッシブ モードでは実行できません。 この場合は、Microsoft 以外のウイルス対策/マルウェア対策ソリューションをアンインストールし、代わりに Microsoft Defender ウイルス対策をインストール/有効化する必要があります。 詳細については、「Defender [for Endpoint とのウイルス対策ソリューションの互換性」を参照してください](microsoft-defender-antivirus-compatibility.md)。

Windows Server 2016 を使用している場合に Microsoft Defender ウイルス対策の有効化に問題がある場合は、次の PowerShell コマンドレットを使用します。

`mpcmdrun -wdenable`

> [!TIP]
> さらにサポートが必要な場合 「Microsoft [Defender Antivirus on Windows Server」を参照してください](microsoft-defender-antivirus-on-windows-server.md)。

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Windows Server で Microsoft Defender ウイルス対策をパッシブ モードに設定する

> [!IMPORTANT]
> Windows Server、バージョン 1803 以降、または Windows Server 2019 では、Microsoft Defender ウイルス対策をパッシブ モードに設定できます。 ただし、Windows Server 2016 ではパッシブ モードはサポートされていません。 詳細については [、「Microsoft Defender for Endpoint とのウイルス対策ソリューションの互換性」を参照してください](defender-compatibility.md)。

組織は既存のエンドポイント保護ソリューションを引き続き使用していますので、Microsoft Defender Antivirus をパッシブ モードに設定する必要があります。 そうすることで、既存のソリューションと Microsoft Defender Antivirus は、Microsoft Defender for Endpoint へのオンボーディングが完了するまで、並べて実行できます。

1. レジストリ エディターを開き、次に移動します。 <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. **ForcePassiveMode** という DWORD エントリを編集 (または作成) し、次の設定を指定します。
   - DWORD の値を **1 に設定します**。
   - [基本 **] で**、[16 進数] **を選択します**。

> [!NOTE]
> 他のメソッドを使用して、次のようなレジストリ キーを設定できます。
>- [グループ ポリシーの基本設定](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [ローカル グループ ポリシー オブジェクト ツール](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Configuration Manager のパッケージ](/mem/configmgr/apps/deploy-use/packages-and-programs)

### <a name="enable-microsoft-defender-antivirus-on-your-windows-client-devices"></a>Windows クライアント デバイスで Microsoft Defender ウイルス対策を有効にする

組織が Microsoft 以外のウイルス対策ソリューションを使用している場合、Microsoft Defender Antivirus は組織の Windows デバイスで無効になっている可能性が最も高い。 移行プロセスのこの手順では、Microsoft Defender ウイルス対策を有効にする必要があります。 

Microsoft Defender ウイルス対策を有効にするには、Intune を使用することをお勧めします。 ただし、次の表に示すメソッドを使用できます。

|メソッド  |操作  |
|---------|---------|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**注**: Intune は現在 Microsoft エンドポイント マネージャーです。 | 1. Microsoft Endpoint Manager 管理センターに [移動し、](https://go.microsoft.com/fwlink/?linkid=2109431) サインインします。<p> 2. [**デバイス**  >  **構成プロファイル] を選択** し、構成するプロファイルの種類を選択します。 デバイス制限プロファイルの種類をまだ作成していない場合、または新しいデバイス制限の種類を作成する場合は[、「Microsoft Intune](/intune/device-restrictions-configure)でデバイス制限設定を構成する」を参照してください。<p> 3. [プロパティ] **を選択** し、[構成設定: **編集] を選択します**。<p> 4. **[Microsoft Defender ウイルス対策] を展開します**。 <p> 5. クラウド **による保護を有効にする**。<p> 6. [サンプル申請の前にユーザー **に確認** する] ドロップダウンで、[すべてのサンプルを **自動的に送信する] を選択します**。<p> 7. [望ましくない可能性 **のあるアプリケーションの** 検出] ドロップダウンで、[有効にする] または [**監査] を****選択します**。<p> 8. [確認] **+ [保存] を選択** し、[保存] を **選択します**。<p>**ヒント**: Intune デバイス プロファイルの詳細 (設定の作成および構成方法など)については、「Microsoft Intune デバイス プロファイルとは」 [を参照してください](/intune/device-profiles)。|
|Windows のコントロール パネル     |ここでのガイダンスに従います [。Microsoft Defender ウイルス対策を有効にする](/mem/intune/user-help/turn-on-defender-windows)。 <p>**注**: 一部の *バージョンの* Windows では *、Microsoft Defender ウイルス* Windows Defender代わりにウイルス対策ソフトウェアが表示される場合があります。        |
|[高度なグループ ポリシーの管理](/microsoft-desktop-optimization-pack/agpm/) <br/>または<br/>[グループ ポリシー管理コンソール](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  | 1. [コンピューターの構成 **]**  >  **[管理用テンプレート**  >  **] Windows コンポーネント Microsoft** Defender Antivirus  >  **に移動します**。 <p> 2. [Microsoft Defender ウイルス対策を無効にする] という **ポリシーを探します**。<p> 3. [ポリシー **設定の編集] を選択** し、ポリシーが無効になっているか確認します。 このアクションにより、Microsoft Defender ウイルス対策が有効です。 <p>**注**: 一部の *バージョンの* Windows では *、Microsoft Defender ウイルス* Windows Defender代わりにウイルス対策ソフトウェアが表示される場合があります。 |


### <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode"></a>Microsoft Defender ウイルス対策がパッシブ モードにあるか確認する

Microsoft Defender ウイルス対策をパッシブ モードに設定すると、既存のエンドポイント保護ソリューションと共に実行できます。 次の表で説明するように、コマンド プロンプトまたは PowerShell を使用してこのタスクを実行できます。

|メソッド  |操作  |
|---------|---------|
|コマンド プロンプト     | 1. Windows デバイスで、管理者としてコマンド プロンプトを開きます。 <p> 2. と `sc query windefend` 入力し、Enter キーを押します。<p> 3. 結果を確認して、Microsoft Defender Antivirus がパッシブ モードで実行されているのを確認します。         |
|PowerShell     | 1. Windows デバイスで、管理者としてWindows PowerShellを開きます。<p> 2. [Get-MpComputerStatus コマンドレットを実行](/powershell/module/defender/Get-MpComputerStatus) します。 <p> 3. 結果の一覧で **、AMRunningMode: パッシブ** モードまたは **AMRunningMode: SxS パッシブ** モードのいずれかを探します。          |

> [!NOTE]
> 一部の *バージョンの* Windows では *、Microsoft Defender ウイルス* Windows Defender代わりにウイルス対策ソフトウェアが表示される場合があります。

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策の更新プログラムを取得する

Microsoft Defender ウイルス対策をパッシブ モードで実行している場合でも、新しいマルウェアや攻撃の手法から保護するために必要な最新のテクノロジと機能をデバイスに提供するには、Microsoft Defender ウイルス対策を最新の状態に保つことが [重要です](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。

Microsoft Defender ウイルス対策を最新の状態に保つことに関連する更新プログラムには、次の 2 種類があります。
- セキュリティ インテリジェンスの更新プログラム
- 製品の更新

更新プログラムを取得するには、「Microsoft Defender ウイルス対策の更新プログラムの管理」のガイダンスに [従い、ベースラインを適用します](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)。

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution"></a>既存のソリューションの除外リストに Microsoft Defender for Endpoint を追加する

セットアップ プロセスのこの手順では、既存のエンドポイント保護ソリューションおよび組織が使用している他のセキュリティ製品の除外リストに Microsoft Defender for Endpoint を追加します。 

> [!TIP]
> 除外の構成に関するヘルプについては、ソリューション プロバイダーのドキュメントを参照してください。

構成する特定の除外は、実行しているエンドポイントまたはデバイスの Windows のバージョンによって異なるので、次の表に示します。

|OS |除外 |
|--|--|
|- Windows 10 [バージョン 1803](/windows/release-health/status-windows-10-1803) 以降 [(Windows 10](/windows/release-health/release-information)リリース情報を参照)<br/>- [KB4493441](https://support.microsoft.com/help/4493441) がインストールされている Windows 10 バージョン 1703 または 1709 <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server バージョン 1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<p>  |
|- [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <br/>- [Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/>- [Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/>**注**: 監視ホスト一時ファイル 6\45 は、番号が異なるサブフォルダーを指定できます。 <br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策の除外リストに既存のソリューションを追加する

セットアップ プロセスのこの手順では、既存のソリューションを Microsoft Defender ウイルス対策除外リストに追加します。 

Microsoft Defender ウイルス対策 [スキャンに除外を追加する](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)場合は、パスとプロセスの除外を追加する必要があります。 次の点に注意してください。
- パスの除外は、特定のファイルと、それらのファイルにアクセスするファイルを除外します。
- プロセスの除外は、プロセスが触れたものも除外しますが、プロセス自体は除外しません。
- 各実行可能ファイル (.exe) をパスの除外とプロセスの除外の両方として一覧表示すると、プロセスと、その実行可能ファイルが触れるものは除外されます。
- 完全なパスを使用してプロセスの除外をリストし、その名前でのみリストします。 (名前専用メソッドの安全性が低い)。

次の表に示す通り、いくつかの方法から除外を Microsoft Defender ウイルス対策に追加できます。

|メソッド | 操作|
|--|--|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**注**: Intune は現在 Microsoft エンドポイント マネージャーです。 | 1. Microsoft Endpoint Manager 管理センターに [移動し、](https://go.microsoft.com/fwlink/?linkid=2109431) サインインします。<p> 2. [**デバイス**  >  **構成プロファイル] を選択** し、構成するプロファイルを選択します。<p> 3. [管理] **で、[** プロパティ] を **選択します**。<p> 4. [構成設定 **: 編集] を選択します**。<p> 5. **[Microsoft Defender ウイルス** 対策] を展開し **、[Microsoft Defender ウイルス対策の除外] を展開します**。<p> 6. Microsoft Defender ウイルス対策スキャンから除外するファイルとフォルダー、拡張機能、およびプロセスを指定します。 詳細については [、「Microsoft Defender ウイルス対策の除外」を参照してください](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)。<p> 7. [確認] **+ [保存] を選択** し、[保存] を **選択します**。  |
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/) | 1. [Configuration Manager](/mem/configmgr/core/servers/manage/admin-console)コンソールを使用して、[アセットとコンプライアンス エンドポイント保護マルウェア対策ポリシー] に移動し、変更するポリシー  >    >  を選択します。 <p> 2. Microsoft Defender ウイルス対策スキャンから除外するファイルとフォルダー、拡張機能、およびプロセスの除外設定を指定します。 |
|[グループ ポリシー オブジェクト](/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. グループ ポリシー管理コンピューターで、グループ [](https://technet.microsoft.com/library/cc731212.aspx)ポリシー管理コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。<p> 2. グループ ポリシー管理 **エディターで、[** コンピューター **の構成** ] に移動し、[管理用 **テンプレート] を選択します**。<p> 3. ツリーを Microsoft Defender ウイルス対策と除外> **Windows コンポーネント>展開します**。<br/>**注**: 一部の *バージョンの* Windows では *、Microsoft Defender ウイルス* Windows Defender代わりにウイルス対策ソフトウェアが表示される場合があります。<p> 4. [パスの除外] **設定を** ダブルクリックし、除外を追加します。<br/>- オプションを [有効] に **設定します**。<br/>- [オプション]**セクションで****、[Show.... を選択します**。<br/>- [値名] 列の下に、各フォルダー **を独自の行に指定** します。<br/>- ファイルを指定する場合は、ドライブ文字、フォルダー パス、ファイル名、拡張子など、ファイルへの完全修飾パスを入力してください。 [値 **] 列に「0」****と入力** します。<p> 5. **[OK] を選択します**。<p> 6. [拡張機能の除外] **設定をダブルクリック** し、除外を追加します。<br/>- オプションを [有効] に **設定します**。<br/>- [オプション]**セクションで****、[Show.... を選択します**。<br/>- [値の名前] 列の下に、それぞれのファイル拡張子 **を独自の行に入力** します。  [値 **] 列に「0」****と入力** します。<p> 7. **[OK] を選択します**。 |
|ローカル グループ ポリシー オブジェクト |1. エンドポイントまたはデバイスで、ローカル グループ ポリシー エディターを開きます。 <p>2. [コンピューターの **構成] [**  >  **管理用テンプレート**]  >  **[Windows コンポーネント**  >  **] [Microsoft Defender ウイルス対策**  >  **の除外] に移動します**。<p>**注**: 一部の *バージョンの* Windows では *、Microsoft Defender ウイルス* Windows Defender代わりにウイルス対策ソフトウェアが表示される場合があります。<p>3. パスとプロセスの除外を指定します。 |
|レジストリ キー |1. 次のレジストリ キーをエクスポートします `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` 。<p>2. レジストリ キーをインポートします。 次に、2 つの例を紹介します。<br/>- ローカル パス: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- ネットワーク共有: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>デバイス グループ、デバイス コレクション、および組織単位を設定する

| コレクションの種類 | 操作 |
|--|--|
|[デバイス グループ](/microsoft-365/security/defender-endpoint/machine-groups) (以前はコンピューター グループと呼ばば) を使用すると、セキュリティ運用チームは、自動調査や修復などのセキュリティ機能を構成できます。<br/> デバイス グループは、セキュリティ運用チームが必要に応じて修復アクションを実行できるよう、これらのデバイスへのアクセスを割り当てる場合にも役立ちます。 <br/>デバイス グループは、デバイス グループMicrosoft Defender セキュリティ センター。 |1. [ ] ( ) のMicrosoft Defender セキュリティ センター移動 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) します。<p>2. 左側のナビゲーション ウィンドウで、[アクセス許可  >  **設定] を**  >  **選択します**。  <p>3. **[+ デバイス グループの追加] を選択します**。<p>4. デバイス グループの名前と説明を指定します。<p>5. [オートメーション レベル **] ボックスの一覧** で、オプションを選択します。 (Full - **脅威を自動的に修復することをお勧めします**。)さまざまなオートメーション レベルの詳細については、「脅威を修復する方法 [」を参照してください](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)。<p>6. 一致するルールの条件を指定して、デバイス グループに属するデバイスを特定します。 たとえば、ドメイン、OS のバージョンを選択したり、デバイス タグを [使用することもできます](/microsoft-365/security/defender-endpoint/machine-tags)。<p>7. [ユーザー アクセス **] タブ** で、デバイス グループに含まれるデバイスにアクセスできる役割を指定します。 <p>8. [完了] **を選択します**。 |
|[デバイス コレクションを使用](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) すると、セキュリティ運用チームは、アプリケーションの管理、コンプライアンス設定の展開、または組織内のデバイスへのソフトウェア更新プログラムのインストールを行えます。<br/>デバイス コレクションは、Configuration Manager を使用 [して作成されます](/mem/configmgr/)。 |「コレクションを作成する [」の手順に従います](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create)。 |
|[組織単位](/azure/active-directory-domain-services/create-ou) を使用すると、ユーザー アカウント、サービス アカウント、コンピューター アカウントなどのオブジェクトを論理的にグループ化できます。 その後、管理者を特定の組織単位に割り当て、グループ ポリシーを適用して対象の構成設定を適用できます。<br/> 組織単位は、ドメイン サービス[Azure Active Directory定義されます](/azure/active-directory-domain-services)。 | 「組織単位を作成する」の手順に従って、ドメイン Azure Active Directory[ドメインを作成します](/azure/active-directory-domain-services/create-ou)。 |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>マルウェア対策ポリシーとリアルタイム保護を構成する

Configuration Manager とデバイス コレクションを使用して、マルウェア対策ポリシーを構成します。
- Configuration [Manager の「マルウェア対策ポリシーの作成と展開Endpoint Protection」を参照してください](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)。
- マルウェア対策ポリシーを作成して構成する場合は、リアルタイムの保護設定を確認[](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings)し、一目でブロック[を有効にします](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)。

> [!TIP]
> オンボーディング時に組織のデバイスの前にポリシーを展開できます。

## <a name="next-step"></a>次の手順

**おめでとう** ございます! Microsoft Defender for Endpoint への切り替えの [セットアップ フェーズが完了しました](switch-to-microsoft-defender-migration.md#the-migration-process)。

- [フェーズ 3: エンドポイント用 Microsoft Defender にオンボードするに進む](switch-to-microsoft-defender-onboard.md)
