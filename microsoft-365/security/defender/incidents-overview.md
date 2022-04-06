---
title: Microsoft 365 Defenderを使用したインシデント対応
description: Microsoft 365 Defender ポータルで、デバイス、ユーザー、メールボックス間で発生したインシデントを調査します。
keywords: インシデント, アラート, 調査, 分析, 応答, 相関関係, 攻撃, マシン, デバイス, ユーザー, ID, ID, メールボックス, 電子メール, 365, Microsoft, m365, インシデント対応, サイバー攻撃
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
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 15b540f9993e8f2163f464379aca9496bec4cca7
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665384"
---
# <a name="incident-response-with-microsoft-365-defender"></a>Microsoft 365 Defenderを使用したインシデント対応

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

> Microsoft 365 Defender を体験しますか? [ラボ環境で評価](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)、または[運用でパイロット プロジェクトを実行](m365d-pilot.md?ocid=cx-evalpilot)することができます。
>

Microsoft 365 Defenderのインシデントは、攻撃のストーリーを構成する相関アラートと関連データのコレクションです。

Microsoft 365 サービスおよびアプリは、疑わしい、または悪意のあるイベントやアクティビティを検出した場合にアラートを作成します。 個々のアラートは、完了した攻撃、または進行中の攻撃に関する貴重な手がかりとなります。 ただし、攻撃は通常、デバイス、ユーザー、メールボックスなどの異なる種類のエンティティに対抗してさまざまな技術を採用しています。 その結果、テナント内の複数のエンティティに複数のアラートが表示されます。

個々のアラートを組み合わせて攻撃に関する分析情報を取得するのは困難で時間がかかるため、Microsoft 365 Defender はアラートとその関連情報を自動的にインシデントに集約します。

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="エンティティからインシデントにイベントを関連付けるMicrosoft 365 Defender方法。" lightbox="../../media/incidents-overview/incidents.png":::

Microsoft 365 Defender (4 分) のインシデントの概要をご覧ください。

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

関連するアラートをインシデントにグループ化することで、攻撃を包括的に表示します。 たとえば、次が表示されます。

- 攻撃の開始場所。
- 使用された戦術。
- 攻撃がテナントにどの程度まで侵入したか。
- 攻撃の範囲 (影響を受けたデバイス、ユーザー、メールボックスの数など)。
- 攻撃に関連付けられているすべてのデータ。

[有効に](m365d-enable.md)した場合、Microsoft 365 Defenderは自動化と人工知能を使用してアラートを[自動的に調査および解決](m365d-autoir.md)できます。 また、追加の修復手順を実行して攻撃を解決することもできます。

## <a name="incidents-and-alerts-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルでのインシデントとアラート

Microsoft 365 Defender ポータルのクイック起動で **インシデント&アラート>インシデントからインシデント** を管理 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">します</a>。 次に例を示します。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Microsoft 365 Defender ポータルの [インシデント] ページ。" lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

インシデント名を選択すると、インシデントの概要が表示され、追加情報を含むタブへのアクセスが提供されます。 次に例を示します。

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 Defender ポータルのインシデントの [概要] ページ" lightbox="../../media/incidents-overview/incidents-ss-incident-summary.png":::

インシデントの追加タブは次のとおりです。

- アラート

  インシデントに関連するすべてのアラートとその情報。

- デバイス

  インシデントの一部または関連として識別されたすべてのデバイス。

- ユーザー

  インシデントの一部または関連として識別されたすべてのユーザー。

- メールボックス

  インシデントの一部または関連として識別されたすべてのメールボックス。

- 調査

  インシデントのアラートによってトリガーされるすべての [自動調査](m365d-autoir.md) 。

- 証拠と応答

  インシデントのアラートでサポートされているすべてのイベントと疑わしいエンティティ。

- Graph (プレビュー)

  攻撃の一部であるさまざまな疑わしいエンティティと、ユーザー、デバイス、メールボックスなどの関連資産を接続する攻撃を視覚的に表したものです。

インシデントとそのデータの関係と、Microsoft 365 Defender ポータルのインシデントのタブを次に示します。

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Microsoft 365 Defender ポータルのインシデントとそのデータとインシデントのタブとの関係。" lightbox="../../media/incidents-overview/incidents-security-center.png":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>Microsoft 365 Defenderのインシデント対応ワークフローの例

Microsoft 365 Defender ポータルを使用してMicrosoft 365のインシデントに対応するためのワークフローの例を次に示します。

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Microsoft 365 Defender ポータルのインシデント対応ワークフローの例。" lightbox="../../media/incidents-overview/incidents-example-workflow.png":::

継続的に、インシデント キュー内で、分析と解決優先度が最も高いインシデントを特定し、対応の準備をします。 これは、次を組み合わせたものです：

- インシデント キューのフィルター処理と並べ替えを通じて、最も優先度の高いインシデントを決定するための[トリアージ](incident-queue.md)。
- タイトルを変更し、アナリストに割り当て、タグとコメントを追加してインシデントを[管理](manage-incidents.md)する。

独自のインシデント対応ワークフローでは、次の手順を検討してください。

1. インシデントごとに、 [攻撃とアラートの調査と分析を](investigate-incidents.md)開始します。

   1. インシデントの概要を表示して、そのスコープと重大度、および [**概要**] タブと **[Graph** (プレビュー)] タブで影響を受けるエンティティを確認します。

   1. アラートの分析を開始し、[ **アラート** ] タブで配信元、スコープ、重大度を理解します。

   1. 必要に応じて、[デバイス]、[ユーザー]、[メールボックス] タブで、影響を受けた **デバイス**、 **ユーザー**、メールボックスに関 **する情報を** 収集します。

   1. Microsoft 365 Defenderが [調査] タブで [一部のアラートを自動的に解決した](m365d-autoir.md)方法 **を確認** します。

   1. 必要に応じて、[ **証拠と応答** ] タブの詳細については、インシデントのデータ セットの情報を使用します。

2. 分析後または分析中に、封じ込めを実行して、攻撃やセキュリティ上の追加の影響を軽減し、脅威を根絶する。

3. 可能な限り、テナント リソースをインシデントの前の状態に復元して攻撃から回復する。

4. インシデントを[解決](manage-incidents.md#resolve-an-incident)し、インシデント後の学習に時間がかかります。

   - 攻撃の種類とその影響を理解する。
   - セキュリティ攻撃の傾向について [、Threat Analytics](threat-analytics.md) とセキュリティ コミュニティの攻撃を調査します。
   - インシデントの解決に使用したワークフローを思い出し、必要に応じて標準のワークフロー、プロセス、ポリシー、プレイブックを更新する。
   - セキュリティ構成の変更が必要かどうかを判断し、実装する。

セキュリティ分析を初めて使用する場合は、 [最初のインシデントへの対応に関する概要](incidents-overview.md) を参照して追加情報を入手し、インシデントの例を詳しく説明します。

Microsoft 製品全体のインシデント対応の詳細については、 [この記事](/security/compass/incident-response-overview)を参照してください。

## <a name="example-security-operations-for-microsoft-365-defender"></a>Microsoft 365 Defenderのセキュリティ操作の例

Microsoft 365 Defenderのセキュリティ操作 (SecOps) の例を次に示します。

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Microsoft 365 Defenderのセキュリティ操作の例" lightbox="../../media/incidents-overview/incidents-example-operations.png":::

毎日のタスクには次のものが含まれます。

- インシデント[の管理](manage-incidents.md)
- アクション センターでの [自動調査と対応 (AIR)](m365d-action-center.md) アクションの確認
- 最新の [Threat Analytics の](threat-analytics.md)確認
- インシデントへの[対応](investigate-incidents.md)

毎月のタスクには、次のものが含まれます。

- [AIR 設定](m365d-configure-auto-investigation-response.md)の確認
- [セキュリティ スコア](microsoft-secure-score-improvement-actions.md)と[脅威&脆弱性管理の](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)確認
- IT セキュリティ管理チェーンへのレポート

四半期ごとのタスクには、最高情報セキュリティ責任者 (CISO) に対するセキュリティ結果のレポートとブリーフィングを含めることができます。

年間のタスクには、スタッフ、システム、およびプロセスをテストするための重大なインシデントまたは違反の演習の実施が含まれる場合があります。

毎日、毎月、四半期、年間のタスクを使用して、プロセス、ポリシー、およびセキュリティ構成を更新または調整できます。

詳細については、「[Microsoft 365 Defenderをセキュリティ操作に統合する](integrate-microsoft-365-defender-secops.md)」を参照してください。

### <a name="secops-resources-across-microsoft-products"></a>Microsoft 製品全体の SecOps リソース

Microsoft 製品全体の SecOps の詳細については、次のリソースを参照してください。

- [Capabilities](/security/compass/security-operations-capabilities)
- [ベスト プラクティス](/security/compass/security-operations)
- [ビデオとスライド](/security/compass/security-operations-videos-and-decks)

## <a name="get-incident-notifications-by-email"></a>電子メールでインシデント通知を取得する

新しいインシデントや既存のインシデントの更新に関するメールをスタッフに通知するMicrosoft 365 Defenderを設定できます。 次に基づいて通知を受け取ることを選択できます。

- インシデントの重大度。
- デバイス グループ。
- インシデントごとの最初の更新時のみ。

電子メール通知には、インシデントの名前、重大度、カテゴリなどのインシデントに関する重要な詳細が含まれています。 インシデントに直接移動し、すぐに分析を開始することもできます。 詳細については、「インシデントの [調査](investigate-incidents.md)」を参照してください。

電子メール通知で受信者を追加または削除できます。 新しい受信者は、インシデントの追加後に通知を受け取ります。

> [!NOTE]
> 電子メール通知設定を構成するには、[ **セキュリティ設定の管理** ] アクセス許可が必要です。 基本的なアクセス許可管理を使用するように選択した場合、セキュリティ管理者ロールまたはグローバル管理者ロールを持つユーザーは、電子メール通知を構成できます。 <br> <br>
同様に、組織でロールベースのアクセス制御 (RBAC) を使用している場合は、管理が許可されているデバイス グループに基づいてのみ通知を作成、編集、削除、および受信できます。

### <a name="create-a-rule-for-email-notifications"></a>電子メール通知のルールを作成する

次の手順に従って新しいルールを作成し、メール通知設定をカスタマイズします。

1. ナビゲーション ウィンドウで、**インシデント メール通知設定 > Microsoft 365 Defender >** 選択します。
2. [ **項目の追加]** を選択します。
3. [ **基本]** ページで、ルール名と説明を入力し、[ **次へ**] を選択します。
4. [ **通知の設定]** ページで、次を構成します。
    - **アラートの重大度** - インシデント通知をトリガーするアラートの重大度を選択します。 たとえば、重大度の高いインシデントについてのみ通知する場合は、[ **高**] を選択します。
    - **デバイス グループ スコープ** - すべてのデバイス グループを指定するか、テナント内のデバイス グループの一覧から選択できます。
    - **インシデントごとに最初に発生した 場合にのみ通知する** - 他の選択内容に一致する最初のアラートについてのみ通知する場合に選択します。 インシデントに関連するその後の更新やアラートでは、追加の通知は送信されません。
    - [**メールに組織名を含める**] - 組織名をメール通知に表示する場合に選択します。
    - [**テナント固有のポータル リンクを含める**] - 特定の Microsoft 365 テナントにアクセスするため、メール通知にテナント ID を含むリンクを追加する場合、選択してください。

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="Microsoft 365 Defender ポータルのインシデント メール通知の [通知の設定] ページ。" lightbox="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png":::

5. **[次へ]** を選択します。 [ **受信者]** ページで、インシデント通知を受信する電子メール アドレスを追加します。 新しい各メール アドレスを入力した後、[ **追加]** を選択します。 通知をテストし、受信者が受信トレイで受信することを確認するには、[ **テストメールの送信**] を選択します。
6. **[次へ]** を選択します。 [ **ルールの確認** ] ページで、ルールの設定を確認し、[ **ルールの作成**] を選択します。 受信者は、設定に基づいて電子メールでインシデント通知の受信を開始します。

既存のルールを編集するには、ルールの一覧からルールを選択します。 ルール名が表示されたウィンドウで、[ **ルールの編集]** を選択し、[ **基本**]、[ **通知の設定]**、[ **受信者]** ページで変更を行います。

ルールを削除するには、ルールの一覧からルールを選択します。 ルール名が表示されたウィンドウで、[削除] を選択 **します**。

## <a name="training-for-security-analysts"></a>セキュリティ アナリスト向けトレーニング

Microsoft Learn のこのラーニング モジュールを使用して、Microsoft 365 Defenderを使用してインシデントとアラートを管理する方法を理解します。

|トレーニング: |Microsoft 365 Defender を使用してインシデントを調査する|
|---|---|
|![Microsoft 365 Defenderトレーニング アイコンを使用してインシデントを調査します。](../../media/incidents-overview/m365-defender-address-security-investigation.svg)| Microsoft 365 Defender複数のサービスの脅威データを統合し、AI を使用してインシデントやアラートに組み合わせます。 インシデントからその管理までの時間を最小限に抑え、その後の対応と解決の方法について説明します。 <p> 27 分 - 6 単位 |

> [!div class="nextstepaction"]
> [スタート>](/learn/modules/defender-investigate-incidents/)

## <a name="next-steps"></a>次の手順

セキュリティ チームのエクスペリエンス レベルまたはロールに基づいて、一覧表示されている手順を使用します。

### <a name="experience-level"></a>エクスペリエンス レベル

この表に従って、セキュリティ分析とインシデント対応に関するレベルのエクスペリエンスを確認します。

| レベル | 手順 |
|:-------|:-----|
| **New** | <ol><li> 最初の[インシデントに対応するチュートリアル](first-incident-overview.md)を参照して、Microsoft 365 Defender ポータルで一般的な分析、修復、インシデント後のレビューの一般的なプロセスのガイド付きツアーを、攻撃の例と共に入手してください。 </li><li> 重大度やその他の要因に基づいて [、優先順位を](incident-queue.md) 付ける必要があるインシデントを確認します。 </li><li> [インシデント管理ワークフローに](manage-incidents.md)基づいて、名前の変更、割り当て、分類、タグとコメントの追加を含むインシデントを管理します。</li></ol> |
| **経験** | <ol><li> Microsoft 365 Defender ポータルの [インシデント] ページから **インシデント** キューを概要します。 グループ プロフィールでは次の操作ができます。 </li> <ul><li> 重大度やその他の要因に基づいて [、優先順位を](incident-queue.md) 付ける必要があるインシデントを確認します。 </li><li> [インシデント管理ワークフローに](manage-incidents.md)基づいて、名前の変更、割り当て、分類、タグとコメントの追加を含むインシデントを管理します。 </li><li> インシデント [の調査](investigate-incidents.md) を実行します。 </li></ul> </li><li> [脅威分析](threat-analytics.md)を使用して、新たな脅威を追跡し、対応します。 </li><li>  [高度な脅威](advanced-hunting-overview.md)ハンティングを使用して、脅威をプロアクティブに探します。 </li><li> フィッシング、パスワード スプレー、アプリの同意付与攻撃に関する詳細なガイダンスについては、次の [インシデント対応プレイブック](/security/compass/incident-response-playbooks) を参照してください。 </li></ol> |

### <a name="security-team-role"></a>セキュリティ チームロール

セキュリティ チームの役割に基づいて、次の表に従います。

| 役割 | 手順 |
|---|---|
| インシデント レスポンダー (階層 1) | Microsoft 365 Defender ポータルの [インシデント] ページから **インシデント** キューを概要します。 グループ プロフィールでは次の操作ができます。 <ul><li> 重大度やその他の要因に基づいて [、優先順位を](incident-queue.md) 付ける必要があるインシデントを確認します。 </li><li> [インシデント管理ワークフローに](manage-incidents.md)基づいて、名前の変更、割り当て、分類、タグとコメントの追加を含むインシデントを管理します。 </li></ul> |
| セキュリティ調査担当者またはアナリスト (階層 2) | <ol><li> Microsoft 365 Defender ポータルの [**インシデント]** ページからインシデントの [調査](investigate-incidents.md)を実行します。 </li><li> フィッシング、パスワード スプレー、アプリの同意付与攻撃に関する詳細なガイダンスについては、次の [インシデント対応プレイブック](/security/compass/incident-response-playbooks) を参照してください。 </li></ol> |
| 高度なセキュリティ アナリストまたは脅威の捜索者 (階層 3) | <ol><li>Microsoft 365 Defender ポータルの [**インシデント]** ページからインシデントの [調査](investigate-incidents.md)を実行します。 </li><li> [脅威分析](threat-analytics.md)を使用して、新たな脅威を追跡し、対応します。 </li><li> [高度な脅威](advanced-hunting-overview.md)ハンティングを使用して、脅威をプロアクティブに探します。 </li><li> フィッシング、パスワード スプレー、アプリの同意付与攻撃に関する詳細なガイダンスについては、次の [インシデント対応プレイブック](/security/compass/incident-response-playbooks) を参照してください。 |
| SOC マネージャー | [Microsoft 365 Defenderをセキュリティ オペレーション センター (SOC) に統合する](integrate-microsoft-365-defender-secops.md)方法について説明します。 |
