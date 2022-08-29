---
title: Windows Server で Microsoft Defender ウイルス対策の除外を構成する
ms.reviewer: pahuijbr
manager: dansimp
description: Windows Server には、サーバーロールに基づく自動除外が含まれています。 カスタム除外を追加することもできます。
keywords: 除外, サーバー, 自動除外, 自動, カスタム, スキャン, Microsoft Defender ウイルス対策
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.collection: M365-security-compliance
ms.openlocfilehash: 7205a612954dfbd283b61ca377c81c5f78243f58
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67388685"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a>Windows Server で Microsoft Defender ウイルス対策の除外を構成する


**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

Windows Server 2016および Windows Server 2019 の Microsoft Defender ウイルス対策では、指定したサーバー ロールで定義されているように、特定の除外対象に自動的に登録されます。 これらの除外は、[Windows セキュリティ アプリ](microsoft-defender-security-center-antivirus.md)に表示される標準の除外リストには表示されません。

サーバー ロール定義の自動除外に加えて、カスタム除外を追加または削除できます。 これを行うには、次の記事を参照してください。
- [ファイル名、拡張子、フォルダーの場所に基づいて除外を構成および検証する](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [プロセスによって開かれたファイルの除外を構成して検証する](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a>留意すべき点がいくつかあります

- カスタム除外は、自動除外よりも優先されます。
- 自動除外は、 [リアルタイム保護 (RTP)](configure-protection-features-microsoft-defender-antivirus.md) スキャンにのみ適用されます。 
- 自動除外は [、完全スキャン、クイック スキャン、またはオンデマンド スキャン](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan)では適用されません。
- カスタム除外と重複除外は、自動除外と競合しません。
- Microsoft Defender ウイルス対策では、展開イメージサービスと管理 (DISM) ツールを使用して、コンピューターにインストールされているロールを決定します。
- オペレーティング システムに含まれていないソフトウェアについては、適切な除外を設定する必要があります。
- Windows Server 2012 R2 には、インストール可能な機能として Microsoft Defender ウイルス対策がありません。 これらのサーバーを Defender for Endpoint にオンボードすると、Microsoft Defender ウイルス対策がインストールされ、オペレーティング システム ファイルの既定の除外が適用されます。 ただし、サーバー ロールの除外 (以下で指定) は自動的には適用されないため、必要に応じてこれらの除外を構成する必要があります。 詳細については、「[Windows サーバーを Microsoft Defender for Endpoint にオンボードする](configure-server-endpoints.md)」を参照してください。

この記事では、Windows Server 2016 以降の Microsoft Defender ウイルス対策の除外の概要について説明します。

Microsoft Defender ウイルス対策はWindows Server 2016以降に組み込まれているため、オペレーティング システム ファイルとサーバーの役割の除外は自動的に行われます。 ただし、カスタム除外を定義できます。 必要に応じて、自動除外をオプトアウトすることもできます。

この記事に含まれるセクションは次のとおりです。

|Section|説明|
|---|---|
|[Windows Server 2016以降の自動除外](#automatic-exclusions-on-windows-server-2016-or-later)|2 つの主な種類の自動除外について説明し、自動除外の詳細な一覧を含めます|
|[自動除外のオプトアウト](#opting-out-of-automatic-exclusions)|自動除外をオプトアウトする方法を説明する重要な考慮事項と手順が含まれています|
|[カスタム除外の定義](#defining-custom-exclusions)|カスタム除外を定義するためのハウツー情報へのリンクを提供します|

## <a name="automatic-exclusions-on-windows-server-2016-or-later"></a>Windows Server 2016以降の自動除外

Windows Server 2016以降では、次の除外を定義する必要はありません。

- オペレーティング システム ファイル
- サーバー ロールと、サーバー ロールを介して追加されるすべてのファイル

Microsoft Defender ウイルス対策は組み込まれているため、Windows Server 2016 以降のオペレーティング システム ファイルの除外は必要ありません。 さらに、Windows Server 2016以降を実行してロールをインストールすると、Microsoft Defender ウイルス対策には、サーバー ロールの自動除外と、ロールのインストール中に追加されるすべてのファイルが含まれます。

オペレーティング システムの除外とサーバー ロールの除外は、[Windows セキュリティ アプリ](microsoft-defender-security-center-antivirus.md)に表示される標準の除外リストには表示されません。

> [!NOTE]
> サーバー ロールとオペレーティング システム ファイルの自動除外は、Windows Server 2012には適用されません。 自動除外は、Windows Server 2012 R2 を実行しているサーバーが Defender for Endpoint にオンボードされている場合に適用できます。 (「[Windows サーバーをMicrosoft Defender for Endpoint サービスにオンボードする](configure-server-endpoints.md)」を参照してください)。


### <a name="the-list-of-automatic-exclusions"></a>自動除外の一覧

次のセクションでは、自動除外ファイル パスとファイルの種類で配信される除外について説明します。

#### <a name="default-exclusions-for-all-roles"></a>すべてのロールの既定の除外

このセクションでは、Windows Server 2016、Windows Server 2019、Windows Server 2022 のすべてのロールの既定の除外を示します。

> [!IMPORTANT]
> - 既定の場所は、この記事で説明する場所とは異なる場合があります。
> - Windows 機能またはサーバーの役割として含まれていないソフトウェアの除外を設定するには、ソフトウェアの製造元のドキュメントを参照してください。

##### <a name="windows-tempedb-files"></a>Windows "temp.edb" ファイル

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\windows.edb`

##### <a name="windows-update-files-or-automatic-update-files"></a>Windows Update ファイルまたは自動更新ファイル

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

##### <a name="windows-security-files"></a>Windows セキュリティ ファイル

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

##### <a name="group-policy-files"></a>グループ ポリシー ファイル

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

##### <a name="wins-files"></a>WINS ファイル

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

##### <a name="file-replication-service-frs-exclusions"></a>ファイル レプリケーション サービス (FRS) の除外

- ファイル レプリケーション サービス (FRS) 作業フォルダー内のファイル。 FRS 作業フォルダーがレジストリ キーで指定されている `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- FRS データベースログ ファイル。 FRS データベース ログ ファイル フォルダーがレジストリ キーで指定されている `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`

  - `%windir%\Ntfrs\*\Edb\*.log`

- FRS ステージング フォルダー。 ステージング フォルダーがレジストリ キーで指定されている `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- FRS プレインストール フォルダー。 このフォルダーは、フォルダーによって指定されます `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- 分散ファイル システム レプリケーション (DFSR) データベースと作業フォルダー。 これらのフォルダーは、レジストリ キーによって指定されます `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`

  > [!NOTE]
  > カスタムの場所については、「 [自動除外のオプトアウト](#opting-out-of-automatic-exclusions)」を参照してください。

  - `%systemdrive%\System Volume Information\DFSR\$db_normal$`
  - `%systemdrive%\System Volume Information\DFSR\FileIDTable_*`
  - `%systemdrive%\System Volume Information\DFSR\SimilarityTable_*`
  - `%systemdrive%\System Volume Information\DFSR\*.XML`
  - `%systemdrive%\System Volume Information\DFSR\$db_dirty$`
  - `%systemdrive%\System Volume Information\DFSR\$db_clean$`
  - `%systemdrive%\System Volume Information\DFSR\$db_lostl$`
  - `%systemdrive%\System Volume Information\DFSR\Dfsr.db`
  - `%systemdrive%\System Volume Information\DFSR\*.frx`
  - `%systemdrive%\System Volume Information\DFSR\*.log`
  - `%systemdrive%\System Volume Information\DFSR\Fsr*.jrs`
  - `%systemdrive%\System Volume Information\DFSR\Tmp.edb`

##### <a name="process-exclusions"></a>プロセスの除外

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

##### <a name="hyper-v-exclusions"></a>Hyper-V の除外

次の表に、Hyper-V ロールをインストールするときに自動的に配信されるファイルの種類の除外、フォルダーの除外、およびプロセスの除外の一覧を示します。

|除外の種類|詳細|
|---|---|
|ファイルの種類|`*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs`|
|Folders|`%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks`|
|プロセス|`%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe`|

##### <a name="sysvol-files"></a>SYSVOL ファイル

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


#### <a name="active-directory-exclusions"></a>Active Directory の除外

このセクションでは、Active Directory Domain Services (AD DS) をインストールするときに自動的に配信される除外の一覧を示します。

##### <a name="ntds-database-files"></a>NTDS データベース ファイル

データベース ファイルがレジストリ キーで指定されている `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

##### <a name="the-ad-ds-transaction-log-files"></a>AD DS トランザクション ログ ファイル

トランザクション ログ ファイルはレジストリ キーで指定されます。 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

##### <a name="the-ntds-working-folder"></a>NTDS 作業フォルダー

このフォルダーはレジストリ キーで指定されます `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

##### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a>AD DS および AD DS 関連のサポート ファイルのプロセス除外

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

#### <a name="dhcp-server-exclusions"></a>DHCP サーバーの除外

このセクションでは、DHCP サーバーの役割をインストールするときに自動的に配信される除外の一覧を示します。 DHCP サーバー ファイルの場所は、レジストリ キーの *DatabasePath*、 *DhcpLogFilePath*、 *BackupDatabasePath* パラメーターによって指定されます。 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

#### <a name="dns-server-exclusions"></a>DNS サーバーの除外

このセクションでは、DNS サーバーの役割をインストールするときに自動的に配信されるファイルとフォルダーの除外とプロセスの除外の一覧を示します。

##### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a>DNS サーバー ロールのファイルとフォルダーの除外

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

##### <a name="process-exclusions-for-the-dns-server-role"></a>DNS サーバー ロールのプロセス除外

- `%systemroot%\System32\dns.exe`

#### <a name="file-and-storage-services-exclusions"></a>ファイル サービスとストレージ サービスの除外

このセクションでは、File および Storage Services ロールをインストールするときに自動的に配信されるファイルとフォルダーの除外の一覧を示します。 以下に示す除外には、クラスタリング ロールの除外は含まれません。

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

#### <a name="print-server-exclusions"></a>印刷サーバーの除外

このセクションでは、印刷サーバー ロールをインストールするときに自動的に配信されるファイルの種類の除外、フォルダーの除外、およびプロセスの除外の一覧を示します。

##### <a name="file-type-exclusions"></a>ファイルの種類の除外

- `*.shd`
- `*.spl`

##### <a name="folder-exclusions"></a>フォルダーの除外

このフォルダーはレジストリ キーで指定されます `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`

- `%system32%\spool\printers\*`

##### <a name="process-exclusions"></a>プロセスの除外

- `spoolsv.exe`

#### <a name="web-server-exclusions"></a>Web サーバーの除外

このセクションでは、Web サーバー ロールをインストールするときに自動的に配信されるフォルダーの除外とプロセスの除外の一覧を示します。

##### <a name="folder-exclusions"></a>フォルダーの除外

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

##### <a name="process-exclusions"></a>Process exclusions

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

##### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a>Sysvol\Sysvol フォルダーまたは SYSVOL_DFSR\Sysvol フォルダー内のファイルのスキャンをオフにする

フォルダーと`SYSVOL_DFSR\Sysvol`すべてのサブフォルダーの現在の`Sysvol\Sysvol`場所は、レプリカ セット ルートのファイル システムの再解析ターゲットです。 フォルダーでは `Sysvol\Sysvol` 、 `SYSVOL_DFSR\Sysvol` 既定で次の場所が使用されます。

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

現在アクティブな `SYSVOL` パスは NETLOGON 共有によって参照され、次のサブキーの SysVol 値名によって決定できます。 `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`

このフォルダーとそのすべてのサブフォルダーから次のファイルを除外します。

- `*.adm`
- `*.admx`
- `*.adml`
- `Registry.pol`
- `Registry.tmp`
- `*.aas`
- `*.inf`
- `Scripts.ini`
- `*.ins`
- `Oscfilter.ini`

#### <a name="windows-server-update-services-exclusions"></a>Windows Server Update Services除外

このセクションでは、Windows Server Update Services (WSUS) ロールをインストールするときに自動的に配信されるフォルダーの除外の一覧を示します。 WSUS フォルダーがレジストリ キーで指定されている `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="opting-out-of-automatic-exclusions"></a>自動除外のオプトアウト

Windows Server 2016 以降では、セキュリティ インテリジェンス更新プログラムによって提供される定義済みの除外は、ロールまたは機能の既定のパスのみを除外します。 カスタム パスにロールまたは機能をインストールした場合、または一連の除外を手動で制御する場合は、セキュリティ インテリジェンス更新プログラムで配信される自動除外をオプトアウトしてください。 ただし、自動的に配信される除外は、Windows Server 2016 以降向けに最適化されていることに注意してください。 [除外リストを定義する前に除外を定義するための推奨事項](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)に関するページを参照してください。

> [!WARNING]
> 自動除外をオプトアウトすると、パフォーマンスに悪影響を与えたり、データが破損したりする可能性があります。 自動的に配信される除外は、Windows Server 2016、Windows Server 2019、および Windows Server 2022 ロール用に最適化されています。

定義済みの除外では **既定のパス** のみが除外されるため、NTDS フォルダーと SYSVOL フォルダーを元のパス *とは異なる別の* ドライブまたはパスに移動する場合は、除外を手動で追加する必要があります。 [フォルダー名またはファイル拡張子に基づいて除外の一覧を構成](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension)する方法に関するページを参照してください。

グループ ポリシー、PowerShell コマンドレット、WMI を使用して、自動除外リストを無効にすることができます。

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-windows-server-2019-and-windows-server-2022"></a>グループ ポリシーを使用して、Windows Server 2016、Windows Server 2019、Windows Server 2022 で自動除外リストを無効にする

1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11))を開きます。 構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。

2. **グループ ポリシー管理エディター** で **[コンピューターの構成**] に移動し、[**管理用テンプレート**] を選択します。

3. ツリーを **Windows コンポーネント** \> **Microsoft Defender ウイルス対策** \> **の除外** に展開します。

4. [ **自動除外を無効にする**] をダブルクリックし、オプションを **[有効]** に設定します。 次に [**OK**] を選びます。

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server"></a>PowerShell コマンドレットを使用して Windows Server で自動除外リストを無効にする

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

詳細については、次のリソースを参照してください。

- [PowerShell コマンドレットを使用して、Microsoft Defender ウイルス対策を構成して実行します](use-powershell-cmdlets-microsoft-defender-antivirus.md)。
- [Microsoft Defender ウイルス対策で PowerShell を使用します](/powershell/module/defender/)。

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server"></a>Windows 管理命令 (WMI) を使用して、Windows Server で自動除外リストを無効にする

次のプロパティには、[MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) クラスの **Set** メソッドを使用します。

```WMI
DisableAutoExclusions
```

詳細と許可されるパラメーターについては、次を参照してください。

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="defining-custom-exclusions"></a>カスタム除外の定義

必要に応じて、カスタム除外を追加または削除できます。 これを行うには、次の記事を参照してください。

- [ファイル名、拡張子、フォルダーの場所に基づいて除外を構成および検証する](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [プロセスによって開かれたファイルの除外を構成して検証する](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策スキャンの除外を構成して検証する](configure-exclusions-microsoft-defender-antivirus.md)
- [ファイル名、拡張子、フォルダーの場所に基づいて除外を構成および検証する](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [プロセスによって開かれたファイルの除外を構成して検証する](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [除外を定義する際に避ける必要のある一般的な間違い](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策のスキャンと修復の結果をカスタマイズ、開始、および確認する](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
