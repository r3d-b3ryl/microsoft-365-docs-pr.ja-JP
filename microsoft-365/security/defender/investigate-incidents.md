---
title: Microsoft 365 Defender のインシデントを調査する
description: デバイス、ユーザー、メールボックスに関連するインシデントを分析します。
keywords: インシデント、コンピューター、デバイス、ユーザー、ID、メール、電子メール、メールボックス、調査、グラフ、証拠
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
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 99acc25c3949b758dab990a9c2e9104b9158accd
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861877"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender のインシデントを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**

- Microsoft 365 Defender

Microsoft 365 Defender は、デバイス、ユーザー、およびメールボックス全体からのすべての関連するアラート、資産、調査、および証拠をインシデントに集約し、攻撃の幅広い全体を総合的に調査します。

インシデント内では、ネットワークに影響を与えるアラートを調査し、その意味を理解し、効果的な修復計画を策定できるよう証拠を照合します。

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

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 セキュリティ センターのインシデントの概要ページの例":::

攻撃カテゴリを使用すると、キル チェーンに対する攻撃の進行状況を視覚的および数値的に確認できます。 他の Microsoft セキュリティ製品と同様に、Microsoft 365 Defender は[MITRE ATT &trade; ](https://attack.mitre.org/)と CK フレームワーク&揃っています。

範囲セクションでは、このインシデントの一部である最も影響を受ける資産の一覧が表示されます。 この資産に関する特定の情報 (リスク レベル、調査の優先順位、資産のタグ付けなど) がある場合は、その情報もこのセクションに表示されます。

アラートのタイムラインでは、アラートが発生した時系列の順序と、これらのアラートがこのインシデントにリンクされている理由を確認できます。

最後に、 - 証拠セクションには、インシデントに含まれるさまざまなアーティファクトの数とその修復状態の概要が示されています。そのため、必要なアクションが必要な場合は直ちに特定できます。

この概要は、インシデントの最初のトリアージを支援するために、注意する必要があるインシデントの最高の特性に関する洞察を提供します。

## <a name="alerts"></a>アラート

[アラート **] タブ** で、インシデントに関連するアラートや、次のようなアラートに関するその他の情報のアラート キューを表示できます。

- 重大度。
- アラートに関与したエンティティ。
- アラートのソース (Microsoft Defender for Identity、Microsoft Defender for Endpoint、Microsoft Defender for Office 365)。
- リンクされた理由。

次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="インシデントのアラート ページの例":::

既定では、アラートは時系列的に順序付けされ、インシデントが時間の間にどのように再生されたのか確認できます。 各アラートを選択すると、アラートのメイン ページに移動し、アラートの詳細な調査を実行できます。 

アラートの調査でアラート キューとアラート ページを使用する方法 [について説明します。](investigate-alerts.md)

## <a name="devices"></a>デバイス

[ **デバイス]** タブには、インシデントに関連付けたすべてのデバイスが一覧表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="インシデントのデバイス ページの例":::

デバイスのチェック マークを選択すると、デバイス、ディレクトリ データ、アクティブなアラート、ログオンしているユーザーの詳細を確認できます。 デバイスの名前を選択すると、Microsoft Defender for Endpoints デバイス インベントリにデバイスの詳細が表示されます。

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Microsoft Defender for Endpoints のデバイス ページの例":::

デバイス ページから、すべての通知、タイムライン、セキュリティに関する推奨事項など、デバイスに関する追加情報を収集できます。 たとえば、[タイムライン]タブから、コンピューターのタイムラインをスクロールして、発生したアラートと一緒に、コンピューター上で観察されたイベントと動作を時系列順に表示できます。

> [!TIP]
> デバイス ページでオンデマンド スキャンを実行できます。 Microsoft 365 セキュリティ センターで、[エンドポイント] > **を選択します**。 通知があるデバイスを選択し、ウイルス対策スキャンを実行します。 ウイルス対策スキャンなどのアクションは追跡され、[デバイス インベントリ] ページ **に表示** されます。 詳細については、「デバイスで [Microsoft Defender ウイルス対策スキャンを実行する」を参照してください](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)。

## <a name="users"></a>ユーザー

[ **ユーザー]** タブには、インシデントの一部または関連付けとして識別されたすべてのユーザーが一覧表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="インシデントの [ユーザー] ページの例":::

ユーザーのチェック マークを選択すると、ユーザー アカウントの脅威、露出、連絡先情報の詳細を確認できます。 ユーザー名を選択すると、追加のユーザー アカウントの詳細が表示されます。

## <a name="mailboxes"></a>メールボックス

[ **メールボックス] タブ** には、インシデントの一部または関連付けとして識別されたすべてのメールボックスが一覧表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="インシデントのメールボックス ページの例":::

メールボックスのチェック マークを選択すると、アクティブなアラートの一覧を表示できます。 メールボックス名を選択すると、Microsoft Defender for microsoft Defender for microsoft Defender 365 の [エクスプローラー] ページに追加Office表示されます。

## <a name="investigations"></a>調査

[ **調査] タブ** には、このインシデントのアラートによってトリガーされる自動調査の一覧が表示されます。 調査は、Microsoft Defender for Endpoint および Defender for Office 365 で実行するように自動調査を構成した方法に応じて、修復アクションを実行するか、アナリストによるアクションの承認を待機します。

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="インシデントの [調査] ページの例":::

調査を選択して [調査の詳細] ページに移動すると、調査と修復状況に関する詳細情報が表示されます。 調査の一環として承認待ちアクションがある場合は、[保留中のアクション] タブに表示されます。インシデント修復の一環としてアクションを実行します。

## <a name="evidence-and-response"></a>証拠と対応

[ **証拠と応答] タブ** には、インシデント内のアラートでサポートされているイベントと疑わしいエンティティが表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="インシデントの証拠と応答ページの例":::

Microsoft 365 Defender は、インシデントがサポートしているすべてのイベントと、アラート内の不審なエンティティを自動的に調査し、重要な電子メール、ファイル、プロセス、サービス、IP アドレスなどの情報を提供します。 これにより、インシデントの潜在的な脅威をすばやく検出してブロックできます。

分析された各エンティティには、評決 (悪意のある、疑わしい、クリーン) と修復状態がマークされます。 これにより、インシデント全体の修復状態と、次に実行できる手順を理解できます。

## <a name="related-topics"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの優先度設定](incident-queue.md)
- [インシデントの管理](manage-incidents.md)

