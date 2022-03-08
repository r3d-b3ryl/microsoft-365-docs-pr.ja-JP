---
title: 攻撃表面の縮小ルールのリファレンス
description: ルールごとに攻撃表面の縮小ルールに関する詳細を一覧表示します。
keywords: 攻撃表面の縮小ルール、ASR、asr ルール、ヒップ、ホスト侵入防止システム、保護ルール、悪用防止ルール、悪用防止ルール、悪用ルール、感染防止ルール、Microsoft Defender for Endpoint、CONFIGURE ASR ルール、ASR ルールの説明
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar,
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.date: 02/04/2022
ms.openlocfilehash: 5ffbe15fe9fa06e7c06546f9452d6c4f2bddfc39
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63329615"
---
# <a name="attack-surface-reduction-rules-reference"></a>攻撃表面の縮小ルールのリファレンス

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

この記事では、攻撃の軽減ルールに関する情報を提供します。

- [サポートされているオペレーティング システムのバージョン](#supported-operating-systems)
- [サポートされている構成管理システム](#supported-configuration-management-systems)
- [ルールごとのアラートと通知の詳細](#per-rule-alert-and-notification-details)
- [ルールごとの説明](#per-rule-descriptions)
  - ルールの説明
  - GUID
  - 構成管理システムのルール名

## <a name="public-preview-supported-operating-systems"></a>パブリック プレビュー: サポートされているオペレーティング システム

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

次の表に、現在プレリリース製品である攻撃表面縮小ルールでサポートされているオペレーティング システムの一覧を示します。 ルールはアルファベット順に表示されます。 特に指定しない限り、最小 Windows&nbsp; 10 ビルドはバージョン 1709 (RS3、ビルド 16299) 以降です。最小 Windows&nbsp; Server ビルドはバージョン 1809 以降です。

> [!NOTE]
> Windows Server2012R2&nbsp;&nbsp; および Windows&nbsp;&nbsp; Server2016&nbsp; の攻撃表面縮小ルールは、最新の統合ソリューション パッケージを使用してオンボードされたデバイスで使用できます。 詳細については、「[R2 および 2016 Preview](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview) の最新の統合ソリューションのWindows Server 2012」を参照してください。
>

| ルールの名前 | &nbsp;Windows Server 2016 <sup>[[1](#fn1)]<sup></sup> | &nbsp;Windows Server 2012 R2 <sup>[[1](#fn1)]<sup></sup> |
|---|:---:|:---:|
|[悪用された脆弱な署名済みドライバーの悪用をブロックする](#block-abuse-of-exploited-vulnerable-signed-drivers) | Y | Y |
|[Adobe Reader の子プロセスの作成をブロックする](#block-adobe-reader-from-creating-child-processes) | Y | Y |
|[すべてのアプリケーションOffice子プロセスの作成をブロックする](#block-all-office-applications-from-creating-child-processes) | Y | Y |
|[ローカル セキュリティ機関サブシステムからの資格情報のWindowsをブロックする (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | Y | Y |
|[メール クライアントと Web メールから実行可能なコンテンツをブロックする](#block-executable-content-from-email-client-and-webmail) | Y | Y |
|[有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | Y | Y |
|[難読化される可能性のあるスクリプトの実行をブロックする](#block-execution-of-potentially-obfuscated-scripts) | Y | Y |
|[JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | N | N |
|[実行可能Office作成するアプリケーションをブロックする](#block-office-applications-from-creating-executable-content) | Y | Y |
|[アプリケーションOffice他のプロセスへのコードの挿入をブロックする](#block-office-applications-from-injecting-code-into-other-processes)  | Y | Y |
|[通信Office子プロセスの作成をブロックする](#block-office-communication-application-from-creating-child-processes) | Y | Y |
|[WMI イベント サブスクリプションによる永続化のブロック](#block-persistence-through-wmi-event-subscription) \*_ファイルとフォルダーの除外はサポートされていません。_ | N | N |
|[PSExec および WMI コマンドから発生するプロセス作成をブロックする](#block-process-creations-originating-from-psexec-and-wmi-commands) | Y | Y |
|[USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする](#block-untrusted-and-unsigned-processes-that-run-from-usb) | Y | Y |
|[Win32 API 呼び出しをブロックOfficeマクロ](#block-win32-api-calls-from-office-macros) | N | N |
|[ランサムウェアに対する高度な保護の使用](#use-advanced-protection-against-ransomware) | Y | Y |
|  |  |  |

(<a id="fn1">1</a>) 2016 年と 2016 年の最新の統合ソリューションをWindows Server 2012します。 詳細については、「Defender [for Endpoint サービスへのオンボード Windows サーバー」を参照してください](configure-server-endpoints.md)。

_パブリック プレビューの終了: サポートされているオペレーティング システム_

## <a name="supported-operating-systems"></a>サポートされるオペレーティング システム

次の表に、現在一般提供にリリースされているルールでサポートされているオペレーティング システムの一覧を示します。 ルールはアルファベット順に表示されます。

> [!Note]
>
> 特に指定しない限り、最小 Windows&nbsp; 10 ビルドはバージョン 1709 (RS3、ビルド 16299) 以降です。最小 Windows&nbsp; Server ビルドはバージョン 1809 以降です。
>

|ルールの名前|&nbsp;Windows 10|&nbsp;Windows Server 2019|&nbsp;Windows Server|
|---|:---:|:---:|:---:|
|[悪用された脆弱な署名済みドライバーの悪用をブロックする](#block-abuse-of-exploited-vulnerable-signed-drivers) | Y | Y | Y <br><br> バージョン 1803 (半期チャネル) 以降 |
|[Adobe Reader の子プロセスの作成をブロックする](#block-adobe-reader-from-creating-child-processes) | Y バージョン 1809 以降 | Y | Y  <br><br> |
|[すべてのアプリケーションOffice子プロセスの作成をブロックする](#block-all-office-applications-from-creating-child-processes) | Y | Y | Y <br><br> |
|[ローカル セキュリティ機関サブシステムからの資格情報のWindowsをブロックする (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | Y バージョン 1803 以降 | Y <br><br> | Y <br><br> |
|[メール クライアントと Web メールから実行可能なコンテンツをブロックする](#block-executable-content-from-email-client-and-webmail) | Y | Y <br><br> | Y <br><br> |
|[有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | Y バージョン 1803 以降 | Y <br><br> | Y <br><br> |
|[難読化される可能性のあるスクリプトの実行をブロックする](#block-execution-of-potentially-obfuscated-scripts) | Y | Y <br><br> | Y <br><br> |
|[JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | Y | Y <br><br> | Y <br><br> |
|[実行可能Office作成するアプリケーションをブロックする](#block-office-applications-from-creating-executable-content) | Y | Y <br><br> | Y <br><br> |
|[アプリケーションOffice他のプロセスへのコードの挿入をブロックする](#block-office-applications-from-injecting-code-into-other-processes)  | Y | Y <br><br> | Y <br><br> |
|[通信Office子プロセスの作成をブロックする](#block-office-communication-application-from-creating-child-processes) | Y | Y <br><br> | Y <br><br> |
|[WMI イベント サブスクリプションによる永続化のブロック](#block-persistence-through-wmi-event-subscription) <br><br> \*_ファイルとフォルダーの除外はサポートされていません。_ | Y バージョン 1903 (ビルド 18362) 以降| Y | Y <br><br> バージョン 1903 (ビルド 18362) 以降 |
|[PSExec および WMI コマンドから発生するプロセス作成をブロックする](#block-process-creations-originating-from-psexec-and-wmi-commands) | Y バージョン 1803 以降 | Y <br><br> | Y <br><br>  |
|[USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする](#block-untrusted-and-unsigned-processes-that-run-from-usb) | Y | Y <br><br> | Y <br><br> |
|[Win32 API 呼び出しをブロックOfficeマクロ](#block-win32-api-calls-from-office-macros) | Y | Y <br><br> | Y <br><br> |
|[ランサムウェアに対する高度な保護の使用](#use-advanced-protection-against-ransomware) | Y バージョン 1803 以降 | Y <br><br> | Y <br><br> |
|  |  |  |  |

## <a name="supported-configuration-management-systems"></a>サポートされている構成管理システム

この表で参照されている構成管理システムのバージョンに関する情報へのリンクは、次の表の下に示します。

|ルールの名前 | Intune | Microsoft エンドポイント マネージャー |Microsoft Endpoint Configuration Manager |グループ ポリシー<sup>[[1](#fn1)]<sup></sup> | PowerShell<sup>[[1](#fn1)]<sup></sup>  |
|---|:---:|:---:|:---:|:---:|:---:|
|[悪用された脆弱な署名済みドライバーの悪用をブロックする](#block-abuse-of-exploited-vulnerable-signed-drivers) | Y  | Y MEM OMA-URI |   | Y  |  Y |
|[Adobe Reader の子プロセスの作成をブロックする](#block-adobe-reader-from-creating-child-processes) | Y |   | Y | Y  | Y  |
|[すべてのアプリケーションOffice子プロセスの作成をブロックする](#block-all-office-applications-from-creating-child-processes) | Y |   |Y <br><br> CB 1710 | Y  | Y  |
|[ローカル セキュリティ機関サブシステムからの資格情報のWindowsをブロックする (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | Y  |   | Y <br><br>CB 1802 | Y  | Y  |
|[メール クライアントと Web メールから実行可能なコンテンツをブロックする](#block-executable-content-from-email-client-and-webmail) | Y |  |Y <br><br> CB 1710 | Y | Y  |
|[有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | Y |   | Y <br><br> CB 1802 |  Y |  Y |
|[難読化される可能性のあるスクリプトの実行をブロックする](#block-execution-of-potentially-obfuscated-scripts) | Y |   |  Y  <br><br> CB 1710 | Y  | Y  |
|[JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | Y |   | Y <br><br> CB 1710 | Y  | Y  |
|[実行可能Office作成するアプリケーションのブロック](#block-office-applications-from-creating-executable-content) | Y |  |Y <br><br> CB 1710 | Y  | Y  |
|[アプリケーションOffice他のプロセスへのコードの挿入をブロックする](#block-office-applications-from-injecting-code-into-other-processes) | Y |  | Y <br><br> CB 1710 | Y  | Y  |
|[通信Officeプロセスの作成をブロックする](#block-office-communication-application-from-creating-child-processes) | Y |  |Y <br><br> CB 1710 | Y  | Y  |
|[WMI イベント サブスクリプションによる永続化のブロック](#block-persistence-through-wmi-event-subscription) |  |  |  |Y   | Y  |
|[PSExec および WMI コマンドから発生するプロセス作成をブロックする](#block-process-creations-originating-from-psexec-and-wmi-commands) | Y |   |   |  Y | Y  |
|[USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする](#block-untrusted-and-unsigned-processes-that-run-from-usb) | Y |   |Y <br><br> CB 1802  | Y  | Y  |
|[Win32 API 呼び出しをブロックOfficeマクロ](#block-win32-api-calls-from-office-macros) | Y |   | Y <br><br> CB 1710  | Y  |  Y |
|[ランサムウェアに対する高度な保護の使用](#use-advanced-protection-against-ransomware) | Y |   | Y <br><br> CB 1802 | Y  | Y  |
|  |  |  |  |  |  |

  (<a id="fn1">1</a>) 任意のルールの GUID を使用して、ルールごとに攻撃表面の縮小ルールを構成できます。

- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)
- [Microsoft Endpoint Manager CB 1710](/configmgr/core/servers/manage/updates)
- [System Center Configuration Manager (SCCM) CB 1710](/configmgr/core/servers/manage/updates) <br>_SCCM は Microsoft Endpoint Configuration Manager です。_

## <a name="per-rule-alert-and-notification-details"></a>ルールごとのアラートと通知の詳細

トースト通知は、ブロック モードのすべてのルールに対して生成されます。 他のモードのルールはトースト通知を生成しません

"ルールの状態" が指定されているルールの場合:

- 組み合わせを含む \<ASR Rule, Rule State\> ASR ルールは、高クラウド ブロック レベルのデバイスに対する Microsoft Defender for Endpoint の通知 (トースト通知) を表示するために使用されます。 高いクラウド ブロック レベルではないデバイスは、ASR ルール、ルールの状態、<の組み合わせに>されません。
- EDR アラートは、指定された状態の ASR ルールに対して生成されますが、クラウド ブロック レベルの高いデバイスに対してだけ生成されます。

| ルール名: | ルールの状態: | EDR でアラートを生成しますか? <br> (はい&nbsp;\|&nbsp;いいえ) | トースト通知を生成しますか? <br> (はい&nbsp;\|&nbsp;いいえ) |
|---|:---:|:---:|:---:|
|   |   |  _高クラウド ブロック レベルのデバイスの場合のみ_ | _ブロック モードの場合のみ_ |
|[悪用された脆弱な署名済みドライバーの悪用をブロックする](#block-abuse-of-exploited-vulnerable-signed-drivers) |   | N  | Y |
|[Adobe Reader の子プロセスの作成をブロックする](#block-adobe-reader-from-creating-child-processes) | ブロック  | Y <br> 高クラウド ブロック レベルのデバイスが必要  | Y <br> 高クラウド ブロック レベルのデバイスが必要 |
|[すべてのアプリケーションOffice子プロセスの作成をブロックする](#block-all-office-applications-from-creating-child-processes) |   | N | Y |
|[Windows ローカル セキュリティ機関サブシステムからの資格情報の盗用をブロックする (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) |   | N | Y |
|[メール クライアントと Web メールから実行可能なコンテンツをブロックする](#block-executable-content-from-email-client-and-webmail) |   | Y <br> 高クラウド ブロック レベルのデバイスが必要 | Y <br> 高クラウド ブロック レベルのデバイスが必要 |
|[有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) |   | N | Y |
|[難読化される可能性のあるスクリプトの実行をブロックする](#block-execution-of-potentially-obfuscated-scripts) |  AuditBlock&nbsp;\|&nbsp; | Y \| Y <br> 高クラウド ブロック レベルのデバイスが必要  | N \| Y <br> 高クラウド ブロック レベルのデバイスが必要 |
|[JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | ブロック | Y <br> 高クラウド ブロック レベルのデバイスが必要  | Y <br> 高クラウド ブロック レベルのデバイスが必要 |
|[実行可能Office作成するアプリケーションをブロックする](#block-office-applications-from-creating-executable-content) |   | N | Y |
|[アプリケーションOffice他のプロセスへのコードの挿入をブロックする](#block-office-applications-from-injecting-code-into-other-processes)  |   | N | Y |
|[通信Office子プロセスの作成をブロックする](#block-office-communication-application-from-creating-child-processes) |  |  N | Y |
|[WMI イベント サブスクリプションによる永続化のブロック](#block-persistence-through-wmi-event-subscription) |  AuditBlock&nbsp;\|&nbsp; | Y \| Y <br> 高クラウド ブロック レベルのデバイスが必要  | N \| Y <br> 高クラウド ブロック レベルのデバイスが必要 |
|[PSExec および WMI コマンドから発生するプロセス作成をブロックする](#block-process-creations-originating-from-psexec-and-wmi-commands) |   | N | Y |
|[USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする](#block-untrusted-and-unsigned-processes-that-run-from-usb) | AuditBlock&nbsp;\|&nbsp; | Y \| Y <br> 高クラウド ブロック レベルのデバイスが必要  | N \| Y <br> 高クラウド ブロック レベルのデバイスが必要 |
|[Win32 API 呼び出しをブロックOfficeマクロ](#block-win32-api-calls-from-office-macros) |   | N | Y |
|[ランサムウェアに対する高度な保護の使用](#use-advanced-protection-against-ransomware) | AuditBlock&nbsp;\|&nbsp; | Y \| Y <br> 高クラウド ブロック レベルのデバイスが必要  | N \| Y <br> 高クラウド ブロック レベルのデバイスが必要 |
|   |   |   |   |
  
## <a name="asr-rule-modes"></a>ASR ルール モード

- **[構成されていない****] または [無効** にする]: これは、ASR ルールが有効になっていないか無効になっている状態です。 この状態のコードは 0 です。
- **ブロック**: これは、ASR ルールが有効になっている状態です。 この状態のコードは 1 です。
- **監査**: これは、ASR ルールが展開される組織または環境に対する影響的な動作について評価される状態です。 この状態のコードは 2 です。
- **警告** これは、ASR ルールが有効になっている状態で、エンド ユーザーに通知を表示しますが、エンド ユーザーはブロックをバイパスできます。 この状態のコードは 6 です。

_警告モード_ は、潜在的に危険なアクションについてユーザーに通知するブロック モードの種類です。 ユーザーは、ブロック警告メッセージをバイパスし、基になるアクションを許可することができます。 [ **OK** ] を選択してブロックを適用するか、ブロックの時点で生成されるエンド ユーザーのポップアップ トースト通知を使用してバイパス **オプション (ブロック** 解除) を選択できます。 警告がブロック解除された後は、次回警告メッセージが発生するまで操作が許可され、その時点でエンド ユーザーはアクションを再実行する必要があります。

[許可] ボタンをクリックすると、ブロックは 24 時間表示されません。 24 時間後、エンドユーザーはブロックを再度許可する必要があります。 ASR ルールの警告モードは、RS5+ (1809+) デバイスでのみサポートされます。 以前のバージョンのデバイスでバイパスが ASR ルールに割り当てられている場合、ルールはブロックモードになります。

PowerShell を使用して警告モードでルールを設定するには、そのルールを "Warn" AttackSurfaceReductionRules_Actions指定します。 例:

```powershell
-command "& {&'Add-MpPreference' -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Warn"} 
```

## <a name="per-rule-descriptions"></a>ルールごとの説明

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a>悪用された脆弱な署名済みドライバーの悪用をブロックする

このルールは、アプリケーションが脆弱な署名済みドライバーをディスクに書き込むのを防ぐためです。 インザワイルドで\-  \-脆弱な署名済みドライバーは、カーネルにアクセスするのに十分な特権を持つローカル アプリケーションによって悪用される可能性があります。 脆弱な署名付きドライバーを使用すると、攻撃者はセキュリティ ソリューションを無効または回避し、最終的にはシステムの侵害につながる可能性があります。

[ **悪用された脆弱な** 署名済みドライバーの悪用をブロックする] ルールは、システム上に既に存在するドライバーの読み込みをブロックしない。

> [!NOTE]
>
> このルールは、MEM OMA-URI を使用して構成できます。 カスタム ルール [の構成については、「MEM OMA-URI](enable-attack-surface-reduction.md#mem) 」を参照してください。
>
> PowerShell を使用してこのルールを [構成できます](enable-attack-surface-reduction.md#powershell)。
>
> ドライバーを調べるには、この Web サイトを使用して分析 [用のドライバーを送信します](https://www.microsoft.com/en-us/wdsi/driversubmission)。

<!--The above link is the 'only link' that exists for having drivers examined. The 'en-us' component is required to make the link work. Any alterations to this link will result in a 404.
-->

Intune 名: `Block abuse of exploited vulnerable signed drivers` (まだ使用できません)

Configuration Manager 名: まだ使用できません
  
GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`

<!-- Hide this intro with no subsequent list items
Advanced hunting action type:
-->

<!-- 
Dependencies:
-->

### <a name="block-adobe-reader-from-creating-child-processes"></a>Adobe Reader の子プロセスの作成をブロックする

このルールは、Adobe Reader によるプロセスの作成をブロックすることで攻撃を防止します。

ソーシャル エンジニアリングや悪用を通じて、マルウェアはペイロードをダウンロードして起動し、Adobe Reader から抜け出す可能性があります。 Adobe Reader によって子プロセスが生成されるのをブロックすることで、子プロセスをベクターとして使用しようとするマルウェアが拡散を防止します。

Intune 名: `Process creation from Adobe Reader (beta)`

Configuration Manager 名: まだ使用できません

GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`

高度なハンティング アクションの種類:

- AsrAdobeReaderChildProcessAudited
- AsrAdobeReaderChildProcessBlocked

依存関係: MDAV

### <a name="block-all-office-applications-from-creating-child-processes"></a>すべてのアプリケーションOffice子プロセスの作成をブロックする

このルールは、Officeプロセスの作成をブロックします。 Officeには、Word、Excel、PowerPoint、OneNote、Access が含まれます。

悪意のある子プロセスを作成する方法は、一般的なマルウェア戦略です。 ベクターとして悪用Officeマルウェアは、VBA マクロを実行し、コードを悪用して、より多くのペイロードをダウンロードして実行しようとする場合が多い。 ただし、一部の正当な業務行アプリケーションでは、良性の目的で子プロセスを生成する場合があります。コマンド プロンプトを生成したり、PowerShell を使用してレジストリ設定を構成したりします。

Intune 名: `Office apps launching child processes`

Configuration Manager 名: `Block Office application from creating child processes`

GUID: `d4f940ab-401b-4efc-aadc-ad5f3c50688a`

高度なハンティング アクションの種類:

- AsrOfficeChildProcessAudited
- AsrOfficeChildProcessBlocked

依存関係: MDAV

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a>ローカル セキュリティ機関サブシステムからの資格情報のWindowsをブロックする

このルールは、ローカル セキュリティ機関サブシステム サービス (LSASS) をロックダウンして資格情報の盗用を防ぐのに役立ちます。

LSASS は、コンピューターにサインインするユーザーをWindowsします。 Microsoft Defender Credential Guard in Windowsは、通常、LSASS から資格情報を抽出しようとして防止します。 ただし、一部の組織では、カスタム スマートカード ドライバーやローカル セキュリティ機関 (LSA) に読み込む他のプログラムとの互換性の問題により、すべてのコンピューターで Credential Guard を有効にできない場合があります。 このような場合、攻撃者は Mimikatz のようなハッキング ツールを使用して、LSASS からクリアテキスト パスワードと NTLM ハッシュをスクレイピングできます。

> [!NOTE]
> 一部のアプリでは、実行中のすべてのプロセスを列挙し、網羅的なアクセス許可を使用して開きます。 このルールは、アプリのプロセスのオープン アクションを拒否し、詳細をセキュリティ イベント ログに記録します。 このルールでは、多くのノイズが発生する可能性があります。 LSASS を列挙するだけで、機能に実際の影響がないアプリがある場合は、除外リストに追加する必要はありません。 それ自体では、このイベント ログ エントリは必ずしも悪意のある脅威を示すとは限りません。
  
> [!IMPORTANT]
> 攻撃表面縮小 (ASR) ルール "Windows ローカル セキュリティ機関サブシステム (lsass.exe) からの資格情報の盗用をブロックする" の既定の状態は [構成されていません] から [構成済み] に変更され、既定のモードは [ブロック] に設定されます。 他のすべての ASR ルールは既定の状態のままです。未 **構成です**。 エンドユーザーの通知を減らすために、ルールに追加のフィルター ロジックが既に組み込まれています。 ユーザーは、既定のモードを **上書きする監査** モード、 **警告** モード、または **無効** モードにルールを構成できます。 このルールの機能は、ルールが既定モードで構成されているかどうか、または手動でブロック モードを有効にした場合と同じです。  

Intune 名: `Flag credential stealing from the Windows local security authority subsystem`

Configuration Manager 名: `Block credential stealing from the Windows local security authority subsystem`

GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`

高度なハンティング アクションの種類:

- AsrLsassCredentialTheftAudited
- AsrLsassCredentialTheftBlocked

依存関係: MDAV

### <a name="block-executable-content-from-email-client-and-webmail"></a>メール クライアントと Web メールから実行可能なコンテンツをブロックする

このルールは、Microsoft Outlook アプリケーションまたは Outlook.com および他の一般的な Web メール プロバイダー内で開いた電子メールから起動する次のファイルの種類をブロックします。

- 実行可能ファイル (.exe、.dll、.scr など)
- スクリプト ファイル (PowerShell .ps、Visual Basic .vbs、JavaScript ファイル.jsなど)

Intune 名: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`

Microsoft エンドポイント マネージャー名:`Block executable content from email client and webmail`

GUID: `be9ba2d9-53ea-4cdc-84e5-9b1eeee46550`

高度なハンティング アクションの種類:

- AsrExecutableEmailContentAudited
- AsrExecutableEmailContentBlocked

依存関係: MDAV

> [!NOTE]
> [メール **クライアントと Web メールからの** 実行可能なコンテンツをブロックする] というルールには、使用するアプリケーションに応じて、次の別の説明があります。
>
> - Intune (構成プロファイル): 電子メール (Web メール/メール クライアント) から削除された実行可能コンテンツ (exe、dll、ps、js、vbs など) の実行 (例外なし)。
> - エンドポイント マネージャー: 電子メールおよび Web メール クライアントからの実行可能コンテンツのダウンロードをブロックします。
> - グループ ポリシー: 電子メール クライアントと Web メールから実行可能なコンテンツをブロックします。

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a>有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする

このルールは、実行可能ファイル (.exe、.dll、.scr など) の起動をブロックします。 したがって、信頼されていない実行可能ファイルまたは不明な実行可能ファイルを起動すると、ファイルが悪意のあるものか最初は明らかではなかっていない可能性があります。

> [!IMPORTANT]
> このルールを [使用するには、クラウドによる保護](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) を有効にする必要があります。
>
> GUID で **有病率**`01443614-cd74-433a-b99e-2ecdc07bfc25`、年齢、または信頼できるリスト条件を満たしていない場合、実行可能ファイルの実行をブロックするルールは、Microsoft が所有し、管理者によって指定されていません。 このルールでは、クラウド配信の保護を使用して、信頼できるリストを定期的に更新します。
>
> 個々のファイルまたはフォルダー (フォルダー パスまたは完全修飾リソース名を使用) を指定できますが、適用するルールや除外を指定することはできません。

Intune 名: `Executables that don't meet a prevalence, age, or trusted list criteria`

Configuration Manager 名: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`

GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`

高度なハンティング アクションの種類:

- AsrUntrustedExecutableAudited
- AsrUntrustedExecutableBlocked

依存関係: MDAV、クラウド保護

### <a name="block-execution-of-potentially-obfuscated-scripts"></a>難読化される可能性のあるスクリプトの実行をブロックする

このルールは、難読化されたスクリプト内の疑わしいプロパティを検出します。

スクリプト難読化は、マルウェア作成者と正当なアプリケーションの両方が、知的財産を隠したり、スクリプトの読み込み時間を短縮したりするために使用する一般的な手法です。 マルウェアの作成者は難読化を使用して悪意のあるコードを読みにくくし、人間やセキュリティ ソフトウェアによる詳細な調査を防止します。

Intune 名: `Obfuscated js/vbs/ps/macro code`

Configuration Manager 名: `Block execution of potentially obfuscated scripts`

GUID: `5beb7efe-fd9a-4556-801d-275e5ffc04cc`

高度なハンティング アクションの種類:

- AsrObfuscatedScriptAudited
- AsrObfuscatedScriptBlocked

依存関係: MDAV、AMSI

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a>JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする

このルールにより、スクリプトは悪意のあるダウンロードコンテンツを起動できません。 JavaScript または VBScript で記述されたマルウェアは、インターネットから他のマルウェアをフェッチして起動するダウンデータとして機能する場合が多い。

一般的ではないが、一般企業向けアプリケーションでは、スクリプトを使用してインストーラーをダウンロードおよび起動する場合があります。

Intune 名: `js/vbs executing payload downloaded from Internet (no exceptions)`

Configuration Manager 名: `Block JavaScript or VBScript from launching downloaded executable content`

GUID: `d3e037e1-3eb8-44c8-a917-57927947596d`

高度なハンティング アクションの種類:

- AsrScriptExecutableDownloadAudited
- AsrScriptExecutableDownloadBlocked

依存関係: MDAV、AMSI

### <a name="block-office-applications-from-creating-executable-content"></a>実行可能Office作成するアプリケーションをブロックする

このルールはOfficeコードがディスクに書き込まれるのをブロックすることで、Word、Excel、PowerPoint などのアプリが悪意のある実行可能なコンテンツを作成するのを防止します。

マルウェアは、Officeとして悪用され、悪意のあるOfficeをディスクに保存しようとする可能性があります。 これらの悪意のあるコンポーネントは、コンピューターの再起動後も存続し、システム上で保持されます。 したがって、このルールは一般的な永続化手法に対して防御します。

Intune 名: `Office apps/macros creating executable content`

SCCM 名: `Block Office applications from creating executable content`

GUID: `3b576869-a4ec-4529-8536-b80a7769e899`

高度なハンティング アクションの種類:

- AsrExecutableOfficeContentAudited
- AsrExecutableOfficeContentBlocked

依存関係: MDAV、RPC

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a>アプリケーションOffice他のプロセスへのコードの挿入をブロックする

このルールは、アプリから他のプロセスへのOffice挿入の試行をブロックします。

攻撃者は、悪意のあるOfficeをコード挿入によって他のプロセスに移行するために、アプリを使用しようとする可能性があります。そのため、コードはクリーン なプロセスとして悪用される可能性があります。

コードインジェクションを使用する正当なビジネス上の目的はありません。

このルールは、Word、Excel、およびPowerPoint。

Intune 名: `Office apps injecting code into other processes (no exceptions)`

Configuration Manager 名: `Block Office applications from injecting code into other processes`

GUID: `75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84`

高度なハンティング アクションの種類:

- AsrOfficeProcessInjectionAudited
- AsrOfficeProcessInjectionBlocked

依存関係: MDAV

### <a name="block-office-communication-application-from-creating-child-processes"></a>通信Office子プロセスの作成をブロックする

このルールは、Outlookプロセスを作成する一方で、正当なプロセス機能Outlookします。

このルールは、ソーシャル エンジニアリング攻撃から保護し、コードを悪用して、セキュリティ上の脆弱性を悪用Outlook。 また、ユーザーのOutlook[が](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/)侵害された場合に攻撃者が使用する可能性のある、特定のルールやフォームの悪用から保護します。

> [!NOTE]
> このルールは、DLP ポリシー のヒントとツール ヒントをブロックOutlook。 このルールは、Outlookおよび Outlook.com にのみ適用されます。

Intune 名: `Process creation from Office communication products (beta)`

Configuration Manager 名: 使用できません

GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`

高度なハンティング アクションの種類:

- AsrOfficeCommAppChildProcessAudited
- AsrOfficeCommAppChildProcessBlocked

依存関係: MDAV

### <a name="block-persistence-through-wmi-event-subscription"></a>WMI イベント サブスクリプションによる永続化のブロック

この規則により、マルウェアが WMI を悪用してデバイスでの永続性を獲得するのを防ぎます。

> [!IMPORTANT]
> ファイルとフォルダーの除外は、この攻撃表面の縮小ルールには適用されません。

ファイルレス脅威は、さまざまな戦術を採用して潜伏し、ファイル システムに見つからないようにして、定期的に実行制御を獲得します。 脅威の中には、WMI リポジトリとイベント モデルを悪用して、潜伏できるものがあります。

Intune 名: 使用できません

Configuration Manager 名: 使用できません

GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`

高度なハンティング アクションの種類:

- AsrPersistenceThroughWmiAudited
- AsrPersistenceThroughWmiBlocked

依存関係: MDAV、RPC

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a>PSExec および WMI コマンドから発生するプロセス作成をブロックする

このルールは、 [PsExec](/sysinternals/downloads/psexec) および WMI を介して作成 [されたプロセスの実行](/windows/win32/wmisdk/about-wmi) をブロックします。 PsExec と WMI の両方がコードをリモートで実行できるので、コマンドと制御の目的でこの機能を不正に使用したり、組織のネットワーク全体に感染を広げる危険性があります。

> [!WARNING]
> Intune または別の MDM ソリューションを使用してデバイスを管理する場合にのみ、 [このルールを](/intune) 使用します。 このルールは、Configuration Manager クライアント[が正しく](/configmgr)機能するためにMicrosoft Endpoint Configuration Manager WMI コマンドをブロックします。

Intune 名: `Process creation from PSExec and WMI commands`

Configuration Manager 名: 該当なし

GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`

高度なハンティング アクションの種類:

- AsrPsexecWmiChildProcessAudited
- AsrPsexecWmiChildProcessBlocked

依存関係: MDAV

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a>USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする

このルールを使用すると、管理者は、SD カードを含む USB リムーバブル ドライブから署名されていない実行可能ファイルまたは信頼されていない実行可能ファイルを実行できません。 ブロックされているファイルの種類には、実行可能ファイル (.exe、.dll.scr など) が含まれます。

Intune 名: `Untrusted and unsigned processes that run from USB`

Configuration Manager 名: `Block untrusted and unsigned processes that run from USB`

GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`

高度なハンティング アクションの種類:

- AsrUntrustedUsbProcessAudited
- AsrUntrustedUsbProcessBlocked

依存関係: MDAV

### <a name="block-win32-api-calls-from-office-macros"></a>Win32 API 呼び出しをブロックOfficeマクロ

このルールは、VBA マクロが Win32 API を呼び出すのを防止します。

Office VBA では、Win32 API 呼び出しが有効です。 マルウェアは、 [Win32 API](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) を呼び出してディスクに直接何も書き込みせずに悪意のあるシェルコードを起動するなど、この機能を悪用する可能性があります。 ほとんどの組織では、他の方法でマクロを使用している場合でも、Win32 API を毎日の機能で呼び出す機能に依存しません。

サポートされるオペレーティング システム

- [Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows サーバー バージョン 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune 名: `Win32 imports from Office macro code`

Configuration Manager 名: `Block Win32 API calls from Office macros`

GUID: `92e97fa1-2edf-4476-bdd6-9dd0b4dddc7b`

高度なハンティング アクションの種類:

- AsrOfficeMacroWin32ApiCallsAudited
- AsrOfficeMacroWin32ApiCallsBlocked

依存関係: MDAV、AMSI

### <a name="use-advanced-protection-against-ransomware"></a>ランサムウェアに対する高度な保護の使用

このルールは、ランサムウェアに対する保護の追加層を提供します。 クライアントとクラウドの両方のヒューリスティックを使用して、ファイルがランサムウェアに似ているかどうかを判断します。 このルールは、次の 1 つ以上の特性を持つファイルをブロックしない。

- このファイルは、Microsoft クラウドで既に無傷である必要があります。
- ファイルは有効な署名付きファイルです。
- ファイルはランサムウェアと見なされないほど普及しています。

このルールは、ランサムウェアを防止するために注意を払う傾向があります。

> [!NOTE]
> このルールを [使用するには、クラウドによる保護](enable-cloud-protection-microsoft-defender-antivirus.md) を有効にする必要があります。

Intune 名: `Advanced ransomware protection`

Configuration Manager 名: `Use advanced protection against ransomware`

GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`

高度なハンティング アクションの種類:

- AsrRansomwareAudited
- AsrRansomwareBlocked

依存関係: MDAV、クラウド保護
