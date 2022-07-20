---
title: Microsoft 365 Defender でインシデントを調査する
description: デバイス、ユーザー、メールボックスに関連するインシデントを調査します。
keywords: インシデント, インシデント, 分析, 応答, マシン, デバイス, ユーザー, ID, メール, 電子メール, メールボックス, 調査, グラフ, 証拠
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
ms.topic: conceptual
search.appverid:
- MOE150
ms.technology: m365d
ms.openlocfilehash: 441f9ce5824c1de82a5629e4c0ba9192ed89a529
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2022
ms.locfileid: "66895077"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender でインシデントを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

Microsoft 365 Defenderは、デバイス、ユーザー、メールボックス全体からのすべての関連するアラート、資産、調査、および証拠をインシデントに集約して、攻撃全体を包括的に調べます。

インシデント内では、ネットワークに影響を与えるアラートを分析し、その意味を理解し、証拠を照合して、効果的な修復計画を作成できるようにします。

## <a name="initial-investigation"></a>初期調査

詳細を確認する前に、インシデントのプロパティと概要を確認してください。

まず、チェック マーク列からインシデントを選択します。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="Microsoft 365 Defender ポータルでインシデントを選択する" lightbox="../../media/investigate-incidents/incidents-ss-incident-select.png":::

これを行うと、概要ウィンドウが開き、インシデントに関する重要な情報 (重大度など) が割り当てられ、 [MITRE ATT&インシデントの CK&trade;](https://attack.mitre.org/) カテゴリが表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="Microsoft 365 Defender ポータルでインシデントの概要の詳細を表示するウィンドウ。" lightbox="../../media/investigate-incidents/incidents-ss-incident-side-panel.png":::

ここから、[ **インシデント ページを開く**] を選択できます。 これにより、インシデントのメイン ページが開き、アラート、デバイス、ユーザー、調査、証拠の概要情報とタブが表示されます。

インシデント キューからインシデント名を選択して、インシデントのメイン ページを開くこともできます。

## <a name="summary"></a>概要

[ **概要]** ページでは、インシデントに関する注目すべき点の概要を一目で確認できます。

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 Defender ポータルでのインシデントの概要情報" lightbox="../../media/incidents-overview/incidents-ss-incident-summary.png":::

情報は、これらのセクションで整理されています。

| Section | 説明 |
|:-------|:-----|
| アラートとカテゴリ | 攻撃がキル チェーンに対してどのように進行したかを示す視覚的および数値的なビュー。 他の Microsoft セキュリティ製品と同様に、Microsoft 365 Defenderは [MITRE ATT&CK&trade;](https://attack.mitre.org/) フレームワークに準拠しています。 アラートタイムラインには、アラートが発生した時系列順と、それぞれの状態と名前が表示されます。 |
| 範囲 |  影響を受けるデバイス、ユーザー、メールボックスの数を表示し、リスク レベルと調査の優先順位の順にエンティティを一覧表示します。 |
| 証拠 | インシデントの影響を受けるエンティティの数を表示します。 |
| インシデント情報 | タグ、状態、重大度など、インシデントのプロパティを表示します。 |
|||

**[概要**] ページを使用して、インシデントの相対的な重要度を評価し、関連するアラートと影響を受けたエンティティにすばやくアクセスします。

## <a name="alerts"></a>アラート

[ **アラート** ] タブでは、インシデントに関連するアラートのアラート キューと、それらに関するその他の情報 (次のように) を表示できます。

- 重大 度。
- アラートに関与したエンティティ。
- アラートのソース (Microsoft Defender for Identity、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Defender for Cloud Apps、アプリ ガバナンス アドオン)。
- それらが一緒にリンクされた理由。

次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Microsoft 365 Defender ポータルのインシデントの [アラート] ウィンドウ" lightbox="../../media/investigate-incidents/incident-alerts.png":::

既定では、時間の経過と共に攻撃がどのように行ったかを確認できるように、アラートは時系列順に並べ替えられます。 インシデント内でアラートを選択すると、全体的なインシデントのコンテキストに固有のアラート情報がMicrosoft 365 Defenderに表示されます。 

アラートのイベント、現在のアラートの原因となった他のトリガーされたアラート、および攻撃に関連するすべての影響を受けるエンティティとアクティビティ (デバイス、ファイル、ユーザー、メールボックスなど) を確認できます。

次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-alert-example.png" alt-text="Microsoft 365 Defender ポータルのインシデント内のアラートの詳細。" lightbox="../../media/investigate-incidents/incident-alert-example.png":::

インシデント アラート ページには、次のセクションがあります。

- アラート ストーリー。これには次のものが含まれます。

   - どうしたのですか

   - 実行された処理

   - 関連イベント

- 右側のウィンドウのアラート プロパティ (状態、詳細、説明など)

すべてのアラートに、[ **アラート ストーリー** ] セクションに一覧表示されているすべてのサブセクションがあるわけではありません。

[アラートの調査](investigate-alerts.md)でアラート キューとアラート ページを使用する方法について説明します。

## <a name="devices"></a>デバイス

[ **デバイス]** タブには、インシデントに関連するすべてのデバイスが一覧表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Microsoft 365 Defender ポータルのインシデントの [デバイス] ページ" lightbox="../../media/investigate-incidents/incident-devices.png":::

デバイスのチェック マークを選択すると、デバイス、ディレクトリ データ、アクティブなアラート、ログオンしているユーザーの詳細を確認できます。 デバイスの名前を選択すると、Defender for Endpoint デバイス インベントリにデバイスの詳細が表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Microsoft Defender for Endpointの [デバイス インベントリ] オプション関連ページ。" lightbox="../../media/investigate-incidents/incident-devices-details.png":::

デバイス ページから、すべてのアラート、タイムライン、セキュリティに関する推奨事項など、デバイスに関する追加情報を収集できます。 たとえば、[ **タイムライン** ] タブでは、コンピューターのタイムラインをスクロールし、アラートが発生したコンピューターで観察されたすべてのイベントと動作を時系列順に表示できます。

> [!TIP]
> デバイス ページでオンデマンド スキャンを実行できます。 Microsoft 365 Defender ポータルで、[**エンドポイント] > [デバイス インベントリ]** を選択します。 アラートを含むデバイスを選択し、ウイルス対策スキャンを実行します。 ウイルス対策スキャンなどのアクションは追跡され、[ **デバイス インベントリ]** ページに表示されます。 詳細については、「 [デバイスでの Defender ウイルス対策スキャンの実行」を](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)参照してください。

## <a name="users"></a>ユーザー

[ **ユーザー]** タブには、インシデントの一部または関連として識別されたすべてのユーザーが一覧表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Microsoft 365 Defender ポータルの [ユーザー] ページ。" lightbox="../../media/investigate-incidents/incident-users.png":::

ユーザーのチェック マークを選択すると、ユーザー アカウントの脅威、露出、連絡先情報の詳細を確認できます。 ユーザー名を選択すると、追加のユーザー アカウントの詳細が表示されます。

追加のユーザー情報を表示し、ユーザーを調査するインシデントのユーザーを管理する方法について説明 [します](investigate-users.md)。


## <a name="mailboxes"></a>メールボックス

[ **メールボックス]** タブには、インシデントの一部または関連として識別されたすべてのメールボックスが一覧表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Microsoft 365 Defender ポータルのインシデントの [メールボックス] ページ。" lightbox="../../media/investigate-incidents/incident-mailboxes.png":::

メールボックスのチェック マークを選択すると、アクティブなアラートの一覧を表示できます。 メールボックス名を選択すると、Defender for Office 365のエクスプローラー ページに追加のメールボックスの詳細が表示されます。

## <a name="investigations"></a>調査

[ **調査]** タブには、このインシデントのアラートによってトリガーされたすべての [自動調査](m365d-autoir.md) が一覧表示されます。 自動調査は、Defender for Endpoint と Defender for Office 365 で実行するように自動調査を構成した方法に応じて、修復アクションを実行するか、アナリストによるアクションの承認を待ちます。

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Microsoft 365 Defender ポータルのインシデントの [調査] ページ" lightbox="../../media/investigate-incidents/incident-investigations.png":::

調査を選択して詳細ページに移動し、調査と修復の状態に関する完全な情報を確認します。 調査の一環として承認のために保留中のアクションがある場合、[ **保留中のアクション履歴** ] タブにアクションが表示されます。インシデント修復の一環としてアクションを実行します。

次を示す [ **調査グラフ** ] タブもあります。

- 組織内の影響を受ける資産へのアラートの接続。
- どのエンティティがどのアラートに関連し、それらが攻撃のストーリーにどのように含まれているか。
- インシデントのアラート。

調査グラフは、攻撃の一部であるさまざまな疑わしいエンティティを、ユーザー、デバイス、メールボックスなどの関連資産に接続することで、攻撃の完全な範囲をすばやく理解するのに役立ちます。 

詳細については、「[Microsoft 365 Defenderでの自動調査と応答](m365d-autoir.md)」を参照してください。

## <a name="evidence-and-response"></a>証拠と応答

[ **証拠と応答]** タブには、インシデントのアラートでサポートされているすべてのイベントと疑わしいエンティティが表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Microsoft 365 Defender ポータルのインシデントの [証拠と対応] ページ" lightbox="../../media/investigate-incidents/incident-evidence.png":::

Microsoft 365 Defenderは、アラートでサポートされているすべてのインシデントのサポートされているイベントと疑わしいエンティティを自動的に調査し、重要な電子メール、ファイル、プロセス、サービス、IP アドレスなどの情報を提供します。 これにより、インシデント内の潜在的な脅威をすばやく検出してブロックできます。

分析された各エンティティは、判定 (悪意のある、疑わしい、クリーン) と修復状態でマークされます。 これにより、インシデント全体の修復状態と、次に実行できる手順を理解するのに役立ちます。

## <a name="graph-preview"></a>Graph (プレビュー)

**[グラフ**] タブには、攻撃の完全な範囲、時間の経過と共にネットワーク経由で攻撃がどのように拡散したか、開始された場所、攻撃者がどれだけ離れた場所に行ったかを示します。 攻撃の一部であるさまざまな疑わしいエンティティと、ユーザー、デバイス、メールボックスなどの関連資産を接続します。 

[ **グラフ** ] タブでは、次のことができます。

1. 時間の経過と共に発生したアラートとグラフ上のノードを再生して、攻撃の時系列を理解します。


   :::image type="content" source="../../media/investigate-incidents/incident-graph-play.gif" alt-text="グラフ ページでのアラートとノードの再生":::
 

2. エンティティ ウィンドウを開くと、エンティティの詳細を確認し、ファイルの削除やデバイスの分離などの修復アクションに対処できます。
 
   :::image type="content" source="../../media/investigate-incidents/incident-graph-entity-pane.png" alt-text="Microsoft 365 Defender ポータルの [グラフ] ページのエンティティ ウィンドウ" lightbox="../../media/investigate-incidents/incident-graph-entity-pane.png":::

3. 関連するエンティティに基づいてアラートを強調表示します。
 
   :::image type="content" source="../../media/investigate-incidents/incident-graph-alert.png" alt-text="[グラフ] ページのアラート の強調表示" lightbox="../../media/investigate-incidents/incident-graph-alert.png":::

## <a name="next-steps"></a>次の手順

必要に応じて、

- [インシデントのアラートを調査する](investigate-alerts.md)
- [インシデントのユーザーを調査する](investigate-users.md)

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの優先度設定](incident-queue.md)
- [インシデントの管理](manage-incidents.md)
