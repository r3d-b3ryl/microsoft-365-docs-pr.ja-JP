---
title: Microsoft 365 Defender でインシデントを調査する
description: デバイス、ユーザー、メールボックスに関連するインシデントを調査します。
keywords: インシデント、インシデント、分析、応答、コンピューター、デバイス、ユーザー、ID、メール、メール、メールボックス、調査、グラフ、証拠
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
- incidentresponse
- m365solution-incidentresponse
- m365solution-overview
ms.topic: conceptual
search.appverid:
- MOE150
ms.technology: m365d
ms.openlocfilehash: 776680db7b2666cc964f82e88cd6af9e6bab7558
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2022
ms.locfileid: "64500257"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender でインシデントを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

Microsoft 365 Defender、デバイス、ユーザー、およびメールボックス全体からのすべての関連するアラート、資産、調査、および証拠をインシデントに集約し、攻撃の幅広い全体を総合的に調査します。

インシデント内では、ネットワークに影響を与えるアラートを分析し、その意味を理解し、証拠を照合して、効果的な修復計画を策定できます。

## <a name="initial-investigation"></a>初期調査

詳細を確認する前に、インシデントのプロパティと概要を確認してください。

まず、チェック マーク列からインシデントを選択します。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="ポータルでインシデントをMicrosoft 365 Defenderする" lightbox="../../media/investigate-incidents/incidents-ss-incident-select.png":::

その場合、概要ウィンドウが開き、インシデントに関する重要な情報 (重大度、割り当て先、 [インシデントの MITRE ATT&CK&trade;](https://attack.mitre.org/) カテゴリなど) が表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="ポータル内のインシデントの概要の詳細を表示Microsoft 365 Defenderします。" lightbox="../../media/investigate-incidents/incidents-ss-incident-side-panel.png":::

ここから、[インシデントページを開 **く] を選択できます**。 これにより、インシデントのメイン ページが開き、アラート、デバイス、ユーザー、調査、および証拠の概要情報とタブが表示されます。

インシデント キューからインシデント名を選択して、インシデントのメイン ページを開く方法も指定できます。

## <a name="summary"></a>概要

[ **概要] ページ** では、インシデントに関する一番上の情報をスナップショットで確認できます。

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="ポータル内のインシデントのMicrosoft 365 Defender情報" lightbox="../../media/incidents-overview/incidents-ss-incident-summary.png":::

情報は、これらのセクションで整理されています。

| Section | 説明 |
|:-------|:-----|
| アラートとカテゴリ | キル チェーンに対する攻撃の進行状況を視覚的および数値的に表示します。 他の Microsoft セキュリティ製品と同様に、Microsoft 365 Defender CK フレームワークの [MITRE ATT&配置&trade;](https://attack.mitre.org/)されます。 アラートのタイムラインには、アラートが発生した時系列の順序と、それぞれの状態と名前が表示されます。 |
| 範囲 |  影響を受けたデバイス、ユーザー、メールボックスの数を表示し、リスク レベルと調査の優先度の順にエンティティを一覧表示します。 |
| 証拠 | インシデントの影響を受けるエンティティの数を表示します。 |
| インシデント情報 | タグ、状態、重大度などのインシデントのプロパティを表示します。 |
|||

[概要 **] ページを使用** して、インシデントの相対的な重要度を評価し、関連付けられたアラートと影響を受けたエンティティにすばやくアクセスします。

## <a name="alerts"></a>アラート

[アラート **] タブ** で、インシデントに関連するアラートや、次のようなアラートに関するその他の情報について、アラート キューを表示できます。

- 重大度。
- アラートに関与したエンティティ。
- アラートのソース (Microsoft Defender for Identity、Microsoft Defender for Endpoint、microsoft Defender for Office 365、Defender for Cloud Apps、およびアプリ ガバナンス アドオン)。
- リンクされた理由。

次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="ポータル内のインシデントの [アラート] ウィンドウMicrosoft 365 Defenderします。" lightbox="../../media/investigate-incidents/incident-alerts.png":::

既定では、アラートは時系列的に順序付けされ、時間の間に攻撃がどのように実行されたのか確認できます。 インシデント内でアラートを選択すると、Microsoft 365 Defenderのコンテキストに固有のアラート情報が表示されます。 

アラートのイベント、その他のトリガーされたアラートによって現在のアラートが発生したイベント、およびデバイス、ファイル、ユーザー、メールボックスなど、攻撃に関連する影響を受けるすべてのエンティティとアクティビティを確認できます。

次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-alert-example.png" alt-text="ポータル内のインシデント内のアラートのMicrosoft 365 Defender。" lightbox="../../media/investigate-incidents/incident-alert-example.png":::

インシデント通知ページには、次のセクションがあります。

- アラート ストーリー:次の内容が含まれます。

   - どうしたのですか

   - 実行された処理

   - 関連イベント

- 右側のウィンドウのアラート プロパティ (状態、詳細、説明など)

すべてのアラートに、[アラート ストーリー] セクションに一覧表示されているサブセクション **が表示される場合** があります。

アラートの調査でアラート キューとアラート ページを使用する方法 [について説明します](investigate-alerts.md)。

## <a name="devices"></a>デバイス

[ **デバイス]** タブには、インシデントに関連付けたすべてのデバイスが一覧表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="ポータル内のインシデントの [デバイス] Microsoft 365 Defender" lightbox="../../media/investigate-incidents/incident-devices.png":::

デバイスのチェック マークを選択すると、デバイス、ディレクトリ データ、アクティブなアラート、ログオンしているユーザーの詳細を確認できます。 デバイスの名前を選択すると、Defender for Endpoint デバイス インベントリにデバイスの詳細が表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Microsoft Defender for Endpoint の [デバイス インベントリ] オプション関連ページ。" lightbox="../../media/investigate-incidents/incident-devices-details.png":::

デバイス ページから、すべての通知、タイムライン、セキュリティに関する推奨事項など、デバイスに関する追加情報を収集できます。 たとえば、[タイムライン] タブから、コンピューターのタイムラインをスクロールして、発生したアラートと一緒に、コンピューター上で観察されたイベントと動作を時系列順に表示できます。

> [!TIP]
> デバイス ページでオンデマンド スキャンを実行できます。 [デバイス] Microsoft 365 Defenderで、[エンドポイント] を選択 **>デバイス インベントリを選択します**。 通知があるデバイスを選択し、ウイルス対策スキャンを実行します。 ウイルス対策スキャンなどのアクションは追跡され、[デバイス インベントリ] ページ **に表示** されます。 詳細については、「デバイスで [Defender ウイルス対策スキャンを実行する」を参照してください](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)。

## <a name="users"></a>ユーザー

[ **ユーザー]** タブには、インシデントの一部または関連付けとして識別されたすべてのユーザーが一覧表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="ポータルの [ユーザー] ページMicrosoft 365 Defenderします。" lightbox="../../media/investigate-incidents/incident-users.png":::

ユーザーのチェック マークを選択すると、ユーザー アカウントの脅威、露出、連絡先情報の詳細を確認できます。 ユーザー名を選択すると、追加のユーザー アカウントの詳細が表示されます。

ユーザーの調査で、追加のユーザー情報を表示し、インシデントのユーザーを管理する [方法について学習します](investigate-users.md)。


## <a name="mailboxes"></a>メールボックス

[ **メールボックス] タブ** には、インシデントの一部または関連付けとして識別されたすべてのメールボックスが一覧表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="ポータル内のインシデントの [メールボックス] ページMicrosoft 365 Defenderします。" lightbox="../../media/investigate-incidents/incident-mailboxes.png":::

メールボックスのチェック マークを選択すると、アクティブなアラートの一覧を表示できます。 メールボックス名を選択すると、その他のメールボックスの詳細が [エクスプローラー] ページで [Defender for defender for Office 365。

## <a name="investigations"></a>調査

[ **調査] タブ** には、このインシデントのアラート [によって](m365d-autoir.md) トリガーされる自動調査の一覧が表示されます。 自動調査では、エンドポイント用 Defender および Defender for Office 365 で実行するように自動調査を構成した方法に応じて、修復アクションを実行するか、アナリストによるアクションの承認を待ちます。

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="ポータル内のインシデントの [調査] Microsoft 365 Defender" lightbox="../../media/investigate-incidents/incident-investigations.png":::

調査を選択して詳細ページに移動し、調査と修復の状態に関する完全な情報を確認します。 調査の一環として承認待ちアクションがある場合は、[保留中のアクションの履歴] **タブに表示** されます。インシデント修復の一環としてアクションを実行します。

[調査] グラフ タブ **には、次** の情報が表示されます。

- 組織内の影響を受け取ったアセットへのアラートの接続。
- どのエンティティが、どのアラートに関連付け、どのエンティティが攻撃のストーリーの一部であるのか。
- インシデントのアラート。

調査グラフを使用すると、攻撃の一部であるさまざまな不審なエンティティと、ユーザー、デバイス、メールボックスなどの関連する資産を接続することで、攻撃の全範囲をすばやく把握できます。 

詳細については、「自動調査と応答」を参照[Microsoft 365 Defender](m365d-autoir.md)。

## <a name="evidence-and-response"></a>証拠と対応

[ **証拠と応答] タブ** には、インシデント内のアラートでサポートされているイベントと疑わしいエンティティが表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="ポータル内のインシデントの証拠とMicrosoft 365 Defenderページ" lightbox="../../media/investigate-incidents/incident-evidence.png":::

Microsoft 365 Defenderアラート内のすべてのインシデントでサポートされているイベントと不審なエンティティを自動的に調査し、重要な電子メール、ファイル、プロセス、サービス、IP アドレスなどの情報を提供します。 これにより、インシデントの潜在的な脅威をすばやく検出してブロックできます。

分析された各エンティティには、評決 (悪意のある、疑わしい、クリーン) と修復状態がマークされます。 これにより、インシデント全体の修復状態と、次に実行できる手順を理解できます。

## <a name="graph-preview"></a>Graph (プレビュー)

[**Graph**] タブには、攻撃の全範囲、攻撃がネットワーク経由で時間の間にどのように広がったか、開始した場所、攻撃者がどこまで攻撃を行ったかが表示されます。 攻撃の一部であるさまざまな不審なエンティティを、ユーザー、デバイス、メールボックスなどの関連資産と接続します。 

[オプション] **Graph** で、次の方法を実行できます。

1. 時間の間に発生したアラートとグラフ上のノードを再生して、攻撃の時系列を把握します。


   :::image type="content" source="../../media/investigate-incidents/incident-graph-play.gif" alt-text="[警告とノードの再生] ページGraphします。":::
 

2. エンティティ ウィンドウを開き、エンティティの詳細を確認し、ファイルの削除やデバイスの分離などの修復アクションに対応できます。
 
   :::image type="content" source="../../media/investigate-incidents/incident-graph-entity-pane.png" alt-text="ポータルの [Graph] ページのエンティティ ウィンドウMicrosoft 365 Defenderします。" lightbox="../../media/investigate-incidents/incident-graph-entity-pane.png":::

3. 関連するエンティティに基づいてアラートを強調表示します。
 
   :::image type="content" source="../../media/investigate-incidents/incident-graph-alert.png" alt-text="[メッセージ] ページのGraph強調表示" lightbox="../../media/investigate-incidents/incident-graph-alert.png":::

## <a name="next-steps"></a>次の手順

必要に応じて、

- [インシデントのアラートを調査する](investigate-alerts.md)
- [インシデントのユーザーを調査する](investigate-users.md)

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの優先度設定](incident-queue.md)
- [インシデントの管理](manage-incidents.md)
