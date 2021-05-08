---
title: Symantec to Microsoft Defender for Endpoint - フェーズ 2, セットアップ
description: これは、シマンテックから Microsoft Defender for Endpoint への移行のフェーズ 2 セットアップです。
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 32ed277c87f5cca1a286cc24549dc331774cf03b
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245734"
---
# <a name="migrate-from-symantec---phase-2-set-up-microsoft-defender-for-endpoint"></a>Symantec からの移行 - フェーズ 2: エンドポイント用 Microsoft Defender のセットアップ

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![フェーズ 1: 準備](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)<br/>[フェーズ 1: 準備](symantec-to-microsoft-defender-atp-prepare.md) |![フェーズ 2: 設定](images/phase-diagrams/setup.png)<br/>フェーズ 2: 設定 |[![フェーズ 3: オンボード](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[フェーズ 3: オンボード](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
||*お前はここにいる!* | |


**Symantec から [Microsoft Defender](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)** for Endpoint への移行のセットアップ フェーズへようこそ。 このフェーズには、次の手順が含まれます。
1. [(特定のバージョンのMicrosoft Defender ウイルス対策) を有効または再インストールWindowsします](#enable-or-reinstall-microsoft-defender-antivirus-for-certain-versions-of-windows)。
2. [[Microsoft Defender ウイルス対策を有効にする] をクリックします](#enable-microsoft-defender-antivirus)。
3. [ユーザーの更新プログラムを取得Microsoft Defender ウイルス対策。](#get-updates-for-microsoft-defender-antivirus)
4. [エンドポイント用 Microsoft Defender を Symantec の除外リストに追加します](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-symantec)。
5. [シマンテックを削除の除外リストに追加Microsoft Defender ウイルス対策。](#add-symantec-to-the-exclusion-list-for-microsoft-defender-antivirus)
6. [エンドポイント用 Microsoft Defender の除外リストにシマンテックを追加します](#add-symantec-to-the-exclusion-list-for-microsoft-defender-for-endpoint)。
7. [デバイス グループ、デバイス コレクション、および組織単位を設定します](#set-up-your-device-groups-device-collections-and-organizational-units)。
8. [マルウェア対策ポリシーとリアルタイム保護を構成します](#configure-antimalware-policies-and-real-time-protection)。

## <a name="enable-or-reinstall-microsoft-defender-antivirus-for-certain-versions-of-windows"></a>有効または再インストールMicrosoft Defender ウイルス対策 (特定のバージョンのサーバー Windows)

> [!TIP]
> このタスクを実行Windows 10、このタスクを実行する必要があります。 [有効にする **[] に進Microsoft Defender ウイルス対策。](#enable-microsoft-defender-antivirus)**

特定のバージョンのWindows、Microsoft Defender ウイルス対策または無効になっている可能性があります。 これは、シマンテックMicrosoft Defender ウイルス対策サードパーティのウイルス対策製品をインストールしても、パッシブ モードまたは無効モードに入らないためです。 詳細については、「互換性[Microsoft Defender ウイルス対策」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。 

Symantec から Microsoft Defender for Endpoint に移行する前に、デバイスを有効または再インストールし、パッシブ モードMicrosoft Defender ウイルス対策する必要があります。 

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>サーバー Microsoft Defender ウイルス対策再インストールWindowsする

> [!NOTE]
> 次の手順は、次のバージョンのデバイスを実行しているエンドポイントまたはデバイスにのみ適用Windows。
> - Windows Server 2019
> - Windowsサーバーバージョン 1803 (コア専用モード)
> - Windows Server 2016
> 
> Microsoft Defender ウイルス対策はWindows 10組み込みですが、無効になっている可能性があります。 この場合は、[有効にする][に進Microsoft Defender ウイルス対策。](#enable-microsoft-defender-antivirus)

1. エンドポイントまたはデバイスのローカル管理者として、サーバーを開Windows PowerShell。

1. 次の PowerShell コマンドレットを実行します。<br/>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <br/>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`

    > [!NOTE]
    > PS を実行しているタスク シーケンス内で DISM コマンドを使用する場合は、次のパスを使用cmd.exe必要です。
    > 例:<br/>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<br/>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. 実行中のMicrosoft Defender ウイルス対策確認するには、次の PowerShell コマンドレットを使用します。 <br/>
   `Get-Service -Name windefend`

#### <a name="are-you-using-windows-server-2016"></a>アプリを使用Windows Server 2016?

サーバーを使用している場合Windows Server 2016有効にMicrosoft Defender ウイルス対策 PowerShell コマンドレットを使用します。

`mpcmdrun -wdenable`

> [!TIP]
> さらにヘルプが必要ですか? [「Microsoft Defender ウイルス対策と 2019 Windows Server 2016」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-on-windows-server-2016)。

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>サーバー Microsoft Defender ウイルス対策パッシブ モードに設定Windowsする

組織で引き続きシマンテックを使用している場合は、パッシブ モードMicrosoft Defender ウイルス対策設定する必要があります。 そうすることで、Symantec と Microsoft Defender ウイルス対策は、Microsoft Defender for Endpoint へのオンボーディングが完了するまで、並べて実行できます。

1. レジストリ エディターを開き、次に移動します。 <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. **ForceDefenderPassiveMode** という DWORD エントリを編集 (または作成) し、次の設定を指定します。
   - DWORD の値を **1 に設定します**。
   - [基本 **] で**、[16 進数] **を選択します**。

> [!NOTE]
> 他のメソッドを使用して、次のようなレジストリ キーを設定できます。
>- [グループ ポリシーの基本設定](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [ローカル グループ ポリシー オブジェクト ツール](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Configuration Manager のパッケージ](/mem/configmgr/apps/deploy-use/packages-and-programs)

## <a name="enable-microsoft-defender-antivirus"></a>[有効Microsoft Defender ウイルス対策

組織はプライマリ ウイルス対策ソリューションとして Symantec を使用していますので、Microsoft Defender ウイルス対策は組織のデバイスでWindowsされます。 移行プロセスのこの手順では、移行を有効Microsoft Defender ウイルス対策。 

アプリを有効Microsoft Defender ウイルス対策 Intune を使用することをお勧めします。 ただし、次の表に示すメソッドを使用できます。

|メソッド  |操作  |
|---------|---------|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**メモ**: Intune がMicrosoft エンドポイント マネージャー。 |1. 管理センター Microsoft エンドポイント マネージャー[に移動し、](https://go.microsoft.com/fwlink/?linkid=2109431)サインインします。<br/><br/>2. [**デバイス**  >  **構成プロファイル] を選択** し、構成するプロファイルの種類を選択します。 まだデバイス制限プロファイルの種類を作成していない場合、または新しいデバイス制限の種類を作成する場合は、「デバイス制限の設定を構成する」を参照[Microsoft Intune。](/intune/device-restrictions-configure)<br/><br/>3. [プロパティ] **を選択** し、[構成設定: **編集] を選択します**。<br/><br/>4. [Microsoft Defender ウイルス対策]**を展開します**。 <br/><br/>5. クラウド **による保護を有効にする**。<br/><br/>6. [サンプル申請の前にユーザー **に確認** する] ドロップダウンで、[すべてのサンプルを **自動的に送信する] を選択します**。<br/><br/>7. [望ましくない可能性 **のあるアプリケーションの** 検出] ドロップダウンで、[有効にする] または [**監査] を****選択します**。<br/><br/>8. [確認] **+ [保存] を選択** し、[保存] を **選択します**。<br/>Intune デバイス プロファイルの作成および構成方法など、Intune デバイス プロファイルの詳細については、「デバイス プロファイルのMicrosoft Intune[参照してください](/intune/device-profiles)。|
|コントロール パネル (Windows     |ここでのガイダンスに従います[。[電源を入Microsoft Defender ウイルス対策。](/mem/intune/user-help/turn-on-defender-windows) <br/>**注**: 一部のバージョン *の**Windows Defender ウイルス対策のMicrosoft Defender ウイルス対策* の代わりに、Windows。        |
|[高度なグループ ポリシーの管理](/microsoft-desktop-optimization-pack/agpm/) <br/>または<br/>[グループ ポリシー管理コンソール](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  |1. に移動します `Computer configuration > Administrative templates > Windows components > Microsoft Defender Antivirus` 。 <br/><br/>2. [オフにする] というポリシーを探 **Microsoft Defender ウイルス対策。**<br/><br/>3. [ポリシー **設定の編集] を選択** し、ポリシーが無効になっているか確認します。 これにより、Microsoft Defender ウイルス対策。 <br/><br/>**注**: 一部のバージョン *の**Windows Defender ウイルス対策のMicrosoft Defender ウイルス対策* の代わりに、Windows。 |

### <a name="verify-that-microsoft-defender-antivirus-is-in-passive-mode"></a>パッシブ モードMicrosoft Defender ウイルス対策確認する

Microsoft Defender ウイルス対策モードに設定すると、シマンテックとMicrosoft Defender ウイルス対策実行できます。 次の表で説明するように、コマンド プロンプトまたは PowerShell を使用してこのタスクを実行できます。

|メソッド  |操作  |
|---------|---------|
|コマンド プロンプト     |1. デバイスでWindowsとしてコマンド プロンプトを開きます。 <br/><br/>2. と `sc query windefend` 入力し、Enter キーを押します。<br/><br/>3. 結果を確認して、Microsoft Defender ウイルス対策モードで実行されている状態を確認します。         |
|PowerShell     |1. デバイスでWindows管理者としてWindows PowerShell開きます。<br/><br/>2. [Get-MpComputerStatus コマンドレットを実行](/powershell/module/defender/Get-MpComputerStatus) します。<br/> <br/>3. 結果の一覧で **、AMRunningMode: パッシブ** モードまたは **AMRunningMode: SxS パッシブ** モードのいずれかを探します。|

> [!NOTE]
> 一部の *バージョンWindows Defender ウイルス対策* では、Microsoft Defender ウイルス対策の *代* わりにWindows。

## <a name="get-updates-for-microsoft-defender-antivirus"></a>ユーザーの更新プログラムを取得Microsoft Defender ウイルス対策

Microsoft Defender ウイルス対策モードで実行されている場合でも、新しいマルウェアや攻撃の手法から保護するために必要な最新のテクノロジと機能をデバイスに提供するには、最新のMicrosoft Defender ウイルス対策を維持する必要[があります](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。

更新プログラムには、最新の状態を維持Microsoft Defender ウイルス対策 2 種類があります。
- セキュリティ インテリジェンスの更新プログラム
- 製品の更新

更新プログラムを取得するには、「更新プログラムの管理」のガイダンス[にMicrosoft Defender ウイルス対策ベースラインを適用します](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)。

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-symantec"></a>Symantec の除外リストに Microsoft Defender for Endpoint を追加する

セットアップ プロセスのこの手順では、Microsoft Defender for Endpoint をシマンテック社および組織が使用している他のセキュリティ製品の除外リストに追加します。 構成する特定の除外は、エンドポイントまたはデバイスWindowsのバージョンによって異なるので、次の表に示します。

|OS |除外 |
|--|--|
|- Windows 10バージョン[1803](/windows/release-health/status-windows-10-1803)以降 (リリース[情報Windows 10参照](/windows/release-health/release-information))<br/>- [kb4493441](https://support.microsoft.com/help/4493441)がインストールされている Windows 10バージョン 1703 または 1709 <br/>- [WindowsServer 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windowsサーバー、バージョン 1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/><br/>  |
|- [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <br/><br/>- [Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/><br/>- [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/><br/>- [Windows Server 2012R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/><br/>- [WindowsServer 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/><br/>**注**: 監視ホスト一時ファイル 6\45 は、番号が異なるサブフォルダーを指定できます。<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-symantec-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>アプリケーションの除外リストにシマンテックを追加Microsoft Defender ウイルス対策

セットアップ プロセスのこの手順では、Symantec と他のセキュリティ ソリューションを[除外リストMicrosoft Defender ウイルス対策追加します。 

> [!NOTE]
> 除外するプロセスとサービスの詳細については、「Broadcom's Processes and services used by Endpoint Protection [14 」 を参照してください](https://knowledge.broadcom.com/external/article/170706/processes-and-services-used-by-endpoint.html)。

スキャンに除外[を追加するMicrosoft Defender ウイルス対策パス](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)とプロセスの除外を追加する必要があります。 次の点に注意してください。
- パスの除外は、特定のファイルと、それらのファイルにアクセスするファイルを除外します。
- プロセスの除外は、プロセスが触れたものも除外しますが、プロセス自体は除外しません。
- 各実行可能ファイル (.exe) をパスの除外とプロセスの除外の両方として一覧表示すると、プロセスと、その実行可能ファイルが触れるものは除外されます。
- 完全なパスを使用してプロセスの除外をリストし、その名前でのみリストします。 (名前専用メソッドの安全性が低い)。

次の表に示す通り、いくつかの方法から除外Microsoft Defender ウイルス対策を追加できます。

|メソッド | 操作|
|--|--|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**メモ**: Intune がMicrosoft エンドポイント マネージャー。 |1. 管理センター Microsoft エンドポイント マネージャー[に移動し、](https://go.microsoft.com/fwlink/?linkid=2109431)サインインします。<br/><br/>2. [**デバイス**  >  **構成プロファイル] を選択** し、構成するプロファイルを選択します。<br/><br/>3. [管理] **で、[** プロパティ] を **選択します**。 <br/><br/>4. [構成設定 **: 編集] を選択します**。<br/><br/>5. [除外 **Microsoft Defender ウイルス対策]** を展開し、[除外Microsoft Defender ウイルス対策 **展開します**。<br/><br/>6. スキャンから除外するファイルとフォルダー、拡張機能、およびプロセスMicrosoft Defender ウイルス対策します。 参照については、「除外[Microsoft Defender ウイルス対策参照してください](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)。<br/><br/>7. [確認] **+ [保存] を選択** し、[保存] を **選択します**。  |
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/) |1. [Configuration Manager](/mem/configmgr/core/servers/manage/admin-console)コンソールを使用して、[アセットとコンプライアンス Endpoint Protectionマルウェア対策ポリシー] に移動し、変更  >  **する** ポリシー  >  を選択します。 <br/><br/>2. ファイルとフォルダー、拡張機能、およびプロセスの除外設定を指定して、スキャンから除外Microsoft Defender ウイルス対策します。 |
|[グループ ポリシー オブジェクト](/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. グループ ポリシー管理コンピューターで、グループ [](https://technet.microsoft.com/library/cc731212.aspx)ポリシー管理コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。<br/><br/>2. グループ ポリシー管理 **エディターで、[** コンピューターの構成] に移動し **、[管理用** テンプレート] **をクリックします**。<br/><br/>3. ツリーを展開して **、除外Windowsコンポーネント> Microsoft Defender ウイルス対策 >します**。<br/>**注**: 一部のバージョン *の**Windows Defender ウイルス対策のMicrosoft Defender ウイルス対策* の代わりに、Windows。<br/><br/>4. [パスの除外] **設定を** ダブルクリックし、除外を追加します。<br/><br/>- オプションを [有効] に **設定します**。<br/><br/>- [オプション] **セクションで** 、[ **表示.... をクリックします**。<br/><br/>- [値名] 列の下に、各フォルダー **を独自の行に指定** します。<br/><br/>- ファイルを指定する場合は、ドライブ文字、フォルダー パス、ファイル名、拡張子など、ファイルへの完全修飾パスを入力してください。 [値 **] 列に「0」****と入力** します。<br/><br/>5. **[OK] をクリックします**。<br/><br/>6. [拡張機能の除外] **設定をダブルクリック** し、除外を追加します。<br/><br/>- オプションを [有効] に **設定します**。<br/><br/>- [オプション] **セクションで** 、[ **表示.... をクリックします**。<br/><br/>- [値の名前] 列の下に、それぞれのファイル拡張子 **を独自の行に入力** します。  [値 **] 列に「0」****と入力** します。<br/>7. **[OK] をクリックします**。 |
|ローカル グループ ポリシー オブジェクト |1. エンドポイントまたはデバイスで、ローカル グループ ポリシー エディターを開きます。 <br/><br/>2. [コンピューター構成 **]**[管理用テンプレート] Windows  >    >  **除外Microsoft Defender ウイルス対策**  >    >  **移動します**。 <br/>**注**: 一部のバージョン *の**Windows Defender ウイルス対策のMicrosoft Defender ウイルス対策* の代わりに、Windows。<br/><br/>3. パスとプロセスの除外を指定します。 |
|レジストリ キー |1. 次のレジストリ キーをエクスポートします `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` 。<br/><br/>2. レジストリ キーをインポートします。 次に、2 つの例を紹介します。<br/>- ローカル パス: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- ネットワーク共有: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

## <a name="add-symantec-to-the-exclusion-list-for-microsoft-defender-for-endpoint"></a>エンドポイント用 Microsoft Defender の除外リストにシマンテックを追加する

エンドポイント用 Microsoft Defender に除外を追加するには、インジケーターを [作成します](/microsoft-365/security/defender-endpoint/manage-indicators#create-indicators-for-files)。

1. [パスワード] ( ) にMicrosoft Defender セキュリティ センター [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) し、サインインします。

1. ナビゲーション ウィンドウで、[ルールインジケーター]**設定**  >  **選択**  >  **します**。

1.  [ファイル ハッシュ **] タブで、[** インジケーターの追加] **を選択します**。

1. [インジケーター **] タブ** で、次の設定を指定します。
   - ファイル ハッシュ (ヘルプが必要ですか? この [記事の「CMPivot を使用してファイル ハッシュを検索](#find-a-file-hash-using-cmpivot) する」を参照してください。
   - [ **有効期限が切れる ] (UTC) で、[しない]** を **選択します**。
   
1. [アクション] **タブ** で、次の設定を指定します。
   - **応答アクション**: **許可**
   - タイトルと説明

1. [スコープ **] タブの**[デバイス グループ **]** で、[スコープ内のすべてのデバイス] または [リストから **選択] を選択します**。

1. [概要 **] タブで** 設定を確認し、[保存] を **クリックします**。

### <a name="find-a-file-hash-using-cmpivot"></a>CMPivot を使用してファイル ハッシュを検索する

CMPivot は、Configuration Manager のコンソール内ユーティリティです。 CMPivot は、環境内のデバイスのリアルタイム状態へのアクセスを提供します。 ターゲット コレクション内の現在接続されているデバイスすべてでクエリをすぐに実行し、結果を返します。 詳細については [、「CMPivot の概要」を参照してください](/mem/configmgr/core/servers/manage/cmpivot-overview)。

CMPivot を使用してファイル ハッシュを取得するには、次の手順を実行します。

1. 前提条件を [確認します](/mem/configmgr/core/servers/manage/cmpivot#prerequisites)。<br/>

2. [CMPivot を起動します](/mem/configmgr/core/servers/manage/cmpivot#start-cmpivot)。 

3. Connectマネージャー ( ) にアクセスします `SCCM_ServerName.DomainName.com` 。

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
|[デバイス グループ](/microsoft-365/security/defender-endpoint/machine-groups) (以前はコンピューター グループと呼ばば) を使用すると、セキュリティ運用チームは、自動調査や修復などのセキュリティ機能を構成できます。<br/> デバイス グループは、セキュリティ運用チームが必要に応じて修復アクションを実行できるよう、これらのデバイスへのアクセスを割り当てる場合にも役立ちます。 <br/>デバイス グループは、デバイス グループMicrosoft Defender セキュリティ センター。 |1. [ ] ( ) のMicrosoft Defender セキュリティ センター移動 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) します。<br/><br/>2. 左側のナビゲーション ウィンドウで、[アクセス許可  >  **設定] を**  >  **選択します**。  <br/><br/>3. **[+ デバイス グループの追加] を選択します**。<br/><br/>4. デバイス グループの名前と説明を指定します。<br/><br/>5. [オートメーション レベル **] ボックスの一覧** で、オプションを選択します。 (Full - **脅威を自動的に修復することをお勧めします**。)さまざまなオートメーション レベルの詳細については、「脅威を修復する方法 [」を参照してください](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)。<br/><br/>6. 一致するルールの条件を指定して、デバイス グループに属するデバイスを特定します。 たとえば、ドメイン、OS のバージョンを選択したり、デバイス タグを [使用することもできます](/microsoft-365/security/defender-endpoint/machine-tags)。<br/> <br/>7. [ユーザー アクセス **] タブ** で、デバイス グループに含まれるデバイスにアクセスできる役割を指定します。 <br/><br/>8. [完了] **を選択します**。 |
|[デバイス コレクションを使用](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) すると、セキュリティ運用チームは、アプリケーションの管理、コンプライアンス設定の展開、または組織内のデバイスへのソフトウェア更新プログラムのインストールを行えます。 <br/>デバイス コレクションは、Configuration Manager を使用 [して作成されます](/mem/configmgr/)。 |「コレクションを作成する [」の手順に従います](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create)。 |
|[組織単位](/azure/active-directory-domain-services/create-ou) を使用すると、ユーザー アカウント、サービス アカウント、コンピューター アカウントなどのオブジェクトを論理的にグループ化できます。 その後、管理者を特定の組織単位に割り当て、グループ ポリシーを適用して対象の構成設定を適用できます。<br/> 組織単位は、ドメイン サービス[Azure Active Directory定義されます](/azure/active-directory-domain-services)。 | 「組織単位を作成する」の手順に従って、ドメイン Azure Active Directory[ドメインを作成します](/azure/active-directory-domain-services/create-ou)。 |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>マルウェア対策ポリシーとリアルタイム保護を構成する

Configuration Manager とデバイス コレクションを使用して、マルウェア対策ポリシーを構成します。

- Configuration [Manager の「マルウェア対策ポリシーの作成と展開Endpoint Protection」を参照してください](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)。

- マルウェア対策ポリシーを作成して構成する場合は、リアルタイムの保護設定を確認[](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings)し、一目でブロック[を有効にします](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)。

> [!TIP]
> オンボーディング時に組織のデバイスの前にポリシーを展開できます。

## <a name="next-step"></a>次の手順

**おめでとう** ございます! Symantec から Microsoft Defender for Endpoint への移行の [セットアップ フェーズが完了しました](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)。
- [フェーズ 3: エンドポイント用 Microsoft Defender にオンボードするに進む](symantec-to-microsoft-defender-atp-onboard.md)
