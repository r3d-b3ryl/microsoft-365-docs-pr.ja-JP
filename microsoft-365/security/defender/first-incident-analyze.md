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
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
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
ms.openlocfilehash: 299cb7847e19e625bbae3122e16c56bb54e05c89
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2022
ms.locfileid: "64499025"
---
# <a name="step-1-triage-and-analyze-your-first-incident"></a>手順 1. 最初のインシデントをトリアージして分析する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

組織の標準に従ってセキュリティ対策を確立、実装、および維持するために少し時間を費やすと、セキュリティ リスクと脅威をすばやく特定するのに役立つセキュリティ ソリューションをセットアップできます。 Microsoft 365 Defenderを使用すると、単一ウィンドウのエクスペリエンスを通じてインシデントを検出、トリアージ、および調査できます。このエクスペリエンスでは、時に判断するために必要な情報を見つける必要があります。

セキュリティ インシデントが検出されると、Microsoft 365 Defender、インシデントやインシデントを他のユーザーよりもトリアージまたは優先順位付けする必要がある詳細が表示されます。 アナリストは、事前設定を決定した後、割り当てられたケースの調査に集中できます。

## <a name="detection-by-microsoft-365-defender"></a>ユーザーによるMicrosoft 365 Defender

Microsoft 365 Defender、複数の Microsoft セキュリティ プラットフォームからアラートとイベントを検出ソースとして受け取り、悪意のあるアクティビティの全体像とコンテキストを作成します。 検出の可能性があるソースは次のとおりです。

- [Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md) は、Microsoft Defender ウイルス対策とクラウド対応の高度な脅威保護を Microsoft Security Graph を使用するエンドポイント検出および応答ソリューション (EDR) です。 Defender for Endpoint は、予防保護、侵害後の検出、自動調査、および対応のための統合プラットフォームです。 エンドポイントをサイバー脅威から保護し、高度な攻撃とデータ侵害を検出し、セキュリティ インシデントを自動化し、セキュリティの態勢を改善します。
- [Microsoft Defender for Identity](/defender-for-identity/what-is) は、オンプレミスの Active Directory ドメイン サービス (AD DS) 信号を使用して、組織に向けられた高度な脅威、侵害された ID、悪意のある内部者のアクションを特定、検出、および調査するクラウドベースのセキュリティ ソリューションです。
- [Microsoft Defender for Cloud Apps](/cloud-app-security/) は、エンタープライズ ユーザーと使用するクラウド リソースの間で、ユーザーがどこにいても、使用しているデバイスに関係なく、リアルタイムでアクセスを仲介するゲートキーパーとして機能します。
- [Microsoft Defender for Office 365](../office-365-security/overview.md)メール メッセージ、リンク (URL)、およびコラボレーション ツールにおける悪意のある脅威から組織を保護します。
- [Azure Security Center](/azure/security-center/security-center-introduction) は、データ センターのセキュリティ体制を強化し、クラウドとオンプレミスのハイブリッド ワークロード全体で高度な脅威保護を提供する統合インフラストラクチャ セキュリティ管理システムです。


このMicrosoft 365 Defender[、インシデント](incidents-overview.md)は、これらの異なる検出ソースからのアラートを関連付けによって識別されます。 リソースを一緒に文字列化したり、複数のアラートをそれぞれのインシデントに区別したりするのではなく、Microsoft 365 Defenderから開始できます。 この方法では、エンドポイント、ID、電子メール、アプリケーション間で効率的にインシデントをトリアージし、攻撃による被害を軽減できます。

## <a name="triage-your-incidents"></a>インシデントのトリアージ

組織の推奨Microsoft 365 Defender方法を使用してインシデントの一覧をトリアージすると、インシデント対応が開始されます。 トリアージとは、インシデントに重要度または緊急度のレベルを割り当て、インシデントを調査する順序を決定します。

優先度を設定するインシデントを決定するための便利なサンプル ガイドMicrosoft 365 Defender、重大度 *+ 影響 = 優先度という数式でまとめることができます*。

- **重大度は**、セキュリティ コンポーネントと統合Microsoft 365 Defenderによって指定されるレベルです。
- **影響** は組織によって決定され、一般に、影響を受けるユーザー、デバイス、影響を受けるサービス (またはその組み合わせ)、およびアラートの種類のしきい値数が含まれますが、これらに限定されません。

アナリストは、組織が設定した優先度の基準 **に** 基づいて調査を開始します。

インシデントの事前設定は、組織によって異なる場合があります。 NIST では、インシデントの機能的および情報的な影響、および回復可能性も考慮する必要があります。

トリアージの 1 つの方法を以下に示します。

1. インシデント ページに [移動してトリ](incidents-overview.md) アージを開始します。 ここでは、組織に影響を与えるインシデントの一覧を確認できます。 既定では、最新のインシデントから最も古いインシデントに配置されます。 ここから、インシデントごとに異なる列が表示され、重大度、カテゴリ、アクティブなアラートの数、影響を受けたエンティティなどが表示されます。 列のセットをカスタマイズし、列名を選択して、一部の列でインシデント キューを並べ替えできます。 必要に応じてインシデント キューをフィルター処理することもできます。 使用可能なフィルターの完全な一覧については、「インシデントの優先順位 [付け」を参照してください](incident-queue.md#available-filters)。

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-queue.png" alt-text="セキュリティ ポータル内Microsoft 365インシデント" lightbox="../../media/first-incident-analyze/first-incident-analyze-queue.png":::

    この一連のインシデントに対してトリアージを実行する方法の 1 つの例は、より多くのユーザーとデバイスに影響を与えたインシデントに優先順位を付ける方法です。 この例では、7 台のデバイス、6 人のユーザー、および 2 つのメールボックスという最大の数のエンティティに影響を与えたため、インシデント ID 6769 に優先順位を付ける場合があります。 さらに、このインシデントには、ID ベースのアラートと資格情報の盗難の可能性を示す Microsoft Defender for Identity からのアラートが含まれていると思います。

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-high-impact.png" alt-text="セキュリティ ポータルでの影響の大きなインシデントの例を示すインシデント** Microsoft 365ページ" lightbox="../../media/first-incident-analyze/first-incident-analyze-high-impact.png":::

2. インシデント名の横にある円を選択して詳細を確認します。 右側にサイド ウィンドウが表示されます。このウィンドウには、トリアージをさらに支援する追加情報が含まれる。

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png" alt-text="セキュリティ ポータルのインシデント側ウィンドウの例を示す [インシデント] Microsoft 365ページ" lightbox="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png":::

   たとえば、攻撃者がインシデントのカテゴリに基づいて使用した [MITRE ATT&CK](https://attack.mitre.org/) の戦術を見て、攻撃者が盗まれた資格情報を使用し、コマンドと制御を確立し、横方向の動きを実行し、一部のデータを引き出したため、このインシデントの優先順位を設定できます。 これらのアクションは、攻撃者が既にネットワークに深く入り込み、機密情報を盗まれた可能性を示唆しています。

   さらに、組織がゼロトラスト フレームワークを実装している場合は、資格情報アクセスを優先順位付けする価値のある重要なセキュリティ違反と見なします。

   サイド ウィンドウを下にスクロールすると、影響を受け取る特定のエンティティ (ユーザー、デバイス、メールボックスなど) が表示されます。 各デバイスの露出レベルと、影響を受けるメールボックスの所有者を確認できます。

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png" alt-text="インシデント側ウィンドウの詳細" lightbox="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png":::

3. サイド ウィンドウをさらに下に移動すると、関連付けられたアラートを確認できます。 Microsoft 365 Defenderアラートの相関関係を 1 つのインシデントに既に実行し、攻撃の修復に費やした時間とリソースを節約できます。 アラートは疑わしいため、ネットワーク上に攻撃者が存在する可能性のある悪意のあるシステム イベントが発生する可能性があります。

   この例では、87 個の個別のアラートが 1 つのセキュリティ インシデントの一部と判断されました。 すべてのアラートを表示して、攻撃の実行方法を簡単に確認できます。

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png" alt-text="セキュリティ ポータルのインシデント側ウィンドウMicrosoft 365通知" lightbox="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png":::

## <a name="analyze-your-first-incident"></a>最初のインシデントを分析する

アラートを囲むコンテキストを理解するのも同様に重要です。 多くの場合、アラートは 1 つの独立したイベントではありません。 同時に発生していない可能性があるプロセス、コマンド、およびアクションのチェーンがあります。 そのため、アナリストは、アラートのコンテキストを理解するために、デバイスのタイムラインで不審なエンティティの最初と最後のアクティビティを探す必要があります。

データの読み取りおよび分析には、Microsoft 365 Defender方法が複数ありますが、アナリストの最後の目標は、インシデントに可能な限り迅速に対応することです。 このMicrosoft 365 Defender業界をリードする自動調査と対応機能を通じて、平均修復時間 [(MTTR)](https://www.microsoft.com/security/blog/2020/05/04/lessons-learned-microsoft-soc-part-3c/) を[](m365d-autoir.md)大幅に短縮することができますが、手動分析が必要な場合は常に存在します。

次に例を示します:

1. トリアージの優先度が決定された後、アナリストはインシデント名を選択して詳細な分析を開始します。 このページには、 **分析を支援** するタブにデータが表示されるインシデントの概要が表示されます。 [アラート **] タブ** の下に、アラートの種類が表示されます。 アナリストは、各アラートをクリックして、それぞれの検出ソースをドリルダウンできます。

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png" alt-text="インシデントの [概要] タブ" lightbox="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png":::

    各検出ソースがカバーするドメインに関するクイック ガイドについては、この記事の [「Detect](#detection-by-microsoft-365-defender) 」セクションを参照してください。

2. [アラート **] タブ** から検出ソースにピボットして、より詳細な調査と分析を実行できます。 たとえば、検出元がアナリストに対応するアラート ページに移動する場合に、[Microsoft Defender for Cloud Apps でマルウェア検出] を選択します。

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-select-alert.png" alt-text="インシデントのアラートを選択する例を示す [インシデント] ページ。" lightbox="../../media/first-incident-analyze/first-incident-analyze-select-alert.png":::

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png" alt-text="Microsoft Defender for Cloud Apps の対応するページ" lightbox="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png":::

3. この例をさらに調査するには、ページの下部までスクロールして、影響を受ける **ユーザーを表示します**。 マルウェア検出を取り巻くアクティビティとコンテキストを表示するには、Annette Hill のユーザー ページを選択します。

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-page.png" alt-text="ユーザー ページ" lightbox="../../media/first-incident-analyze/first-incident-analyze-user-page.png":::

4. ユーザー ページには、TOR ネットワーク IP アドレスアラートからの危険なサインインから始まるイベントが時系列 *に一覧表示* されます。 アクティビティの疑いは、組織がビジネスを行う方法の性質によって異なりますが、ほとんどの場合、ユーザーが匿名で Web を閲覧できるネットワークである Onion Router (TOR) を企業環境で使用すると、通常のオンライン操作では非常に可能性が低く、不要と見なされる可能性があります。

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png" alt-text="ユーザーのイベントの時系列リスト" lightbox="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png":::

5. 各アラートを選択して、アクティビティの詳細を取得できます。 たとえば、[ **Tor IP アドレス] アラートから [** アクティビティ] を選択すると、そのアラートの独自のページに移動します。 Annette は、Office 365管理者であり、管理者特権を示し、ソース インシデントが機密情報へのアクセスにつながった可能性があります。

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" alt-text="Microsoft Defender for Cloud Apps のアラートの詳細" lightbox="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" :::

6. 他のアラートを選択すると、攻撃の完全な画像を取得できます。

## <a name="next-step"></a>次のステップ

:::image type="content" source="../../media/first-incident-overview/first-incident-path-step2.png" alt-text="[最初のインシデントに対応する] ページの [修復] オプション" lightbox="../../media/first-incident-overview/first-incident-path-step2.png":::

インシデントを [修復する方法について学習します](first-incident-remediate.md)。

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの調査](investigate-incidents.md)
- [インシデントの管理](manage-incidents.md)
