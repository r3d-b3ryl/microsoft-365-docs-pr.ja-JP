---
title: マルウェア感染を防ぐために攻撃面の減少ルールを使用する
description: 攻撃表面の縮小ルールは、悪用がアプリやスクリプトを使用してデバイスにマルウェアに感染するのを防ぐのに役立ちます。
keywords: 攻撃表面の縮小ルール、asr、hips、ホスト侵入防止システム、保護ルール、悪用防止、脆弱性対策、悪用、感染防止、Microsoft Defender for Endpoint
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 5392cf40a0d37e332d7b3bec260ab34e9a3a083e
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2021
ms.locfileid: "60882443"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a>マルウェア感染を防ぐために攻撃面の減少ルールを使用する

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="why-attack-surface-reduction-rules-are-important"></a>攻撃表面の縮小ルールが重要な理由

組織の攻撃表面には、攻撃者が組織のデバイスやネットワークを侵害する可能性があるすべての場所が含まれています。 攻撃の表面を減らすことは、組織のデバイスとネットワークを保護する手段であり、攻撃者は攻撃を実行する方法が少なくなっています。 Microsoft Defender for Endpoint で攻撃表面の縮小ルールを構成すると役立ちます。

攻撃表面の縮小ルールは、次のような特定のソフトウェア動作を対象とします。

- ファイルのダウンロードまたは実行を試みる実行可能ファイルとスクリプトの起動
- 難読化されたスクリプトまたはその他の疑わしいスクリプトを実行する
- 通常の毎日の作業中にアプリが通常開始しない動作を実行する

このようなソフトウェアの動作は、正当なアプリケーションで見られる場合があります。 ただし、これらの動作は、マルウェアを介して攻撃者によって悪用されるのが一般的なので、リスクが高いと見なされる場合が多い。 攻撃表面の縮小ルールは、ソフトウェア ベースのリスクの高い動作を制限し、組織の安全を維持するのに役立ちます。

攻撃表面の縮小ルールの構成の詳細については、「攻撃表面の縮小ルールを有効 [にする」を参照してください](enable-attack-surface-reduction.md)。

## <a name="assess-rule-impact-before-deployment"></a>展開前にルールへの影響を評価する

攻撃表面の縮小ルールがネットワークに与える影響を評価するには、このルールのセキュリティに関する推奨事項を [脅威と脆弱性の管理][で開きます](/windows/security/threat-protection/#tvm)。

:::image type="content" source="images/asrrecommendation.png" alt-text="攻撃表面の縮小ルールのセキュリティ reco。":::

[推奨事項の詳細] ウィンドウで、ユーザーの影響を確認して、生産性に悪影響を及ぼさずに、ブロック モードでルールを有効にする新しいポリシーを受け入れ可能なデバイスの割合を確認します。

サポート [されるオペレーティング システムと](enable-attack-surface-reduction.md#requirements) 追加の要件情報については、「攻撃表面縮小ルールを有効にする」の記事の「要件」を参照してください。

## <a name="audit-mode-for-evaluation"></a>評価の監査モード

監査 [モードを使用して](audit-windows-defender.md) 、攻撃表面の縮小ルールが有効な場合に組織に与える影響を評価します。 監査モードですべてのルールを最初に実行して、そのルールがビジネスライン アプリケーションに与える影響を理解できます。 多くの業務用アプリケーションは、限られたセキュリティ上の懸念を持って記述され、マルウェアに似た方法でタスクを実行する可能性があります。 監査データを監視し、必要なアプリケーションの [除外](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) を追加することで、生産性を低下させずに攻撃表面の縮小ルールを展開できます。

## <a name="warn-mode-for-users"></a>ユーザーの警告モード

(**NEW**!)警告モード機能の前に、有効になっている攻撃表面の縮小ルールを監査モードまたはブロック モードに設定できます。 新しい警告モードでは、攻撃表面の縮小ルールによってコンテンツがブロックされるたびに、コンテンツがブロックされたかどうかを示すダイアログ ボックスが表示されます。 ダイアログ ボックスには、コンテンツのブロックを解除するオプションも表示されます。 その後、ユーザーはアクションを再試行し、操作が完了します。 ユーザーがコンテンツのブロックを解除すると、コンテンツは 24 時間ブロック解除されたままで、その後ブロックが再開されます。

警告モードは、ユーザーが自分のタスクを実行するために必要なコンテンツにアクセスするのを防ぐことなく、組織が攻撃表面の縮小ルールを設定するのに役立ちます。

### <a name="requirements-for-warn-mode-to-work"></a>警告モードが機能する要件

警告モードは、次のバージョンの警告を実行しているデバイスWindows。

- [Windows 10 Version 1809](/windows/whats-new/whats-new-windows-10-version-1809)以降
- Windows 11
- [Windows Server バージョン 1809](/windows-server/get-started/whats-new-in-windows-server-1809)以降

Microsoft Defender ウイルス対策モードでリアルタイム保護を実行している[必要があります](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)。

また、マルウェア対策[Microsoft Defender ウイルス対策更新プログラムがインストールされていることを](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)確認します。

- プラットフォームリリースの最小要件: `4.18.2008.9`
- エンジンリリースの最小要件: `1.1.17400.5`

詳細と更新プログラムの取得については [、「Update for Microsoft Defender マルウェア対策プラットフォーム」を参照してください](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)。

### <a name="cases-where-warn-mode-is-not-supported"></a>警告モードがサポートされていない場合

警告モードは、3 つの攻撃表面の縮小ルールを構成するときにサポートMicrosoft エンドポイント マネージャー。 (グループ ポリシーを使用して攻撃表面の縮小ルールを構成する場合は、警告モードがサポートされます)。警告モードを構成するときに警告モードをサポートしない 3 つのMicrosoft エンドポイント マネージャーは次のとおりです。

- [ダウンロードした実行可能コンテンツ (GUID)](attack-surface-reduction-rules.md#block-javascript-or-vbscript-from-launching-downloaded-executable-content)の起動から JavaScript または VBScript をブロックする `d3e037e1-3eb8-44c8-a917-57927947596d`
- [WMI イベント サブスクリプション (GUID) による永続](attack-surface-reduction-rules.md#block-persistence-through-wmi-event-subscription) 化をブロック `e6db77e5-3df2-4cf1-b95a-636979351e5b` する
- [ランサムウェアに対する高度な保護を使用](attack-surface-reduction-rules.md#use-advanced-protection-against-ransomware) する `c1db55ab-c21a-4637-bb3f-a12568109d35` (GUID)

また、警告モードは、以前のバージョンのサーバーを実行しているデバイスではWindows。 このような場合、警告モードで実行するように構成された攻撃表面の縮小ルールは、ブロック モードで実行されます。

## <a name="notifications-and-alerts"></a>通知とアラート

攻撃表面の縮小ルールがトリガーされるたびに、デバイスに通知が表示されます。 会社の詳細や連絡先情報を使用して[通知をカスタマイズ](customize-attack-surface-reduction.md#customize-the-notification)することができます。

また、特定の攻撃表面縮小ルールがトリガーされると、アラートが生成されます。

通知と生成されたアラートは、Microsoft 365 Defender ポータル ( ) (以前は [https://security.microsoft.com](https://security.microsoft.com) Microsoft 365 Defender)[で表示できます](microsoft-defender-security-center.md)。

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a>高度な狩猟と攻撃表面の縮小イベント

高度な検索を使用して、攻撃表面の縮小イベントを表示できます。 受信データの量を合理化するために、高度な検索では、1 時間ごとに一意のプロセスのみを表示できます。 攻撃表面の縮小イベントの時間は、1 時間以内に初めてイベントが表示されます。

たとえば、午後 2 時の間に 10 台のデバイスで攻撃表面の縮小イベントが発生するとします。 最初のイベントが 2:15、最後の 2:45 に発生したとします。 高度な検索では、そのイベントのインスタンスが 1 つ表示されます (実際には 10 台のデバイスで発生した場合でも)、タイムスタンプは午後 2 時 15 分になります。

高度な狩猟の詳細については、「高度な狩猟 [を使用して脅威を事前に検出する」を参照してください](advanced-hunting-overview.md)。

## <a name="attack-surface-reduction-features-across-windows-versions"></a>複数のバージョンの攻撃表面Windows機能

次のエディションとバージョンのデバイスを実行しているデバイスに対して攻撃表面の縮小ルールをWindows。

- Windows 10 Proバージョン[1709](/windows/whats-new/whats-new-windows-10-version-1709)以降
- Windows 10 Enterpriseバージョン[1709](/windows/whats-new/whats-new-windows-10-version-1709)以降
- Windowsサーバー、[バージョン 1803 (半期チャネル)](/windows-server/get-started/whats-new-in-windows-server-1803)以降
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)

  >[!NOTE]
  >Windows Server 2016および Windows Server 2012 R2 は、この機能を動作するには、「オンボード サーバー Windows[](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)を使用してオンボードする必要があります。 


攻撃表面の縮小ルールでは[E5](/windows/deployment/deploy-enterprise-licenses)ライセンスをWindows必要とWindows、高度な管理機能を利用できます。 E5 でのみ使用できる高度な機能はWindows含まれます。

- Defender for Endpoint で利用できる監視、分析、 [およびワークフロー](microsoft-defender-endpoint.md)
- レポート機能と構成機能は[、Microsoft 365 Defender。](/microsoft-365/security/defender/overview-security-center)

これらの高度な機能は、E3 ライセンスWindows ProfessionalまたはWindows使用できません。 ただし、これらのライセンスがある場合は、イベント ビューアーとログMicrosoft Defender ウイルス対策を使用して、攻撃表面の縮小ルール イベントを確認できます。

## <a name="review-attack-surface-reduction-events-in-the-microsoft-365-defender-portal"></a>ポータルで攻撃表面の縮小イベントをMicrosoft 365 Defenderする

Defender for Endpoint は、アラート調査シナリオの一環として、イベントとブロックの詳細なレポートを提供します。

高度な検索を使用して、Microsoft 365 Defender Defender [for](microsoft-defender-security-center.md) Endpoint データ[をクエリできます](advanced-hunting-query-language.md)。 監査モードを実行している [場合](audit-windows-defender.md)は、高度な検索を使用して、攻撃表面の縮小ルールが環境に与える影響を理解できます。

クエリの例を次に示します。

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>イベント ビューアーで攻撃表面の縮小イベントWindows確認する

次のイベント ログをWindowsして、攻撃表面の縮小ルールによって生成されたイベントを表示できます。

1. 評価パッケージ [をダウンロードし](https://aka.ms/mp7z2w) 、デバイス上 *cfa-events.xmlアクセスしやすい* 場所にファイルを抽出します。

2. [イベント ビューアー] という *単語* を入力して、スタート メニューを開Windowsします。

3. [アクション **] で**、[カスタム **ビューのインポート.... を選択します**。

4. 抽出された場所 *cfa-events.xml* ファイルを選択します。 または [、XML を直接コピーします](event-views.md)。

5. **[OK]** を選択します。

イベントをフィルター処理して、次のイベントのみを表示するカスタム ビューを作成できます。そのすべては、フォルダー アクセスの制御に関連しています。

|イベント ID|説明|
|---|---|
|5007|設定が変更された場合のイベント|
|1121|ブロック モードでルールが発生した場合のイベント|
|1122|監査モードでルールが発生した場合のイベント|

イベント ログの攻撃表面の縮小イベント用にリストされている "エンジンバージョン" は、オペレーティング システムではなく Defender for Endpoint によって生成されます。 Defender for Endpoint は Windows 10 および Windows 11 と統合されています。この機能は、Windows 10 または Windows 11 がインストールされているすべてのデバイスで動作します。

## <a name="attack-surface-reduction-rules"></a>攻撃面の減少ルール

次の表とサブセクションでは、16 の攻撃表面の縮小ルールについて説明します。 攻撃表面の縮小ルールは、ルール名によってアルファベット順に表示されます。

グループ ポリシーまたは PowerShell を使用して攻撃表面の縮小ルールを構成する場合は、GUID が必要です。 一方、ユーザー設定またはMicrosoft エンドポイント マネージャーをMicrosoft Intune GUID は必要とされません。

|ルールの名前|GUID|ファイル&フォルダーの除外|サポートされる最小 OS|
|---|:---:|---|---|
|[悪用された脆弱な署名済みドライバーの悪用をブロックする](#block-abuse-of-exploited-vulnerable-signed-drivers)|`56a863a9-875e-4185-98a7-b882c64b5ce5`|サポート|[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上、または Windows 11|
|[Adobe Reader の子プロセスの作成をブロックする](#block-adobe-reader-from-creating-child-processes)|`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`|サポート|[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上、または Windows 11 <br>  [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) <br> [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2) |
|[すべてのアプリケーションOffice子プロセスの作成をブロックする](#block-all-office-applications-from-creating-child-processes)|`D4F940AB-401B-4EFC-AADC-AD5F3C50688A`|サポート|[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上、または Windows 11 <br> Windows Server 2016|
|[ローカル セキュリティ機関サブシステムからの資格情報のWindowsをブロックする (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem)|`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`|サポート|[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上、または Windows 11 <br><br>  [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) <br> [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)|
|[メール クライアントと Web メールから実行可能なコンテンツをブロックする](#block-executable-content-from-email-client-and-webmail)|`BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`|サポート|[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上、または Windows 11 <br> Windows Server 2016 <br> Windows Server 2012 R2|
|[有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)|`01443614-cd74-433a-b99e-2ecdc07bfc25`|サポート|[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上、または Windows 11|
|[難読化される可能性のあるスクリプトの実行をブロックする](#block-execution-of-potentially-obfuscated-scripts)|`5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`|サポート|[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上、または Windows 11 <br>  [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) <br> [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2) |
|[JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)|`D3E037E1-3EB8-44C8-A917-57927947596D`|サポート|[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上、または Windows 11 <br> Windows Server 2016|
|[実行可能Office作成するアプリケーションのブロック](#block-office-applications-from-creating-executable-content)|`3B576869-A4EC-4529-8536-B80A7769E899`|サポート|[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上、または Windows 11 <br> Windows Server 2016 <br> Windows Server 2012 R2 |
|[アプリケーションOffice他のプロセスへのコードの挿入をブロックする](#block-office-applications-from-injecting-code-into-other-processes)|`75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`|サポート|[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上、または Windows 11|
|[通信Officeプロセスの作成をブロックする](#block-office-communication-application-from-creating-child-processes)|`26190899-1602-49e8-8b27-eb1d0a1ce869`|サポート|[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上、または Windows 11|
|[WMI イベント サブスクリプションによる永続化のブロック](#block-persistence-through-wmi-event-subscription)|`e6db77e5-3df2-4cf1-b95a-636979351e5b`|サポート対象外|[Windows 10バージョン 1903](/windows/whats-new/whats-new-windows-10-version-1903) (ビルド 18362) 以上、またはバージョン 11 Windows|
|[PSExec および WMI コマンドから発生するプロセス作成をブロックする](#block-process-creations-originating-from-psexec-and-wmi-commands)|`d1e49aac-8f56-4280-b9ba-993a6d77406c`|サポート|[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上、または Windows 11 <br> <br>  [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) <br> [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)
|
|[USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする](#block-untrusted-and-unsigned-processes-that-run-from-usb)|`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`|サポート|[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上、または Windows 11|
|[Win32 API 呼び出しをブロックOfficeマクロ](#block-win32-api-calls-from-office-macros)|`92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`|サポート|[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上、または Windows 11|
|[ランサムウェアに対する高度な保護の使用](#use-advanced-protection-against-ransomware)|`c1db55ab-c21a-4637-bb3f-a12568109d35`|サポート|[Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3、ビルド 16299) 以上、または Windows 11 <br> <br>  [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) <br> [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2) |
|

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a>悪用された脆弱な署名済みドライバーの悪用をブロックする

このルールは、アプリケーションが脆弱な署名済みドライバーをディスクに書き込むのを防ぐためです。 インザワイルドで脆弱な署名済みドライバーは、カーネルにアクセスするのに十分な特権を持つローカル アプリケーション \-  \- によって悪用される可能性があります。 脆弱な署名付きドライバーを使用すると、攻撃者はセキュリティ ソリューションを無効または回避し、最終的にはシステムの侵害につながる可能性があります。

[ **悪用された脆弱な** 署名済みドライバーの悪用をブロックする] ルールは、システム上に既に存在するドライバーの読み込みをブロックしない。

>[!NOTE]
>
> このルールは [、MEM OMA-URI](enable-attack-surface-reduction.md#mem) カスタム ルールのプロシージャ情報に対して MEM OMA-URI を使用して構成できます。
>
> PowerShell を使用してこのルールを [構成できます](enable-attack-surface-reduction.md#powershell)。
>
> ドライバーを調べるには、この Web サイトを使用して分析 [用のドライバーを送信します](https://www.microsoft.com/en-us/wdsi/driversubmission)。

サポートされるオペレーティング システム

- [Windows 10 Proバージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709)以降
- [Windows 10 Enterpriseバージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709)以降
- [Windows Server バージョン 1803 (半期チャネル)](/windows-server/get-started/whats-new-in-windows-server-1803)以降
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Intune 名: `Block abuse of exploited vulnerable signed drivers`

GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`

### <a name="block-adobe-reader-from-creating-child-processes"></a>Adobe Reader の子プロセスの作成をブロックする

このルールは、Adobe Reader によるプロセスの作成をブロックすることで攻撃を防止します。

ソーシャル エンジニアリングや悪用を通じて、マルウェアはペイロードをダウンロードして起動し、Adobe Reader から抜け出す可能性があります。 Adobe Reader によって子プロセスが生成されるのをブロックすることで、子プロセスをベクターとして使用しようとするマルウェアが拡散を防止します。

サポートされるオペレーティング システム

- [Windows 10 Version 1809](/windows/whats-new/whats-new-windows-10-version-1809)
- [Windowsサーバー、バージョン 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)

Intune 名: `Process creation from Adobe Reader (beta)`

Configuration Manager 名: まだ使用できません

GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`

### <a name="block-all-office-applications-from-creating-child-processes"></a>すべてのアプリケーションOffice子プロセスの作成をブロックする

このルールは、Officeプロセスの作成をブロックします。 Officeには、Word、Excel、PowerPoint、OneNote、Access が含まれます。

悪意のある子プロセスを作成する方法は、一般的なマルウェア戦略です。 マルウェアがベクターとしてOffice、VBA マクロを実行し、コードを悪用して、より多くのペイロードをダウンロードして実行しようとする場合があります。 ただし、一部の正当な業務行アプリケーションでは、良性の目的で子プロセスを生成する場合があります。コマンド プロンプトを生成したり、PowerShell を使用してレジストリ設定を構成したりします。

サポートされるオペレーティング システム

- [Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windowsサーバー、バージョン 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune 名: `Office apps launching child processes`

Configuration Manager 名: `Block Office application from creating child processes`

GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a>ローカル セキュリティ機関サブシステムからの資格情報のWindowsをブロックする

このルールは、ローカル セキュリティ機関サブシステム サービス (LSASS) をロックダウンして資格情報の盗用を防ぐのに役立ちます。

LSASS は、コンピューターにサインインするユーザーをWindowsします。 Microsoft Defender Credential Guard in Windows 10は、通常、LSASS から資格情報を抽出しようとして防止します。 ただし、一部の組織では、カスタム スマートカード ドライバーやローカル セキュリティ機関 (LSA) に読み込む他のプログラムとの互換性の問題により、すべてのコンピューターで Credential Guard を有効にできない場合があります。 このような場合、攻撃者は Mimikatz のようなハッキング ツールを使用して、LSASS からクリアテキスト パスワードと NTLM ハッシュをスクレイピングできます。

> [!NOTE]
> 一部のアプリでは、実行中のすべてのプロセスを列挙し、網羅的なアクセス許可を使用して開きます。 このルールは、アプリのプロセスのオープン アクションを拒否し、詳細をセキュリティ イベント ログに記録します。 このルールでは、多くのノイズが発生する可能性があります。 LSASS を列挙するだけで、機能に実際の影響がないアプリがある場合は、除外リストに追加する必要はありません。 それ自体では、このイベント ログ エントリは必ずしも悪意のある脅威を示すとは限りません。

サポートされるオペレーティング システム

- [Windows 10バージョン 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windowsサーバー、バージョン 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)

Intune 名: `Flag credential stealing from the Windows local security authority subsystem`

Configuration Manager 名: `Block credential stealing from the Windows local security authority subsystem`

GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`

### <a name="block-executable-content-from-email-client-and-webmail"></a>メール クライアントと Web メールから実行可能なコンテンツをブロックする

このルールは、Microsoft Outlook アプリケーション、または Outlook.com や他の一般的な Web メール プロバイダー内で開いた電子メールから、次の種類のファイルの起動をブロックします。

- 実行可能ファイル (.exe、.dll.scr など)
- スクリプト ファイル (PowerShell .ps、Visual Basic .vbs、JavaScript .js ファイルなど)

サポートされるオペレーティング システム

- [Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windowsサーバー、バージョン 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Microsoft エンドポイント マネージャーCB 1710](/configmgr/core/servers/manage/updates)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)

Intune 名: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`

Microsoft エンドポイント マネージャー名:`Block executable content from email client and webmail`

GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`

> [!NOTE]
> [メール **クライアントと Web メールからの** 実行可能なコンテンツをブロックする] というルールには、使用するアプリケーションに応じて、次の別の説明があります。
>
> - Intune (構成プロファイル): 電子メール (Web メール/メール クライアント) から削除された実行可能コンテンツ (exe、dll、ps、js、vbs など) の実行 (例外なし)。
> - エンドポイント マネージャー: メールおよび Web メール クライアントからの実行可能コンテンツのダウンロードをブロックします。
> - グループ ポリシー: 電子メール クライアントと Web メールから実行可能なコンテンツをブロックします。

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a>有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする

次の条件が満たされていない限り、.exe、.dll、.scr などの実行可能ファイルが起動をブロックします。

- 有病率: 実行可能ファイルは 1,000 を超えるエンドポイントで検出されます
- Age: 実行可能ファイルは 24 時間以上前にリリースされました
- 場所: 実行可能ファイルが信頼できるリストまたは除外リストに含まれている

信頼されていない実行可能ファイルまたは不明な実行可能ファイルを起動すると、ファイルが悪意のあるものか最初ははっきりしない可能性があります。

> [!IMPORTANT]
> このルールを [使用するには、クラウドによる保護](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) を有効にする必要があります。
>
> GUID で **有病率** 、年齢、または信頼できるリスト条件を満たしていない場合、実行可能ファイルの実行をブロックするルールは、Microsoft が所有し、管理者によって `01443614-cd74-433a-b99e-2ecdc07bfc25` 指定されていません。 このルールでは、クラウド配信の保護を使用して、信頼できるリストを定期的に更新します。
>
> 個々のファイルまたはフォルダー (フォルダー パスまたは完全修飾リソース名を使用) を指定できますが、適用するルールや除外を指定することはできません。

サポートされるオペレーティング システム

- [Windows 10バージョン 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windowsサーバー、バージョン 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Intune 名: `Executables that don't meet a prevalence, age, or trusted list criteria`

Configuration Manager 名: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`

GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`

### <a name="block-execution-of-potentially-obfuscated-scripts"></a>難読化される可能性のあるスクリプトの実行をブロックする

このルールは、難読化されたスクリプト内の疑わしいプロパティを検出します。

スクリプト難読化は、マルウェア作成者と正当なアプリケーションの両方が、知的財産を隠したり、スクリプトの読み込み時間を短縮したりするために使用する一般的な手法です。 マルウェアの作成者は難読化を使用して悪意のあるコードを読みにくくし、人間やセキュリティ ソフトウェアによる詳細な調査を防止します。

サポートされるオペレーティング システム

- [Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windowsサーバー、バージョン 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)

Intune 名: `Obfuscated js/vbs/ps/macro code`

Configuration Manager 名: `Block execution of potentially obfuscated scripts`

GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a>JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする

このルールにより、スクリプトは悪意のあるダウンロードコンテンツを起動できません。 JavaScript または VBScript で記述されたマルウェアは、インターネットから他のマルウェアをフェッチして起動するダウンデータとして機能する場合が多い。

一般的ではないが、一般企業向けアプリケーションでは、スクリプトを使用してインストーラーをダウンロードおよび起動する場合があります。

サポートされるオペレーティング システム

- [Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windowsサーバー、バージョン 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)

Intune 名: `js/vbs executing payload downloaded from Internet (no exceptions)`

Configuration Manager 名: `Block JavaScript or VBScript from launching downloaded executable content`

GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`

### <a name="block-office-applications-from-creating-executable-content"></a>実行可能Office作成するアプリケーションのブロック

このルール Officeは、悪意のあるコードがディスクに書き込まれるのをブロックすることで、Word、Excel、PowerPoint などのアプリが悪意のある実行可能コンテンツを作成するのを防ぐためです。

マルウェアは、Officeとして悪用され、悪意のあるOfficeをディスクに保存しようとする可能性があります。 これらの悪意のあるコンポーネントは、コンピューターの再起動後も存続し、システム上で保持されます。 したがって、このルールは一般的な永続化手法に対して防御します。

サポートされるオペレーティング システム

- [Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windowsサーバー、バージョン 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [System Center Configuration Manager](/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM がMicrosoft Endpoint Configuration Manager)

Intune 名: `Office apps/macros creating executable content`

SCCM 名: `Block Office applications from creating executable content`

GUID: `3B576869-A4EC-4529-8536-B80A7769E899`

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a>アプリケーションOffice他のプロセスへのコードの挿入をブロックする

このルールは、アプリから他のプロセスへのコードOffice試行をブロックします。

攻撃者は、Officeを使用して、コード挿入を通じて悪意のあるコードを他のプロセスに移行しようとする可能性があります。そのため、コードはクリーン なプロセスとして悪用される可能性があります。

コードインジェクションを使用する正当なビジネス上の目的はありません。

このルールは、Word、Excel、およびPowerPoint。

サポートされるオペレーティング システム

- [Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windowsサーバー、バージョン 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune 名: `Office apps injecting code into other processes (no exceptions)`

Configuration Manager 名: `Block Office applications from injecting code into other processes`

GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`

### <a name="block-office-communication-application-from-creating-child-processes"></a>通信Officeプロセスの作成をブロックする

このルールは、Outlookプロセスを作成する一方で、正当なプロセス機能Outlookします。

このルールは、ソーシャル エンジニアリング攻撃から保護し、コードを悪用して、セキュリティ上の脆弱性を悪用Outlook。 また、ユーザーのOutlook[が](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/)侵害された場合に攻撃者が使用する可能性のある、特定のルールやフォームの悪用から保護します。

> [!NOTE]
> このルールは、DLP ポリシー のヒントとツール ヒントをブロックOutlook。 このルールは、Outlookおよび Outlook.com にのみ適用されます。

サポートされるオペレーティング システム

- [Windows 10 Version 1809](/windows/whats-new/whats-new-windows-10-version-1809)
- [Windowsサーバー、バージョン 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Intune 名: `Process creation from Office communication products (beta)`

Configuration Manager 名: 使用できません

GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`

### <a name="block-persistence-through-wmi-event-subscription"></a>WMI イベント サブスクリプションによる永続化のブロック

このルールは、デバイス上で WMI を攻撃して永続化を達成するマルウェアを防止します。

> [!IMPORTANT]
> ファイルとフォルダーの除外は、この攻撃表面の縮小ルールには適用されません。

ファイルレスの脅威は、隠し、ファイル システムで見られない、定期的な実行制御を得るために、さまざまな戦術を採用しています。 一部の脅威は、WMI リポジトリとイベント モデルを悪用して非表示にできます。

サポートされるオペレーティング システム

- [Windows 10バージョン 1903](/windows/whats-new/whats-new-windows-10-version-1903)
- [Windowsサーバー 1903](/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

Intune 名: 使用できません

Configuration Manager 名: 使用できません

GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a>PSExec および WMI コマンドから発生するプロセス作成をブロックする

このルールは [、PsExec](/sysinternals/downloads/psexec) および WMI を介して作成 [されたプロセスの実行](/windows/win32/wmisdk/about-wmi) をブロックします。 PsExec と WMI の両方がコードをリモートで実行できるので、コマンドと制御の目的でこの機能を不正に使用したり、組織のネットワーク全体に感染を広げる危険性があります。

> [!WARNING]
> Intune または別の MDM ソリューションを使用してデバイスを管理する場合にのみ、 [このルールを](/intune) 使用します。 このルールは、Configuration Manager クライアント[が正しく機能するために使用Microsoft Endpoint Configuration Manager](/configmgr) WMI コマンドをブロックします。

サポートされるオペレーティング システム

- [Windows 10バージョン 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windowsサーバー、バージョン 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)

Intune 名: `Process creation from PSExec and WMI commands`

Configuration Manager 名: 該当なし

GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a>USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする

このルールを使用すると、管理者は、SD カードを含む USB リムーバブル ドライブから署名されていない実行可能ファイルまたは信頼されていない実行可能ファイルを実行できません。 ブロックされたファイルの種類には、実行可能ファイル (.exe、.dll.scr など) が含まれます。

サポートされるオペレーティング システム

- [Windows 10バージョン 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windowsサーバー、バージョン 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Intune 名: `Untrusted and unsigned processes that run from USB`

Configuration Manager 名: `Block untrusted and unsigned processes that run from USB`

GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`

### <a name="block-win32-api-calls-from-office-macros"></a>Win32 API 呼び出しをブロックOfficeマクロ

このルールは、VBA マクロが Win32 API を呼び出すのを防止します。

OfficeVBA では、Win32 API 呼び出しが有効です。 マルウェアは [、Win32 API](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) を呼び出してディスクに直接何も書き込みせずに悪意のあるシェルコードを起動するなど、この機能を悪用する可能性があります。 ほとんどの組織では、他の方法でマクロを使用している場合でも、Win32 API を毎日の機能で呼び出す機能に依存しません。

サポートされるオペレーティング システム

- [Windows 10バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windowsサーバー、バージョン 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune 名: `Win32 imports from Office macro code`

Configuration Manager 名: `Block Win32 API calls from Office macros`

GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`

### <a name="use-advanced-protection-against-ransomware"></a>ランサムウェアに対する高度な保護の使用

このルールは、ランサムウェアに対する保護の追加層を提供します。 クライアントとクラウドの両方のヒューリスティックを使用して、ファイルがランサムウェアに似ているかどうかを判断します。 このルールは、次の 1 つ以上の特性を持つファイルをブロックしない。

- このファイルは、Microsoft クラウドで既に無傷である必要があります。
- ファイルは有効な署名付きファイルです。
- ファイルはランサムウェアと見なされないほど普及しています。

このルールは、ランサムウェアを防止するために注意を払う傾向があります。

> [!NOTE]
> このルールを [使用するには、クラウドによる保護](enable-cloud-protection-microsoft-defender-antivirus.md) を有効にする必要があります。

サポートされるオペレーティング システム

- [Windows 10バージョン 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windowsサーバー、バージョン 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)

Intune 名: `Advanced ransomware protection`

Configuration Manager 名: `Use advanced protection against ransomware`

GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`
