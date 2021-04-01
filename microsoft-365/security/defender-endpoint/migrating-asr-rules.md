---
title: サードパーティの HIPS から ASR ルールへの移行
description: サードパーティのホスト侵入防止システム (HIPS) ソリューションから ASR ルールへの移行にアプローチする方法について説明します。
keywords: 攻撃表面の縮小ルール、asr、asr ルール、ヒップ、ホスト侵入防止システム、保護ルール、悪用防止、脆弱性対策、悪用、感染防止、Microsoft Defender for Endpoint、Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
ms.topic: article
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: ced969fdd3e8b63136f8bd3f043272e76d99bc5e
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476550"
---
# <a name="migrating-from-a-third-party-hips-to-asr-rules"></a>サードパーティの HIPS から ASR ルールへの移行

この記事では、一般的なルールを Microsoft Defender for Endpoint にマップするのに役立ちます。 次の表に、サードパーティの HIPS 製品から ASR ルールに移行する際の一般的な質問とシナリオを示します。

|スコープとアクション|プロセス|操作​​|ファイル/フォルダー、レジストリ キー/値、プロセス、サービスの例|攻撃表面の縮小ルール|その他の推奨機能|
|:--|:--|:--|:--|:--|:--|
|すべてのプロセス: 特定のファイルとレジストリ キーの作成をブロックする||ファイルの作成|*.zepto、*.odin、*.locky、*.jaff、*.lukitus、*.wnry、*.krab|ASR ルールは、侵害のインジケーター (IOC) ではなく攻撃手法をブロックします。 特定のファイル拡張子をブロックしても、デバイスが侵害されるのを防ぐとは限らないため、必ずしも役に立つとは限らない。 攻撃者がペイロードの新しい種類の拡張機能を作成するまで、攻撃を部分的に警告します。|Microsoft Defender AV を有効にし、クラウド保護と動作分析を強くお勧めします。 ASR ルール "ランサムウェアに対する高度な保護を使用する" など、その他の予防を使用してください。 これにより、ランサムウェア攻撃に対するより高いレベルの保護が提供されます。 さらに、これらのレジストリ キーのいくつかは、特定のアラートをトリガーする ASEP 手法など、Microsoft Defender for Endpoint によって監視されます。 使用するレジストリ キーを変更するには、少なくともローカル管理者特権または信頼済みインストーラー特権が必要です。 最小限の管理アカウントまたは権限を持つ、ロックダウンされた環境の使用をお勧めします。 その他のシステム構成は、より広範なセキュリティ推奨事項の一部である"必須ではない役割に対して SeDebug を無効にする" など、有効にできます。|
|すべてのプロセス: 特定のファイルとレジストリ キーの作成をブロックする||レジストリの変更|*\Software \* ,HKCU\Environment\UserInitMprLogonScript,HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs\StartExe, \* HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options \* \Debugger,HKEY_CURRENT_USER\Software\Microsoft\HtmlHelp Author\location,HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SilentProcessExit\MonitorProcess \*|ASR ルールは、侵害のインジケーター (IOC) ではなく攻撃手法をブロックします。 特定のファイル拡張子をブロックしても、デバイスが侵害されるのを防ぐとは限らないため、必ずしも役に立つとは限らない。 攻撃者がペイロードの新しい種類の拡張機能を作成するまで、攻撃を部分的に警告します。|Microsoft Defender AV を有効にし、クラウド保護と動作分析を強くお勧めします。 ASR ルール "ランサムウェアに対する高度な保護を使用する" などの追加の防止を使用してください。 これにより、ランサムウェア攻撃に対するより高いレベルの保護が提供されます。 さらに、これらのレジストリ キーのいくつかは、特定のアラートをトリガーする ASEP 手法など、Microsoft Defender for Endpoint によって監視されます。 さらに、使用するレジストリ キーを変更するには、少なくともローカル管理者特権または信頼済みインストーラー特権が必要です。 最小限の管理アカウントまたは権限を持つ、ロックダウンされた環境の使用をお勧めします。 その他のシステム構成は、より広範なセキュリティ推奨事項の一部である"必須ではない役割に対して SeDebug を無効にする" など、有効にできます。|
|USB からの信頼されていないプログラム: 信頼されていないプログラムがリムーバブル ドライブから実行されるのをブロックする|*|プロセスの実行|*|ASR ルールには、リムーバブル ドライブからの信頼されていないプログラムと署名されていないプログラムの起動を防止する組み込みのルールがあります。"USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする"、GUID "b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4"。|Microsoft Defender for Endpoint を使用して USB デバイスおよび他のリムーバブル メディアの追加コントロールを確認してください。 [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/device-control/control-usb-devices-using-intune)を使用して USB デバイスや他のリムーバブル メディアを制御する方法。 |
|Mshta: 特定の子プロセスの起動から Mshta をブロックする|mshta.exe|プロセスの実行|powershell.exe、cmd.exe、regsvr32.exe|ASR ルールには、子プロセスが "削除" されるのを防ぐための特定のルールmshta.exe。 このコントロールは、Exploit Protection またはアプリケーションコントロールのWindows Defender内です。|アプリケーションWindows Defenderを有効にして、アプリケーションmshta.exeが完全に実行されるのを防ぐ。 組織で一行のビジネス アプリに対して "mshta.exe" が必要な場合は、特定の Windows Defender Exploit Protection ルールを構成して、mshta.exeが子プロセスを起動mshta.exe防止します。|
|Outlook: 子プロセスの起動から Outlook をブロックする|outlook.exe|プロセスの実行|powershell.exe|ASR ルールには、Office 通信アプリ (Outlook、Skype、Teams) による子プロセスの起動を防止するための組み込みのルールがあります。"Office 通信アプリケーションによる子プロセスの作成をブロックする"、GUID "26190899-1602-49e8-8b27-eb1d0a1ce869"|PowerShell からの攻撃表面を最小限に抑えるために、PowerShell の制約付き言語モードを有効にすることをお勧めします。|
|Office: Officeプロセスの起動と実行可能コンテンツの作成をブロックする|winword.exe、powerpnt.exe、excel.exe|プロセスの実行|powershell.exe、cmd.exe、wscript.exe、mshta.exe、EQNEDT32.EXE、regsrv32.exe|ASR ルールには、Office アプリによる子プロセスの起動を防ぐための組み込みのルールがあります。"すべての Office アプリケーションによる子プロセスの作成をブロックする"、GUID "D4F940AB-401B-4EFC-AADC-AD5F3C50688A"。|N/A|
|Office: Officeプロセスの起動と実行可能コンテンツの作成をブロックする|winword.exe、powerpnt.exe、excel.exe|ファイルの作成|C:\Users \* \AppData \* *\* .exe, \* C:\ProgramData .exe,* \* C:\ProgramData \* *\* .com, C:\Users \* AppData\Local\Temp \** \* .com, \* C:\Users *\Downloads \** \* .exe, C:\Users \* \AppData \* *\* \* .scf, C:\ProgramData .scf, C:\Users\Public* \* \* \* \* * \* .exe, C:\Users \Desktop .exe|N/A|
|Wscript: Wscript が特定の種類のファイルを読み取るのをブロックする|wscript.exe|ファイルの読み取り|C:\Users \* \AppData \* *\* .js*、 C:\Users \* \Downloads \* *\* .js*|信頼性とパフォーマンスの問題により、ASR ルールには、特定のプロセスが特定のスクリプト ファイルの種類を読み取るのを防ぐ機能が備え付けなっていません。 これらのシナリオから発生する可能性がある攻撃ベクトルを防止するルールがあります。 ルール名は"JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする" です (GUID "D3E037E1-3EB8-44C8-A917-57927947596D" ") および "難読化される可能性のあるスクリプトの実行をブロックする" (GUID " 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC")|これらのシナリオには特定の攻撃ベクトルを軽減する特定の ASR ルールが含まれていますが、AV は既定で、マルウェア対策スキャン インターフェイス (AMSI) を介してスクリプト (PowerShell、Windows スクリプト ホスト、JavaScript、VBScript など) をリアルタイムで検査できる点に言及することが重要です。 詳しくは、マルウェア対策スキャン インターフェイス [(AMSI) をご覧ください](https://docs.microsoft.com/windows/win32/amsi/antimalware-scan-interface-portal)。 |
|Adobe Acrobat: 子プロセスの起動をブロックする|AcroRd32.exe、Acrobat.exe|プロセスの実行|cmd.exe、powershell.exe、wscript.exe|ASR ルールを使用すると、Adobe Reader による子プロセスの起動をブロックできます。 ルール名は"Block Adobe Reader from creating child processes", GUID "7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c" です。|N/A|
|CertUtil: 実行可能コンテンツのダウンロードまたは作成をブロックする|certutil.exe|ファイルの作成|*.exe|ASR ルールは、Microsoft Defender ウイルス対策保護の一部なので、これらのシナリオをサポートしません。|Microsoft Defender AV は、CertUtil が実行可能なコンテンツを作成またはダウンロードするのを防止します。|
|すべてのプロセス: 重要なシステム コンポーネントを停止するプロセスをブロックする|*|プロセスの終了|MsSense.exe、MsMpEng.exe、NisSrv.exe、svchost.exe*、services.exe、csrss.exe、smss.exe、wininit.exeなど。|ASR ルールは、Windows 10 組み込みのセキュリティ保護で保護されたため、これらのシナリオをサポートしません。|ELAM (早期起動マルウェア対策)、PPL (保護プロセス ライト)、PPL マルウェア対策ライト、および System Guard。|
|特定のプロセス: 特定の起動プロセスの試行をブロックする|"プロセスに名前を付け"|プロセスの実行|tor.exe、bittorrent.exe、cmd.exe、powershell.exeなど。|全体的に、ASR ルールはアプリケーション マネージャーとして機能するようには設計されていない。|ユーザーが特定のプロセスまたはプログラムを起動しに行かねない場合は、アプリケーションコントロールを使用Windows Defender勧めになります。 Microsoft Defender for Endpoint File および Cert インジケーターは、インシデント対応シナリオで使用できます (アプリケーション制御メカニズムとして見る必要はありません)。|
|すべてのプロセス: MDATP AV 構成への未承認の変更をブロックする|*|レジストリの変更|HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\DisableAntiSpyware,HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\AllowRealTimeMonitoring など|ASR ルールは、Microsoft Defender for Endpoint 組み込み保護の一部なので、これらの種類のシナリオについては説明しません。|タンパー プロテクション (オプトイン、Intune から管理) は、DisableAntiVirus、DisableAntiSpyware、DisableRealtimeMonitoring、DisableOnAccessProtection、DisableBehaviorMonitoring、DisableIOAVProtection レジストリ キー (その他) への不正な変更を防止します。 |



関連項目

- [攻撃面の減少の FAQ](attack-surface-reduction-faq.md)
- [攻撃面の減少ルールを有効にする](enable-attack-surface-reduction.md)
- [攻撃面の減少ルールを評価する](evaluate-attack-surface-reduction.md)
