---
title: 攻撃表面の縮小ルールを使用してマルウェアの感染を防止する
description: 攻撃表面の縮小ルールは、悪用がアプリやスクリプトを使用してデバイスにマルウェアに感染するのを防ぐのに役立ちます。
keywords: 攻撃表面の縮小ルール、asr、hips、ホスト侵入防止システム、保護ルール、悪用防止、脆弱性対策、悪用、感染防止、Microsoft Defender for Endpoint、Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: 62f1f5f2d47482f642f00c870b3e0f3112f5f639
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185769"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a>攻撃表面の縮小ルールを使用してマルウェアの感染を防止する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



## <a name="why-attack-surface-reduction-rules-are-important"></a>攻撃表面の縮小ルールが重要な理由

組織の攻撃表面には、攻撃者が組織のデバイスやネットワークを侵害する可能性があるすべての場所が含まれています。 攻撃の表面を減らすことは、組織のデバイスとネットワークを保護する手段であり、攻撃者は攻撃を実行する方法が少なくなっています。 Microsoft Defender for Endpoint で攻撃表面の縮小ルールを構成すると役立ちます。

攻撃表面の縮小ルールは、次のような特定のソフトウェア動作を対象とします。

- ファイルのダウンロードまたは実行を試みる実行可能ファイルとスクリプトを起動する。
- 難読化されたスクリプトまたはその他の疑わしいスクリプトを実行する。そして 
- 通常の毎日の作業中にアプリが開始しない動作を実行します。

このようなソフトウェアの動作は、正当なアプリケーションで見られる場合があります。ただし、これらの動作は、マルウェアを介して攻撃者によって悪用されるのが一般的なので、リスクが高いと見なされる場合が多い。 攻撃表面の縮小ルールは、リスクの高い動作を制限し、組織を安全に保つのに役立ちます。

攻撃表面の縮小ルールの構成の詳細については、「攻撃表面の縮小ルールを有効 [にする」を参照してください](enable-attack-surface-reduction.md)。

## <a name="assess-rule-impact-before-deployment"></a>展開前にルールへの影響を評価する  

攻撃表面の縮小ルールがネットワークに与える影響を評価するには、脅威と脆弱性の管理で、そのルールのセキュリティ推奨事項 [を開きます](https://docs.microsoft.com/windows/security/threat-protection/#tvm)。 

:::image type="content" source="images/asrrecommendation.png" alt-text="攻撃表面の縮小ルールのセキュリティ reco":::

[推奨事項の詳細] ウィンドウで、ユーザーの影響を確認して、生産性に悪影響を及ぼさずに、ブロック モードでルールを有効にする新しいポリシーを受け入れ可能なデバイスの割合を確認します。

## <a name="audit-mode-for-evaluation"></a>評価の監査モード

監査 [モードを使用して](audit-windows-defender.md) 、攻撃表面の縮小ルールが有効になっている場合に組織に与える影響を評価します。 監査モードですべてのルールを最初に実行して、そのルールがビジネスライン アプリケーションに与える影響を理解できます。 多くの業務用アプリケーションは、限られたセキュリティ上の懸念を持って記述され、マルウェアに似た方法でタスクを実行する可能性があります。 監査データを監視し、必要なアプリケーションの [除外](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) を追加することで、生産性を低下させずに攻撃表面の縮小ルールを展開できます。

## <a name="warn-mode-for-users"></a>ユーザーの警告モード

(**NEW**!)警告モード機能の前に、有効になっている攻撃表面の縮小ルールを監査モードまたはブロック モードに設定できます。 新しい警告モードでは、攻撃表面の縮小ルールによってコンテンツがブロックされるたびに、コンテンツがブロックされたかどうかを示すダイアログ ボックスが表示されます。 ダイアログ ボックスには、コンテンツのブロックを解除するオプションも表示されます。 その後、ユーザーはアクションを再試行し、操作が完了します。 ユーザーがコンテンツのブロックを解除すると、コンテンツは 24 時間ブロック解除されたままで、その後ブロックが再開されます。

警告モードは、ユーザーが自分のタスクを実行するために必要なコンテンツにアクセスするのを防ぐことなく、組織が攻撃表面の縮小ルールを設定するのに役立ちます。 

### <a name="requirements-for-warn-mode-to-work"></a>警告モードが機能する要件

警告モードは、次のバージョンの Windows を実行しているデバイスでサポートされています。
- [Windows 10 バージョン 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) 以降
- [Windows Server バージョン 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809) 以降
 
Microsoft Defender ウイルス対策は、アクティブ モードでリアルタイム保護を使用して [実行されている必要があります](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)。

さらに [、Microsoft Defender ウイルス対策とマルウェア対策の更新プログラムがインストールされていることを](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) 確認します。
- プラットフォームリリースの最小要件: `4.18.2008.9`  
- エンジンリリースの最小要件: `1.1.17400.5`

詳細と更新プログラムの取得については [、「Update for Microsoft Defender マルウェア対策プラットフォーム」を参照してください](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)。

### <a name="cases-where-warn-mode-is-not-supported"></a>警告モードがサポートされていない場合

警告モードは、次の攻撃表面縮小ルールではサポートされていません。

- [ダウンロードした実行可能コンテンツ (GUID)](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)の起動から JavaScript または VBScript をブロックする `d3e037e1-3eb8-44c8-a917-57927947596d`
- [WMI イベント サブスクリプション (GUID) による永続](#block-persistence-through-wmi-event-subscription) 化をブロック `e6db77e5-3df2-4cf1-b95a-636979351e5b` する
- [ランサムウェアに対する高度な保護を使用](#use-advanced-protection-against-ransomware) する `c1db55ab-c21a-4637-bb3f-a12568109d35` (GUID)

また、以前のバージョンの Windows を実行しているデバイスでは、警告モードはサポートされていません。 このような場合、警告モードで実行するように構成された攻撃表面の縮小ルールは、ブロック モードで実行されます。

## <a name="notifications-and-alerts"></a>通知とアラート

攻撃表面の縮小ルールがトリガーされるたびに、デバイスに通知が表示されます。 通知は [、会社の詳細](customize-attack-surface-reduction.md#customize-the-notification) と連絡先情報でカスタマイズできます。

さらに、特定の攻撃表面の縮小ルールがトリガーされると、アラートが生成されます。 

通知と生成されるアラートは、Microsoft Defender セキュリティ センター ( ) と Microsoft 365 セキュリティ センター [https://securitycenter.windows.com](https://securitycenter.windows.com) ( ) で表示できます [https://security.microsoft.com](https://security.microsoft.com) 。

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a>高度な狩猟と攻撃表面の縮小イベント

高度な検索を使用して、攻撃表面の縮小イベントを表示できます。 受信データの量を合理化するために、高度な検索では、1 時間ごとに一意のプロセスのみを表示できます。 攻撃表面の縮小イベントの時間は、1 時間以内に初めてイベントが表示されます。

たとえば、午後 2 時の間に 10 台のデバイスで攻撃表面の縮小イベントが発生するとします。 最初のイベントが 2:15、最後の 2:45 に発生したとします。 高度な検索では、そのイベントのインスタンスが 1 つ表示されます (実際には 10 台のデバイスで発生した場合でも)、タイムスタンプは午後 2 時 15 分になります。 

高度な狩猟の詳細については、「高度な狩猟 [を使用して脅威を事前に検出する」を参照してください](advanced-hunting-overview.md)。

## <a name="attack-surface-reduction-features-across-windows-versions"></a>Windows バージョン全体の攻撃表面の縮小機能

次のエディションとバージョンの Windows を実行しているデバイスに対して攻撃表面の縮小ルールを設定できます。
- Windows 10 Pro [バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 以降
- Windows 10 Enterprise バージョン [1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 以降
- Windows Server バージョン [1803 (半期チャネル)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) 以降
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

攻撃表面の縮小ルールは [Windows E5](https://docs.microsoft.com/windows/deployment/deploy-enterprise-licenses)ライセンスを必要としますが、Windows E5 を使用している場合は、高度な管理機能を利用できます。 Windows E5 でのみ使用できるこれらの機能には [、Defender for Endpoint](microsoft-defender-endpoint.md)で使用できる監視、分析、ワークフロー、 [および Microsoft 365](https://docs.microsoft.com/microsoft-365/security/defender/overview-security-center)セキュリティ センターのレポート機能と構成機能が含まれます。 これらの高度な機能は、Windows Professional または Windows E3 ライセンスでは使用できません。ただし、これらのライセンスがある場合は、イベント ビューアーと Microsoft Defender ウイルス対策ログを使用して攻撃表面の縮小ルール イベントを確認できます。

## <a name="review-attack-surface-reduction-events-in-the-microsoft-defender-security-center"></a>Microsoft Defender セキュリティ センターで攻撃表面の縮小イベントを確認する

Defender for Endpoint は、アラート調査シナリオの一環として、イベントとブロックの詳細なレポートを提供します。

高度な検索を使用して Defender for Endpoint データ [を照会できます](advanced-hunting-query-language.md)。 監査モードを実行している [場合](audit-windows-defender.md)は、高度な検索を使用して、攻撃表面の縮小ルールが環境に与える影響を理解できます。

クエリの例を次に示します。

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>Windows イベント ビューアーで攻撃表面の縮小イベントを確認する

Windows イベント ログを確認して、攻撃表面の縮小ルールによって生成されたイベントを表示できます。

1. 評価パッケージ [をダウンロードし](https://aka.ms/mp7z2w) 、デバイス上 *cfa-events.xmlアクセスしやすい* 場所にファイルを抽出します。
2. [スタート] メニューに *「イベント ビューアー*」という単語を入力して、Windows イベント ビューアーを開きます。
3. [アクション **] で**、[カスタム **ビューのインポート.... を選択します**。
4. 抽出された場所 *cfa-events.xml* ファイルを選択します。 または [、XML を直接コピーします](event-views.md)。
5. **[OK]** をクリックします。

イベントをフィルター処理して、次のイベントのみを表示するカスタム ビューを作成できます。そのすべては、フォルダー アクセスの制御に関連しています。

|イベント ID | 説明 |
|:---|:---|
|5007 | 設定が変更された場合のイベント |
|1121 | ブロック モードでルールが発生した場合のイベント |
|1122 | 監査モードでルールが発生した場合のイベント |

イベント ログの攻撃表面の縮小イベント用にリストされている "エンジンバージョン" は、オペレーティング システムではなく Defender for Endpoint によって生成されます。 Defender for Endpoint は Windows 10 と統合されています。そのため、この機能は Windows 10 がインストールされているすべてのデバイスで動作します。

## <a name="attack-surface-reduction-rules"></a>攻撃面の減少ルール

次の表とサブセクションでは、15 の攻撃表面の縮小ルールのそれぞれについて説明します。 攻撃表面の縮小ルールは、ルール名によってアルファベット順に表示されます。 

グループ ポリシーまたは PowerShell を使用して攻撃表面の縮小ルールを構成する場合は、GUID が必要です。 一方、Microsoft Endpoint Manager または Microsoft Intune を使用する場合は、GUID は必要とされません。


| ルールの名前 | GUID | ファイル&フォルダーの除外 | サポートされる最小 OS |
|:-----|:-----:|:-----|:-----|
|[Adobe Reader の子プロセスの作成をブロックする](#block-adobe-reader-from-creating-child-processes) | `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c` | サポート済み | [Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上 |
|[すべてのアプリケーションOffice子プロセスの作成をブロックする](#block-all-office-applications-from-creating-child-processes) | `D4F940AB-401B-4EFC-AADC-AD5F3C50688A` | サポート済み | [Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上 |
|[Windows ローカル セキュリティ機関サブシステムからの資格情報の盗用をブロックする (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2` | サポート済み | [Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上 |
|[メール クライアントと Web メールから実行可能なコンテンツをブロックする](#block-executable-content-from-email-client-and-webmail) | `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550` | サポート済み | [Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上 |
|[有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | `01443614-cd74-433a-b99e-2ecdc07bfc25` | サポート済み | [Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上 |
|[難読化される可能性のあるスクリプトの実行をブロックする](#block-execution-of-potentially-obfuscated-scripts) | `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC` | サポート済み | [Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上 |
|[JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | `D3E037E1-3EB8-44C8-A917-57927947596D` | サポート済み | [Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上 |
|[実行可能Office作成するアプリケーションをブロックする](#block-office-applications-from-creating-executable-content) | `3B576869-A4EC-4529-8536-B80A7769E899` | サポート済み | [Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上 |
|[アプリケーションOffice他のプロセスへのコードの挿入をブロックする](#block-office-applications-from-injecting-code-into-other-processes) | `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84` | サポート済み | [Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上 |
|[通信Office子プロセスの作成をブロックする](#block-office-communication-application-from-creating-child-processes) |`26190899-1602-49e8-8b27-eb1d0a1ce869` |サポート済み |[Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上  |
|[WMI イベント サブスクリプションによる永続化のブロック](#block-persistence-through-wmi-event-subscription) | `e6db77e5-3df2-4cf1-b95a-636979351e5b` | 非サポート | [Windows 10 バージョン 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) (ビルド 18362) 以上 |
|[PSExec および WMI コマンドから発生するプロセス作成をブロックする](#block-process-creations-originating-from-psexec-and-wmi-commands) | `d1e49aac-8f56-4280-b9ba-993a6d77406c` | サポート済み | [Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上 |
|[USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする](#block-untrusted-and-unsigned-processes-that-run-from-usb) | `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4` | サポート済み | [Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上 |
|[Win32 API 呼び出しをブロックOfficeマクロ](#block-win32-api-calls-from-office-macros) | `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B` | サポート済み | [Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上 |
|[ランサムウェアに対する高度な保護の使用](#use-advanced-protection-against-ransomware) | `c1db55ab-c21a-4637-bb3f-a12568109d35` | サポート済み | [Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上 |

### <a name="block-adobe-reader-from-creating-child-processes"></a>Adobe Reader の子プロセスの作成をブロックする

このルールは、Adobe Reader によるプロセスの作成をブロックすることで攻撃を防止します。

ソーシャル エンジニアリングや悪用を通じて、マルウェアはペイロードをダウンロードして起動し、Adobe Reader から抜け出す可能性があります。 Adobe Reader によって子プロセスが生成されるのをブロックすることで、子プロセスをベクターとして使用しようとするマルウェアが拡散を防止します。

このルールは次の中で導入されました。 
- [Windows 10 バージョン 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows Server バージョン 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Intune 名: `Process creation from Adobe Reader (beta)`

Configuration Manager 名: まだ使用できません

GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`

### <a name="block-all-office-applications-from-creating-child-processes"></a>すべてのアプリケーションOffice子プロセスの作成をブロックする

このルールは、Officeプロセスの作成をブロックします。 Officeには、Word、Excel、PowerPoint、OneNote、Access が含まれます。

悪意のある子プロセスを作成する方法は、一般的なマルウェア戦略です。 マルウェアがベクターとしてOfficeマルウェアは、VBA マクロを実行し、コードを悪用して、より多くのペイロードをダウンロードして実行しようとする場合が多い。 ただし、一部の正当な業務行アプリケーションでは、コマンド プロンプトの生成や PowerShell を使用してレジストリ設定を構成するなどの、適切な目的で子プロセスを生成する場合があります。

このルールは次の中で導入されました。 
- [Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server バージョン 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune 名: `Office apps launching child processes`

Configuration Manager 名: `Block Office application from creating child processes`

GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a>Windows ローカル セキュリティ機関サブシステムからの資格情報の盗用をブロックする

このルールは、ローカル セキュリティ機関サブシステム サービス (LSASS) をロックダウンすることで、資格情報の盗用を防ぐのに役立ちます。

LSASS は、Windows コンピューターでサインインするユーザーを認証します。 Windows 10 の Microsoft Defender Credential Guard は、通常、LSASS から資格情報を抽出しようとする試みを防止します。 ただし、一部の組織では、カスタム スマートカード ドライバーやローカル セキュリティ機関 (LSA) に読み込む他のプログラムとの互換性の問題により、すべてのコンピューターで Credential Guard を有効にできない場合があります。 このような場合、攻撃者は Mimikatz のようなハッキング ツールを使用して、LSASS からクリアテキスト パスワードと NTLM ハッシュをスクレイピングできます。

> [!NOTE]
> 一部のアプリでは、実行中のすべてのプロセスを列挙し、網羅的なアクセス許可を使用して開きます。 このルールは、アプリのプロセスのオープン アクションを拒否し、詳細をセキュリティ イベント ログに記録します。 このルールでは、多くのノイズが発生する可能性があります。 LSASS を列挙するだけで、機能に実際の影響がないアプリがある場合は、除外リストに追加する必要はありません。 それ自体では、このイベント ログ エントリは必ずしも悪意のある脅威を示すとは限りません。

このルールは次の中で導入されました。
- [Windows 10 バージョン 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server バージョン 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune 名: `Flag credential stealing from the Windows local security authority subsystem`

Configuration Manager 名: `Block credential stealing from the Windows local security authority subsystem`

GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`

### <a name="block-executable-content-from-email-client-and-webmail"></a>メール クライアントと Web メールから実行可能なコンテンツをブロックする

このルールは、次のファイルの種類が、Microsoft Outlook アプリケーション内で開いた電子メール、または他の一般的な webmail プロバイダー Outlook.com から起動をブロックします。

- 実行可能ファイル (.exe、.dll、.scr など)
- スクリプト ファイル (PowerShell .ps、Visual Basic .vbs、JavaScript .js ファイルなど)

このルールは次の中で導入されました。 
- [Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server バージョン 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Microsoft Endpoint Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune 名: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`

Microsoft Endpoint Manager 名: `Block executable content from email client and webmail`

GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`

> [!NOTE]
> [メール **クライアントと Web メールからの** 実行可能なコンテンツをブロックする] というルールには、使用するアプリケーションに応じて、次の別の説明があります。
> - Intune (構成プロファイル): 電子メール (Web メール/メール クライアント) から削除された実行可能コンテンツ (exe、dll、ps、js、vbs など) の実行 (例外なし)。
> - エンドポイント マネージャー: 電子メールおよび Web メール クライアントからの実行可能なコンテンツのダウンロードをブロックします。
> - グループ ポリシー: 電子メール クライアントと Web メールから実行可能なコンテンツをブロックします。

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a>有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする

このルールは、有病率や年齢の条件を満たしたり、信頼できるリストまたは除外リストに含めない限り、次の種類のファイルの起動をブロックします。

- 実行可能ファイル (.exe、.dll、.scr など)

信頼されていない実行可能ファイルまたは不明な実行可能ファイルを起動すると、ファイルが悪意のある場合、最初は明確にできない可能性があります。

> [!IMPORTANT]
> このルールを [使用するには、クラウドによる保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) を有効にする必要があります。 <br/><br/> GUID で **有病率** 、年齢、または信頼できるリスト条件を満たしていない場合、実行可能ファイルの実行をブロックするルールは、Microsoft が所有し、管理者によって `01443614-cd74-433a-b99e-2ecdc07bfc25` 指定されていません。 このルールでは、クラウド配信の保護を使用して、信頼できるリストを定期的に更新します。
>
>個々のファイルまたはフォルダー (フォルダー パスまたは完全修飾リソース名を使用) を指定できますが、適用するルールや除外を指定することはできません。

このルールは次の中で導入されました。 
- [Windows 10 バージョン 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server バージョン 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune 名: `Executables that don't meet a prevalence, age, or trusted list criteria`

Configuration Manager 名: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`

GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`

### <a name="block-execution-of-potentially-obfuscated-scripts"></a>難読化される可能性のあるスクリプトの実行をブロックする

このルールは、難読化されたスクリプト内の疑わしいプロパティを検出します。

スクリプト難読化は、マルウェア作成者と正当なアプリケーションの両方が、知的財産を隠したり、スクリプトの読み込み時間を短縮したりするために使用する一般的な手法です。 マルウェアの作成者は難読化を使用して悪意のあるコードを読みにくくし、人間やセキュリティ ソフトウェアによる詳細な調査を防止します。

このルールは次の中で導入されました。
- [Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server バージョン 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune 名: `Obfuscated js/vbs/ps/macro code`

Configuration Manager 名: `Block execution of potentially obfuscated scripts`

GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a>JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする

このルールにより、スクリプトは悪意のあるダウンロードコンテンツを起動できません。 JavaScript または VBScript で記述されたマルウェアは、インターネットから他のマルウェアをフェッチして起動するダウンデータとして機能する場合が多い。

一般的ではないが、一般企業向けアプリケーションでは、スクリプトを使用してインストーラーをダウンロードおよび起動する場合があります。

このルールは次の中で導入されました。  
- [Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server バージョン 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune 名: `js/vbs executing payload downloaded from Internet (no exceptions)`

Configuration Manager 名: `Block JavaScript or VBScript from launching downloaded executable content`

GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`

### <a name="block-office-applications-from-creating-executable-content"></a>実行可能Office作成するアプリケーションをブロックする

このルールは、悪意のあるOfficeコードがディスクに書き込まれるのをブロックすることで、Word、Excel、PowerPoint などのアプリによる悪意のある実行可能コンテンツの作成を防止します。

マルウェアは、Officeとして悪用され、悪意のあるOfficeをディスクに保存しようとする可能性があります。 これらの悪意のあるコンポーネントは、コンピューターの再起動後も存続し、システム上で保持されます。 したがって、このルールは一般的な永続化手法に対して防御します。

このルールは次の中で導入されました。 
- [Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server バージョン 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [System Center Configuration Manager](https://docs.microsoft.com/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM は現在 Microsoft Endpoint Configuration Manager)

Intune 名: `Office apps/macros creating executable content`

SCCM 名: `Block Office applications from creating executable content`

GUID: `3B576869-A4EC-4529-8536-B80A7769E899`

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a>アプリケーションOffice他のプロセスへのコードの挿入をブロックする

このルールは、アプリから他のプロセスへのコードOffice試行をブロックします。

攻撃者は、Officeを使用して、コード挿入を通じて悪意のあるコードを他のプロセスに移行しようとする可能性があります。そのため、コードはクリーン なプロセスとして悪用される可能性があります。

コードインジェクションを使用する正当なビジネス上の目的はありません。

このルールは、Word、Excel、および PowerPoint に適用されます。

このルールは次の中で導入されました。 
- [Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server バージョン 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune 名: `Office apps injecting code into other processes (no exceptions)`

Configuration Manager 名: `Block Office applications from injecting code into other processes`

GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`

### <a name="block-office-communication-application-from-creating-child-processes"></a>通信Office子プロセスの作成をブロックする

このルールは、Outlook が子プロセスを作成することを妨げる一方で、正当な Outlook 関数を許可します。

このルールは、ソーシャル エンジニアリング攻撃から保護し、Outlook の脆弱性を悪用するコードの悪用を防止します。 また、ユーザーの [資格情報が侵害された](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) 場合に攻撃者が使用できる Outlook ルールやフォームの悪用から保護します。

> [!NOTE]
> このルールは、Outlook および Outlook Outlook.com 適用されます。

このルールは次の中で導入されました。 
- [Windows 10 バージョン 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows Server バージョン 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Intune 名: `Process creation from Office communication products (beta)`

Configuration Manager 名: 使用できません

GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`

### <a name="block-persistence-through-wmi-event-subscription"></a>WMI イベント サブスクリプションによる永続化のブロック

このルールは、デバイス上で WMI を攻撃して永続化を達成するマルウェアを防止します。

> [!IMPORTANT]
> ファイルとフォルダーの除外は、この攻撃表面の縮小ルールには適用されません。

ファイルレスの脅威は、隠し、ファイル システムで見られない、定期的な実行制御を得るために、さまざまな戦術を採用しています。 一部の脅威は、WMI リポジトリとイベント モデルを悪用して非表示にできます。

このルールは次の中で導入されました。 
- [Windows 10 バージョン 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903)
- [Windows Server 1903](https://docs.microsoft.com/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

Intune 名: 使用できません

Configuration Manager 名: 使用できません

GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a>PSExec および WMI コマンドから発生するプロセス作成をブロックする

このルールは [、PsExec](https://docs.microsoft.com/sysinternals/downloads/psexec) および WMI を介して作成 [されたプロセスの実行](https://docs.microsoft.com/windows/win32/wmisdk/about-wmi) をブロックします。 PsExec と WMI の両方がコードをリモートで実行できるので、コマンドと制御の目的でこの機能を不正に使用したり、組織のネットワーク全体に感染を広げる危険性があります。

> [!WARNING]
> Intune または別の MDM ソリューションを使用してデバイスを管理する場合にのみ、 [このルールを](https://docs.microsoft.com/intune) 使用します。 このルールは [、Configuration Manager](https://docs.microsoft.com/configmgr) クライアントが正しく機能するために使用する WMI コマンドをブロックする Microsoft Endpoint Configuration Manager による管理と互換性がありません。

このルールは次の中で導入されました。 
- [Windows 10 バージョン 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server バージョン 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Intune 名: `Process creation from PSExec and WMI commands`

Configuration Manager 名: 該当なし

GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a>USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする

このルールを使用すると、管理者は、SD カードを含む USB リムーバブル ドライブから署名されていない実行可能ファイルまたは信頼されていない実行可能ファイルを実行できません。 ブロックされたファイルの種類には、実行可能ファイル (.exe、.dll、.scr など) が含まれます。

このルールは次の中で導入されました。 
- [Windows 10 バージョン 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server バージョン 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune 名: `Untrusted and unsigned processes that run from USB`

Configuration Manager 名: `Block untrusted and unsigned processes that run from USB`

GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`

### <a name="block-win32-api-calls-from-office-macros"></a>Win32 API 呼び出しをブロックOfficeマクロ

このルールは、VBA マクロが Win32 API を呼び出すのを防止します。

Office VBA では、Win32 API 呼び出しが有効です。 マルウェアは [、Win32 API](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) を呼び出してディスクに直接何も書き込みせずに悪意のあるシェルコードを起動するなど、この機能を悪用する可能性があります。 ほとんどの組織では、他の方法でマクロを使用している場合でも、Win32 API を毎日の機能で呼び出す機能に依存しません。

このルールは次の中で導入されました。
- [Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server バージョン 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune 名: `Win32 imports from Office macro code`

Configuration Manager 名: `Block Win32 API calls from Office macros`

GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`

### <a name="use-advanced-protection-against-ransomware"></a>ランサムウェアに対する高度な保護の使用

このルールは、ランサムウェアに対する保護の追加層を提供します。 システムに入る実行可能ファイルをスキャンして、信頼できるかどうかを判断します。 ファイルがランサムウェアと密接に似ている場合、このルールは、信頼できるリストまたは除外リストに含まれる場合を含め、ファイルの実行をブロックします。

> [!NOTE]
> このルールを [使用するには、クラウドによる保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) を有効にする必要があります。

このルールは次の中で導入されました。 
- [Windows 10 バージョン 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server バージョン 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Intune 名: `Advanced ransomware protection`

Configuration Manager 名: `Use advanced protection against ransomware`

GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`

## <a name="see-also"></a>関連項目

- [攻撃表面の縮小に関する FAQ](attack-surface-reduction-faq.md)
- [攻撃表面の縮小ルールを有効にする](enable-attack-surface-reduction.md)
- [攻撃表面の縮小ルールを評価する](evaluate-attack-surface-reduction.md)
- [Microsoft Defender Antivirus と他のウイルス対策/マルウェア対策ソリューションとの互換性](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
