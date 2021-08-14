---
title: インシデントを調査Microsoft 365 Defender
description: デバイス、ユーザー、メールボックスに関連するインシデントを調査します。
keywords: インシデント、インシデント、分析、応答、コンピューター、デバイス、ユーザー、ID、メール、メール、メールボックス、調査、グラフ、証拠
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
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
- MET150
ms.technology: m365d
ms.openlocfilehash: 6672723f6a4f3319e837fbb85442a031414e5cba67809197312eebf411a301e4
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53862683"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>インシデントを調査Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

Microsoft 365 Defender、デバイス、ユーザー、およびメールボックス全体からのすべての関連するアラート、資産、調査、および証拠をインシデントに集約し、攻撃の幅広い全体を総合的に調査します。

インシデント内では、ネットワークに影響を与えるアラートを分析し、その意味を理解し、証拠を照合して、効果的な修復計画を策定できます。

## <a name="initial-investigation"></a>初期調査

詳細を確認する前に、インシデントのプロパティと概要を確認してください。

まず、チェック マーク列からインシデントを選択します。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="チェック マーク列からインシデントを選択する例":::

その場合、概要ウィンドウが開き、インシデントに関する重要な情報 (重大度、割り当て先、インシデントの[MITRE ATT&CK &trade; ](https://attack.mitre.org/)カテゴリなど) が表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="インシデントの概要ウィンドウの例":::

ここから、[インシデントページを開 **く] を選択できます**。 これにより、インシデントのメイン ページが開き、アラート、デバイス、ユーザー、調査、および証拠の概要情報とタブが表示されます。

インシデント キューからインシデント名を選択して、インシデントのメイン ページを開く方法も指定できます。

## <a name="summary"></a>概要

[ **概要] ページ** では、インシデントに関する一番上の情報をスナップショットで確認できます。

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="セキュリティ センターのインシデントの概要ページMicrosoft 365例":::

攻撃カテゴリを使用すると、キル チェーンに対する攻撃の進行状況を視覚的および数値的に確認できます。 他の Microsoft セキュリティ製品と同様に、Microsoft 365 Defender CK フレームワークの[MITRE ATT &trade;&配置](https://attack.mitre.org/)されます。

範囲セクションでは、このインシデントの一部である最も影響を受ける資産の一覧が表示されます。 この資産に関する特定の情報 (リスク レベル、調査の優先順位、資産のタグ付けなど) がある場合は、その情報もこのセクションに表示されます。

アラートのタイムラインでは、アラートが発生した時系列の順序と、これらのアラートがこのインシデントにリンクされている理由を確認できます。

最後に、 - 証拠セクションには、インシデントに含まれるさまざまなアーティファクトの数とその修復状態の概要が示されています。そのため、必要なアクションが必要な場合は直ちに特定できます。

この概要は、インシデントの最初のトリアージを支援するために、注意する必要があるインシデントの最高の特性に関する洞察を提供します。

## <a name="alerts"></a>アラート

[アラート **] タブ** で、インシデントに関連するアラートや、次のようなアラートに関するその他の情報のアラート キューを表示できます。

- 重大度。
- アラートに関与したエンティティ。
- アラートのソース (Microsoft Defender for Identity、 Microsoft Defender for Endpoint、 Microsoft Defender for Office 365)。
- リンクされた理由。

次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="インシデントのアラート ページの例":::

既定では、アラートは時系列的に順序付けされ、インシデントが時間の間にどのように再生されたのか確認できます。 インシデント内でアラートを選択すると、Microsoft 365 Defenderのコンテキストに固有のアラート情報が表示されます。 

アラートのイベント、その他のトリガーされたアラートによって現在のアラートが発生したイベント、およびファイル、ユーザー、メールボックスなど、攻撃に関連する影響を受けるすべてのエンティティとアクティビティを確認できます。

次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-alert-example.png" alt-text="インシデント内のアラートの詳細ページの例":::

このインシデント アラート ページは、次のセクションで構成されます。

- アラート ストーリー(発生した内容の概要を含む)
- 関連するイベントとアラート
- 概要の詳細

アラートの調査でアラート キューとアラート ページを使用する方法 [について説明します](investigate-alerts.md)。

## <a name="devices"></a>デバイス

[ **デバイス]** タブには、インシデントに関連付けたすべてのデバイスが一覧表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="インシデントのデバイス ページの例":::

デバイスのチェック マークを選択すると、デバイス、ディレクトリ データ、アクティブなアラート、ログオンしているユーザーの詳細を確認できます。 デバイスの名前を選択すると、Microsoft Defender for Endpoints デバイス インベントリにデバイスの詳細が表示されます。

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Microsoft Defender for Endpoints のデバイス ページの例":::

デバイス ページから、すべての通知、タイムライン、セキュリティに関する推奨事項など、デバイスに関する追加情報を収集できます。 たとえば、[タイムライン]タブから、コンピューターのタイムラインをスクロールして、発生したアラートと一緒に、コンピューター上で観察されたイベントと動作を時系列順に表示できます。

> [!TIP]
> デバイス ページでオンデマンド スキャンを実行できます。 セキュリティ センターでMicrosoft 365デバイス インベントリの **[エンドポイント] >を選択します**。 通知があるデバイスを選択し、ウイルス対策スキャンを実行します。 ウイルス対策スキャンなどのアクションは追跡され、[デバイス インベントリ] ページ **に表示** されます。 詳細については、「デバイスでスキャン[を実行Microsoft Defender ウイルス対策」を参照してください](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)。

## <a name="users"></a>ユーザー

[ **ユーザー]** タブには、インシデントの一部または関連付けとして識別されたすべてのユーザーが一覧表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="インシデントの [ユーザー] ページの例":::

ユーザーのチェック マークを選択すると、ユーザー アカウントの脅威、露出、連絡先情報の詳細を確認できます。 ユーザー名を選択すると、追加のユーザー アカウントの詳細が表示されます。

ユーザーの調査で追加のユーザー情報を表示し、インシデントのユーザーを管理する方法 [について学習します](investigate-users.md)。


## <a name="mailboxes"></a>メールボックス

[ **メールボックス] タブ** には、インシデントの一部または関連付けとして識別されたすべてのメールボックスが一覧表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="インシデントのメールボックス ページの例":::

メールボックスのチェック マークを選択すると、アクティブなアラートの一覧を表示できます。 メールボックス名を選択すると、Microsoft Defender for microsoft Defender の [エクスプローラー] ページに追加のメールボックスの詳細が表示Office 365。

## <a name="investigations"></a>調査

[ **調査] タブ** には、このインシデントのアラート [によって](m365d-autoir.md) トリガーされる自動調査の一覧が表示されます。 調査は、Microsoft Defender for Endpoint および Defender for Office 365 で実行するように自動調査を構成した方法に応じて、修復アクションを実行するか、アナリストによるアクションの承認を待機します。

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="インシデントの [調査] ページの例":::

調査を選択して詳細ページに移動し、調査と修復の状態に関する完全な情報を確認します。 調査の一環として承認待ちアクションがある場合は、[保留中のアクションの履歴] **タブに表示** されます。インシデント修復の一環としてアクションを実行します。

[調査] グラフ タブ **には、次** の情報が表示されます。

- 組織内の影響を受け取ったアセットへのアラートの接続。
- どのエンティティが、どのアラートに関連付け、どのエンティティが攻撃のストーリーの一部であるのか。
- インシデントのアラート。

調査グラフを使用すると、攻撃の一部であるさまざまな不審なエンティティと、ユーザー、デバイス、メールボックスなどの関連する資産を接続することで、攻撃の全範囲をすばやく把握できます。 

詳細については、「自動調査と応答[」](m365d-autoir.md)を参照Microsoft 365 Defender。

## <a name="evidence-and-response"></a>証拠と対応

[ **証拠と応答] タブ** には、インシデント内のアラートでサポートされているイベントと疑わしいエンティティが表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="インシデントの証拠と応答ページの例":::

Microsoft 365 Defenderアラート内のすべてのインシデントでサポートされているイベントと不審なエンティティを自動的に調査し、重要な電子メール、ファイル、プロセス、サービス、IP アドレスなどの情報を提供します。 これにより、インシデントの潜在的な脅威をすばやく検出してブロックできます。

分析された各エンティティには、評決 (悪意のある、疑わしい、クリーン) と修復状態がマークされます。 これにより、インシデント全体の修復状態と、次に実行できる手順を理解できます。

## <a name="next-steps"></a>次の手順

必要に応じて、

- [インシデントのアラートを調査する](investigate-alerts.md)
- [インシデントのユーザーを調査する](investigate-users.md)

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの優先度設定](incident-queue.md)
- [インシデントの管理](manage-incidents.md)

