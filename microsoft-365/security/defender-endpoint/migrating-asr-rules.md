---
title: サード パーティの HIPS から ASR ルールへの移行
description: サード パーティのホスト侵入防止システム (HIPS) ソリューションから ASR ルールへの移行にアプローチする方法について説明します。
keywords: 攻撃面の縮小ルール、asr、asr ルール、hips、ホスト侵入防止システム、保護ルール、アンチエクスプロイト、アンチエクスプロイト、エクスプロイト、感染防止、Microsoft Defender for Endpoint
ms.topic: article
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: lovina-saldanha
ms.author: dansimp
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 7e07f4a40bc7ef73dd04dbe9eb114ea7eb1e080c
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67384393"
---
# <a name="migrating-from-a-third-party-hips-to-asr-rules"></a>サード パーティの HIPS から ASR ルールへの移行

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

この記事では、一般的なルールをMicrosoft Defender for Endpointにマップするのに役立ちます。

## <a name="scenarios-when-migrating-from-a-third-party-hips-product-to-asr-rules"></a>サードパーティの HIPS 製品から ASR ルールに移行する場合のシナリオ

### <a name="block-creation-of-specific-files"></a>特定のファイルの作成をブロックする

- **適用対象** - すべてのプロセス
- **Operation**- File Creation
- **ファイル/フォルダー、レジストリ キー/値、プロセス、サービスの例** - *.ze pdb、*.odin、*.locky、*.jaff、*.lukitus、*.wnry、*.krab
- **攻撃表面の縮小ルール**- ASR ルールは、侵害のインジケーター (IOC) ではなく、攻撃手法をブロックします。 特定のファイル拡張子をブロックすると、デバイスが侵害されるのを防ぐわけではないため、必ずしも役に立つとは限りません。 攻撃者がペイロードの新しい種類の拡張機能を作成するまで、攻撃は部分的にしか阻止されません。
- **その他の推奨される機能** - Microsoft Defender ウイルス対策を有効にし、Cloud Protection および Behavior Analysis を使用することを強くお勧めします。 ASR 規則 「ランサムウェアに対する高度な保護を使用する」など、他の防止を使用することをお勧めします。 これにより、ランサムウェア攻撃に対するより高いレベルの保護が提供されます。 さらに、これらのレジストリ キーの多くは、ASEP 手法などのMicrosoft Defender for Endpointによって監視され、特定のアラートがトリガーされます。 使用するレジストリ キーには、ローカル 管理または信頼されたインストーラーの特権を変更する必要があります。 最小限の管理アカウントまたは権限を持つロックダウンされた環境を使用することをお勧めします。 その他のシステム構成を有効にできます。これには、広範なセキュリティに関する推奨事項の一部である "必要でないロールの SeDebug を無効にする" などです。

### <a name="block-creation-of-specific-registry-keys"></a>特定のレジストリ キーの作成をブロックする

- **適用対象** - すべてのプロセス
- **プロセス** - N/A
- **操作** - レジストリの変更
- **ファイル/フォルダー、レジストリ キー/値、プロセス、サービス**- の例 *\Software,HKCU*\Environment\UserInitMprLogonScript,HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs *\StartExe, HKLM\Microsoft\Windows NT\CurrentVersion\Image File Execution Options\Debugger*, HKEY_CURRENT_USER\Software\Microsoft\HtmlHelp Author\location, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SilentProcessExit*\MonitorProcessProcesse
- **攻撃表面の縮小ルール**- ASR ルールは、侵害のインジケーター (IOC) ではなく、攻撃手法をブロックします。 特定のファイル拡張子をブロックすると、デバイスが侵害されるのを防ぐわけではないため、必ずしも役に立つとは限りません。 攻撃者がペイロードの新しい種類の拡張機能を作成するまで、攻撃は部分的にしか阻止されません。
- **その他の推奨される機能** - Microsoft Defender ウイルス対策を有効にし、Cloud Protection および Behavior Analysis を使用することを強くお勧めします。 ASR 規則 「ランサムウェアに対する高度な保護を使用する」など、追加の防止を使用することをお勧めします。 これにより、ランサムウェア攻撃に対するより高いレベルの保護が提供されます。 さらに、これらのレジストリ キーの一部は、ASEP 手法などのMicrosoft Defender for Endpointによって監視され、特定のアラートがトリガーされます。 さらに、使用するレジストリ キーには、ローカル 管理または信頼されたインストーラーの特権を変更する必要があります。 最小限の管理アカウントまたは権限を持つロックダウンされた環境を使用することをお勧めします。 その他のシステム構成を有効にできます。これには、広範なセキュリティに関する推奨事項の一部である "必要でないロールの SeDebug を無効にする" などです。

### <a name="block-untrusted-programs-from-running-from-removable-drives"></a>信頼されていないプログラムがリムーバブル ドライブから実行されないようにブロックする

- **適用対象** - USB から信頼されていないプログラム
- **プロセス**- *
- **操作** - プロセスの実行
- **ファイル/フォルダー、レジストリ キー/値、プロセス、サービスの例:-*
- **攻撃 Surface Reduction ルール**- ASR ルールには、リムーバブル ドライブからの信頼されていないプログラムと署名されていないプログラムの起動を防ぐための組み込みの規則があります。"USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする"、GUID "b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4"。
- **その他の推奨機能**- Microsoft Defender for Endpointを使用して USB デバイスやその他のリムーバブル メディアの追加のコントロールを調べてください:[Microsoft Defender for Endpointを使用して USB デバイスやその他のリムーバブル メディアを制御する方法](/windows/security/threat-protection/device-control/control-usb-devices-using-intune)。

### <a name="block-mshta-from-launching-certain-child-processes"></a>特定の子プロセスの起動から Mshta をブロックする

- **適用対象** - Mshta
- **プロセス**- mshta.exe
- **操作** - プロセスの実行
- **ファイル/フォルダー、レジストリ キー/値、プロセス、サービス**- powershell.exe、cmd.exe、regsvr32.exeの例
- **攻撃表面の縮小ルール**- ASR ルールには、子プロセスが "mshta.exe" されないようにするための特定のルールは含まれていません。 このコントロールは、Exploit Protection または Windows Defender アプリケーション制御の送金内にあります。
- **その他の推奨される機能** - Windows Defenderアプリケーション制御を有効にして、mshta.exeが完全に実行されないようにします。 組織で基幹業務アプリに "mshta.exe" が必要な場合は、特定のWindows Defender Exploit Protection ルールを構成して、mshta.exeが子プロセスを起動できないようにします。

### <a name="block-outlook-from-launching-child-processes"></a>Outlook による子プロセスの起動をブロックする

- **適用対象** - Outlook
- **プロセス**- outlook.exe
- **操作** - プロセスの実行
- **ファイル/フォルダー、レジストリ キー/値、プロセス、サービス- powershell.exeの例**
- **攻撃表面の削減ルール**- ASR ルールには、Office 通信アプリ (Outlook、Skype、Teams) が子プロセスを起動できないようにする組み込みの規則があります。"Office 通信アプリケーションによる子プロセスの作成をブロックする"、GUID "26190899-1602-49e8-8b27-eb1d0a1ce869"
- **その他の推奨される機能** - PowerShell からの攻撃面を最小限に抑えるために、PowerShell の制約付き言語モードを有効にすることをお勧めします。

### <a name="block-office-apps-from-launching-child-processes"></a>Office Apps による子プロセスの起動をブロックする

- **Office に適用されます**
- **プロセス**- winword.exe、powerpnt.exe、excel.exe
- **操作** - プロセスの実行
- **ファイル/フォルダー、レジストリ キー/値、プロセス、サービス**- powershell.exe、cmd.exe、wscript.exe、mshta.exe、EQNEDT32.EXE、regsrv32.exeの例
- **攻撃 Surface Reduction ルール** - ASR ルールには、Office アプリが子プロセスを起動できないようにする組み込みの規則があります。"すべての Office アプリケーションが子プロセスを作成できないようにする"、GUID "d4f940ab-401b-4efc-aadc-ad5f3c50688a"
- **その他の推奨機能** - N/A

### <a name="block-office-apps-from-creating-executable-content"></a>Office Apps での実行可能コンテンツの作成をブロックする

- **Office に適用されます**
- **プロセス**- winword.exe、powerpnt.exe、excel.exe
- **Operation**- File Creation
- **ファイル/フォルダーの例、レジストリ キー/値、 プロセス、サービス**- C:\Users *\AppData **.exe、C:\ProgramData**.exe、C:\ProgramData**.com、C:\Users* AppData\Local\**Temp.com、C:\Users*\Downloads**.exe、C:\Users *\AppData.scf **、C:\ProgramData.scf、C:\** Users\Public*.exe、C:\Users*\Desktop***.exe
- **攻撃表面の縮小ルール** - N/A。

### <a name="block-wscript-from-reading-certain-types-of-files"></a>特定の種類のファイルの読み取りから Wscript をブロックする

- **適用対象** - Wscript
- **プロセス**- wscript.exe
- **Operation**- File Read
- **ファイル/フォルダー、レジストリ キー/値、プロセス、サービスの例**- C:\Users *\AppData**.js、C:\Users*\Downloads**.js
- **攻撃表面の縮小ルール**- 信頼性とパフォーマンスの問題により、ASR ルールには、特定のプロセスが特定のスクリプト ファイルの種類を読み取らないようにする機能はありません。 これらのシナリオから発生する可能性がある攻撃ベクトルを防ぐルールがあります。 ルール名は "ダウンロードした実行可能コンテンツの起動から JavaScript または VBScript をブロックする" です (GUID "d3e037e1-3eb8-44c8-a917-57927947596d ") と "難読化される可能性があるスクリプトの実行をブロックする" (GUID " 5beb7efe-fd9a-4556-801d-275e5ffc04cc")。
- **その他の推奨機能** - これらのシナリオ内で特定の攻撃ベクトルを軽減する特定の ASR ルールがありますが、AV は既定でマルウェア対策スキャン インターフェイス (AMSI) を介してスクリプト (PowerShell、Windows スクリプト ホスト、JavaScript、VBScript など) をリアルタイムで検査できることに言及することが重要です。 詳細については、 [マルウェア対策スキャン インターフェイス (AMSI)](/windows/win32/amsi/antimalware-scan-interface-portal) を参照してください。

### <a name="block-launch-of-child-processes"></a>子プロセスの起動をブロックする

- **Adobe Acrobat に適用されます**
- **プロセス**- AcroRd32.exe、Acrobat.exe
- **操作** - プロセスの実行
- **ファイル/フォルダー、レジストリ キー/値、プロセス、サービス**- cmd.exe、powershell.exe、wscript.exeの例
- **攻撃 Surface Reduction ルール** - ASR ルールを使用すると、Adobe Reader による子プロセスの起動をブロックできます。 ルール名は"子プロセスの作成から Adobe Reader をブロックする"、GUID "7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c" です。
- **その他の推奨機能** - N/A

### <a name="block-download-or-creation-of-executable-content"></a>実行可能コンテンツのダウンロードまたは作成をブロックする

- **適用対象**- CertUtil: 実行可能ファイルのダウンロードまたは作成をブロックする
- **プロセス**- certutil.exe
- **Operation**- File Creation
- **ファイル/フォルダー、レジストリ キー/値、プロセス、サービスの例** - *.exe
- **攻撃表面の縮小ルール**- ASR ルールは、Microsoft Defender ウイルス対策保護の一部であるため、これらのシナリオをサポートしていません。
- **その他の推奨される機能** - Microsoft Defender ウイルス対策では、CertUtil が実行可能コンテンツを作成またはダウンロードできないようにします。

### <a name="block-processes-from-stopping-critical-system-components"></a>重要なシステム コンポーネントを停止するプロセスをブロックする

- **適用対象** - すべてのプロセス
- **プロセス**- *
- **操作** - プロセス終了
- **ファイル/フォルダー、レジストリ キー/値、プロセス、サービス**- MsSense.exe、MsMpEng.exe、NisSrv.exe、svchost.exe*、services.exe、csrss.exe、smss.exe、wininit.exeなどの例。
- **攻撃表面の削減規則** - ASR ルールでは、Windows 組み込みのセキュリティ保護で保護されているため、これらのシナリオはサポートされません。
- **その他の推奨機能** - ELAM (早期起動マルウェア対策)、PPL (保護プロセス ライト)、PPL マルウェア対策ライト、および System Guard。

### <a name="block-specific-launch-process-attempt"></a>特定の起動プロセス試行をブロックする

- **適用対象** の特定のプロセス
- **プロセス** - "プロセスに名前を付けます"
- **操作** - プロセスの実行
- **ファイル/フォルダー、レジストリ キー/値、プロセス、サービス**- tor.exe、bittorrent.exe、cmd.exe、powershell.exeなどの例
- **攻撃表面の縮小ルール**- 全体的に見ると、ASR ルールはアプリケーション マネージャーとして機能するようには設計されていません。
- **その他の推奨される機能** - ユーザーが特定のプロセスまたはプログラムを起動できないようにするには、Windows Defenderアプリケーション制御を使用することをお勧めします。 Microsoft Defender for Endpointファイルインジケーターと証明書インジケーターは、インシデント対応シナリオで使用できます (アプリケーション制御メカニズムとは見なされません)。

### <a name="block-unauthorized-changes-to-microsoft-defender-antivirus-configurations"></a>Microsoft Defender ウイルス対策の構成に対する未承認の変更をブロックする

- **適用対象** - すべてのプロセス
- **プロセス**- *
- **操作** - レジストリの変更
- **ファイル/フォルダー、レジストリ キー/値、プロセス、サービスの例** - HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\DisableAntiSpyware、HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\AllowRealTimeMonitoring など。
- **攻撃表面の縮小ルール**- ASR ルールは、組み込みの保護の一部であるため、これらのシナリオMicrosoft Defender for Endpoint対象としません。
- **その他の推奨機能** - 改ざん防止 (オプトイン、Intuneから管理) により、DisableAntiVirus、DisableAntiSpyware、DisableRealtimeMonitoring、DisableOnAccessProtection、DisableBehaviorMonitoring、DisableIOAVProtection レジストリ キー (その他) に対する不正な変更が防止されます。

関連項目

- [攻撃面の減少の FAQ](attack-surface-reduction-faq.yml)
- [攻撃面の減少ルールを有効にする](enable-attack-surface-reduction.md)
- [攻撃面の減少ルールを評価する](evaluate-attack-surface-reduction.md)
