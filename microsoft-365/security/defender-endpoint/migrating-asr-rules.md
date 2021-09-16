---
title: サードパーティの HIPS から ASR ルールへの移行
description: サードパーティのホスト侵入防止システム (HIPS) ソリューションから ASR ルールへの移行にアプローチする方法について説明します。
keywords: 攻撃表面の縮小ルール、asr、asr ルール、ヒップ、ホスト侵入防止システム、保護ルール、悪用防止、脆弱性対策、悪用、感染防止、Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.topic: article
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: 0c2ffdde4ff259f2a2ef098a6d715cbcd785dfe4
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2021
ms.locfileid: "59401688"
---
# <a name="migrating-from-a-third-party-hips-to-asr-rules"></a>サードパーティの HIPS から ASR ルールへの移行

この記事では、一般的なルールを Microsoft Defender for Endpoint にマップするのに役立ちます。

## <a name="scenarios-when-migrating-from-a-third-party-hips-product-to-asr-rules"></a>サードパーティの HIPS 製品から ASR ルールに移行する場合のシナリオ

### <a name="block-creation-of-specific-files"></a>特定のファイルの作成をブロックする

- **適用対象**- すべてのプロセス
- **操作**- ファイルの作成
- **ファイル/** フォルダー、レジストリ キー/値、プロセス、サービスの例 - *.zepto、*.odin、*.locky、*.jaff、*.lukitus、*.wnry、*.krab
- **攻撃表面の縮小ルール**- ASR ルールは、侵害のインジケーター (IOC) ではなく、攻撃手法をブロックします。 特定のファイル拡張子をブロックしても、デバイスが侵害されるのを防ぐとは限らないので、必ずしも役に立つとは限らない。 攻撃者がペイロードの新しい種類の拡張機能を作成するまで、攻撃を部分的に警告します。
- **その他の推奨機能**- Microsoft Defender AV を有効にし、クラウド保護と動作分析を強くお勧めします。 ASR ルール "ランサムウェアに対する高度な保護を使用する" など、他の予防を使用することをお勧めします。 これにより、ランサムウェア攻撃に対するより高いレベルの保護が提供されます。 さらに、これらのレジストリ キーの多くは、特定のアラートをトリガーする ASEP 手法など、Microsoft Defender for Endpoint によって監視されます。 使用するレジストリ キーには、少なくともローカル管理者特権または信頼できるインストーラー特権を変更する必要があります。 最小限の管理アカウントまたは権限を持つ、ロックダウンされた環境の使用をお勧めします。 その他のシステム構成は、より広範なセキュリティ推奨事項の一部である"必須ではない役割に対して SeDebug を無効にする" など、有効にできます。

### <a name="block-creation-of-specific-registry-keys"></a>特定のレジストリ キーの作成をブロックする

- **適用対象**- すべてのプロセス
- **プロセス**- N/A
- **操作**- レジストリの変更
- **ファイル/フォルダー、レジストリ キー/値、プロセス、サービスの例** - *\Software*,HKCU\Environment\UserInitMprLogonScript,HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs\StartExe,*HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image* File Execution Options \Debugger, HKEY_CURRENT_USER\Software\Microsoft\HtmlHelp Author\location, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SilentProcessExit*\\MonitorProcess
- **攻撃表面の縮小ルール**- ASR ルールは、侵害のインジケーター (IOC) ではなく、攻撃手法をブロックします。 特定のファイル拡張子をブロックしても、デバイスが侵害されるのを防ぐとは限らないため、必ずしも役に立つとは限らない。 攻撃者がペイロードの新しい種類の拡張機能を作成するまで、攻撃を部分的に警告します。
- **その他の推奨機能**- Microsoft Defender AV を有効にし、クラウド保護と動作分析を強くお勧めします。 ASR ルール "ランサムウェアに対する高度な保護を使用する" などの追加の防止を使用することをお勧めします。 これにより、ランサムウェア攻撃に対するより高いレベルの保護が提供されます。 さらに、これらのレジストリ キーのいくつかは、特定のアラートをトリガーする ASEP 手法など、Microsoft Defender for Endpoint によって監視されます。 さらに、使用するレジストリ キーには、少なくともローカル管理者特権または信頼できるインストーラー特権を変更する必要があります。 最小限の管理アカウントまたは権限を持つ、ロックダウンされた環境の使用をお勧めします。 その他のシステム構成は、より広範なセキュリティ推奨事項の一部である"必須ではない役割に対して SeDebug を無効にする" など、有効にできます。

### <a name="block-untrusted-programs-from-running-from-removable-drives"></a>信頼されていないプログラムがリムーバブル ドライブから実行されるのをブロックする

- **適用対象**- USB からの信頼されていないプログラム
- **プロセス**- *
- **操作**- プロセスの実行
- **ファイル/フォルダー、レジストリ キー/値、プロセス、サービスの例:-*
- **攻撃表面** の縮小ルール - ASR ルールには、リムーバブル ドライブからの信頼されていないプログラムと署名されていないプログラムの起動を防止する組み込みのルールがあります。"USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする"、GUID "b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4"。
- **その他の推奨** 機能 - Microsoft Defender for Endpoint を使用して USB デバイスおよび他のリムーバブル メディアの追加コントロールを確認してください。[Microsoft Defender for Endpoint](/windows/security/threat-protection/device-control/control-usb-devices-using-intune)を使用して USB デバイスや他のリムーバブル メディアを制御する方法。

### <a name="block-mshta-from-launching-certain-child-processes"></a>特定の子プロセスの起動から Mshta をブロックする

- **適用対象**- Mshta
- **プロセス**- mshta.exe
- **操作**- プロセスの実行
- **ファイル/フォルダー、レジストリ キー/** 値、プロセス、サービス - powershell.exe、cmd.exe、regsvr32.exe
- **攻撃表面の縮小ルール**- ASR ルールには、子プロセスが "削除" されるのを防ぐための特定のmshta.exe。 このコントロールは、Exploit Protection またはアプリケーション コントロールのWindows Defender内です。
- **その他の推奨機能**- アプリケーションWindows Defenderを有効にして、アプリケーションmshta.exe完全に実行されるのを防ぐ。 組織で業務用アプリの "mshta.exe" が必要な場合は、特定の Windows Defender Exploit Protection ルールを構成して、mshta.exeプロセスの起動を防止します。

### <a name="block-outlook-from-launching-child-processes"></a>子Outlookの起動をブロックする

- **に適用される**- Outlook
- **プロセス**- outlook.exe
- **操作**- プロセスの実行
- **ファイル/フォルダー、レジストリ キー/値、プロセス、サービス** の例 - powershell.exe
- 攻撃 **表面** 縮小ルール - ASR ルールには、Office 通信アプリ (Outlook、Skype、および Teams) が子プロセスを起動するのを防ぐ組み込みのルールがあります。"Office 通信アプリケーションによる子プロセスの作成をブロックする"、GUID "26190899-1602-49e8-8b27-eb1d0a1869"
- **その他の推奨機能**- PowerShell の攻撃表面を最小限に抑えるために、PowerShell の制約付き言語モードを有効にすることをお勧めします。

### <a name="block-office-apps-from-launching-child-processes"></a>アプリOfficeプロセスの起動をブロックする

- **に適用される**- Office
- **プロセス**- winword.exe、powerpnt.exe、excel.exe
- **操作**- プロセスの実行
- **ファイル/フォルダー、レジストリ キー/** 値、プロセス、サービス - powershell.exe、cmd.exe、wscript.exe、mshta.exe、EQNEDT32.EXE、regsrv32.exe
- 攻撃 **表面** の縮小ルール - ASR ルールには、Office アプリが子プロセスを起動するのを防ぐための組み込みのルールがあります。"すべての Office アプリケーションによる子プロセスの作成をブロックする"、GUID "d4f940ab-401b-4efc-aadc-ad5f3c50688a"。
- **その他の推奨機能**- N/A

### <a name="block-office-apps-from-creating-executable-content"></a>アプリOfficeコンテンツの作成をブロックする

- **に適用される**- Office
- **プロセス**- winword.exe、powerpnt.exe、excel.exe
- **操作**- ファイルの作成
- **ファイル/フォルダー、レジストリ キー/値の例** プロセス、サービス - C:\Users ***\AppData.exe、C:\ProgramData**.exe、C:\ProgramData**.com、C:\Users* AppData\Local\Temp **.com、C:\Users*\Downloads**.exe、C:\Users ***\AppData .scf、C:\ProgramData .scf、C**.exe:\Users\Users\Desktop***.exe*
- **攻撃表面の縮小ルール**- N/A。

### <a name="block-wscript-from-reading-certain-types-of-files"></a>Wscript が特定の種類のファイルを読み取るのをブロックする

- **適用対象**- Wscript
- **プロセス**- wscript.exe
- **操作**- ファイルの読み取り
- **ファイル/** フォルダー、レジストリ キー/値、プロセス、サービスの例 - C:\Users *\AppData**.js、C:\Users*\Downloads**.js
- **攻撃表面の縮小** ルール - 信頼性とパフォーマンスの問題により、ASR ルールは特定のプロセスが特定のスクリプト ファイルの種類を読み取るのを防ぐ機能を持っていません。 これらのシナリオから発生する可能性がある攻撃ベクトルを防止するルールがあります。 ルール名は"JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする" です (GUID "d3e037e1-3eb8-44c8-a917-57927947596d" ") および "難読化される可能性のあるスクリプトの実行をブロックする" (GUID " 5beb7efe-fd9a-4556-801d-275e5ffc04cc")。
- その他の推奨機能 **-** これらのシナリオ内には特定の攻撃ベクトルを軽減する特定の ASR ルールが含まれていますが、AV は既定でマルウェア対策スキャン インターフェイス (AMSI) を介してスクリプト (PowerShell、Windows スクリプト ホスト、JavaScript、VBScript など) をリアルタイムで検査できる点に言及することが重要です。 詳しくは、マルウェア対策スキャン インターフェイス [(AMSI) をご覧ください](/windows/win32/amsi/antimalware-scan-interface-portal)。

### <a name="block-launch-of-child-processes"></a>子プロセスの起動をブロックする

- **適用対象**- Adobe Acrobat
- **プロセス**- AcroRd32.exe、Acrobat.exe
- **操作**- プロセスの実行
- **ファイル/フォルダー、レジストリ キー/** 値、プロセス、サービス - cmd.exe、powershell.exe、wscript.exe
- **攻撃表面の縮小ルール**- ASR ルールを使用すると、Adobe Reader による子プロセスの起動をブロックできます。 ルール名は"Block Adobe Reader from creating child processes", GUID "7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c" です。
- **その他の推奨機能**- N/A

### <a name="block-download-or-creation-of-executable-content"></a>実行可能コンテンツのダウンロードまたは作成をブロックする

- **適用対象**- CertUtil: 実行可能ファイルのダウンロードまたは作成をブロックする
- **プロセス**- certutil.exe
- **操作**- ファイルの作成
- **ファイル/フォルダー、レジストリ キー/** 値、プロセス、サービスの例 - *.exe
- **攻撃表面の縮小ルール**- ASR ルールは、セキュリティ保護の一部なので、これらのシナリオをMicrosoft Defender ウイルス対策しません。
- **その他の推奨機能**- Microsoft Defender AV では、CertUtil が実行可能なコンテンツを作成またはダウンロードできません。

### <a name="block-processes-from-stopping-critical-system-components"></a>重要な System コンポーネントを停止するプロセスをブロックする

- **適用対象**- すべてのプロセス
- **プロセス**- *
- **操作**- プロセスの終了
- **ファイル/** フォルダー、レジストリ キー/値、プロセス、サービス - MsSense.exe、MsMpEng.exe、NisSrv.exe、svchost.exe*、services.exe、csrss.exe、smss.exe、wininit.exe など。
- **攻撃表面の縮小ルール**- ASR ルールは、組み込みのセキュリティ保護で保護Windows 10シナリオをサポートしません。
- **その他の推奨** 機能 - ELAM (早期起動マルウェア対策)、PPL (Protection Process Light)、PPL AntiMalware Light、System Guard。

### <a name="block-specific-launch-process-attempt"></a>特定の起動プロセスの試行をブロックする

- **適用対象**- 特定のプロセス
- **プロセス**- "Name your Process"
- **操作**- プロセスの実行
- **ファイル/フォルダー、レジストリ** キー/値、プロセス、サービス - tor.exe、bittorrent.exe、cmd.exe、powershell.exe など
- **攻撃表面の縮小ルール**- 全体的に、ASR ルールはアプリケーション マネージャーとして機能するように設計されていない。
- **その他の推奨機能**- ユーザーが特定のプロセスまたはプログラムを起動Windows Defender勧めします。 Microsoft Defender for Endpoint File および Cert インジケーターは、インシデント対応シナリオで使用できます (アプリケーション制御メカニズムとして見るべきではない)。

### <a name="block-unauthorized-changes-to-microsoft-defender-antivirus-configurations"></a>構成に対する承認されていないMicrosoft Defender ウイルス対策ブロックする

- **適用対象**- すべてのプロセス
- **プロセス**- *
- **操作**- レジストリの変更
- ファイル/フォルダー、レジストリ キー **/** 値、プロセス、サービス - HKLM\SOFTWARE\Policyes\Microsoft\Windows Defender\DisableAntiSpyware、HKLM\SOFTWARE\Policyes\Microsoft\Windows Defender\Policy Manager\AllowRealTimeMonitoring など。
- **攻撃表面の縮小ルール**- ASR ルールは Microsoft Defender for Endpoint 組み込み保護の一部なので、これらのシナリオをカバーしません。
- その他の推奨機能 **-** タンパープロテクション (オプトイン、Intune から管理) は、DisableAntiVirus、DisableAntiSpyware、DisableRealtimeMonitoring、DisableOnAccessProtection、DisableBehaviorMonitoring、DisableIOAVProtection レジストリ キー (その他) に対する承認されていない変更を防止します。

関連項目

- [攻撃面の減少の FAQ](attack-surface-reduction-faq.yml)
- [攻撃面の減少ルールを有効にする](enable-attack-surface-reduction.md)
- [攻撃面の減少ルールを評価する](evaluate-attack-surface-reduction.md)
