---
title: 手順 1. 最初のインシデントをトリアージして分析する
description: Microsoft 365 Defenderで最初のインシデントの分析をトリアージして開始する方法。
keywords: インシデント, アラート, 調査, 相関関係, 攻撃, マシン, デバイス, ユーザー, ID, ID, メールボックス, 電子メール, 365, microsoft, m365, インシデント対応, サイバー攻撃
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
- m365solution-firstincident
- highpri
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b930181681d5849af4e99bf41d2b8643329175a5
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482232"
---
# <a name="step-1-triage-and-analyze-your-first-incident"></a>手順 1。 最初のインシデントをトリアージして分析する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

組織の基準に従ってセキュリティ対策の確立、実装、保守に時間を費やすと、セキュリティ のリスクと脅威を迅速に特定するのに役立つセキュリティ ソリューションを設定できます。 Microsoft 365 Defenderを使用すると、単一ウィンドウのエクスペリエンスを通じてインシデントを検出、トリアージ、および調査できます。ここでは、タイムリーな意思決定に必要な情報を見つけることができます。

セキュリティ インシデントが検出されると、インシデントやインシデントを他のインシデントよりもトリアージまたは優先順位付けするために必要な詳細がMicrosoft 365 Defenderに表示されます。 優先順位付けを決定した後、アナリストは自分に割り当てられたケースの調査に重点を置くことができます。

## <a name="detection-by-microsoft-365-defender"></a>Microsoft 365 Defenderによる検出

Microsoft 365 Defenderは、複数の Microsoft セキュリティ プラットフォームからアラートとイベントを検出ソースとして受信し、悪意のあるアクティビティの全体像とコンテキストを作成します。 考えられる検出ソースは次のとおりです。

- [Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md)は、Microsoft Security Graph を使用して Microsoft Defender ウイルス対策とクラウド対応の高度な脅威保護を使用するエンドポイント検出および応答ソリューション (EDR) です。 Defender for Endpoint は、予防保護、違反後の検出、自動調査、および対応のための統合プラットフォームです。 エンドポイントをサイバー脅威から保護し、高度な攻撃とデータ侵害を検出し、セキュリティ インシデントを自動化し、セキュリティ体制を向上させます。
- [Microsoft Defender for Identity](/defender-for-identity/what-is)は、オンプレミスの Active Directory Domain Services (AD DS) シグナルを使用して、組織に向けられた高度な脅威、侵害された ID、悪意のあるインサイダー アクションを識別、検出、調査するクラウドベースのセキュリティ ソリューションです。
- [Microsoft Defender for Cloud Apps](/cloud-app-security/)は、エンタープライズ ユーザーと使用するクラウド リソースの間のアクセスをリアルタイムで仲介するゲートキーパーとして機能します。ユーザーが配置されている場所と、使用しているデバイスに関係なく。
- [Microsoft Defender for Office 365は、](../office-365-security/overview.md)電子メール メッセージ、リンク (URL)、およびコラボレーション ツールの悪意のある脅威から組織を保護します。
- [Azure Security Center](/azure/security-center/security-center-introduction)は、データ センターのセキュリティ体制を強化し、クラウドとオンプレミスのハイブリッド ワークロード全体で高度な脅威保護を提供する統合インフラストラクチャ セキュリティ管理システムです。


Microsoft 365 Defenderでは、これらのさまざまな検出ソースからのアラートを関連付けることで[、インシデント](incidents-overview.md)が識別されます。 リソースを文字列化したり、複数のアラートをそれぞれのインシデントに区別したりする代わりに、Microsoft 365 Defenderのインシデント キューからすぐに開始できます。 この方法を使用すると、エンドポイント、ID、電子メール、アプリケーション間で効率的な方法でインシデントをトリアージし、攻撃による被害を軽減できます。

## <a name="triage-your-incidents"></a>インシデントをトリアージする

Microsoft 365 Defenderのインシデント対応は、組織の推奨される優先順位付け方法を使用してインシデントの一覧をトリアージすると開始されます。 トリアージとは、インシデントに重要度または緊急度のレベルを割り当てることを意味し、調査する順序を決定します。

Microsoft 365 Defenderで優先順位を付けるインシデントを決定するための便利なサンプル ガイドは、「*重大度 + 影響 = 優先度」* の数式で要約できます。

- **重大度** は、Microsoft 365 Defenderおよびその統合セキュリティ コンポーネントによって指定されるレベルです。
- **影響** は組織によって決定され、影響を受けるユーザー、デバイス、影響を受けるサービス (またはその組み合わせ)、さらにはアラートの種類のしきい値の数が一般的に含まれますが、これらに限定されません。

その後、アナリストは、組織によって設定された **優先度** 条件に基づいて調査を開始します。

インシデントの優先順位付けは、組織によって異なる場合があります。 また、NIST では、インシデントの機能的および情報的影響と回復性を考慮することをお勧めします。

トリアージに対する 1 つの方法を次に示します。

1. [インシデント](incidents-overview.md) ページに移動してトリアージを開始します。 ここでは、組織に影響を与えるインシデントの一覧を確認できます。 既定では、最新のインシデントから最も古いインシデントに配置されます。 ここから、重大度、カテゴリ、アクティブなアラートの数、影響を受けたエンティティなどを示すインシデントごとに異なる列を表示することもできます。 列のセットをカスタマイズし、列名を選択して、これらの列の一部でインシデント キューを並べ替えることができます。 必要に応じて、インシデント キューをフィルター処理することもできます。 使用可能なフィルターの完全な一覧については、「 [インシデントの優先順位付け](incident-queue.md#available-filters)」を参照してください。

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-queue.png" alt-text="Microsoft 365 セキュリティ ポータルのインシデント" lightbox="../../media/first-incident-analyze/first-incident-analyze-queue.png":::

    この一連のインシデントに対してトリアージを実行する方法の 1 つの例は、より多くのユーザーとデバイスに影響を与えたインシデントに優先順位を付ける方法です。 この例では、インシデント ID 6769 が最も多くのエンティティ (7 つのデバイス、6 人のユーザー、2 つのメールボックス) に影響を与えたため、インシデント ID 6769 に優先順位を付ける場合があります。 さらに、インシデントには、id ベースのアラートと資格情報の盗難の可能性を示すMicrosoft Defender for Identityからのアラートが含まれているようです。

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-high-impact.png" alt-text="Microsoft 365 セキュリティ ポータルでの影響の大きいインシデントの例を示すインシデント** ページ" lightbox="../../media/first-incident-analyze/first-incident-analyze-high-impact.png":::

2. インシデント名の横にある円を選択して、詳細を確認します。 右側にサイド ウィンドウが表示されます。このウィンドウには、トリアージをさらに支援する追加情報が含まれています。

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png" alt-text="Microsoft 365 セキュリティ ポータルのインシデント側ウィンドウの例を示す [インシデント] ページ" lightbox="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png":::

   たとえば、攻撃者がインシデントのカテゴリに基づいて使用した [MITRE ATT&CK](https://attack.mitre.org/) 戦術を調べると、攻撃者は盗難された資格情報を使用し、コマンドと制御を確立し、横移動を実行し、一部のデータを流出したため、このインシデントに優先順位を付けることができます。 これらのアクションは、攻撃者が既にネットワークに深く侵入し、機密情報を盗んだ可能性があることを示唆しています。

   さらに、組織がゼロ トラスト フレームワークを実装している場合は、資格情報アクセスを優先順位付けする価値のある重要なセキュリティ違反と見なします。

   サイド ウィンドウを下にスクロールすると、影響を受ける特定のエンティティ (ユーザー、デバイス、メールボックスなど) が表示されます。 各デバイスの公開レベルと、影響を受けるメールボックスの所有者を確認できます。

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png" alt-text="インシデント側ウィンドウの詳細" lightbox="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png":::

3. サイド ウィンドウのさらに下には、関連するアラートが表示されます。 Microsoft 365 Defenderは、既にアラートを 1 つのインシデントに関連付けて実行しており、攻撃の修復に費やす時間とリソースを節約できます。 アラートは疑わしいため、ネットワーク上に攻撃者が存在することを示唆する悪意のあるシステム イベントである可能性があります。

   この例では、87 個の個別のアラートが 1 つのセキュリティ インシデントの一部であると判断されました。 すべてのアラートを表示して、攻撃がどのように行ったかを簡単に確認できます。

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png" alt-text="Microsoft 365 セキュリティ ポータルのインシデント側ウィンドウのアラート" lightbox="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png":::

## <a name="analyze-your-first-incident"></a>最初のインシデントを分析する

アラートを囲むコンテキストを理解することは、同様に重要です。 多くの場合、アラートは 1 つの独立したイベントではありません。 同時に発生していない可能性があるプロセス、コマンド、およびアクションのチェーンが作成されます。 そのため、アナリストは、アラートのコンテキストを理解するために、デバイスのタイムラインで疑わしいエンティティの最初と最後のアクティビティを探す必要があります。

Microsoft 365 Defenderを使用してデータを読み取り、分析する方法は複数ありますが、アナリストの最終目標は、インシデントにできるだけ早く対応することです。 Microsoft 365 Defenderは、業界をリードする[自動調査と対応](m365d-autoir.md)機能を通じて[平均修復時間 (MTTR)](https://www.microsoft.com/security/blog/2020/05/04/lessons-learned-microsoft-soc-part-3c/) を大幅に短縮できますが、常に手動分析が必要な場合があります。

次に例を示します:

1. トリアージの優先順位が決定されると、アナリストはインシデント名を選択して詳細な分析を開始します。 このページには、分析を支援するためにデータがタブに表示される **インシデントの概要** が表示されます。 [ **アラート** ] タブに、アラートの種類が表示されます。 アナリストは、各アラートをクリックして、それぞれの検出ソースにドリルダウンできます。

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png" alt-text="インシデントの [概要] タブ" lightbox="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png":::

    各検出ソースの対象となるドメインに関するクイック ガイドについては、この記事の [「検出](#detection-by-microsoft-365-defender) 」セクションを参照してください。

2. [ **アラート** ] タブから、検出ソースにピボットして、より詳細な調査と分析を行うことができます。 たとえば、検出ソースとしてMicrosoft Defender for Cloud Appsを使用してマルウェア検出を選択すると、アナリストは対応するアラート ページに移動します。

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-select-alert.png" alt-text="インシデントのアラートを選択する例を示す [インシデント] ページ。" lightbox="../../media/first-incident-analyze/first-incident-analyze-select-alert.png":::

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png" alt-text="Microsoft Defender for Cloud Apps内の対応するページ" lightbox="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png":::

3. この例をさらに詳しく調べるには、ページの下部までスクロールして **、影響を受けたユーザー** を表示します。 マルウェア検出を取り巻くアクティビティとコンテキストを表示するには、AnnetteHill のユーザー ページを選択します。

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-page.png" alt-text="ユーザー ページ" lightbox="../../media/first-incident-analyze/first-incident-analyze-user-page.png":::

4. ユーザー ページには、 *TOR ネットワーク IP アドレス アラートからの危険なサインインから* 始まるイベントが時系列で一覧表示されます。 アクティビティの疑わしい点は組織がビジネスを行う方法の性質に依存しますが、ほとんどの場合、ユーザーが匿名で Web を閲覧できるネットワークである The Onion ルーター (TOR) を使用すると、エンタープライズ環境では通常のオンライン操作では非常に可能性が低く、不要と見なされる場合があります。

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png" alt-text="ユーザーのイベントの時系列リスト" lightbox="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png":::

5. 各アラートを選択して、アクティビティの詳細を取得できます。 たとえば、 **Tor IP アドレス アラートから [アクティビティ** ] を選択すると、そのアラートの独自のページが表示されます。 Annette はOffice 365の管理者であり、特権の昇格と、ソース インシデントが機密情報へのアクセスにつながった可能性があることを示します。

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" alt-text="Microsoft Defender for Cloud Appsのアラートの詳細" lightbox="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" :::

6. 他のアラートを選択すると、攻撃の全体像を把握できます。

## <a name="next-step"></a>次のステップ

:::image type="content" source="../../media/first-incident-overview/first-incident-path-step2.png" alt-text="[最初のインシデントに対応する] ページの [修復] オプション" lightbox="../../media/first-incident-overview/first-incident-path-step2.png":::

[インシデントを修復](first-incident-remediate.md)する方法について説明します。

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの調査](investigate-incidents.md)
- [インシデントの管理](manage-incidents.md)
