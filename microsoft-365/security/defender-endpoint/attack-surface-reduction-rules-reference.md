---
title: 攻撃面の縮小ルールリファレンス
description: 攻撃表面の縮小ルールに関する詳細をルールごとに一覧表示します。
keywords: 攻撃表面の縮小ルール, ASR, asr ルール, hips, ホスト侵入防止システム, 保護ルール, 悪用防止ルール, アンチエクスプロイト, 悪用ルール, 感染防止ルール, Microsoft Defender for Endpoint, ASR ルールの構成, ASR ルールの説明
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
ms.openlocfilehash: 1eee7e482423e2292e9fe9db42333db481d44175
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64783759"
---
# <a name="attack-surface-reduction-rules-reference"></a>攻撃面の縮小ルールリファレンス

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

この記事では、攻撃軽減ルールに関する情報を提供します。

- [サポートされているオペレーティング システムのバージョン](#supported-operating-systems)
- [サポートされている構成管理システム](#supported-configuration-management-systems)
- [ルールごとのアラートと通知の詳細](#per-rule-alert-and-notification-details)
- [ASR の規則と GUID マトリックス](#asr-rules-and-guids-matrix)
- [ASR ルール モード](#asr-rule-modes)
- [ルールごとの説明](#per-rule-descriptions)
  - ルールの説明
  - 構成管理システムのルール名

## <a name="supported-operating-systems"></a>サポートされているオペレーティング システム 

次の表に、現在一般公開にリリースされているルールでサポートされているオペレーティング システムを示します。 この表には、規則のアルファベット順が一覧表示されます。

> [!Note]
>
> 特に明記されていない限り、最小Windows&nbsp; 10 ビルドはバージョン 1709 (RS3、ビルド 16299) 以降です。最小Windows&nbsp; Server ビルドのバージョンは 1809 以降です。
>
> Windows&nbsp; Server2012R2&nbsp;&nbsp; および Windows&nbsp; Server2016&nbsp; の攻撃面の縮小ルールは、最新の統合ソリューション パッケージを使用してオンボードされたデバイスで使用できます。 詳細については、「[Windows Server 2012 R2 および 2016 Preview の最新の統合ソリューションの新機能](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)」を参照してください。

| ルール名|Windows 10 | Windows Server 2019 | &nbsp;Windows Server | <sup>Windows Server 2016 [[1, 2](#fn1)]<sup></sup> | &nbsp;Windows Server 2012 R2 <sup>[[1, 2](#fn1)]<sup></sup> |
|:---|:---:|:---:|:---:|:---:|:---:|
| [悪用された脆弱な署名されたドライバーの悪用をブロックする](#block-abuse-of-exploited-vulnerable-signed-drivers) | Y | Y | Y <br> バージョン 1803 (半期チャネル) 以降 | Y | Y |
| [Adobe Reader による子プロセスの作成をブロックする](#block-adobe-reader-from-creating-child-processes) | Y バージョン 1809 以降 | Y | Y | Y | Y |
| [すべてのOffice アプリケーションによる子プロセスの作成をブロックする](#block-all-office-applications-from-creating-child-processes) | Y | Y | Y | Y | Y |
| [Windowsローカル セキュリティ機関サブシステムからの資格情報の盗用をブロックする (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | Y <br> バージョン 1803 以降 | Y | Y | Y | Y |
| [電子メール クライアントと webmail から実行可能コンテンツをブロックする](#block-executable-content-from-email-client-and-webmail) | Y | Y | Y | Y | Y |
| [実行可能ファイルが有病率、年齢、または信頼されたリスト条件を満たしていない限り、実行可能ファイルの実行をブロックする](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | Y <br> バージョン 1803 以降 | Y | Y | Y | Y |
| [難読化される可能性があるスクリプトの実行をブロックする](#block-execution-of-potentially-obfuscated-scripts) | Y | Y | Y | Y | Y |
| [ダウンロードした実行可能コンテンツの起動から JavaScript または VBScript をブロックする](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | Y | Y | Y | N | N |
| [アプリケーションOffice実行可能コンテンツの作成をブロックする](#block-office-applications-from-creating-executable-content) | Y | Y | Y | Y | Y |
| [アプリケーションOfficeコードを他のプロセスに挿入できないようにブロックする](#block-office-applications-from-injecting-code-into-other-processes)  | Y | Y | Y | Y | Y |
| [通信アプリケーションOffice子プロセスの作成をブロックする](#block-office-communication-application-from-creating-child-processes) | Y | Y | Y | Y | Y |
| [WMI イベント サブスクリプションを使用して永続化をブロックする](#block-persistence-through-wmi-event-subscription) <br> \*_ファイルとフォルダーの除外はサポートされていません。_ | Y <br> バージョン 1903 (ビルド 18362) 以降 | Y | Y <br> バージョン 1903 (ビルド 18362) 以降 | N | N |
| [PSExec コマンドと WMI コマンドから生成されたプロセス作成をブロックする](#block-process-creations-originating-from-psexec-and-wmi-commands) | Y <br> バージョン 1803 以降 | Y | Y | Y | Y |
| [USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする](#block-untrusted-and-unsigned-processes-that-run-from-usb) | Y | Y | Y | Y | Y |
| [Office マクロからの Win32 API 呼び出しをブロックする](#block-win32-api-calls-from-office-macros) | Y | Y | Y | N | N |
| [ランサムウェアに対する高度な保護を使用する](#use-advanced-protection-against-ransomware) | Y <br> バージョン 1803 以降 | Y | Y | Y | Y |

(<a id="fn1">1</a>) Windows Server 2012と 2016 の最新の統合ソリューションを参照します。 詳細については、「[Windows サーバーを Defender for Endpoint サービスにオンボードする」を](configure-server-endpoints.md)参照してください。

(<a id="fn1">2</a>) Windows&nbsp; Server 2016 および Windows&nbsp; Server 2012R2&nbsp; の場合、Microsoft Endpoint Configuration Managerの最小必須バージョンはバージョン 2111 です。

## <a name="supported-configuration-management-systems"></a>サポートされている構成管理システム

この表で参照されている構成管理システムのバージョンに関する情報へのリンクを次の表に示します。

|ルール名 | Intune | Microsoft エンドポイント マネージャー |Microsoft Endpoint Configuration Manager |<sup>グループ ポリシー[[1](#fn1)]<sup></sup> | PowerShell<sup>[[1](#fn1)]<sup></sup>  |
|---|:---:|:---:|:---:|:---:|:---:|
|[悪用された脆弱な署名されたドライバーの悪用をブロックする](#block-abuse-of-exploited-vulnerable-signed-drivers) | Y  | Y MEM OMA-URI |   | Y  |  Y  |
|[Adobe Reader による子プロセスの作成をブロックする](#block-adobe-reader-from-creating-child-processes) | Y |   |  | Y  | Y  |
|[すべてのOffice アプリケーションによる子プロセスの作成をブロックする](#block-all-office-applications-from-creating-child-processes) | Y |   |Y <br><br> CB 1710 | Y  | Y  |
|[Windowsローカル セキュリティ機関サブシステムからの資格情報の盗用をブロックする (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | Y  |   | Y <br><br>CB 1802 | Y  | Y  |
|[電子メール クライアントと webmail から実行可能コンテンツをブロックする](#block-executable-content-from-email-client-and-webmail) | Y |  |Y <br><br> CB 1710 | Y | Y  |
|[実行可能ファイルが有病率、年齢、または信頼されたリスト条件を満たしていない限り、実行可能ファイルの実行をブロックする](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | Y |   | Y <br><br> CB 1802 |  Y |  Y |
|[難読化される可能性があるスクリプトの実行をブロックする](#block-execution-of-potentially-obfuscated-scripts) | Y |   |  Y  <br><br> CB 1710 | Y  | Y  |
|[ダウンロードした実行可能コンテンツの起動から JavaScript または VBScript をブロックする](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | Y |   | Y <br><br> CB 1710 | Y  | Y  |
|[アプリケーションOffice実行可能コンテンツの作成をブロックする](#block-office-applications-from-creating-executable-content) | Y |  |Y <br><br> CB 1710 | Y  | Y  |
|[アプリケーションOfficeコードを他のプロセスに挿入できないようにブロックする](#block-office-applications-from-injecting-code-into-other-processes) | Y |  | Y <br><br> CB 1710 | Y  | Y  |
|[通信アプリケーションOffice子プロセスの作成をブロックする](#block-office-communication-application-from-creating-child-processes) | Y |  |Y <br><br> CB 1710 | Y  | Y  |
|[WMI イベント サブスクリプションを使用して永続化をブロックする](#block-persistence-through-wmi-event-subscription) |  |  |  |Y   | Y  |
|[PSExec コマンドと WMI コマンドから生成されたプロセス作成をブロックする](#block-process-creations-originating-from-psexec-and-wmi-commands) | Y |   |   |  Y | Y  |
|[USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする](#block-untrusted-and-unsigned-processes-that-run-from-usb) | Y |   |Y <br><br> CB 1802  | Y  | Y  |
|[Office マクロからの Win32 API 呼び出しをブロックする](#block-win32-api-calls-from-office-macros) | Y |   | Y <br><br> CB 1710  | Y  |  Y |
|[ランサムウェアに対する高度な保護を使用する](#use-advanced-protection-against-ransomware) | Y |   | Y <br><br> CB 1802 | Y  | Y  |
|  |  |  |  |  |  |

  (<a id="fn1">1</a>) 任意のルールの GUID を使用して、ルールごとに攻撃表面の縮小ルールを構成できます。

- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)
- [Microsoft エンドポイント マネージャー CB 1710](/configmgr/core/servers/manage/updates)
- [System Center Configuration Manager (SCCM) CB 1710](/configmgr/core/servers/manage/updates) <br>_SCCM がMicrosoft Endpoint Configuration Managerになりました。_

## <a name="per-rule-alert-and-notification-details"></a>ルールごとのアラートと通知の詳細

トースト通知は、ブロック モードのすべてのルールに対して生成されます。 その他のモードのルールでは、トースト通知は生成されません

"Rule State" が指定されたルールの場合:

- 組み合わせの \<ASR Rule, Rule State\> ASR ルールは、高クラウド ブロック レベルのデバイスに対してのみ、Microsoft Defender for Endpointにアラート (トースト通知) を表示するために使用されます。 クラウド ブロック レベルが高いデバイスでは、<ASR ルール、ルール状態、>の組み合わせに対してアラートが生成されません
- EDRアラートは、指定された状態の ASR ルールに対して生成されますが、クラウド ブロック レベルの高いデバイスに対してのみ生成されます。

| ルール名: | ルールの状態: | EDRでアラートを生成しますか? <br> (はい&nbsp;\|&nbsp;いいえ) | トースト通知を生成しますか? <br> (はい&nbsp;\|&nbsp;いいえ) |
|---|:---:|:---:|:---:|
|   |   |  _高クラウド ブロック レベルのデバイスの場合のみ_ | _ブロック モードのみ_ |
|[悪用された脆弱な署名されたドライバーの悪用をブロックする](#block-abuse-of-exploited-vulnerable-signed-drivers) |   | N  | Y |
|[Adobe Reader による子プロセスの作成をブロックする](#block-adobe-reader-from-creating-child-processes) | ブロック  | Y <br> 高クラウド ブロック レベルのデバイスが必要です  | Y <br> 高クラウド ブロック レベルのデバイスが必要です |
|[すべてのOffice アプリケーションによる子プロセスの作成をブロックする](#block-all-office-applications-from-creating-child-processes) |   | N | Y |
|[Windowsローカル セキュリティ機関サブシステムからの資格情報の盗用をブロックする (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) |   | N | Y |
|[電子メール クライアントと webmail から実行可能コンテンツをブロックする](#block-executable-content-from-email-client-and-webmail) |   | Y <br> 高クラウド ブロック レベルのデバイスが必要です | Y <br> 高クラウド ブロック レベルのデバイスが必要です |
|[実行可能ファイルが有病率、年齢、または信頼されたリスト条件を満たしていない限り、実行可能ファイルの実行をブロックする](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) |   | N | Y |
|[難読化される可能性があるスクリプトの実行をブロックする](#block-execution-of-potentially-obfuscated-scripts) |  AuditBlock&nbsp;\|&nbsp; | Y \| Y <br> 高クラウド ブロック レベルのデバイスが必要です  | N \| Y <br> 高クラウド ブロック レベルのデバイスが必要です |
|[ダウンロードした実行可能コンテンツの起動から JavaScript または VBScript をブロックする](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | ブロック | Y <br> 高クラウド ブロック レベルのデバイスが必要です  | Y <br> 高クラウド ブロック レベルのデバイスが必要です |
|[アプリケーションOffice実行可能コンテンツの作成をブロックする](#block-office-applications-from-creating-executable-content) |   | N | Y |
|[アプリケーションOfficeコードを他のプロセスに挿入できないようにブロックする](#block-office-applications-from-injecting-code-into-other-processes)  |   | N | Y |
|[通信アプリケーションOffice子プロセスの作成をブロックする](#block-office-communication-application-from-creating-child-processes) |  |  N | Y |
|[WMI イベント サブスクリプションを使用して永続化をブロックする](#block-persistence-through-wmi-event-subscription) |  AuditBlock&nbsp;\|&nbsp; | Y \| Y <br> 高クラウド ブロック レベルのデバイスが必要です  | N \| Y <br> 高クラウド ブロック レベルのデバイスが必要です |
|[PSExec コマンドと WMI コマンドから生成されたプロセス作成をブロックする](#block-process-creations-originating-from-psexec-and-wmi-commands) |   | N | Y |
|[USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする](#block-untrusted-and-unsigned-processes-that-run-from-usb) | AuditBlock&nbsp;\|&nbsp; | Y \| Y <br> 高クラウド ブロック レベルのデバイスが必要です  | N \| Y <br> 高クラウド ブロック レベルのデバイスが必要です |
|[Office マクロからの Win32 API 呼び出しをブロックする](#block-win32-api-calls-from-office-macros) |   | N | Y |
|[ランサムウェアに対する高度な保護を使用する](#use-advanced-protection-against-ransomware) | AuditBlock&nbsp;\|&nbsp; | Y \| Y <br> 高クラウド ブロック レベルのデバイスが必要です  | N \| Y <br> 高クラウド ブロック レベルのデバイスが必要です |
|   |   |   |   |
  
## <a name="asr-rules-and-guids-matrix"></a>ASR の規則と GUID マトリックス

| [ルール名] | ルール GUID |
|:-----|:-----|
| 悪用された脆弱な署名されたドライバーの悪用をブロックする | 56a863a9-875e-4185-98a7-b882c64b5ce5 |
| Adobe Reader による子プロセスの作成をブロックする | 7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c |
| すべてのOffice アプリケーションによる子プロセスの作成をブロックする | d4f940ab-401b-4efc-aadc-ad5f3c50688a |
| Windowsローカル セキュリティ機関サブシステムからの資格情報の盗用をブロックする (lsass.exe) | 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2 |
| 電子メール クライアントと webmail から実行可能コンテンツをブロックする | be9ba2d9-53ea-4cdc-84e5-9b1eeee46550 |
| 実行可能ファイルが有病率、年齢、または信頼されたリスト条件を満たしていない限り、実行可能ファイルの実行をブロックする | 01443614-cd74-433a-b99e-2ecdc07bfc25 |
| 難読化される可能性があるスクリプトの実行をブロックする | 5beb7efe-fd9a-4556-801d-275e5ffc04cc |
| ダウンロードした実行可能コンテンツの起動から JavaScript または VBScript をブロックする | d3e037e1-3eb8-44c8-a917-57927947596d |
| アプリケーションOffice実行可能コンテンツの作成をブロックする | 3b576869-a4ec-4529-8536-b80a7769e899 |
| アプリケーションOfficeコードを他のプロセスに挿入できないようにブロックする | 75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84 |
| 通信アプリケーションOffice子プロセスの作成をブロックする | 26190899-1602-49e8-8b27-eb1d0a1ce869 |
| WMI イベント サブスクリプションを使用して永続化をブロックする <br>* ファイルとフォルダーの除外はサポートされていません。 | e6db77e5-3df2-4cf1-b95a-636979351e5b |
| PSExec コマンドと WMI コマンドから生成されたプロセス作成をブロックする | d1e49aac-8f56-4280-b9ba-993a6d77406c |
| USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする | b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4 |
| Office マクロからの Win32 API 呼び出しをブロックする | 92e97fa1-2edf-4476-bdd6-9dd0b4dddc7b |
| ランサムウェアに対する高度な保護を使用する | c1db55ab-c21a-4637-bb3f-a12568109d35 |

## <a name="asr-rule-modes"></a>ASR ルール モード

- **未構成** または **無効**: これは、ASR 規則が有効になっていないか無効になっている状態です。 この状態のコードは 0 です。
- **ブロック**: これは、ASR 規則が有効になっている状態です。 この状態のコードは 1 です。
- **監査**: これは、ASR 規則が展開される組織または環境に対する影響を与える動作について評価される状態です。 この状態のコードは 2 です。
- **警告** これは、ASR 規則が有効になっている状態であり、エンド ユーザーに通知を表示しますが、エンド ユーザーがブロックをバイパスすることを許可します。 この状態のコードは 6 です。

_警告モード_ は、危険な可能性があるアクションについてユーザーに警告するブロック モードの種類です。 ユーザーは、ブロック警告メッセージをバイパスし、基になるアクションを許可することを選択できます。 ユーザーは **、[OK] を** 選択してブロックを適用するか、ブロックの時点で生成されるエンド ユーザーポップアップ トースト通知を使用してバイパス オプション [ **ブロック** 解除] を選択できます。 警告のブロックが解除された後は、次回警告メッセージが発生するまで操作が許可されます。この時点で、エンド ユーザーはアクションを再評価する必要があります。

[許可] ボタンをクリックすると、ブロックは 24 時間非表示になります。 24 時間後、エンド ユーザーはブロックを再度許可する必要があります。 ASR ルールの警告モードは、RS5+ (1809 以降) デバイスでのみサポートされます。 バイパスが古いバージョンのデバイスの ASR ルールに割り当てられている場合、ルールはブロック モードになります。

また、AttackSurfaceReductionRules_Actionsを "警告" として指定するだけで、PowerShell を使用して警告モードでルールを設定することもできます。 例:

```powershell
-command "& {&'Add-MpPreference' -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Warn"} 
```

## <a name="per-rule-descriptions"></a>ルールごとの説明

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a>悪用された脆弱な署名されたドライバーの悪用をブロックする

この規則により、アプリケーションが脆弱な署名付きドライバーをディスクに書き込むのを防ぎます。 脆弱な署名されたドライバーは、カーネルにアクセス _するのに十分な特権_\-を持つローカル アプリケーション\-によって悪用される可能性があります。 脆弱な署名されたドライバーを使用すると、攻撃者はセキュリティ ソリューションを無効または回避し、最終的にシステムの侵害につながります。

**悪用された脆弱な署名付きドライバーのブロックの悪用** ルールでは、システムに既に存在するドライバーの読み込みをブロックしません。

> [!NOTE]
>
> このルールは、MEM OMA-URI を使用して構成できます。 カスタムルールを構成する方法については、 [MEM OMA-URI](enable-attack-surface-reduction.md#mem) を参照してください。
>
> [PowerShell](enable-attack-surface-reduction.md#powershell) を使用してこの規則を構成することもできます。
>
> ドライバーを調べるには、この Web サイトを使用して [分析用のドライバーを送信します](https://www.microsoft.com/en-us/wdsi/driversubmission)。

<!--The above link is the 'only link' that exists for having drivers examined. The 'en-us' component is required to make the link work. Any alterations to this link will result in a 404.
-->

Intune名: `Block abuse of exploited vulnerable signed drivers` (まだ使用できません)

Configuration Manager名: まだ使用できません
  
GUID：  `56a863a9-875e-4185-98a7-b882c64b5ce5`

<!-- Hide this intro with no subsequent list items
Advanced hunting action type:
-->

<!-- 
Dependencies: none provided by engineering
-->

### <a name="block-adobe-reader-from-creating-child-processes"></a>Adobe Reader による子プロセスの作成をブロックする

このルールは、Adobe Reader によるプロセスの作成をブロックすることで、攻撃を防ぎます。

ソーシャル エンジニアリングや悪用を通じて、マルウェアはペイロードをダウンロードして起動し、Adobe Reader から抜け出すことができます。 Adobe Reader によって子プロセスが生成されるのをブロックすることで、それをベクターとして使用しようとするマルウェアが拡散するのを防ぎます。

Intune名:`Process creation from Adobe Reader (beta)`

Configuration Manager名: まだ使用できません

GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`

高度なハンティング アクションの種類:

- AsrAdobeReaderChildProcessAudited
- AsrAdobeReaderChildProcessBlocked

依存関係: MDAV

### <a name="block-all-office-applications-from-creating-child-processes"></a>すべてのOffice アプリケーションによる子プロセスの作成をブロックする

このルールは、アプリOffice子プロセスの作成をブロックします。 Office アプリには、Word、Excel、PowerPoint、OneNote、Access が含まれます。

悪意のある子プロセスを作成することは、一般的なマルウェア戦略です。 ベクターとしてOfficeを悪用するマルウェアは、多くの場合、VBA マクロを実行し、コードを悪用して、より多くのペイロードをダウンロードして実行しようとします。 ただし、一部の正当な基幹業務アプリケーションでは、無害な目的で子プロセスが生成される場合もあります。コマンド プロンプトの生成や、PowerShell を使用したレジストリ設定の構成などです。

Intune名:`Office apps launching child processes`

Configuration Manager名:`Block Office application from creating child processes`

GUID: `d4f940ab-401b-4efc-aadc-ad5f3c50688a`

高度なハンティング アクションの種類:

- AsrOfficeChildProcessAudited
- AsrOfficeChildProcessBlocked

依存関係: MDAV

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a>Windowsローカル セキュリティ機関サブシステムからの資格情報の盗難をブロックする

この規則は、ローカル セキュリティ機関サブシステム サービス (LSASS) をロックダウンすることで、資格情報の盗難を防ぐのに役立ちます。

LSASS は、Windows コンピューターにサインインするユーザーを認証します。 Windowsの Microsoft Defender Credential Guard では、通常、LSASS から資格情報を抽出する試みを防ぎます。 ただし、一部の組織では、カスタム スマートカード ドライバーまたはローカル セキュリティ機関 (LSA) に読み込まれる他のプログラムとの互換性の問題により、すべてのコンピューターで Credential Guard を有効にできません。 このような場合、攻撃者は Mimikatz などのハッキング ツールを使用して、LSASS からクリアテキスト パスワードと NTLM ハッシュをスクレーピングできます。

> [!NOTE]
> 一部のアプリでは、実行中のすべてのプロセスがコードによって列挙され、完全なアクセス許可で開こうとします。 このルールは、アプリのプロセスオープン アクションを拒否し、詳細をセキュリティ イベント ログに記録します。 このルールでは、多くのノイズが発生する可能性があります。 LSASS を列挙するだけで機能に実質的な影響がないアプリがある場合は、除外リストに追加する必要はありません。 このイベント ログ エントリ自体は、必ずしも悪意のある脅威を示すわけではありません。
  
> [!IMPORTANT]
> 攻撃表面削減 (ASR) 規則の既定の状態 "Windowsローカル セキュリティ機関サブシステム (lsass.exe)からの資格情報の盗難をブロックする" は **、[未構成] から [構成済み]** に変更され、既定のモードは **[ブロック**] に設定されます。 その他のすべての ASR ルールは、既定の状態のままになります。 **未構成** です。 エンド ユーザーの通知を減らすために、ルールに追加のフィルター 処理ロジックが既に組み込まれています。 お客様は、既定のモードをオーバーライドする **監査**、 **警告** 、または **無効** モードにルールを構成できます。 この規則の機能は同じです。ルールが既定モードで構成されているか、ブロック モードを手動で有効にした場合です。

Intune名:`Flag credential stealing from the Windows local security authority subsystem`

Configuration Manager名:`Block credential stealing from the Windows local security authority subsystem`

GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`

高度なハンティング アクションの種類:

- AsrLsassCredentialTheftAudited
- AsrLsassCredentialTheftBlocked

依存関係: MDAV

### <a name="block-executable-content-from-email-client-and-webmail"></a>電子メール クライアントと webmail から実行可能コンテンツをブロックする

この規則では、Microsoft Outlook アプリケーションまたはOutlook.com やその他の一般的な Web メール プロバイダー内で開かれた電子メールから次のファイルの種類を起動できないようにします。

- 実行可能ファイル (.exe、.dll、.scr など)
- スクリプト ファイル (PowerShell .ps、Visual Basic .vbs、JavaScript .js ファイルなど)

Intune名:`Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`

Microsoft エンドポイント マネージャー名:`Block executable content from email client and webmail`

GUID: `be9ba2d9-53ea-4cdc-84e5-9b1eeee46550`

高度なハンティング アクションの種類:

- AsrExecutableEmailContentAudited
- AsrExecutableEmailContentBlocked

依存関係: MDAV

> [!NOTE]
> **ルール[電子メール クライアントと Webmail からの実行可能コンテンツのブロック**] には、使用するアプリケーションに応じて、次の代替説明があります。
>
> - Intune (構成プロファイル): 電子メール (webmail/メール クライアント) から削除された実行可能コンテンツ (exe、dll、ps、js、vbs など) の実行 (例外なし)。
> - エンドポイント マネージャー: 電子メールおよび Web メール クライアントからの実行可能コンテンツのダウンロードをブロックします。
> - グループ ポリシー: 電子メール クライアントと webmail から実行可能コンテンツをブロックします。

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a>実行可能ファイルが有病率、年齢、または信頼されたリスト条件を満たしていない限り、実行可能ファイルの実行をブロックする

この規則は、.exe、.dll、.scr などの実行可能ファイルの起動をブロックします。 したがって、信頼されていない実行可能ファイルまたは不明な実行可能ファイルを起動すると、ファイルが悪意のある場合は最初は明確にならない可能性があるため、リスクが高い可能性があります。

> [!IMPORTANT]
> このルールを使用するには [、クラウド配信の保護を有効にする](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 必要があります。
>
> GUID を使用して **有病率、年齢、または信頼されたリスト条件を満たしていない限り、実行可能ファイルの実行をブロック** するルールは、Microsoft が所有し、管理者は指定しません。`01443614-cd74-433a-b99e-2ecdc07bfc25` この規則では、クラウド配信の保護を使用して、信頼されたリストを定期的に更新します。
>
> 個々のファイルまたはフォルダーを (フォルダー パスまたは完全修飾リソース名を使用して) 指定できますが、適用するルールまたは除外を指定することはできません。

Intune名:`Executables that don't meet a prevalence, age, or trusted list criteria`

Configuration Manager名:`Block executable files from running unless they meet a prevalence, age, or trusted list criteria`

GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`

高度なハンティング アクションの種類:

- AsrUntrustedExecutableAudited
- AsrUntrustedExecutableBlocked

依存関係: MDAV、Cloud Protection

### <a name="block-execution-of-potentially-obfuscated-scripts"></a>難読化される可能性があるスクリプトの実行をブロックする

このルールは、難読化されたスクリプト内で疑わしいプロパティを検出します。

スクリプトの難読化は、マルウェア作成者と正当なアプリケーションの両方が、知的財産を隠したり、スクリプトの読み込み時間を短縮したりするために使用する一般的な手法です。 また、マルウェアの作成者は難読化を使用して、悪意のあるコードの読み取りを困難にし、人間やセキュリティ ソフトウェアによる綿密な調査を防ぎます。

Intune名:`Obfuscated js/vbs/ps/macro code`

Configuration Manager名:`Block execution of potentially obfuscated scripts`

GUID: `5beb7efe-fd9a-4556-801d-275e5ffc04cc`

高度なハンティング アクションの種類:

- AsrObfuscatedScriptAudited
- AsrObfuscatedScriptBlocked

依存関係: MDAV、AMSI

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a>ダウンロードした実行可能コンテンツの起動から JavaScript または VBScript をブロックする

この規則により、スクリプトで悪意のあるダウンロードコンテンツが起動されるのを防ぎます。 JavaScript または VBScript で記述されたマルウェアは、多くの場合、インターネットから他のマルウェアをフェッチして起動するためのダウンローダーとして機能します。

一般的ではありませんが、基幹業務アプリケーションでは、スクリプトを使用してインストーラーをダウンロードして起動する場合があります。

Intune名:`js/vbs executing payload downloaded from Internet (no exceptions)`

Configuration Manager名:`Block JavaScript or VBScript from launching downloaded executable content`

GUID: `d3e037e1-3eb8-44c8-a917-57927947596d`

高度なハンティング アクションの種類:

- AsrScriptExecutableDownloadAudited
- AsrScriptExecutableDownloadBlocked

依存関係: MDAV、AMSI

### <a name="block-office-applications-from-creating-executable-content"></a>アプリケーションOffice実行可能コンテンツの作成をブロックする

この規則により、Word、Excel、PowerPointなどのOffice アプリが悪意のある実行可能コンテンツを作成できないようにします。悪意のあるコードがディスクに書き込まれるのをブロックします。

Officeをベクターとして悪用するマルウェアは、Officeから抜け出し、悪意のあるコンポーネントをディスクに保存しようとする可能性があります。 これらの悪意のあるコンポーネントは、コンピューターの再起動後も存続し、システムに保持されます。 したがって、この規則は、一般的な永続化手法から保護します。

Intune名:`Office apps/macros creating executable content`

SCCM 名: `Block Office applications from creating executable content`

GUID: `3b576869-a4ec-4529-8536-b80a7769e899`

高度なハンティング アクションの種類:

- AsrExecutableOfficeContentAudited
- AsrExecutableOfficeContentBlocked

依存関係: MDAV、RPC

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a>アプリケーションOfficeコードを他のプロセスに挿入できないようにブロックする

このルールは、Office アプリから他のプロセスへのコード挿入の試行をブロックします。

攻撃者は、Office アプリを使用して、コードインジェクションを通じて悪意のあるコードを他のプロセスに移行しようとする可能性があります。そのため、コードはクリーン プロセスとして偽装できます。

コードインジェクションを使用するための既知の正当なビジネス目的はありません。

この規則は、Word、Excel、PowerPointに適用されます。

Intune名:`Office apps injecting code into other processes (no exceptions)`

Configuration Manager名:`Block Office applications from injecting code into other processes`

GUID: `75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84`

高度なハンティング アクションの種類:

- AsrOfficeProcessInjectionAudited
- AsrOfficeProcessInjectionBlocked

依存関係: MDAV

### <a name="block-office-communication-application-from-creating-child-processes"></a>通信アプリケーションOffice子プロセスの作成をブロックする

この規則では、正当なOutlook関数を許可しながら、Outlookが子プロセスを作成できないようにします。

この規則は、ソーシャル エンジニアリング攻撃から保護し、コードを悪用してOutlookの脆弱性を悪用することを防ぎます。 また、ユーザーの資格情報が侵害されたときに攻撃者が使用できる[Outlook規則やフォームの悪用](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/)から保護します。

> [!NOTE]
> このルールは、Outlookの DLP ポリシー ヒントとツールヒントをブロックします。 この規則は、OutlookおよびOutlook.com にのみ適用されます。

Intune名:`Process creation from Office communication products (beta)`

Configuration Manager名: 使用できません

GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`

高度なハンティング アクションの種類:

- AsrOfficeCommAppChildProcessAudited
- AsrOfficeCommAppChildProcessBlocked

依存関係: MDAV

### <a name="block-persistence-through-wmi-event-subscription"></a>WMI イベント サブスクリプションを使用して永続化をブロックする

この規則により、マルウェアが WMI を悪用してデバイスでの永続性を獲得するのを防ぎます。

> [!IMPORTANT]
> ファイルとフォルダーの除外は、この攻撃面の縮小ルールには適用されません。

ファイルレス脅威は、さまざまな戦術を採用して潜伏し、ファイル システムに見つからないようにして、定期的に実行制御を獲得します。 脅威の中には、WMI リポジトリとイベント モデルを悪用して、潜伏できるものがあります。

Intune名: 使用できません

Configuration Manager名: 使用できません

GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`

高度なハンティング アクションの種類:

- AsrPersistenceThroughWmiAudited
- AsrPersistenceThroughWmiBlocked

依存関係: MDAV、RPC

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a>PSExec コマンドと WMI コマンドから生成されたプロセス作成をブロックする

このルールは、 [PsExec](/sysinternals/downloads/psexec) と [WMI](/windows/win32/wmisdk/about-wmi) を介して作成されたプロセスの実行をブロックします。 PsExec と WMI は両方ともリモートでコードを実行できるため、コマンドと制御の目的でこの機能をマルウェアが悪用したり、組織のネットワーク全体に感染を広げたりするリスクがあります。

> [!WARNING]
> このルールは、[Intune](/intune)または別の MDM ソリューションを使用してデバイスを管理している場合にのみ使用します。 この規則は、[Configuration Manager](/configmgr) クライアントが正しく機能するために使用する WMI コマンドをブロックするため、Microsoft Endpoint Configuration Managerを使用した管理と互換性がありません。

Intune名:`Process creation from PSExec and WMI commands`

Configuration Manager名: 適用されません

GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`

高度なハンティング アクションの種類:

- AsrPsexecWmiChildProcessAudited
- AsrPsexecWmiChildProcessBlocked

依存関係: MDAV

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a>USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする

この規則を使用すると、管理者は、SD カードを含む USB リムーバブル ドライブから署名されていない実行可能ファイルまたは信頼されていない実行可能ファイルを実行できないようにすることができます。 ブロックされたファイルの種類には、実行可能ファイル (.exe、.dll、.scr など) が含まれます。

Intune名:`Untrusted and unsigned processes that run from USB`

Configuration Manager名:`Block untrusted and unsigned processes that run from USB`

GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`

高度なハンティング アクションの種類:

- AsrUntrustedUsbProcessAudited
- AsrUntrustedUsbProcessBlocked

依存関係: MDAV

### <a name="block-win32-api-calls-from-office-macros"></a>Office マクロからの Win32 API 呼び出しをブロックする

この規則では、VBA マクロが Win32 API を呼び出すのを防ぎます。

VBA Office Win32 API 呼び出しを有効にします。 マルウェアは、 [Win32 API を呼び出して、ディスクに](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) 直接何も書き込まずに悪意のあるシェルコードを起動するなど、この機能を悪用する可能性があります。 ほとんどの組織は、マクロを他の方法で使用する場合でも、日常の機能で Win32 API を呼び出す機能に依存していません。

サポートされるオペレーティング システム

- [Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows サーバー、バージョン 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune名:`Win32 imports from Office macro code`

Configuration Manager名:`Block Win32 API calls from Office macros`

GUID: `92e97fa1-2edf-4476-bdd6-9dd0b4dddc7b`

高度なハンティング アクションの種類:

- AsrOfficeMacroWin32ApiCallsAudited
- AsrOfficeMacroWin32ApiCallsBlocked

依存関係: MDAV、AMSI

### <a name="use-advanced-protection-against-ransomware"></a>ランサムウェアに対する高度な保護を使用する

このルールは、ランサムウェアに対する保護の追加レイヤーを提供します。 クライアントヒューリスティックとクラウド ヒューリスティックの両方を使用して、ファイルがランサムウェアに似ているかどうかを判断します。 この規則では、次の 1 つ以上の特性を持つファイルはブロックされません。

- このファイルは、Microsoft クラウドで既に無傷であることが判明しています。
- ファイルは有効な署名済みファイルです。
- ファイルはランサムウェアと見なされないほど一般的です。

このルールは、ランサムウェアを防ぐために注意を払う側で誤る傾向があります。

> [!NOTE]
> このルールを使用するには [、クラウド配信の保護を有効にする](enable-cloud-protection-microsoft-defender-antivirus.md) 必要があります。

Intune名:`Advanced ransomware protection`

Configuration Manager名:`Use advanced protection against ransomware`

GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`

高度なハンティング アクションの種類:

- AsrRansomwareAudited
- AsrRansomwareBlocked

依存関係: MDAV、Cloud Protection
