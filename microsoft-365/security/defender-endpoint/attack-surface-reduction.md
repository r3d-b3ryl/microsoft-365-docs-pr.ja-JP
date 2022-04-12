---
title: マルウェア感染を防ぐために攻撃面の減少ルールを使用する
description: 攻撃表面の縮小ルールは、悪用がアプリやスクリプトを使用してデバイスをマルウェアに感染させるのを防ぐのに役立ちます。
keywords: 攻撃表面の縮小ルール, asr, hips, ホスト侵入防止システム, 保護ルール, アンチエクスプロイト, antiexploit, exploit, infection prevention, Microsoft Defender for Endpoint
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.custom:
- asr
- admindeeplinkDEFENDER
ms.technology: mde
ms.topic: article
ms.collection:
- m365initiative-m365-defender
- M365-security-compliance
ms.date: 1/18/2022
ms.openlocfilehash: a93563b3758db8346af12978440c16d91f28bed5
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788064"
---
# <a name="attack-surface-reduction-rules-overview"></a>攻撃面の縮小ルールの概要

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

## <a name="why-attack-surface-reduction-rules-are-important"></a>攻撃面の縮小ルールが重要な理由

組織の攻撃対象には、攻撃者が組織のデバイスまたはネットワークを侵害する可能性があるすべての場所が含まれます。 攻撃対象を減らすことは、組織のデバイスとネットワークを保護することを意味します。これにより、攻撃者は攻撃を実行する方法が少なくなります。 Microsoft Defender for Endpointで攻撃面の縮小ルールを構成すると役立ちます。

攻撃表面の縮小ルールは、次のような特定のソフトウェア動作を対象とします。

- ファイルのダウンロードまたは実行を試みる実行可能ファイルとスクリプトの起動
- 難読化された、またはその他の疑わしいスクリプトの実行
- 通常の日常的な作業中にアプリが通常開始しない動作を実行する

このようなソフトウェア動作は、正当なアプリケーションで見られる場合があります。 ただし、これらの動作は、マルウェアを介して攻撃者によって一般的に悪用されるため、リスクが高いと見なされることがよくあります。 攻撃面の縮小ルールは、ソフトウェア ベースの危険な動作を制約し、組織を安全に保つのに役立ちます。

攻撃表面の縮小ルールの構成の詳細については、「 [攻撃面の縮小ルールを有効にする」を](enable-attack-surface-reduction.md)参照してください。

## <a name="assess-rule-impact-before-deployment"></a>デプロイ前にルールの影響を評価する

脅威と脆弱性の管理でそのルールのセキュリティに関する推奨事項を開くことで、攻撃表面の縮小ルールがネットワークにどのような影響を与えるかを評価[できます。](/windows/security/threat-protection/#tvm)

:::image type="content" source="images/asrrecommendation.png" alt-text="ASR の推奨事項" lightbox="images/asrrecommendation.png":::

推奨事項の詳細ウィンドウで、ユーザーの影響を確認し、生産性に悪影響を与えずにブロック モードでルールを有効にする新しいポリシーを受け入れるデバイスの割合を決定します。

サポートされているオペレーティング システムとその他の [要件](enable-attack-surface-reduction.md#requirements) に関する情報については、「攻撃面の縮小ルールを有効にする」の記事の要件を参照してください。

## <a name="audit-mode-for-evaluation"></a>評価用の監査モード

[監査モード](audit-windows-defender.md)を使用して、攻撃表面の縮小ルールが有効な場合に組織にどのような影響を与えるかを評価します。 すべてのルールを最初に監査モードで実行し、それらが基幹業務アプリケーションに与える影響を理解できるようにします。 多くの基幹業務アプリケーションは、セキュリティ上の問題が限定的に記述されており、マルウェアに似た方法でタスクを実行する可能性があります。 監査データを監視し、必要なアプリケーションの [除外を追加](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) することで、生産性を低下させることなく、攻撃表面の縮小ルールをデプロイできます。

## <a name="warn-mode-for-users"></a>ユーザーの警告モード

(**NEW**!)警告モードの機能の前に、有効になっている攻撃表面の縮小ルールを監査モードまたはブロック モードに設定できます。 新しい警告モードでは、攻撃対象の縮小ルールによってコンテンツがブロックされるたびに、コンテンツがブロックされていることを示すダイアログ ボックスがユーザーに表示されます。 このダイアログ ボックスでは、コンテンツのブロックを解除するオプションもユーザーに提供されます。 その後、ユーザーはアクションを再試行し、操作が完了します。 ユーザーがコンテンツのブロックを解除すると、コンテンツは 24 時間ブロック解除されたままになり、ブロックが再開されます。

警告モードは、ユーザーがタスクを実行するために必要なコンテンツにアクセスできないようにすることなく、組織が攻撃面の縮小ルールを設定するのに役立ちます。

### <a name="requirements-for-warn-mode-to-work"></a>警告モードが機能するための要件

警告モードは、次のバージョンのWindowsを実行しているデバイスでサポートされています。

- [Windows 10 Version 1809](/windows/whats-new/whats-new-windows-10-version-1809) 以降
- Windows 11
- [Windows Server バージョン 1809](/windows-server/get-started/whats-new-in-windows-server-1809) 以降

Microsoft Defender ウイルス対策は[、アクティブ モード](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)でリアルタイム保護を使用して実行されている必要があります。

また、[Microsoft Defender ウイルス対策とマルウェア対策の更新プログラム](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)がインストールされていることを確認します。

- プラットフォームリリースの最小要件: `4.18.2008.9`
- エンジンリリースの最小要件: `1.1.17400.5`

詳細と更新プログラムの取得については、「 [Microsoft Defender マルウェア対策プラットフォームの更新プログラム](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)」を参照してください。

### <a name="cases-where-warn-mode-is-not-supported"></a>警告モードがサポートされていない場合

警告モードは、Microsoft エンドポイント マネージャーで構成する場合、3 つの攻撃対象の縮小ルールではサポートされていません。 (グループ ポリシーを使用して攻撃面縮小ルールを構成する場合は、警告モードがサポートされます。Microsoft エンドポイント マネージャーで警告モードを構成するときに警告モードをサポートしない 3 つのルールは次のとおりです。

- ダウンロードした実行可能コンテンツ (GUID`d3e037e1-3eb8-44c8-a917-57927947596d`) の[起動から JavaScript または VBScript をブロックする](attack-surface-reduction-rules-reference.md#block-javascript-or-vbscript-from-launching-downloaded-executable-content)
- [WMI イベント サブスクリプション (GUID) を](attack-surface-reduction-rules-reference.md#block-persistence-through-wmi-event-subscription)`e6db77e5-3df2-4cf1-b95a-636979351e5b`使用して永続化をブロックする
- ランサムウェア (GUID`c1db55ab-c21a-4637-bb3f-a12568109d35`) [に対する高度な保護を使用する](attack-surface-reduction-rules-reference.md#use-advanced-protection-against-ransomware)

また、古いバージョンのWindowsを実行しているデバイスでは、警告モードはサポートされていません。 このような場合は、警告モードで実行するように構成された攻撃面の縮小ルールはブロック モードで実行されます。

## <a name="notifications-and-alerts"></a>通知とアラート

攻撃表面縮小ルールがトリガーされるたびに、デバイスに通知が表示されます。 会社の詳細や連絡先情報を使用して[通知をカスタマイズ](attack-surface-reduction-rules-deployment-implement.md#customize-attack-surface-reduction-rules)することができます。

また、特定の攻撃面縮小ルールがトリガーされると、アラートが生成されます。

通知と生成されたすべてのアラートは、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>で表示できます。

通知とアラートの機能に関する具体的な詳細については、「**攻撃表面の縮小ルールのリファレンス**」の記事で、[ルールごとのアラートと通知の詳細](attack-surface-reduction-rules-reference.md#per-rule-alert-and-notification-details)を参照してください。

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a>高度なハンティングイベントと攻撃面縮小イベント

高度なハンティングを使用して、攻撃面の縮小イベントを表示できます。 受信データの量を合理化するために、高度な捜索では、1 時間あたりの一意のプロセスのみが表示されます。 攻撃表面縮小イベントの時刻は、そのイベントが 1 時間以内に初めて見られる時間です。

たとえば、攻撃面の縮小イベントが午後 2 時の 10 台のデバイスで発生するとします。 最初のイベントが 2:15 で、最後のイベントが 2:45 に発生したとします。 高度な捜索では、そのイベントの 1 つのインスタンスが表示されます (実際には 10 台のデバイスで発生した場合でも)、タイムスタンプは午後 2 時 15 分になります。

高度な捜索の詳細については、「高度な捜索 [で脅威をプロアクティブに検出する](advanced-hunting-overview.md)」を参照してください。

## <a name="attack-surface-reduction-features-across-windows-versions"></a>Windows バージョン間の攻撃面の縮小機能

次のいずれかのエディションとバージョンのWindowsを実行しているデバイスに対して、攻撃面の縮小ルールを設定できます。

- Windows 10 Pro[バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) 以降
- Windows 10 Enterprise[バージョン 1709](/windows/whats-new/whats-new-windows-10-version-1709) 以降
- Windows Server [バージョン 1803 (半期チャネル)](/windows-server/get-started/whats-new-in-windows-server-1803) 以降
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)

  >[!NOTE]
  >この機能を機能させるには、「オンボード Windows サーバー」の手順に従って[、Windows Server 2016とWindows Server 2012](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016) R2 をオンボードする必要があります。

攻撃表面の縮小ルールには[Windows E5 ライセンス](/windows/deployment/deploy-enterprise-licenses)は必要ありませんが、E5 Windowsを使用している場合は、高度な管理機能を利用できます。 Windows E5 でのみ使用できる高度な機能は次のとおりです。

- [Defender for Endpoint](microsoft-defender-endpoint.md) で使用できる監視、分析、ワークフロー
- [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center)のレポート機能と構成機能。

これらの高度な機能は、Windows ProfessionalまたはWindows E3 ライセンスでは使用できません。 ただし、これらのライセンスがある場合は、イベント ビューアー ログとMicrosoft Defender ウイルス対策 ログを使用して、攻撃表面縮小ルール イベントを確認できます。

## <a name="review-attack-surface-reduction-events-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルで攻撃面の縮小イベントを確認する

Defender for Endpoint は、アラート調査シナリオの一環として、イベントとブロックの詳細なレポートを提供します。

[高度な捜索](/microsoft-365/security/defender/advanced-hunting-query-language)を使用して[、Microsoft 365 Defender](microsoft-defender-endpoint.md)で Defender for Endpoint データに対してクエリを実行できます。 

クエリの例を次に示します。

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>Windows イベント ビューアーで攻撃面の縮小イベントを確認する

Windows イベント ログを確認して、攻撃表面の縮小ルールによって生成されたイベントを表示できます。

1. [評価パッケージ](https://aka.ms/mp7z2w)をダウンロードし、デバイス上の簡単にアクセスできる場所にファイル *cfa-events.xml* を抽出します。

2. スタート メニューに単語 *イベント ビューアー* を入力して、Windows イベント ビューアーを開きます。

3. [ **アクション] で**、[ **カスタム ビューのインポート]...** を選択します。

4. ファイルの抽出元 *のファイルcfa-events.xml* を選択します。 または、 [XML を直接コピーします](event-views.md)。

5. [**OK**] を選択します。

次のイベントのみを表示するようにイベントをフィルター処理するカスタム ビューを作成できます。このビューはすべて、フォルダー アクセスの制御に関連します。

|イベント ID|説明|
|---|---|
|5007|設定が変更された場合のイベント|
|1121|ブロック モードでルールが起動した場合のイベント|
|1122|監査モードでルールが起動した場合のイベント|

イベント ログの攻撃表面縮小イベントに表示される "エンジン バージョン" は、オペレーティング システムではなく、Defender for Endpoint によって生成されます。 Defender for Endpoint はWindows 10とWindows 11と統合されているため、この機能は、Windows 10またはWindows 11がインストールされているすべてのデバイスで機能します。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS でMicrosoft Defender for Endpointの基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [IntuneのMicrosoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux でMicrosoft Defender for Endpointの基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android の機能で Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能でMicrosoft Defender for Endpointを構成する](ios-configure-features.md)
