---
title: 診断ログ
description: トラブルシューティング中にデバイスから収集される可能性があるログと、デバイスの保存方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 808ce2e426a0540c95195f26c9872f569e595715
ms.sourcegitcommit: 559df2c86a7822463ce0597140537bab260c746a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2022
ms.locfileid: "62825423"
---
# <a name="diagnostic-logs"></a>診断ログ

問題を報告した場合でも、サービスによって問題が特定された場合でも、ユーザーの介入なしにデバイスから特定の診断ログを収集する必要がある場合があります。

ユーザーが生成したコンテンツや情報をユーザー ディレクトリから収集しません。 デバイスの正常性と状態に関する診断データとログ データのみを収集します。

収集されたログは 28 日間保存され、削除されます。 データ処理標準に従ってデバイスから収集されたログ [を処理します](privacy-personal-data.md)。

## <a name="data-collected"></a>収集されるデータ

次の一覧には、Microsoft Managed Desktop が診断ログを収集する可能性があるすべてのフォルダー、イベント ログ、実行可能ファイル、またはレジストリの場所が含まれています。 収集される実際のデータは、このリストのサブセットであり、特定された問題に依存します。

### <a name="registry-keys"></a>レジストリ キー

- HKLMSYSTEMCurrentControlSetServices\\\\\\
- HKLMSOFTWAREMicrosoftSurface\\\\\\
- HKLMSOFTWAREPoliciesMicrosoft\\\\\\\\ Windows\\ WindowsUpdate
- HKLMSYSTEMCurrentControlSetControlMUIUILanguages\\\\\\\\\\
- HKLMSoftwarePoliciesMicrosoftWindowsStore\\\\\\\\
- HKLMSoftwareMicrosoft\\\\\\ Windows\\ CurrentVersionWindowsStoreWindowsUpdate\\\\
- HKLMSOFTWAREMicrosoft\\\\\\ Windows NT\\ CurrentVersion
- HKLMSOFTWAREMicrosoft\\\\\\ Windows NT\\ CurrentVersion
- HKLMSOFTWAREMicrosoft\\\\\\ Windows\\ CurrentVersionAppModel\\
- HKLMSYSTEMCurrentControlSetFirmwareResources\\\\\\\\
- HKLMSOFTWAREMicrosoftWindowsSelfhost\\\\\\
- HKLMSOFTWAREMicrosoftWindowsUpdate\\\\\\
- HKLMSOFTWAREMicrosoft\\\\\\ Windows\\ CurrentVersionAppx\\
- HKLMSOFTWAREMicrosoft\\\\\\ Windows NT\\ CurrentVersionSuperfetch\\
- HKLMSYSTEMSetup\\\\
- HKLMSoftwareMicrosoftIntuneManagementExtension\\\\\\
- HKLMSOFTWAREMicrosoftSystemCertificatesAuthRoot\\\\\\\\
- HKLMSOFTWAREMicrosoft\\\\ Windows\\高度な脅威保護
- HKLMSOFTWAREMicrosoft\\\\\\ Windows\\ CurrentVersionAuthenticationLogonUI\\\\
- HKLMSOFTWAREMicrosoft\\\\\\ Windows\\ CurrentVersionInternet\\ 設定
- HKLMSoftwareMicrosoft\\\\ Windows\\\\ CurrentVersionUninstall\\
- HKLMSoftwarePolicies\\\\
- HKLMSOFTWAREPoliciesMicrosoftCryptographyConfigurationSSL\\\\\\\\\\\\
- HKLMSOFTWAREPoliciesMicrosoft\\\\\\\\ Windows高度な脅威保護
- HKLMSOFTWAREWOW6432NodeMicrosoft\\\\\\\\ Windows\\ CurrentVersionUninstall\\
- HKLMSYSTEMCurrentControlSetControlSecurityProvidersSCHANNEL\\\\\\\\\\

### <a name="commands"></a>コマンド

- %programfiles%\\windows defendermpcmdrun.exe\\ -GetFiles
- %windir%\\system32\\certutil.exe -store
- %windir%\\system32\\certutil.exe -store -user my
- %windir%\\system32\\Dsregcmd.exe /status
- %windir%\\system32\\ipconfig.exe /all
- %windir%\\system32\\ipconfig.exe/displaydns
- %windir%\\system32\\mdmdiagnosticstool.exe
- %windir%\\system32\\msinfo32.exe /report %temp%\\MDMDiagnosticsmsinfo32.log\\
- %windir%\\system32\\netsh.exe advfirewall show allprofiles
- %windir%\\system32\\netsh.exe advfirewall show global
- %windir%\\system32\\netsh.exe LAN ショー プロファイル
- %windir%\\system32\\netsh.exe winhttp show proxy
- %windir%\\system32\\netsh.exe wlan show profiles
- %windir%\\system32\\netsh.exe wlan show wlanreport
- %windir%\\system32\\ping.exe -n 50 localhost
- %windir%\\system32\\powercfg.exe /batteryreport /output %temp%\\MDMDiagnosticsbattery-report.html\\
- %windir%\\system32\\powercfg.exe /energy/output %temp%\\MDMDiagnosticsenergy-report.html\\
- bitsadmin /list /allusers /verbose
- fltMC.exe
- bcdedit /enum all /v
- manage-bde -protectors -get
- Windows PowerShellコマンド:
    - Get-appxpackage -allusers
    - Get-appxpackage -packagetype バンドル
    - Get-Service wuauserv
    - Get-NetFirewallRule
    - Get-WmiObject -Class win32product\_
    - Get-ComputerInfo
    - Get-Service
    - Get-Process
    - Get-WmiObject Win32PnPSignedDriver\_

### <a name="event-logs"></a>イベント ログ

- アプリケーション
- Microsoft-Windows-AppLocker/EXE and DLL
- Microsoft-Windows-AppLocker/MSI and Script
- Microsoft-Windows-AppLocker/Packaged app-Deployment
- Microsoft-Windows-AppLocker/Packaged app-Execution
- Microsoft-Windows-Bitlocker/Bitlocker Management
- Microsoft-Windows-SENSE/Operational
- Microsoft-Windows-SenseIR/Operational
- セットアップ
- System

### <a name="files"></a>ファイル

- %ProgramData%\\MicrosoftDiagnosticLogCSPCollectors.etl\\\\\\\*
- %ProgramData%\\MicrosoftIntuneManagementExtensionLogs\\\\\\\*。\*
- %ProgramData%\\Microsoft\\ Windows Defender\\ SupportMpSupportFiles.cab\\
- %ProgramData%\\Microsoft\\ Windows\\ WlanReportwlan-report-latest.html\\
- %ProgramData%\\Microsoft\\ Windows\\ WlanReport -SourceFileName wlan-report-latest.html
- %windir%\\ccmlogs.log\\\*
- %windir%\\ccmsetuplogs.log\\\*
- %windir%\\logsCBScbs.log\\\\
- %windir%\\logsmeasuredboot\*\\。\*
- %windir%\\LogsWindowsUpdate.etl\\\*
- %windir%\\inf.log\\\*
- %windir%\\サービス\\ActionList.xml\\
- %windir%\\サービス\\Sessions.xml\\
- %windir%\\SoftwareDistributionDataStoreLogsedb.log\\\\\\
- %windir%\\SoftwareDistributionDataStoreDataStore.edb\\\\
- %windir%\\logsdismdism.log\\\\
- %SystemRoot%\\System32WinevtLogs\\\\\\
- %appdata%\\Microsoft\\ Teams\\ media-stack.blog\\\*
- %appdata%\\Microsoft\\ Teams\\ skylib.blog\\\*
- %appdata%\\Microsoft\\ Teams\\ media-stack.etl\\\*
- %appdata%\\Microsoft\\ Teams\\logs.txt
- %windir%Windows\\ System32winevt\\\\\*.\\\*