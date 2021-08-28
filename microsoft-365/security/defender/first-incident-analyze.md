---
title: 手順 1. 最初のインシデントをトリアージして分析する
description: 最初のインシデントのトリアージと分析を開始する方法は、Microsoft 365 Defender。
keywords: インシデント、アラート、調査、相関関係、攻撃、コンピューター、デバイス、ユーザー、ID、メールボックス、電子メール、365、microsoft、m365、インシデント対応、サイバー攻撃
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
ms.openlocfilehash: 33022fa1ad57b7adf13139272bcdca09a1d9487b
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58568830"
---
# <a name="step-1-triage-and-analyze-your-first-incident"></a>手順 1. 最初のインシデントをトリアージして分析する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

組織の標準に従ってセキュリティ対策を確立、実装、および維持するために少し時間を費やすと、セキュリティ リスクと脅威をすばやく特定するのに役立つセキュリティ ソリューションをセットアップできます。 Microsoft 365 Defenderを使用すると、1 ウィンドウのエクスペリエンスを通じてインシデントを検出、トリアージ、調査できます。このエクスペリエンスでは、時に判断するために必要な情報を見つける必要があります。

セキュリティ インシデントが検出されると、Microsoft 365 Defenderインシデントやインシデントを他のユーザーよりもトリアージまたは優先順位付けする必要がある詳細が表示されます。 アナリストは、事前設定を決定した後、割り当てられたケースの調査に集中できます。

## <a name="detection-by-microsoft-365-defender"></a>ユーザーによるMicrosoft 365 Defender

Microsoft 365 Defender複数の Microsoft セキュリティ プラットフォームからアラートとイベントを検出ソースとして受け取り、悪意のあるアクティビティの全体像とコンテキストを作成します。 次に、検出の可能性があるソースを示します。

- [Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md)は、Microsoft Defender ウイルス対策と Microsoft Security Graph を使用したクラウド対応の高度な脅威保護を使用するエンドポイント検出および応答ソリューション (EDR) です。 Defender for Endpoint は、予防保護、侵害後の検出、自動調査、および対応のための統合プラットフォームです。 エンドポイントをサイバー脅威から保護し、高度な攻撃とデータ侵害を検出し、セキュリティ インシデントを自動化し、セキュリティの態勢を改善します。
- [Microsoft Defender for Identity](/defender-for-identity/what-is) は、オンプレミスの Active Directory ドメイン サービス (AD DS) シグナルを使用して、組織に向けられた高度な脅威、侵害された ID、悪意のあるインサイダーアクションを特定、検出、および調査するクラウドベースのセキュリティ ソリューションです。
- [Microsoft Cloud App Security](/cloud-app-security/)は、エンタープライズ ユーザーと使用するクラウド リソースの間で、ユーザーがどこにいて、使用しているデバイスに関係なく、リアルタイムでブローカー アクセスを仲介するゲートキーパーとして機能します。
- [Microsoft Defender for Office 365](../office-365-security/overview.md)メール メッセージ、リンク (URL)、およびコラボレーション ツールにおける悪意のある脅威から組織を保護します。
- [Azure Security Center](/azure/security-center/security-center-introduction) は、データ センターのセキュリティ体制を強化し、クラウドおよびオンプレミスのハイブリッド ワークロード全体で高度な脅威保護を提供する統合インフラストラクチャ セキュリティ管理システムです。

この[Microsoft 365 Defender、インシデント](incidents-overview.md)は、これらの異なる検出ソースからのアラートを関連付けによって識別されます。 リソースを一緒に文字列化したり、複数のアラートをそれぞれのインシデントに区別したりするのではなく、Microsoft 365 Defenderから開始できます。 これにより、エンドポイント、ID、電子メール、アプリケーション間で効率的にインシデントをトリアージし、攻撃による被害を軽減できます。

## <a name="triage-your-incidents"></a>インシデントのトリアージ

組織の推奨Microsoft 365 Defender方法を使用してインシデントの一覧をトリアージすると、インシデント対応が開始されます。 トリアージとは、インシデントに重要度または緊急度のレベルを割り当て、インシデントを調査する順序を決定します。

優先度を設定するインシデントを決定するための便利なサンプル ガイドMicrosoft 365 Defender、重大度 + 影響 =*優先度という数式で要約できます*。

- **重大度は**、セキュリティ コンポーネントとその統合Microsoft 365 Defenderによって指定されるレベルです。
- **影響** は組織によって決定され、一般に、影響を受けるユーザー、デバイス、影響を受けるサービス (またはその組み合わせ)、およびアラートの種類のしきい値数が含まれますが、これらに限定されません。

アナリストは、組織が設定した優先度の基準 **に** 基づいて調査を開始します。

インシデントの事前設定は、組織によって異なる場合があります。 NIST では、インシデントの機能的および情報的な影響、および回復可能性も考慮する必要があります。

次に示すのは、トリアージに対する 1 つの方法です。

1. インシデント ページに [移動してトリ](incidents-overview.md) アージを開始します。 ここでは、組織に影響を与えるインシデントの一覧を確認できます。 既定では、最新のインシデントから最も古いインシデントに配置されます。 ここから、インシデントごとに異なる列が表示され、重大度、カテゴリ、アクティブなアラートの数、影響を受けたエンティティなどが表示されます。 列のセットをカスタマイズし、列名を選択して、これらの列によってインシデント キューを並べ替えできます。 必要に応じてインシデント キューをフィルター処理することもできます。 使用可能なフィルターの完全な一覧については、「インシデントの優先順位 [付け」を参照してください](incident-queue.md#available-filters)。

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-queue.png" alt-text="インシデント キューの例。":::

    この一連のインシデントに対してトリアージを実行する方法の 1 つの例は、より多くのユーザーとデバイスに影響を与えたインシデントに優先順位を付ける方法です。 この例では、7 台のデバイス、6 人のユーザー、および 2 つのメールボックスという最大のエンティティ数に影響を与えたため、インシデント ID 6769 の優先順位を付ける場合があります。 さらに、このインシデントには、ID ベースのアラートと資格情報の盗難の可能性を示す Microsoft Defender for Identity からのアラートが含まれていると思います。

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-high-impact.png" alt-text="影響の大きなインシデントの例。":::

2. インシデント名の横にある円を選択して詳細を確認します。 右側にサイド ウィンドウが表示されます。このウィンドウには、トリアージをさらに支援する追加情報が含まれる。

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png" alt-text="インシデント側ウィンドウの例。":::

   たとえば、攻撃者がインシデントのカテゴリに基づいて使用した [MITRE ATT&CK](https://attack.mitre.org/) の戦術を見て、攻撃者が盗まれた資格情報を使用し、コマンドと制御を確立し、横方向の動きを実行し、一部のデータを削除したため、このインシデントの優先順位を付けることができます。 これは、攻撃者が既にネットワークに深く入り込み、機密情報を盗まれた可能性を示唆しています。

   さらに、組織がゼロトラスト フレームワークを実装している場合は、資格情報アクセスを優先順位付けする価値のある重要なセキュリティ違反と見なします。

   サイド ウィンドウを下にスクロールすると、影響を受け取る特定のエンティティ (ユーザー、デバイス、メールボックスなど) が表示されます。 各デバイスの露出レベルと、影響を受けるメールボックスの所有者を確認できます。

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png" alt-text="インシデント側ウィンドウの詳細の例。":::

3. サイド ウィンドウをさらに下に移動すると、関連付けられたアラートを確認できます。 Microsoft 365 Defenderアラートの相関関係を 1 つのインシデントに既に実行し、攻撃の修復に費やした時間とリソースを節約できます。 アラートは疑わしいため、ネットワーク上に攻撃者が存在する可能性のある悪意のあるシステム イベントが発生する可能性があります。

   この例では、87 個の個別のアラートが 1 つのセキュリティ インシデントの一部と判断されました。 すべてのアラートを表示して、攻撃の実行方法を簡単に確認できます。

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png" alt-text="インシデント側ウィンドウのアラートの例。":::

## <a name="analyze-your-first-incident"></a>最初のインシデントを分析する

アラートを取り巻くコンテキストを理解するのも同様に重要です。 多くの場合、アラートは 1 つの独立したイベントではありません。 同時に発生していない可能性があるプロセス、コマンド、およびアクションのチェーンがあります。 そのため、アナリストは、アラートのコンテキストを理解するために、デバイスのタイムラインで不審なエンティティの最初と最後のアクティビティを探す必要があります。

データの読み取りおよび分析には、Microsoft 365 Defender方法が複数ありますが、アナリストの最後の目標は、インシデントに可能な限り迅速に対応することです。 このMicrosoft 365 Defender業界をリードする自動調査と対応機能を通じて、平均修復時間[(MTTR)](https://www.microsoft.com/security/blog/2020/05/04/lessons-learned-microsoft-soc-part-3c/)を大幅に短縮することができますが、手動分析が必要な場合は常に存在します。 [](m365d-autoir.md)

次に例を示します:

1. トリアージの優先度が決定された後、アナリストはインシデント名を選択して詳細な分析を開始します。 このページには、 **分析を支援** するタブにデータが表示されるインシデントの概要が表示されます。 [アラート] **タブ** の下に、アラートの種類が表示されます。 アナリストは、各アラートをクリックして、それぞれの検出ソースをドリルダウンできます。

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png" alt-text="インシデントの [概要] タブの例。":::

    各検出ソースがカバーするドメインに関するクイック ガイドについては、この記事の [「Detect」](#detection-by-microsoft-365-defender) セクションを参照してください。

2. [アラート **] タブ** から、アナリストは検出ソースにピボットして、より詳細な調査と分析を実行できます。 たとえば、検出ソースとして [マルウェア検出] Microsoft Cloud App Securityを選択すると、アナリストは対応するアラート ページに移動します。

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-select-alert.png" alt-text="インシデントのアラートを選択する例。":::

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png" alt-text="ページ内の対応するページのMicrosoft Cloud App Security。":::

3. この例をさらに調査するには、ページの下部までスクロールして、影響を受ける **ユーザーを表示します**。 マルウェア検出を取り巻くアクティビティとコンテキストを確認するには、Annette Hill のユーザー ページを選択します。

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-page.png" alt-text="ユーザー ページの例。":::

4. ユーザー ページには *、TOR* ネットワーク IP アドレスアラートからの危険なサインインから始まるイベントの時系列リストがあります。 アクティビティの疑いは、組織がビジネスを行う方法の性質によって異なりますが、ほとんどの場合、ユーザーが匿名で Web を閲覧できるネットワークである Onion Router (TOR) を企業環境で使用すると、通常のオンライン操作では非常に可能性が低く、不要と見なされる可能性があります。

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png" alt-text="ユーザーのイベントの時系列リストの例。":::

5. 各アラートを選択して、アクティビティの詳細を取得できます。 たとえば、[Tor **IP アドレス** ] アラートから [アクティビティ] を選択すると、そのアラートの独自のページに移動します。 Annette は、Office 365管理者であり、特権が昇格され、ソース インシデントが機密情報へのアクセスにつながった可能性があります。

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" alt-text="ユーザーの通知の詳細のMicrosoft Cloud App Security。":::

6. 他のアラートを選択すると、アナリストは攻撃の完全な画像を取得できます。

## <a name="next-step"></a>次の手順

[![手順 2: インシデントを修復する方法について学習します。](../../media/first-incident-overview/first-incident-path-step2.png)](first-incident-remediate.md)

インシデントを [修復する方法について学習します](first-incident-remediate.md)。

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの調査](investigate-incidents.md)
- [インシデントの管理](manage-incidents.md)
