---
title: '[設定] にMicrosoft Defender for Endpoint - セットアップ'
description: Defender for Endpoint に切り替えます。 セットアップ プロセスを確認します。これには、セットアップ プロセスのインストールMicrosoft Defender ウイルス対策。
keywords: 移行、Microsoft Defender for Endpoint、ウイルス対策、パッシブ モード、セットアップ プロセス
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
ms.topic: article
ms.custom: migrationguides
ms.date: 04/01/2022
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 5dd5c78c366a708104b4662be86d71056d6a726a
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64632713"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-2-setup"></a>[設定] Microsoft Defender for Endpoint - フェーズ 2: セットアップに切り替えます。

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![フェーズ 1: 準備します。](images/phase-diagrams/prepare.png#lightbox)](switch-to-mde-phase-1.md)<br/>[フェーズ 1: 準備](switch-to-mde-phase-1.md)|![フェーズ 2: セットアップ。](images/phase-diagrams/setup.png#lightbox)<br/>フェーズ 2: 設定|[![フェーズ 3: Onboard3。](images/phase-diagrams/onboard.png#lightbox)](switch-to-mde-phase-3.md)<br/>[フェーズ 3: オンボード](switch-to-mde-phase-3.md)|
|---|---|---|
||*お前はここにいる!*||

**Defender [for Endpoint への切り替えのセットアップ フェーズへようこそ](switch-to-mde-overview.md#the-migration-process)**。 このフェーズには、次の手順が含まれます。

1. [エンドポイント上のMicrosoft Defender ウイルス対策/有効にする](#reinstallenable-microsoft-defender-antivirus-on-your-endpoints)。
2. [エンドポイントの Defender を構成します](#configure-defender-for-endpoint)。
3. [既存のソリューションの除外リストに Defender for Endpoint を追加します](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution)。
4. [既存のソリューションを、既存のソリューションの除外リストに追加Microsoft Defender ウイルス対策](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus)。
5. [デバイス グループ、デバイス コレクション、および組織単位を設定します](#set-up-your-device-groups-device-collections-and-organizational-units)。

## <a name="reinstallenable-microsoft-defender-antivirus-on-your-endpoints"></a>エンドポイントの再インストールMicrosoft Defender ウイルス対策有効にする

特定のバージョンの WindowsではMicrosoft Defender ウイルス対策 Microsoft 以外のウイルス対策/マルウェア対策ソリューションがインストールされている場合、ユーザーがアンインストールまたは無効になっている可能性があります。 アプリケーションを実行しているWindows Defender for Endpoint にオンボードされている場合、Microsoft Defender ウイルス対策 Microsoft 以外のウイルス対策ソリューションと共にパッシブ モードで実行できます。 詳細については、「Defender [for Endpoint によるウイルス対策保護」を参照してください](microsoft-defender-antivirus-compatibility.md#antivirus-protection-without-defender-for-endpoint)。

Defender for Endpoint に切り替える場合は、特定の手順を実行して、エンドポイントを再インストールまたは有効にする必要Microsoft Defender ウイルス対策。 次の表では、クライアントとサーバーで実行Windows説明します。

|エンドポイントの種類|操作|
|---|---|
|Windowsクライアント (エンドポイントが実行されているエンドポイントWindows 10、Windows 11)|一般に、クライアントに対して何もWindowsする必要はありません (Microsoft Defender ウイルス対策がアンインストールされていない限り)。 一般に、Microsoft Defender ウイルス対策インストールする必要がありますが、移行プロセスのこの時点で無効になっている可能性が最も高い。 <br/><br/> Microsoft 以外のウイルス対策/マルウェア対策ソリューションがインストールされ、クライアントがまだ Defender for Endpoint にオンボードされていない場合、Microsoft Defender ウイルス対策は自動的に無効になります。 その後、クライアント エンドポイントが Defender for Endpoint にオンボードされている場合、それらのエンドポイントが Microsoft 以外のウイルス対策ソリューションを実行している場合、Microsoft Defender ウイルス対策パッシブ モードになります。 <br/><br/> Microsoft 以外のウイルス対策ソリューションがアンインストールされた場合、Microsoft Defender ウイルス対策アクティブ モードに切り替わります。|
|Windows サーバー|サーバー Windows、サーバーを再インストールしMicrosoft Defender ウイルス対策パッシブ モードに手動で設定する必要があります。 サーバー Windows、Microsoft 以外のウイルス対策/マルウェア対策がインストールされている場合、Microsoft Defender ウイルス対策 Microsoft 以外のウイルス対策ソリューションと一緒に実行することはできません。 このような場合は、手動Microsoft Defender ウイルス対策またはアンインストールされます。 <br/><br/> サーバーでサーバーを再Microsoft Defender ウイルス対策またはWindowsするには、次のタスクを実行します。 <br/>- [インストール時Microsoft Defender ウイルス対策再インストールWindows Server 2016](#re-enable-microsoft-defender-antivirus-on-windows-server-2016)<br/>- [サーバー Microsoft Defender ウイルス対策バージョン 1803 以降Windowsに再インストールする](#re-enable-microsoft-defender-antivirus-on-windows-server-version-1803-or-later)<br/>- [サーバー Microsoft Defender ウイルス対策パッシブ モードに設定Windowsする](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server) <br/><br/>Windows Server での Microsoft Defender ウイルス対策 の再インストールまたは再有効化に関する問題が発生した場合は、「トラブルシューティング: Microsoft Defender ウイルス対策 が Windows Server でアンインストール[される」を参照](switch-to-mde-troubleshooting.md#microsoft-defender-antivirus-is-getting-uninstalled-on-windows-server)してください。|

> [!TIP]
> Microsoft 以外のウイルス対策保護をMicrosoft Defender ウイルス対策状態の詳細については、「互換性」を参照Microsoft Defender ウイルス対策[してください](microsoft-defender-antivirus-compatibility.md)。

### <a name="re-enable-microsoft-defender-antivirus-on-windows-server-2016"></a>サーバー上でMicrosoft Defender ウイルス対策を再Windows Server 2016

マルウェア保護ツール ユーティリティ[をCommand-Lineして](command-line-arguments-microsoft-defender-antivirus.md)、マルウェア保護を有効Microsoft Defender ウイルス対策再Windows Server 2016。

1. サーバーのローカル管理者として、コマンド プロンプトを開きます。

2. 次のコマンドを実行します。`MpCmdRun.exe -wdenable`

3. デバイスを再起動します。

### <a name="re-enable-microsoft-defender-antivirus-on-windows-server-version-1803-or-later"></a>バージョン 1803 以降Microsoft Defender ウイルス対策サーバー Windowsを再び有効にする

> [!IMPORTANT]
> 次の手順は、次のバージョンのデバイスを実行しているエンドポイントまたはデバイスにのみWindows。
> - Windows Server 2022
> - Windows Server 2019
> - Windows サーバー バージョン 1803 (コア専用モード)

1. サーバーのローカル管理者として、サーバーを開Windows PowerShell。

2. Windows PowerShell コマンドレットを実行します。

   ```powershell
   # For Windows Server 2016
   Dism /online /Enable-Feature /FeatureName:Windows-Defender-Features
   Dism /online /Enable-Feature /FeatureName:Windows-Defender
   Dism /online /Enable-Feature /FeatureName:Windows-Defender-Gui
   # For Windows Server 2019 and Windows Server 2022
   Dism /online /Enable-Feature /FeatureName:Windows-Defender
   ```

   PowerShell を実行しているタスク シーケンス内で DISM コマンドを使用する場合は、次のパスを使用cmd.exe必要です。
   例:

   ```powershell
   c:\windows\sysnative\cmd.exe /c Dism /online /Enable-Feature /FeatureName:Windows-Defender-Features
   c:\windows\sysnative\cmd.exe /c Dism /online /Enable-Feature /FeatureName:Windows-Defender
   ```

3. デバイスを再起動します。

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>サーバー Microsoft Defender ウイルス対策パッシブ モードに設定Windowsする

> [!TIP]
> これで、R2 Microsoft Defender ウイルス対策 2016 でパッシブ モードWindows Server 2012実行できます。 詳細については、「[Microsoft Defender for Endpoint をインストールするためのオプション](configure-server-endpoints.md#options-to-install-the-microsoft-defender-for-endpoint-packages)」 を参照してください。

1. レジストリ エディターを開き、に移動します `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`。

2. **ForceDefenderPassiveMode** という DWORD エントリを編集 (または作成) し、次の設定を指定します。

   - DWORD の値を **1 に設定します**。

   - [基本 **] で**、[16 進数] **を選択します**。

> [!NOTE]
> Defender for Endpoint にオンボーディングした後、サーバー上で Microsoft Defender ウイルス対策パッシブ モードに設定するWindowsがあります。 パッシブ モードが予想通り設定された状態を検証するには、**Microsoft-Windows-Windows Defender** 操作ログ (`C:\Windows\System32\winevt\Logs`に位置) でイベント *5007* を検索し、**ForceDefenderPassiveMode** レジストリ キーまたは **PassiveMode** レジストリ キーが 0x1 に設定された **状態** を確認します。

### <a name="are-you-using-windows-server-2012-r2-or-windows-server-2016"></a>Windows Server 2012 R2 または Windows Server 2016 を使用していますか?

上記の方法を使用Microsoft Defender ウイルス対策 R2 および 2016 のパッシブ モードでWindows Server 2012を実行できます。 詳細については、「[Microsoft Defender for Endpoint をインストールするためのオプション](configure-server-endpoints.md#options-to-install-the-microsoft-defender-for-endpoint-packages)」 を参照してください。

## <a name="configure-defender-for-endpoint"></a>Android 機能用に Microsoft Defender for Endpoint を構成する

移行プロセスのこの手順では、エンドポイントのMicrosoft Defender ウイルス対策構成します。 次のIntune使用することをお勧めします。ただし、次の表に示すメソッドを使用できます。

|メソッド|操作|
|---|---|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/><br/> **注**: Intuneは、現在、Microsoft エンドポイント マネージャー。|1. 管理センター Microsoft エンドポイント マネージャー[に移動し、](https://go.microsoft.com/fwlink/?linkid=2109431)サインインします。<br/><br/>2. [ **デバイス構成プロファイル** \> **] を選択** し、構成するプロファイルの種類を選択します。 まだデバイス制限プロファイルの種類を作成していない場合、または新しいデバイス制限を作成する場合は、「デバイス制限の設定を構成する」を参照[Microsoft Intune。](/intune/device-restrictions-configure)<br/><br/>3. [プロパティ] **を選択** し、[構成設定: **編集] を選択します。**<br/><br/>4. [Microsoft Defender ウイルス対策] **を展開します**。<br/><br/>5. クラウド **による保護を有効にする**。<br/><br/>6. [サンプル申請の前にユーザー **に確認** する] ドロップダウンで、[すべてのサンプルを **自動的に送信する] を選択します**。<br/><br/>7. [望ましくない **可能性があるアプリケーションを** 検出する] ドロップダウンで、[有効にする] または [**監査] を****選択します**。<br/><br/>8. [確認] **+ [保存] を選択** し、[保存] を **選択します**。 <br/><br/> **ヒント**: デバイス プロファイルの作成Intune構成方法など、デバイス プロファイルの詳細については、「デバイス プロファイルとはMicrosoft Intune [参照してください](/intune/device-profiles)。|
|Microsoft Endpoint Configuration Manager|「[マルウェア対策ポリシーを作成して展開する」を参照Endpoint ProtectionをConfiguration Manager](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)。 <br/><br/> マルウェア対策ポリシーを作成して構成する場合は、リアルタイムの保護設定を確認[](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings)し、一目でブロック[を有効にしてください](configure-block-at-first-sight-microsoft-defender-antivirus.md)。
|コントロール パネルのWindows|ここでのガイダンスに従います。[[電源を入Microsoft Defender ウイルス対策](/mem/intune/user-help/turn-on-defender-windows)。 (一部のバージョン *では**Windows Defender ウイルス対策のMicrosoft Defender ウイルス対策* が表示される場合Windows)。|
|[高度なグループ ポリシーの管理](/microsoft-desktop-optimization-pack/agpm/) <br/><br/> or <br/><br/> [グループ ポリシー管理コンソール](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)|1. [コンピューター構成 **] [** \> **管理用テンプレート] Windows** \> **に移動Microsoft Defender ウイルス対策** \> **。**<br/><br/>2. [オフにする] というポリシーを探 **Microsoft Defender ウイルス対策。**<br/><br/>3. [ポリシー **設定の編集] を選択** し、ポリシーが無効になっているか確認します。 このアクションを使用すると、Microsoft Defender ウイルス対策。 <br/>(一部のバージョン *では**Windows Defender ウイルス対策のMicrosoft Defender ウイルス対策* が表示される場合Windows)。|

> [!TIP]
> 組織のデバイスがオンボードされる前にポリシーを展開できます。

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution"></a>既存Microsoft Defender for Endpointの除外リストに追加する

セットアップ プロセスのこの手順では、既存のエンドポイント保護ソリューションおよび組織が使用している他のセキュリティ製品の除外リストに Defender for Endpoint を追加します。

> [!TIP]
> 除外の構成に関するヘルプについては、ソリューション プロバイダーのドキュメントを参照してください。

構成する特定の除外は、エンドポイントまたはデバイスWindowsのバージョンによって異なるので、次の表に示します。
<br/><br/>

| OS |除外 |
|:--|:--|
|Windows 11 <br/><br/>Windows 10バージョン [1803](/windows/release-health/status-windows-10-1803) 以降 (リリース[情報Windows 10参照](/windows/release-health/release-information))<br/><br/>Windows 10バージョン 1703 または 1709 [KB4493441 がインストール](https://support.microsoft.com/help/4493441)されている場合 <br/><br/> Windows Server 2022<br/><br/>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019) <br/><br/>[Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/><br/>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/><br/>[Windows Server バージョン 1803](/windows-server/get-started/whats-new-in-windows-server-1803) | `C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCM.exe`<br/><br/>さらに、Windows Server 2012 R2 および 2016 では、[KB5005292](https://support.microsoft.com/en-us/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac) を使用して Sense EDR コンポーネントを更新した後で、次の除外が必要になります。<br/> <br/> `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\MsSense.exe` <br/><br/>`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\SenseCnCProxy.exe`<br/><br/>`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\SenseIR.exe`<br/><br/>`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\SenseCE.exe`<br/><br/>`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\SenseSampleUploader.exe`<br/><br/>`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\SenseCM.exe` |
|[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/><br/>[Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/><br/>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/><br/>**注**: ホスト一時ファイル 6\45 の監視には、番号が付くサブフォルダーが異なる場合があります。<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>既存のソリューションを、既存のソリューションの除外リストに追加Microsoft Defender ウイルス対策

セットアップ プロセスのこの手順では、既存のソリューションを既定の除外リストMicrosoft Defender ウイルス対策追加します。 次の表に示す通り、複数Microsoft Defender ウイルス対策から除外を追加できます。 

|メソッド|操作|
|---|---|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/><br/> **注**: Intuneは、現在、Microsoft エンドポイント マネージャー。|1. 管理センター Microsoft エンドポイント マネージャー[に移動し、](https://go.microsoft.com/fwlink/?linkid=2109431)サインインします。<br/><br/>2. [ **デバイス構成プロファイル** \> **] を選択** し、構成するプロファイルを選択します。<br/><br/>3. [管理] **で、[** プロパティ] を **選択します**。<br/><br/>4. [構成 **設定: 編集] を選択します**。<br/><br/>5. [除外 **Microsoft Defender ウイルス対策**] を展開し、[除外 **Microsoft Defender ウイルス対策展開します**。<br/><br/>6. スキャンから除外するファイルとフォルダー、拡張機能、およびプロセスMicrosoft Defender ウイルス対策します。 詳細については、「除外[のMicrosoft Defender ウイルス対策参照してください](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)。<br/><br/>7. [確認] **+ [保存] を選択** し、[保存] を **選択します**。|
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/)|1. Configuration Managerコンソール \>  \>を[使用](/mem/configmgr/core/servers/manage/admin-console)して、[アセットとコンプライアンス Endpoint Protection マルウェア対策ポリシー] に移動し、変更するポリシーを選択します。<br/><br/>2. ファイルとフォルダー、拡張機能、およびプロセスの除外設定を指定して、スキャンから除外Microsoft Defender ウイルス対策します。|
|[グループ ポリシー オブジェクト](/previous-versions/windows/desktop/Policy/group-policy-objects)|1. グループ ポリシー管理コンピューターで [、グループ ポリシー](https://technet.microsoft.com/library/cc731212.aspx) 管理コンソールを開き、構成する グループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。<br/><br/>2. [管理エディター] **グループ ポリシー[****コンピューターの構成**] に移動し、[管理用テンプレート **] を選択します**。<br/><br/>3. ツリーを展開して **、除外Windowsコンポーネント\>Microsoft Defender ウイルス対策\>します**。 (一部のバージョン *では**Windows Defender ウイルス対策のMicrosoft Defender ウイルス対策* が表示される場合Windows)。<br/><br/>4. [パスの除外] **設定を** ダブルクリックし、除外を追加します。<br/><br/>5. オプションを [有効] に **設定します**。<br/><br/>6. [オプション] セクション **で** 、[ **表示....] を選択します**。<br/><br/>7. [値の名前] 列の下に、各フォルダーを **独自の行に指定** します。 ファイルを指定する場合は、ドライブ文字、フォルダー パス、ファイル名、拡張子など、ファイルへの完全修飾パスを入力してください。 [値 **] 列に「0****」と入力** します。<br/><br/>8. [OK] を **選択します**。<br/><br/>9. [拡張機能の除外] **設定を** ダブルクリックし、除外を追加します。<br/><br/>10. オプションを [有効] に **設定します**。<br/><br/>11. [オプション] **セクションで** 、[ **表示....] を選択します**。<br/><br/>12. [値名] 列の下に、それぞれのファイル拡張子 **を独自の行に入力** します。 [値 **] 列に「0****」と入力** します。<br/><br/>13. [OK] を **選択します**。|
|ローカル グループ ポリシー オブジェクト|1. エンドポイントまたはデバイスで、ローカル ファイル エディターをグループ ポリシーします。<br/><br/>2. [除外] **の [コンピューター**\>構成 **管理**\>用テンプレート] Windows **コンポーネントMicrosoft Defender ウイルス対策** \>  \> **移動します**。 (一部のバージョン *では**Windows Defender ウイルス対策のMicrosoft Defender ウイルス対策* が表示される場合Windows)。<br/><br/>3. パスとプロセスの除外を指定します。|
|レジストリ キー|1. 次のレジストリ キーをエクスポートします。 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions`<br/><br/>2. レジストリ キーをインポートします。 次に、2 つの例を紹介します。<br/>- ローカル パス: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg`<br/>- ネットワーク共有: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg`|

### <a name="keep-the-following-points-about-exclusions-in-mind"></a>除外に関する以下の点を念頭に置く

スキャンに除外[を追加するMicrosoft Defender ウイルス対策パス](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)とプロセスの除外を追加する必要があります。

次の点に注意してください。

- *パスの除外は* 、特定のファイルと、それらのファイルにアクセスするファイルを除外します。

- *プロセスの除外は* 、プロセスが触れたものも除外しますが、プロセス自体は除外しません。

- 完全なパスを使用してプロセスの除外をリストし、その名前でのみリストします。 (名前専用メソッドの安全性が低い)。

- 各実行可能ファイル (.exe) をパスの除外とプロセスの除外の両方として一覧表示すると、プロセスと、その実行可能ファイルが触れるものは除外されます。

## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>デバイス グループ、デバイス コレクション、および組織単位を設定する

デバイス グループ、デバイス コレクション、組織単位を使用すると、セキュリティ チームはセキュリティ ポリシーを効率的かつ効率的に管理および割り当てできます。 次の表では、これらの各グループと、それらを構成する方法について説明します。 組織では、3 つのコレクションの種類すべてが使用されない場合があります。

|コレクションの種類|操作|
|---|---|
|[デバイス グループ](/microsoft-365/security/defender-endpoint/machine-groups) (以前はコンピューター *グループと呼* ばば) を使用すると、セキュリティ運用チームは、自動調査や修復などのセキュリティ機能を構成できます。 <br/><br/> デバイス グループは、セキュリティ運用チームが必要に応じて修復アクションを実行できるよう、これらのデバイスへのアクセスを割り当てる場合にも役立ちます。 <br/><br/> デバイス グループは、攻撃が検出および停止されている間に、"初期アクセスアラート" などのアラートがトリガーされ、[Microsoft 365 Defender ポータルに表示](/microsoft-365/security/defender/microsoft-365-defender)されます。|1. ポータル () にMicrosoft 365 Defenderします<https://security.microsoft.com>。<br/><br/>2. 左側のナビゲーション ウィンドウで、[エンドポイント **アクセス許可設定** \> **グループ** \> **] を** \> **選択します**。<br/><br/>3. [ **+ デバイス グループの追加] を選択します**。<br/><br/>4. デバイス グループの名前と説明を指定します。<br/><br/>5. [オートメーション レベル **] ボックスの一覧** で、オプションを選択します。 (Full **- 脅威を自動的に修復することをお勧めします**)。さまざまなオートメーション レベルの詳細については、「脅威の修復 [方法」を参照してください](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)。<br/><br/>6. 一致するルールの条件を指定して、デバイス グループに属するデバイスを特定します。 たとえば、ドメイン、OS のバージョンを選択したり、デバイス タグを [使用することもできます](/microsoft-365/security/defender-endpoint/machine-tags)。<br/><br/>7. [ユーザー アクセス **] タブ** で、デバイス グループに含まれるデバイスにアクセスできる役割を指定します。<br/><br/>8. [完了] **を選択します**。|
|[デバイス コレクションを使用](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) すると、セキュリティ運用チームは、アプリケーションの管理、コンプライアンス設定の展開、または組織内のデバイスへのソフトウェア更新プログラムのインストールを行えます。 <br/><br/> デバイス コレクションは、デバイス コレクションを使用[Configuration Manager](/mem/configmgr/)。|「コレクションの作成」 [の手順に従います](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create)。|
|[組織単位](/azure/active-directory-domain-services/create-ou) を使用すると、ユーザー アカウント、サービス アカウント、コンピューター アカウントなどのオブジェクトを論理的にグループ化できます。 <br/><br/> その後、管理者を特定の組織単位に割り当て、グループ ポリシーを適用して対象の構成設定を適用できます。 <br/><br/> 組織単位は、ドメイン サービス[Azure Active Directory定義されます](/azure/active-directory-domain-services)。|「組織単位を[作成する」の手順に従って、Azure Active Directoryドメインに登録します](/azure/active-directory-domain-services/create-ou)。|

## <a name="next-step"></a>次のステップ

**おめでとう** ございます! Defender for Endpoint への切り替えのセットアップ [フェーズが完了しました](switch-to-mde-overview.md#the-migration-process)。

- [フェーズ 3: Defender for Endpoint にオンボードするに進む](switch-to-mde-phase-3.md)
