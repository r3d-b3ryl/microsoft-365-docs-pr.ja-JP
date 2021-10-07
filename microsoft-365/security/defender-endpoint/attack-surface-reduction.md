---
title: マルウェア感染を防ぐために攻撃面の減少ルールを使用する
description: 攻撃表面の縮小ルールは、悪用がアプリやスクリプトを使用してデバイスにマルウェアに感染するのを防ぐのに役立ちます。
keywords: 攻撃表面の縮小ルール、asr、hips、ホスト侵入防止システム、保護ルール、悪用防止、脆弱性対策、悪用、感染防止、Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 7ba6f456ff97644d43157c433a1cec136c17270a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201483"
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

イベント ログの攻撃表面の縮小イベント用にリストされている "エンジンバージョン" は、オペレーティング システムではなく Defender for Endpoint によって生成されます。 Defender for Endpoint は、Windows 10と統合されています。そのため、この機能は、インストールされているすべてのデバイスWindows 10します。
