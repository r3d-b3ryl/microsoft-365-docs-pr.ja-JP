---
title: サーバー Microsoft Defender ウイルス対策の除外をWindowsする
ms.reviewer: ''
manager: dansimp
description: Windowsサーバーには、サーバーの役割に基づく自動除外が含まれます。 カスタム除外を追加できます。
keywords: 除外、サーバー、自動除外、自動、カスタム、スキャン、Microsoft Defender ウイルス対策
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 02/10/2021
ms.openlocfilehash: 6e0636122a5ef2d173e6eee53c4c303bb8cc46c8df7b1eeaa5d7b026f1c04ea0
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53904037"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a>サーバー Microsoft Defender ウイルス対策の除外をWindowsする


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender ウイルス対策サーバー 2019 Windows Server 2016および Windowsサーバー 2019 では、指定したサーバーの役割で定義されている特定の除外に自動的に登録されます。 これらの除外は、アプリに表示される標準の除外リスト[にはWindows セキュリティされません](microsoft-defender-security-center-antivirus.md)。

> [!NOTE]
> 自動除外は、リアルタイム保護 (RTP) スキャンにのみ適用されます。 フル/クイック スキャンまたはオンデマンド スキャンでは、自動除外は適用されません。

サーバーの役割定義の自動除外に加えて、カスタム除外を追加または削除できます。 これを行うには、次の記事を参照してください。
- [ファイル名、拡張子、フォルダーの場所に基づいて除外を構成および検証する](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [プロセスによって開いたファイルの除外を構成および検証する](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a>いくつかの点に気を付ける必要があります

次の重要な点に注意してください。

- カスタム除外は、自動除外よりも優先されます。
- 自動除外は、リアルタイム保護 (RTP) スキャンにのみ適用されます。 フル/クイック スキャンまたはオンデマンド スキャンでは、自動除外は適用されません。
- カスタム除外と重複除外は、自動除外と競合しない。
- Microsoft Defender ウイルス対策展開イメージのサービスと管理 (DISM) ツールを使用して、コンピューターにインストールされている役割を特定します。

## <a name="opt-out-of-automatic-exclusions"></a>自動除外をオプトアウトする

サーバー 2019 Windows Server 2016および Windowsでは、セキュリティ インテリジェンス更新プログラムによって提供される定義済みの除外は、役割または機能の既定のパスのみを除外します。 カスタム パスに役割または機能をインストールした場合、または一連の除外を手動で制御する場合は、セキュリティ インテリジェンス更新プログラムで配信される自動除外をオプトアウトしてください。 ただし、自動的に配信される除外は、2019 年と 2019 年Windows Server 2016に最適化されています。 除外 [リストを定義する前に、「除外を](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) 定義するための推奨事項」を参照してください。

> [!WARNING]
> 自動除外をオプトアウトすると、パフォーマンスに悪影響を及ぼすか、データが破損する可能性があります。 自動的に配信される除外は、サーバー 2019 Windows Server 2016およびWindowsに最適化されます。

定義済みの除外は既定のパスのみを除外しますので、NTDS と SYSVOL を元のパスとは異なる別のドライブまたはパスに移動する場合は、ここでの情報[](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension)を使用して手動で除外を追加する必要があります。 

グループ ポリシー、PowerShell コマンドレット、および WMI を使用して、自動除外リストを無効にできます。

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a>グループ ポリシーを使用して、サーバー 2019 およびサーバー 2019 のWindows Server 2016 Windows無効にする

1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11))を開きます。 構成するグループ ポリシー オブジェクトを右クリックし、[編集] を **クリックします**。
2. グループ ポリシー **管理エディターで 、[** コンピューターの構成] **に移動し**、[管理用テンプレート] **をクリックします**。
3. ツリーを展開して、[**除外Windowsコンポーネント**  >  **Microsoft Defender ウイルス対策**  >  **展開します**。
4. [自動除外を **オフにする] をダブルクリック** し、オプションを [有効] に **設定します**。 次に、[ **OK**] をクリックします。 

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-2019"></a>PowerShell コマンドレットを使用して、2019 年と 2019 年の自動除外リストWindows Server 2016無効にする

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

詳細については、次のリソースを参照してください。

- [PowerShell コマンドレットを使用して、PowerShell コマンドレットを構成して実行Microsoft Defender ウイルス対策。](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [PowerShell と一緒にMicrosoft Defender ウイルス対策。](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a>サーバー Windowsサーバー 2019 の自動除外リストを無効にするには、Windows管理命令 (WMI Windows Server 2016) をWindowsします。

次の **プロパティ** に対して [、MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) クラスの Set メソッドを使用します。

```WMI
DisableAutoExclusions
```

詳細と許可されるパラメーターについては、以下を参照してください。
- [Windows DefenderWMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="list-of-automatic-exclusions"></a>自動除外の一覧

次のセクションでは、自動除外ファイル パスとファイルの種類で配信される除外について説明します。

### <a name="default-exclusions-for-all-roles"></a>すべての役割の既定の除外

このセクションでは、すべてのユーザーロールと 2019 Windows Server 2016の除外を一覧表示します。

> [!NOTE]
> 既定の場所は、この記事に記載されている場所とは異なる場合があります。

#### <a name="windows-tempedb-files"></a>Windows"temp.edb" ファイル

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

#### <a name="windows-update-files-or-automatic-update-files"></a>Windowsファイルの更新または自動更新ファイル

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

#### <a name="windows-security-files"></a>Windows セキュリティファイル

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

#### <a name="group-policy-files"></a>グループ ポリシー ファイル

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

#### <a name="wins-files"></a>WINS ファイル

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

#### <a name="file-replication-service-frs-exclusions"></a>ファイル レプリケーション サービス (FRS) の除外

- ファイル レプリケーション サービス (FRS) 作業フォルダー内のファイル。 FRS 作業フォルダーがレジストリ キーで指定されている `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- FRS データベース ログ ファイル。 FRS データベース ログ ファイル フォルダーがレジストリ キーで指定されている `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`

  - `%windir%\Ntfrs\*\Edb\*.log`

- FRS ステージング フォルダー。 ステージング フォルダーがレジストリ キーで指定されている `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- FRS プレインストール フォルダー。 このフォルダーは、フォルダーによって指定されます。 `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- 分散ファイル システム レプリケーション (DFSR) データベースと作業フォルダー。 これらのフォルダーは、レジストリ キーによって指定されます。 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`

  > [!NOTE]
  > カスタムの場所については、「自動除外 [をオプトアウトする」を参照してください](#opt-out-of-automatic-exclusions)。

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

#### <a name="process-exclusions"></a>プロセスの除外

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

#### <a name="hyper-v-exclusions"></a>Hyper-V の除外

次の表に、Hyper-V の役割をインストールするときに自動的に配信されるファイルの種類の除外、フォルダーの除外、およびプロセスの除外の一覧を示します。

|ファイルの種類の除外 |フォルダーの除外  | Process exclusions |
|:--|:--|:--|
| `*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs` | `%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks` | `%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe` |

#### <a name="sysvol-files"></a>SYSVOL ファイル

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


### <a name="active-directory-exclusions"></a>Active Directory の除外

このセクションでは、Active Directory ドメイン サービスをインストールするときに自動的に配信される除外の一覧を示します。

#### <a name="ntds-database-files"></a>NTDS データベース ファイル

データベース ファイルはレジストリ キーで指定されます。 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

#### <a name="the-ad-ds-transaction-log-files"></a>DS ADログ ファイル

トランザクション ログ ファイルはレジストリ キーで指定されます。 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

#### <a name="the-ntds-working-folder"></a>NTDS 作業フォルダー

このフォルダーはレジストリ キーで指定されます。 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

#### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a>DS および DS 関連のADファイルAD除外を処理する

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

### <a name="dhcp-server-exclusions"></a>DHCP サーバーの除外

このセクションでは、DHCP Server の役割をインストールするときに自動的に配信される除外の一覧を示します。 DHCP Server ファイルの場所は、レジストリ キーの *DatabasePath、DhcpLogFilePath、**および BackupDatabasePath* パラメーターによって指定されます。 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

### <a name="dns-server-exclusions"></a>DNS サーバーの除外

このセクションでは、DNS Server の役割をインストールするときに自動的に配信されるファイルとフォルダーの除外とプロセスの除外の一覧を示します。

#### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a>DNS Server の役割のファイルとフォルダーの除外

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

#### <a name="process-exclusions-for-the-dns-server-role"></a>DNS Server の役割の除外を処理する

- `%systemroot%\System32\dns.exe`

### <a name="file-and-storage-services-exclusions"></a>ファイルとStorageサービスの除外

このセクションでは、File および Storage サービスの役割をインストールするときに自動的に配信されるファイルとフォルダーの除外の一覧を示します。 以下に示す除外には、クラスター化の役割の除外は含めされません。

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

### <a name="print-server-exclusions"></a>サーバーの除外を印刷する

このセクションでは、Print Server の役割をインストールするときに自動的に配信されるファイルの種類の除外、フォルダーの除外、およびプロセスの除外を一覧表示します。

#### <a name="file-type-exclusions"></a>ファイルの種類の除外

- `*.shd`
- `*.spl`

#### <a name="folder-exclusions"></a>フォルダーの除外

このフォルダーはレジストリ キーで指定されます。 `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`

- `%system32%\spool\printers\*`

#### <a name="process-exclusions"></a>プロセスの除外

- `spoolsv.exe`

### <a name="web-server-exclusions"></a>Web サーバーの除外

このセクションでは、Web Server の役割をインストールするときに自動的に配信されるフォルダーの除外とプロセスの除外の一覧を示します。

#### <a name="folder-exclusions"></a>フォルダーの除外

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

#### <a name="process-exclusions"></a>Process exclusions

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

#### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a>Sysvol\Sysvol フォルダーまたは sysvol フォルダー内のファイルのスキャンをオフSYSVOL_DFSR\Sysvol フォルダー

or フォルダーとすべてのサブフォルダーの現在の場所は、レプリカ セット ルートのファイル システムの再 `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` 解析ターゲットです。 フォルダー `Sysvol\Sysvol` は `SYSVOL_DFSR\Sysvol` 、既定で次の場所を使用します。

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

現在アクティブなパスは NETLOGON 共有によって参照され、次のサブキーの `SYSVOL` SysVol 値名によって決定できます。 `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`

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

### <a name="windows-server-update-services-exclusions"></a>Windows Server Update Services除外

このセクションでは、ユーザー (WSUS) の役割をインストールするときに自動的に配信されるフォルダー Windows Server Update Services一覧を示します。 WSUS フォルダーがレジストリ キーで指定されている `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="see-also"></a>関連項目

- [スキャンの除外を構成およびMicrosoft Defender ウイルス対策する](configure-exclusions-microsoft-defender-antivirus.md)
- [ファイル名、拡張子、フォルダーの場所に基づいて除外を構成および検証する](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [プロセスによって開いたファイルの除外を構成および検証する](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [除外を定義する際に避ける必要のある一般的な間違い](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [スキャンと修復の結果をカスタマイズ、開始Microsoft Defender ウイルス対策確認する](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
