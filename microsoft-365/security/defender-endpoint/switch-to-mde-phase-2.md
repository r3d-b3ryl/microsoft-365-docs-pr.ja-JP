---
title: Microsoft Defender for Endpointに切り替える - セットアップ
description: Defender for Endpoint に切り替えます。 Microsoft Defender ウイルス対策のインストールを含むセットアップ プロセスを確認します。
keywords: 移行, Microsoft Defender for Endpoint, ウイルス対策, パッシブ モード, セットアップ プロセス
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
# <a name="switch-to-microsoft-defender-for-endpoint---phase-2-setup"></a>Microsoft Defender for Endpoint - フェーズ 2: セットアップに切り替える

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![フェーズ 1: 準備します。](images/phase-diagrams/prepare.png#lightbox)](switch-to-mde-phase-1.md)<br/>[フェーズ 1: 準備](switch-to-mde-phase-1.md)|![フェーズ 2: セットアップします。](images/phase-diagrams/setup.png#lightbox)<br/>フェーズ 2: 設定|[![フェーズ 3: Onboard3。](images/phase-diagrams/onboard.png#lightbox)](switch-to-mde-phase-3.md)<br/>[フェーズ 3: オンボード](switch-to-mde-phase-3.md)|
|---|---|---|
||*お客様はここにいます。*||

**[Defender for Endpoint に切り替える](switch-to-mde-overview.md#the-migration-process)セットアップ フェーズへようこそ**。 このフェーズには、次の手順が含まれます。

1. [エンドポイントでMicrosoft Defender ウイルス対策を再インストール/有効にします](#reinstallenable-microsoft-defender-antivirus-on-your-endpoints)。
2. [Defender for Endpoint を構成します](#configure-defender-for-endpoint)。
3. [既存のソリューションの除外リストに Defender for Endpoint を追加します](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution)。
4. [Microsoft Defender ウイルス対策の除外リストに既存のソリューションを追加します](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus)。
5. [デバイス グループ、デバイス コレクション、および組織単位を設定します](#set-up-your-device-groups-device-collections-and-organizational-units)。

## <a name="reinstallenable-microsoft-defender-antivirus-on-your-endpoints"></a>エンドポイントでのMicrosoft Defender ウイルス対策の再インストール/有効化

特定のバージョンのWindowsでは、Microsoft 以外のウイルス対策/マルウェア対策ソリューションがインストールされたときに、Microsoft Defender ウイルス対策がアンインストールまたは無効になっている可能性があります。 Windowsを実行しているエンドポイントが Defender for Endpoint にオンボードされている場合、Microsoft Defender ウイルス対策は Microsoft 以外のウイルス対策ソリューションと共にパッシブ モードで実行できます。 詳細については、「 [Defender for Endpoint を使用したウイルス対策保護」を参照してください](microsoft-defender-antivirus-compatibility.md#antivirus-protection-without-defender-for-endpoint)。

Defender for Endpoint への切り替えを行う際に、Microsoft Defender ウイルス対策を再インストールまたは有効にするには、特定の手順を実行する必要がある場合があります。 次の表では、Windows クライアントとサーバーで実行する操作について説明します。

|エンドポイントの種類|操作|
|---|---|
|Windows クライアント (Windows 10やWindows 11を実行しているエンドポイントなど)|一般に、Windows クライアントに対してアクションを実行する必要はありません (Microsoft Defender ウイルス対策がアンインストールされていない場合)。 一般に、Microsoft Defender ウイルス対策は引き続きインストールする必要がありますが、移行プロセスのこの時点では無効になっている可能性が高くなります。 <br/><br/> Microsoft 以外のウイルス対策/マルウェア対策ソリューションがインストールされていて、クライアントがまだ Defender for Endpoint にオンボードされていない場合、Microsoft Defender ウイルス対策は自動的に無効になります。 その後、クライアント エンドポイントが Defender for Endpoint にオンボードされると、それらのエンドポイントが Microsoft 以外のウイルス対策ソリューションを実行している場合、Microsoft Defender ウイルス対策パッシブ モードになります。 <br/><br/> Microsoft 以外のウイルス対策ソリューションがアンインストールされると、Microsoft Defender ウイルス対策自動的にアクティブ モードになります。|
|Windows サーバー|Windows Server では、Microsoft Defender ウイルス対策を再インストールし、手動でパッシブ モードに設定する必要があります。 Windows サーバーでは、Microsoft 以外のウイルス対策/マルウェア対策がインストールされている場合、Microsoft Defender ウイルス対策は Microsoft 以外のウイルス対策ソリューションと共に実行できません。 このような場合、Microsoft Defender ウイルス対策は手動で無効またはアンインストールされます。 <br/><br/> Windows Server でMicrosoft Defender ウイルス対策を再インストールまたは有効にするには、次のタスクを実行します。 <br/>- [Windows Server 2016にMicrosoft Defender ウイルス対策を再インストールする](#re-enable-microsoft-defender-antivirus-on-windows-server-2016)<br/>- [Windows Server バージョン 1803 以降でMicrosoft Defender ウイルス対策を再インストールする](#re-enable-microsoft-defender-antivirus-on-windows-server-version-1803-or-later)<br/>- [Windows サーバーでMicrosoft Defender ウイルス対策をパッシブ モードに設定する](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server) <br/><br/>Windows サーバーでのMicrosoft Defender ウイルス対策の再インストールまたは再有効化の問題が発生した場合[は、「トラブルシューティング: Microsoft Defender ウイルス対策がWindows Server でアンインストールされる」を参照してください](switch-to-mde-troubleshooting.md#microsoft-defender-antivirus-is-getting-uninstalled-on-windows-server)。|

> [!TIP]
> Microsoft 以外のウイルス対策保護を使用したMicrosoft Defender ウイルス対策状態の詳細については、「[Microsoft Defender ウイルス対策互換性](microsoft-defender-antivirus-compatibility.md)」を参照してください。

### <a name="re-enable-microsoft-defender-antivirus-on-windows-server-2016"></a>Windows Server 2016でMicrosoft Defender ウイルス対策を再度有効にする

[Malware Protection Command-Line ユーティリティ](command-line-arguments-microsoft-defender-antivirus.md)を使用して、Windows Server 2016でMicrosoft Defender ウイルス対策を再度有効にすることができます。

1. サーバー上のローカル管理者として、コマンド プロンプトを開きます。

2. 次のコマンドを実行します。`MpCmdRun.exe -wdenable`

3. デバイスを再起動します。

### <a name="re-enable-microsoft-defender-antivirus-on-windows-server-version-1803-or-later"></a>Windows Server バージョン 1803 以降でMicrosoft Defender ウイルス対策を再度有効にする

> [!IMPORTANT]
> 次の手順は、次のバージョンのWindowsを実行しているエンドポイントまたはデバイスにのみ適用されます。
> - Windows Server 2022
> - Windows Server 2019
> - Windows Server バージョン 1803 (コア専用モード)

1. サーバー上のローカル管理者として、Windows PowerShellを開きます。

2. Windows PowerShell コマンドレットを実行します。

   ```powershell
   # For Windows Server 2016
   Dism /online /Enable-Feature /FeatureName:Windows-Defender-Features
   Dism /online /Enable-Feature /FeatureName:Windows-Defender
   Dism /online /Enable-Feature /FeatureName:Windows-Defender-Gui
   # For Windows Server 2019 and Windows Server 2022
   Dism /online /Enable-Feature /FeatureName:Windows-Defender
   ```

   PowerShell を実行しているタスク シーケンス内で DISM コマンドを使用する場合は、次のcmd.exeへのパスが必要です。
   例:

   ```powershell
   c:\windows\sysnative\cmd.exe /c Dism /online /Enable-Feature /FeatureName:Windows-Defender-Features
   c:\windows\sysnative\cmd.exe /c Dism /online /Enable-Feature /FeatureName:Windows-Defender
   ```

3. デバイスを再起動します。

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Windows サーバーでMicrosoft Defender ウイルス対策をパッシブ モードに設定する

> [!TIP]
> Windows Server 2012 R2 と 2016 では、パッシブ モードでMicrosoft Defender ウイルス対策を実行できるようになりました。 詳細については、「[Microsoft Defender for Endpoint をインストールするためのオプション](configure-server-endpoints.md#options-to-install-the-microsoft-defender-for-endpoint-packages)」 を参照してください。

1. レジストリ エディターを開き、次に `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`移動します。

2. **ForceDefenderPassiveMode** という DWORD エントリを編集 (または作成) し、次の設定を指定します。

   - DWORD の値を 1 に設定 **します**。

   - [ **基本**] で 、[ **16 進数**] を選択します。

> [!NOTE]
> Defender for Endpoint にオンボードした後、Windows Server でMicrosoft Defender ウイルス対策をパッシブ モードに設定する必要がある場合があります。 パッシブ モードが想定どおりに設定されたことを確認するには、**Microsoft Windows-Windows Defender操作** ログ (場所) で`C:\Windows\System32\winevt\Logs`*イベント 5007* を検索し、**ForceDefenderPassiveMode** または **PassiveMode** レジストリ キーが **0x1** に設定されていることを確認します。

### <a name="are-you-using-windows-server-2012-r2-or-windows-server-2016"></a>Windows Server 2012 R2 または Windows Server 2016 を使用していますか?

上記の方法を使用して、Windows Server 2012 R2 および 2016 でパッシブ モードでMicrosoft Defender ウイルス対策を実行できるようになりました。 詳細については、「[Microsoft Defender for Endpoint をインストールするためのオプション](configure-server-endpoints.md#options-to-install-the-microsoft-defender-for-endpoint-packages)」 を参照してください。

## <a name="configure-defender-for-endpoint"></a>Android 機能用に Microsoft Defender for Endpoint を構成する

移行プロセスのこの手順では、エンドポイントのMicrosoft Defender ウイルス対策を構成します。 Intuneを使用することをお勧めします。ただし、次の表に示す任意のメソッドを使用できます。

|メソッド|操作|
|---|---|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/><br/> **注**: IntuneはMicrosoft エンドポイント マネージャーの一部になりました。|1. [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)に移動し、サインインします。<br/><br/>2. [ **デバイス** \> **構成プロファイル]** を選択し、構成するプロファイルの種類を選択します。 **デバイス制限** プロファイルの種類をまだ作成していない場合、または新しいデバイス制限の種類を作成する場合は、「[Microsoft Intuneでデバイス制限設定を構成する](/intune/device-restrictions-configure)」を参照してください。<br/><br/>3. **[プロパティ**] を選択し、[**構成設定: 編集]** を選択します。<br/><br/>4. **[Microsoft Defender ウイルス対策**] を展開します。<br/><br/>5. **クラウド配信保護を** 有効にします。<br/><br/>6. [ **サンプルの提出前にユーザーにプロンプトを表示** する] ドロップダウンで、[ **すべてのサンプルを自動的に送信する**] を選択します。<br/><br/>7. [ **望ましくない可能性があるアプリケーションの検出** ] ドロップダウンで、[ **有効]** または [ **監査**] を選択します。<br/><br/>8. **[確認と保存**] を選択し、[ **保存]** を選択します。 <br/><br/> **ヒント**: デバイス プロファイルの作成と構成方法など、Intuneデバイス プロファイルの詳細については、「[Microsoft Intune デバイス プロファイルとは」](/intune/device-profiles)を参照してください。|
|Microsoft Endpoint Configuration Manager|[Configuration ManagerでEndpoint Protectionのマルウェア対策ポリシーを作成してデプロイ](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)する方法に関する説明を参照してください。 <br/><br/> マルウェア対策ポリシーを作成して構成するときは、 [リアルタイムの保護設定](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) を確認し、 [ブロックを一目で有効に](configure-block-at-first-sight-microsoft-defender-antivirus.md)してください。
|Windowsのコントロール パネル|こちらのガイダンスに従ってください:[Microsoft Defender ウイルス対策を有効にします](/mem/intune/user-help/turn-on-defender-windows)。 (一部のバージョン *のWindows* では *、Microsoft Defender ウイルス対策ではなくWindows Defender ウイルス対策* が表示される場合があります)。|
|[高度なグループ ポリシーの管理](/microsoft-desktop-optimization-pack/agpm/) <br/><br/> または <br/><br/> [グループ ポリシー管理コンソール](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)|1. **[コンピューター構成** \> **管理用テンプレート** \> **] Windowsコンポーネント** \> **Microsoft Defender ウイルス対策** に移動します。<br/><br/>2. [**Microsoft Defender ウイルス対策をオフにする]** というポリシーを探します。<br/><br/>3. [ **ポリシー設定の編集]** を選択し、ポリシーが無効になっていることを確認します。 このアクションにより、Microsoft Defender ウイルス対策が有効になります。 <br/>(一部のバージョン *のWindows* では *、Microsoft Defender ウイルス対策ではなくWindows Defender ウイルス対策* が表示される場合があります)。|

> [!TIP]
> 組織のデバイスがオンボードされる前に、ポリシーを展開できます。

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution"></a>既存のソリューションの除外リストにMicrosoft Defender for Endpointを追加する

セットアップ プロセスのこの手順では、既存のエンドポイント保護ソリューションと組織が使用しているその他のセキュリティ製品の除外リストに Defender for Endpoint を追加します。

> [!TIP]
> 除外の構成に関するヘルプについては、ソリューション プロバイダーのドキュメントを参照してください。

構成する特定の除外は、エンドポイントまたはデバイスが実行されているWindowsのバージョンによって異なり、次の表に示します。
<br/><br/>

| OS |除外 |
|:--|:--|
|Windows 11 <br/><br/>Windows 10[バージョン 1803](/windows/release-health/status-windows-10-1803) 以降 ([リリース情報Windows 10](/windows/release-health/release-information)参照)<br/><br/>[KB4493441](https://support.microsoft.com/help/4493441) がインストールされているWindows 10、バージョン 1703 または 1709 <br/><br/> Windows Server 2022<br/><br/>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019) <br/><br/>[Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/><br/>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/><br/>[Windows Server バージョン 1803](/windows-server/get-started/whats-new-in-windows-server-1803) | `C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCM.exe`<br/><br/>さらに、最新の統合ソリューションを実行Windows Server 2012 R2 と 2016 では、[KB5005292](https://support.microsoft.com/en-us/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac) を使用して Sense EDR コンポーネントを更新した後、次の除外が必要です。<br/> <br/> `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\MsSense.exe` <br/><br/>`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\SenseCnCProxy.exe`<br/><br/>`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\SenseIR.exe`<br/><br/>`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\SenseCE.exe`<br/><br/>`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\SenseSampleUploader.exe`<br/><br/>`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\SenseCM.exe` |
|[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/><br/>[Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/><br/>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/><br/>**注**: ホスト一時ファイル 6\45 の監視には、異なる番号のサブフォルダーを指定できます。<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策の除外リストに既存のソリューションを追加する

セットアップ プロセスのこの手順では、既存のソリューションをMicrosoft Defender ウイルス対策除外リストに追加します。 次の表に示すように、除外をMicrosoft Defender ウイルス対策に追加するには、いくつかの方法から選択できます。 

|メソッド|操作|
|---|---|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/><br/> **注**: IntuneはMicrosoft エンドポイント マネージャーの一部になりました。|1. [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)に移動し、サインインします。<br/><br/>2. [ **デバイス** \> **構成プロファイル]** を選択し、構成するプロファイルを選択します。<br/><br/>3. [ **管理**] で [ **プロパティ**] を選択します。<br/><br/>4. **[構成設定: 編集]** を選択します。<br/><br/>5. **[Microsoft Defender ウイルス対策] を** 展開し、Microsoft Defender ウイルス対策 [**除外] を展開します**。<br/><br/>6. Microsoft Defender ウイルス対策 スキャンから除外するファイルとフォルダー、拡張機能、プロセスを指定します。 参照については、「[Microsoft Defender ウイルス対策除外](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)」を参照してください。<br/><br/>7. **[校閲と保存**] を選択し、[ **保存]** を選択します。|
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/)|1. [Configuration Manager コンソール](/mem/configmgr/core/servers/manage/admin-console)を使用して、[**資産とコンプライアンス** \> **Endpoint Protection** \> **マルウェア対策ポリシー**] に移動し、変更するポリシーを選択します。<br/><br/>2. Microsoft Defender ウイルス対策 スキャンから除外するファイルとフォルダー、拡張機能、プロセスの除外設定を指定します。|
|[グループ ポリシー オブジェクト](/previous-versions/windows/desktop/Policy/group-policy-objects)|1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](https://technet.microsoft.com/library/cc731212.aspx)を開き、構成するグループ ポリシー オブジェクトを右クリックし、[**編集]** を選択します。<br/><br/>2. **グループ ポリシー管理エディター** で、[**コンピューターの構成**] に移動し、[**管理用テンプレート**] を選択します。<br/><br/>3. ツリーを展開して **、除外Microsoft Defender ウイルス対策コンポーネント\>をWindows\>します**。 (一部のバージョン *のWindows* では *、Microsoft Defender ウイルス対策ではなくWindows Defender ウイルス対策* が表示される場合があります)。<br/><br/>4. **[パスの除外]** 設定をダブルクリックし、除外を追加します。<br/><br/>5. オプションを **[有効]** に設定します。<br/><br/>6. [ **オプション]** セクションで、[ **表示]...** を選択します。<br/><br/>7. [ **値名** ] 列の下に、各フォルダーを独自の行に指定します。 ファイルを指定する場合は、ドライブ文字、フォルダー パス、ファイル名、拡張子など、ファイルへの完全修飾パスを入力してください。 **[値]** 列に **「0**」と入力します。<br/><br/>8. **[OK] を選択します**。<br/><br/>9. **[拡張機能の除外]** 設定をダブルクリックし、除外を追加します。<br/><br/>10. オプションを **[有効]** に設定します。<br/><br/>11. **[オプション]** セクションの [ **表示]...** を選択します。<br/><br/>12. [ **値名** ] 列の下に、各ファイル拡張子を独自の行に入力します。 **[値]** 列に **「0**」と入力します。<br/><br/>13. **[OK] を選択します**。|
|ローカル グループ ポリシー オブジェクト|1. エンドポイントまたはデバイスで、ローカル グループ ポリシー エディターを開きます。<br/><br/>2. **[コンピューター構成** \> **管理テンプレート** \> **] Windows [コンポーネント** \> **Microsoft Defender ウイルス対策** \> **除外]** に移動します。 (一部のバージョン *のWindows* では *、Microsoft Defender ウイルス対策ではなくWindows Defender ウイルス対策* が表示される場合があります)。<br/><br/>3. パスとプロセスの除外を指定します。|
|レジストリ キー|1. 次のレジストリ キーをエクスポートします `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions`。<br/><br/>2. レジストリ キーをインポートします。 次に、2 つの例を紹介します。<br/>- ローカル パス: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg`<br/>- ネットワーク共有: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg`|

### <a name="keep-the-following-points-about-exclusions-in-mind"></a>除外に関する次の点に留意してください

[Microsoft Defender ウイルス対策 スキャンに除外を](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)追加する場合は、パスとプロセスの除外を追加する必要があります。

次の点に注意してください。

- *パスの除外では、特定の* ファイルとそのファイルにアクセスするものは除外されます。

- *プロセスの除外では* 、プロセスが触れるものは除外されますが、プロセス自体は除外されません。

- 完全なパスを使用してプロセスの除外を一覧表示します。名前のみでは一覧表示されません。 (名前のみのメソッドの安全性は低くなります)。)

- 各実行可能ファイル (.exe) をパスの除外とプロセスの除外の両方として一覧表示すると、プロセスとそれが触れるものはすべて除外されます。

## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>デバイス グループ、デバイス コレクション、および組織単位を設定する

デバイス グループ、デバイス コレクション、組織単位を使用すると、セキュリティ チームはセキュリティ ポリシーを効率的かつ効果的に管理および割り当てることができます。 次の表では、これらの各グループとその構成方法について説明します。 組織では、3 つのコレクションの種類をすべて使用できない場合があります。

|コレクションの種類|操作|
|---|---|
|[デバイス グループ](/microsoft-365/security/defender-endpoint/machine-groups) (以前は *マシン グループ* と呼ばれた) を使用すると、セキュリティ運用チームは、自動調査や修復などのセキュリティ機能を構成できます。 <br/><br/> デバイス グループは、セキュリティ運用チームが必要に応じて修復アクションを実行できるように、それらのデバイスへのアクセスを割り当てる場合にも役立ちます。 <br/><br/> デバイス グループは、攻撃が検出および停止された間に作成され、"初期アクセス アラート" などのアラートがトリガーされ[、Microsoft 365 Defender ポータル](/microsoft-365/security/defender/microsoft-365-defender)に表示されます。|1. Microsoft 365 Defender ポータル (<https://security.microsoft.com>) に移動します。<br/><br/>2. 左側のナビゲーション ウィンドウで、**エンドポイント** \> **のアクセス許可** \> **デバイス グループ****設定**\>選択します。<br/><br/>3. [ **+ デバイス グループの追加]** を選択します。<br/><br/>4. デバイス グループの名前と説明を指定します。<br/><br/>5. **[オートメーション] レベル** の一覧で、オプションを選択します。 ( **完全 - 脅威を自動的に修復** することをお勧めします)。さまざまな自動化レベルの詳細については、「 [脅威を修復する方法](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)」を参照してください。<br/><br/>6. 一致ルールの条件を指定して、デバイス グループに属するデバイスを決定します。 たとえば、ドメイン、OS のバージョンを選択したり、 [デバイス タグ](/microsoft-365/security/defender-endpoint/machine-tags)を使用したりすることもできます。<br/><br/>7. [ **ユーザー アクセス** ] タブで、デバイス グループに含まれるデバイスにアクセスできるロールを指定します。<br/><br/>8. [完了] を選択 **します**。|
|[デバイス コレクション](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) を使用すると、セキュリティ運用チームは、アプリケーションの管理、コンプライアンス設定の展開、または組織内のデバイスへのソフトウェア更新プログラムのインストールを行うことができます。 <br/><br/> デバイス コレクションは、[Configuration Manager](/mem/configmgr/)を使用して作成されます。|[「コレクションの作成](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create)」の手順に従います。|
|[組織単位](/azure/active-directory-domain-services/create-ou) を使用すると、ユーザー アカウント、サービス アカウント、コンピューター アカウントなどのオブジェクトを論理的にグループ化できます。 <br/><br/> その後、管理者を特定の組織単位に割り当て、グループ ポリシーを適用して、対象となる構成設定を適用できます。 <br/><br/> 組織単位は[、Azure Active Directory Domain Services](/azure/active-directory-domain-services) で定義されます。|[「Azure Active Directory Domain Services マネージド ドメインで組織単位を作成する](/azure/active-directory-domain-services/create-ou)」の手順に従います。|

## <a name="next-step"></a>次の手順

**おめでとうございます**。 [Defender for Endpoint への切り替え](switch-to-mde-overview.md#the-migration-process)のセットアップ フェーズが完了しました。

- [フェーズ 3: Defender for Endpoint へのオンボードに進む](switch-to-mde-phase-3.md)
