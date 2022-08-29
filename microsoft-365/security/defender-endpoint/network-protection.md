---
title: ネットワーク保護を使用して、不正なサイトへの接続を防止する
description: ユーザーが既知の悪意のある不審なネットワーク アドレスにアクセスできないようにしてネットワークを保護する
keywords: ネットワーク保護、悪用、悪意のある Web サイト、IP、ドメイン、ドメイン、コマンドと制御、SmartScreen、トースト通知
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.date: 08/12/2022
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: overview
ms.collection:
- m365initiative-m365-defender
- M365-security-compliance
ms.openlocfilehash: bb4b0cb1c38fc394d5dfb2ec0498ba72b23e8754
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67388553"
---
# <a name="protect-your-network"></a>ネットワークを保護する

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender ウイルス対策

**プラットフォーム**

- Windows
- macOS
- Linux

Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="overview-of-network-protection"></a>ネットワーク保護の概要

ネットワーク保護は、インターネット ベースのイベントからデバイスを保護するのに役立ちます。 ネットワーク保護は、攻撃面の縮小機能です。 これにより、従業員がアプリケーションを介して危険なドメインにアクセスするのを防ぐことができます。 インターネット上でフィッシング詐欺、悪用、その他の悪意のあるコンテンツをホストするドメインは危険と見なされます。 ネットワーク保護により [、Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) の範囲が拡大され、(ドメインまたはホスト名に基づいて) 低評価ソースに接続しようとするすべての送信 HTTP トラフィックがブロックされます。

ネットワーク保護は、 [Web 保護](web-protection-overview.md) の保護をオペレーティング システム レベルに拡張します。 Microsoft Edge で見られる Web 保護機能は、サポートされている他のブラウザーやブラウザー以外のアプリケーションに提供されます。 また、ネットワーク保護は、 [エンドポイントの検出と応答](overview-endpoint-detection-response.md)と共に使用した場合の侵害のインジケーター (IOC) の可視性とブロックも提供します。 たとえば、ネットワーク保護は、特定のドメインまたはホスト名をブロックするために使用できる [カスタム インジケーター](manage-indicators.md) と連携します。

このビデオでは、ネットワーク保護を使用して、フィッシング詐欺、悪用、その他の悪意のあるコンテンツからデバイスの攻撃面を軽減する方法について説明します。
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yZ]

## <a name="requirements-for-network-protection"></a>ネットワーク保護の要件

ネットワーク保護には、Windows 10または 11 (Pro または Enterprise)、Windows Server バージョン 1803 以降、macOS バージョン 11 以降、または Defender サポートされている Linux バージョン、および Microsoft Defender ウイルス対策のリアルタイム保護が必要です。

| Windows バージョン | Microsoft Defender ウイルス対策 |
|:---|:---|
| Windows 10 バージョン 1709 以降 <br/> Windows 11 <br/> Windows Server 1803 以降 | [Microsoft Defender ウイルス対策のリアルタイム保護](configure-real-time-protection-microsoft-defender-antivirus.md)と[クラウド配信保護](enable-cloud-protection-microsoft-defender-antivirus.md)が有効 (アクティブ) になっていることを確認します。 |

## <a name="why-network-protection-is-important"></a>ネットワーク保護が重要な理由

ネットワーク保護は、Microsoft Defender for Endpointのソリューションの攻撃面削減グループの一部です。 ネットワーク保護を使用すると、URL と IP アドレスをブロックするネットワーク 層をレイヤー化できます。 ネットワーク保護は、特定のブラウザーと標準ネットワーク接続を使用して URL にアクセスできないようにブロックできます。 既定では、ネットワーク保護は、SmartScreen フィードを使用して既知の悪意のある URL からコンピューターを保護します。これにより、Microsoft Edge ブラウザーの SmartScreen と同様の方法で悪意のある URL がブロックされます。 ネットワーク保護機能は、次のように拡張できます。

- 独自の脅威インテリジェンスから IP/URL アドレスをブロックする ([インジケーター](indicator-ip-domain.md))
- 承認されていないサービス[をMicrosoft Defender for Cloud Apps](/defender-cloud-apps/what-is-defender-for-cloud-apps)からブロックする (以前は Microsoft Cloud App Security と呼ばられていました)
- カテゴリに基づいてサイトをブロックする ([Web コンテンツ フィルター](web-content-filtering.md))

ネットワーク保護は、Microsoft の保護と応答スタックの重要な部分です。

> [!TIP]
> Windows Server、Linux、MacOS、Mobile Threat Defense (MTD) のネットワーク保護の詳細については、「 [高度な捜索で脅威をプロアクティブに検出する](advanced-hunting-overview.md)」を参照してください。

### <a name="block-command-and-control-c2-attacks"></a>Block Command and Control (C2) 攻撃

コマンドおよび制御 (C2) サーバー コンピューターは、悪意のあるユーザーがマルウェアによって侵害されたシステムにコマンドを送信し、侵害されたシステムに対して何らかの種類の制御を行うために使用されます。 C2 攻撃は通常、ファイル共有や Web メール サービスなどのクラウドベースのサービスに隠れ、C2 サーバーが一般的なトラフィックとブレンドして検出を回避できるようにします。

C2 サーバーは、次のコマンドを開始するために使用できます。

- データを盗む (フィッシングなど)
- ボットネットで侵害されたコンピューターを制御する
- 正当なアプリケーションを中断する
- ランサムウェアなどのマルウェアを拡散する

Defender for Endpoint のネットワーク保護コンポーネントは、機械学習やインテリジェントな侵害インジケーター (IoC) 識別などの手法を使用して、人間が操作するランサムウェア攻撃で使用される C2 インフラストラクチャへの接続を識別し、ブロックします。

#### <a name="network-protection-new-toast-notifications"></a>ネットワーク保護: 新しいトースト通知

| 新しいマッピング  | 応答カテゴリ  | ソース |
| :--- | :--- | :--- |
| フィッシング詐欺 | フィッシング詐欺 | Smartscreen |
| 悪意 | 悪意がある | Smartscreen |
| コマンドと制御 | C2 | Smartscreen |
| コマンドと制御 | COCO | Smartscreen |
| 悪意 | 信頼 | Smartscreen |
| IT 管理者による | CustomBlockList |   |
| IT 管理者による | CustomPolicy |   |

> [!NOTE]
> **customAllowList** では、エンドポイントに対する通知は生成されません。

### <a name="new-notifications-for-network-protection-determination"></a>ネットワーク保護の決定に関する新しい通知

ネットワーク保護の新しい一般公開機能では、SmartScreen の機能を利用して、悪意のあるコマンド サイトと制御サイトからのフィッシングアクティビティをブロックします。

エンド ユーザーがネットワーク保護が有効になっている環境で Web サイトにアクセスしようとすると、次の 3 つのシナリオが考えられます。

- URL には既知の **評判** があります。この場合、ユーザーはアクセスを妨害することなく許可され、エンドポイントにトースト通知は表示されません。 実際には、ドメインまたは URL は _[許可]_ に設定されます。
- URL には **不明または不確かな評判** があります。ユーザーのアクセスはブロックされますが、ブロックを回避 (ブロック解除) できます。 実際には、ドメインまたは URL は監査に設定 _されます_。
- URL に既知の **悪意のある (悪意のある) 評判** があります。ユーザーはアクセスできません。 実際には、ドメインまたは URL は _[ブロック_] に設定されます。

#### <a name="warn-experience"></a>エクスペリエンスを警告する

ユーザーが Web サイトにアクセスした場合:

- URL に不明または不確かな評価がある場合は、トースト通知によってユーザーに次のオプションが表示されます。

  - **OK** - トースト通知が解放 (削除) され、サイトへのアクセスの試行が終了します。
  - **ブロック解除** - ユーザーは、サイトにアクセスするためにWindows Defenderセキュリティ インテリジェンス (WDSI) ポータルにアクセスする必要はありません。 ユーザーはサイトに 24 時間アクセスできます。その時点で、ブロックはさらに 24 時間再び有効になります。 管理者がサイトを禁止 (ブロック) するまで、ユーザーは引き続き **ブロック解除** を使用してサイトにアクセスでき、ブロック解除のオプションが削除 **されます**。
  - **フィードバック** - トースト通知では、チケットを送信するためのリンクがユーザーに表示されます。これにより、ユーザーはサイトへのアクセスを正当化するために管理者にフィードバックを送信できます。

    :::image type="content" source="images/network-protection-phishing-warn-2.png" alt-text="ネットワーク保護フィッシング コンテンツの警告通知を表示します。":::

  > [!NOTE]
  > 警告エクスペリエンスとブロック エクスペリエンス (下) に示す画像は、両方ともプレースホルダー テキストの例として **"ブロックされた URL" を** 一覧表示します。機能している環境では、実際の URL またはドメインが一覧表示されます。  

#### <a name="block-experience"></a>ブロック エクスペリエンス

ユーザーが Web サイトにアクセスした場合:

- URL の評判が悪い場合は、トースト通知によってユーザーに次のオプションが表示されます。
  - **わかりました** トースト通知が解放 (削除) され、サイトへのアクセスの試行は終了します。
  - **フィードバック** トースト通知では、チケットを送信するためのリンクがユーザーに表示されます。これにより、ユーザーはサイトへのアクセスを正当化するために管理者にフィードバックを送信できます。

    :::image type="content" source="images/network-protection-phishing-blocked.png" alt-text="ネットワーク保護既知のフィッシングコンテンツブロック通知を表示します。" lightbox="images/network-protection-phishing-blocked.png":::

### <a name="network-protection-c2-detection-and-remediation"></a>ネットワーク保護: C2 の検出と修復

最初の形式では、ランサムウェアは商品の脅威であり、事前にプログラムされ、限られた特定の結果 (コンピューターの暗号化など) に焦点を当てています。 しかし、ランサムウェアは人間主導の高度な脅威に進化し、適応性があり、より大規模で広範な結果に焦点を当てています。は、組織全体の資産または身代金のデータを保持する場合などです。

コマンド および制御サーバー (C2) のサポートは、このランサムウェアの進化の重要な部分であり、これらの攻撃がターゲットとする環境に適応することを可能にします。 コマンドアンドコントロール インフラストラクチャへのリンクを解除すると、攻撃の次の段階への進行が停止します。

## <a name="smartscreen-unblock"></a>SmartScreen のブロック解除

Defender for Endpoint インジケーターの新機能により、管理者はエンド ユーザーが一部の URL と IP に対して生成された警告をバイパスできます。 URL がブロックされた理由によっては、SmartScreen ブロックが検出されると、管理者にサイトのブロックを最大 24 時間ブロック解除できる機能が提供される場合があります。 このような場合は、Windows セキュリティトースト通知が表示され、定義された期間、エンド ユーザーが URL または IP の **ブロックを解除** できるようになります。  

:::image type="content" source="images/network-protection-smart-screen-block-notification.png" alt-text="ネットワーク保護の通知をWindows セキュリティします。":::

Microsoft Defender for Endpoint管理者は、次の構成ツールを使用して[、Microsoft 365 Defender](https://security.microsoft.com/)で SmartScreen ブロック解除機能を構成できます。 Microsoft 365 Defender ポータルから、ConfigToolName へのパスに移動します。

:::image type="content" source="images/network-protection-smart-screen-block-configuration.png" alt-text="ネットワーク保護 SmartScreen ブロック構成 ULR と IP フォーム。":::

## <a name="using-network-protection"></a>ネットワーク保護の使用

ネットワーク保護は、通常、管理インフラストラクチャを使用して行われるデバイスごとに有効になります。 サポートされている方法については、「 [ネットワーク保護を有効にする」](enable-network-protection.md)を参照してください。

> [!NOTE]
> ネットワーク保護を有効にするには、Microsoft Defender ウイルス対策をアクティブにする必要があります。

**監査** モードまたは **ブロック** モードでネットワーク保護を有効にすることができます。 IP アドレスまたは URL を実際にブロックする前にネットワーク保護を有効にした場合の影響を評価する場合は、一定期間、監査モードでネットワーク保護を有効にして、ブロックされる内容に関するデータを収集できます。 エンド ユーザーがネットワーク保護によってブロックされていたアドレスまたはサイトに接続した場合の監査モード ログ。

Linux および macOS のネットワーク保護については、「 [Linux 用のネットワーク保護](network-protection-linux.md) と [MacOS 用のネットワーク保護](network-protection-macos.md)」を参照してください。

## <a name="advanced-hunting"></a>高度な追及

高度な捜索を使用して監査イベントを識別する場合は、コンソールから最大 30 日間の履歴を使用できます。 [高度なハンティングを](advanced-hunting-overview.md)参照してください。

監査データは、Defender for Endpoint ポータル ()[https://security.microsoft.com](https://security.microsoft.com) の **高度な捜索** で確認できます。  

イベントは、ActionType が .. の DeviceEvents 内に存在します `ExploitGuardNetworkProtectionAudited`。 ブロックは次のように表示されます `ExploitGuardNetworkProtectionBlocked`。  

次の例には、ブロックされたアクションが含まれています。

```kusto

DeviceEvents
|Where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')

```


:::image type="content" source="images/network-protection-advanced-hunting.png" alt-text="イベントの監査と識別のための高度な捜索。" lightbox="images/network-protection-advanced-hunting.png":::

> [!TIP]
> これらのエントリには、アクションに関する優れた情報を提供する **AdditionalFields** 列にデータが含まれています。 **AdditionalFields** を展開すると、 **IsAudit**、 **ResponseCategory**、 **DisplayName** というフィールドも取得できます。

別の例を次に示します。

```kusto

DeviceEvents:

|where ActionType contains "ExploitGuardNetworkProtection"
|extend ParsedFields=parse_json(AdditionalFields)
|project DeviceName, ActionType, Timestamp, RemoteUrl, InitiatingProcessFileName, IsAudit=tostring(ParsedFields.IsAudit), ResponseCategory=tostring(ParsedFields.ResponseCategory), DisplayName=tostring(ParsedFields.DisplayName)
|sort by Timestamp desc

```
応答カテゴリには、次のようにイベントの原因が示されます。

| ResponseCategory | イベントを担当する機能 |
|:---|:---|
| CustomPolicy |  Wcf  |
| CustomBlockList  |   カスタム インジケーター   |
| CasbPolicy   |   Defender for Cloud Apps   |
| 悪意がある   |   Web の脅威  |
| フィッシング詐欺  |   Web の脅威  |

詳細については、「 [エンドポイント ブロックのトラブルシューティング](web-protection-overview.md#troubleshoot-endpoint-blocks)」を参照してください。

結果として得られる URL と IP の一覧を使用して、デバイスがブロック モードの場合に何がブロックされ、どの機能がブロックされたかを判断できます。 一覧の各項目を確認して、環境に必要な URL または IP を識別します。 環境にとって重要な監査済みのエントリが見つかる場合は、それらをネットワークで許可するインジケーターを作成します。 許可 URL/IP インジケーターは、任意のブロックよりも優先されます。

インジケーターを作成したら、基になる問題の解決を確認できます。

- SmartScreen – 要求のレビュー
- インジケーター – 既存のインジケーターを変更する
- MCA – 承認されていない APP を確認する
- WCF – 要求の再集計

このデータを使用すると、ブロック モードでネットワーク保護を有効にすることに関する情報に基づいた決定を行うことができます。 [ネットワーク保護ブロックの優先順位を](web-protection-overview.md#order-of-precedence)参照してください。

> [!NOTE]
> これはデバイスごとの設定であるため、ブロック モードに移行できないデバイスがある場合は、チャレンジを修正でき、監査イベントを受け取るまで監査のままにすることができます。

誤検知を報告する方法については、「誤検知を [報告する」](web-protection-overview.md#report-false-positives)を参照してください。

独自の Power BI レポートを作成する方法の詳細については、「Power BI を [使用してカスタム レポートを作成する](api-power-bi.md)」を参照してください。

## <a name="configuring-network-protection"></a>ネットワーク保護の構成

ネットワーク保護を有効にする方法の詳細については、「ネットワーク保護を **[有効にする」を](enable-network-protection.md)** 参照してください。 グループ ポリシー、PowerShell、または MDM CSP を使用して、ネットワーク内のネットワーク保護を有効および管理します。

サービスを有効にした後、サービスとデバイス (エンドポイントとも呼ばれます) 間の接続を許可するようにネットワークまたはファイアウォールを構成することが必要になる場合があります。

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="viewing-network-protection-events"></a>ネットワーク保護イベントの表示

ネットワーク保護は[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)で最適に機能します。これにより、[アラート調査シナリオ](investigate-alerts.md)の一環として、エクスプロイト保護イベントとブロックに関する詳細なレポートが提供されます。

ネットワーク保護によって接続がブロックされると、アクション センターから通知が表示されます。 セキュリティ運用チームは、組織 [の](attack-surface-reduction-rules-deployment-implement.md#customize-attack-surface-reduction-rules) 詳細と連絡先情報を使用して通知をカスタマイズできます。 さらに、監視する特定の手法に合わせて、個々の攻撃面縮小ルールを有効にしたりカスタマイズしたりできます。

[また、監査モード](audit-windows-defender.md)を使用して、ネットワーク保護が有効になっている場合に組織にどのような影響を与えるかを評価することもできます。

## <a name="review-network-protection-events-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルでネットワーク保護イベントを確認する

Defender for Endpoint は、 [アラート調査シナリオ](investigate-alerts.md)の一環として、イベントとブロックに対する詳細なレポートを提供します。 これらの詳細は、[アラート キュー](review-alerts.md)のMicrosoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) で表示することも、[高度な捜索](advanced-hunting-overview.md)を使用して表示することもできます。 [監査モード](audit-windows-defender.md)を使用している場合は、高度なハンティングを使用して、ネットワーク保護設定が有効になっている場合に環境にどのような影響を与えるかを確認できます。

高度なハンティングのクエリの例を次に示します。

```kusto

DeviceNetworkEvents
|where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked', 'ConnectionSuccess')

```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Windows イベント ビューアーでネットワーク保護イベントを確認する

Windows イベント ログを確認して、ネットワーク保護が悪意のある IP またはドメインへのアクセスをブロック (または監査) したときに作成されるイベントを確認できます。

1. [XML を直接コピーします](event-views.md)。

2. **[OK]** をクリックします。

この手順では、ネットワーク保護に関連する次のイベントのみを表示するようにフィルター処理するカスタム ビューを作成します。

|イベント ID|説明|
|---|---|
|5007|設定が変更された場合のイベント|
|1125|ネットワーク保護が監査モードで起動した場合のイベント|
|1126|ブロック モードでネットワーク保護が発生した場合のイベント|

## <a name="network-protection-and-the-tcp-three-way-handshake"></a>ネットワーク保護と TCP の 3 方向ハンドシェイク

ネットワーク保護では、サイトへのアクセスを許可するかブロックするかの決定は、 [TCP/IP 経由の 3 方向ハンドシェイク](/troubleshoot/windows-server/networking/three-way-handshake-via-tcpip)が完了した後に行われます。 したがって、サイトがネットワーク保護によってブロックされると、サイトがブロックされていても、Microsoft 365 Defender ポータルでアクションの`ConnectionSuccess``NetworkConnectionEvents`種類が表示される場合があります。 `NetworkConnectionEvents` は、ネットワーク保護からではなく、TCP レイヤーから報告されます。 3 方向ハンドシェイクが完了すると、サイトへのアクセスがネットワーク保護によって許可またはブロックされます。

そのしくみの例を次に示します。

1. ユーザーがデバイス上の Web サイトにアクセスしようとするとします。 サイトは危険なドメインでホストされ、ネットワーク保護によってブロックされる必要があります。  

2. TCP/IP 経由の 3 方向ハンドシェイクが開始されます。 完了する前に `NetworkConnectionEvents` 、アクションがログに記録され、次 `ActionType` のように `ConnectionSuccess`一覧表示されます。 ただし、3 方向ハンドシェイク プロセスが完了するとすぐに、ネットワーク保護によってサイトへのアクセスがブロックされます。 このすべてがすぐに発生します。 [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) でも同様のプロセスが発生します。3 方向ハンドシェイクが完了すると、決定が行われ、サイトへのアクセスがブロックまたは許可されます。

3. Microsoft 365 Defender ポータルでは、アラートキューに[アラート](alerts-queue.md)が一覧表示されます。 そのアラートの詳細には、 `NetworkConnectionEvents` 両方と `AlertEvents`. ActionType が .. のアイテムも含 `NetworkConnectionEvents` まれている場合でも、サイトがブロックされていることがわかります `ConnectionSuccess`。

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a>マルチセッションWindows 10 Enterprise実行している Windows 仮想デスクトップに関する考慮事項

Windows 10 Enterpriseのマルチユーザーの性質上、次の点に留意してください。

1. ネットワーク保護はデバイス全体の機能であり、特定のユーザー セッションを対象にすることはできません。

2. Web コンテンツ フィルター ポリシーもデバイス全体です。

3. ユーザー グループを区別する必要がある場合は、個別の Windows Virtual Desktop ホスト プールと割り当てを作成することを検討してください。

4. ネットワーク保護を監査モードでテストし、ロールアウトする前にその動作を評価します。

5. 多数のユーザーまたは多数のマルチユーザー セッションがある場合は、デプロイのサイズを変更することを検討してください。

### <a name="alternative-option-for-network-protection"></a>ネットワーク保護の代替オプション

Windows Server バージョン 1803 以降および Windows Virtual Desktop on Azure で使用されるマルチセッション 1909 以降Windows 10 Enterpriseの場合、Microsoft Edge のネットワーク保護を有効にするには、次の方法を使用します。

1. [[ネットワーク保護を有効にする]](enable-network-protection.md) を使用し、指示に従ってポリシーを適用します。

2. 次の PowerShell コマンドを実行します。

   - `Set-MpPreference -EnableNetworkProtection Enabled`
   - `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`
   - `Set-MpPreference -AllowNetworkProtectionDownLevel 1`
   - `Set-MpPreference -AllowDatagramProcessingOnWinServer 1`

## <a name="network-protection-troubleshooting"></a>ネットワーク保護のトラブルシューティング

ネットワーク保護が実行される環境により、Microsoft はオペレーティング システム プロキシ設定を検出できない可能性があります。 場合によっては、ネットワーク保護クライアントがクラウド サービスに到達できないことがあります。 接続の問題を解決するには、 [Microsoft Defender ウイルス対策用の静的プロキシを構成します](configure-proxy-internet.md#configure-a-static-proxy-for-microsoft-defender-antivirus)。

## <a name="optimizing-network-protection-performance"></a>ネットワーク保護のパフォーマンスの最適化

ネットワーク保護では、SmartScreen によって検証および許可された後にブロック モードで長い接続の非同期的な検査を開始できるパフォーマンスの最適化が行われるようになりました。これにより、検査の帯域幅に関するコストが削減される可能性があり、アプリの互換性の問題にも役立つ可能性があります。 この最適化機能は既定でオンになっています。 この機能は、次の PowerShell コマンドレットを使用して無効にすることができます。

`Set-MpPreference -AllowSwitchToAsyncInspection $false`

## <a name="see-also"></a>関連項目

- [ネットワーク保護|を評価する](evaluate-network-protection.md) 機能のしくみと、通常作成されるイベントを示す簡単なシナリオを実行します。
- [ネットワーク保護|を有効にする](enable-network-protection.md)グループ ポリシー、PowerShell、または MDM CSP を使用して、ネットワーク内のネットワーク保護を有効および管理します。
- [Microsoft Intuneでの攻撃面の縮小機能の構成](/mem/intune/protect/endpoint-security-asr-policy)
- [Linux |のネットワーク保護](network-protection-linux.md) Microsoft Network Protection for Linux デバイスの使用について説明します。
- [MacOS |のネットワーク保護](network-protection-macos.md) Microsoft Network Protection for MacOS の詳細については、こちらを参照してください。
