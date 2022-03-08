---
title: インシデント対応とMicrosoft 365 Defender
description: ポータル内のデバイス、ユーザー、メールボックス間で発生したインシデントMicrosoft 365 Defenderします。
keywords: インシデント、アラート、調査、分析、応答、相関関係、攻撃、コンピューター、デバイス、ユーザー、ID、ID、メールボックス、電子メール、365、microsoft、m365、インシデント対応、サイバー攻撃
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
ms.openlocfilehash: 25cdc0610f11d1bcd7e8c27faa1cdc9453677d51
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320881"
---
# <a name="incident-response-with-microsoft-365-defender"></a>インシデント対応とMicrosoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

> Microsoft 365 Defender を体験しますか? [ラボ環境で評価](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)、または[運用でパイロット プロジェクトを実行](m365d-pilot.md?ocid=cx-evalpilot)することができます。
>

インシデントは、Microsoft 365 Defenderのストーリーを構成する関連付けられたアラートと関連付けられたデータのコレクションです。 

Microsoft 365 サービスおよびアプリは、疑わしい、または悪意のあるイベントやアクティビティを検出した場合にアラートを作成します。 個々のアラートは、完了した攻撃、または進行中の攻撃に関する貴重な手がかりとなります。 ただし、攻撃は通常、デバイス、ユーザー、メールボックスなどの異なる種類のエンティティに対抗してさまざまな技術を採用しています。 その結果、テナント内の複数のエンティティに複数のアラートが表示されます。 

個々のアラートを組み合わせて攻撃に関する分析情報を取得するのは困難で時間がかかるため、Microsoft 365 Defender はアラートとその関連情報を自動的にインシデントに集約します。

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="エンティティMicrosoft 365 Defenderイベントをインシデントに関連付ける方法。" lightbox="../../media/incidents-overview/incidents.png":::

この短いインシデントの概要については、Microsoft 365 Defender (4 分) をご覧ください。

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

関連するアラートをインシデントにグループ化することで、攻撃を包括的に表示します。 たとえば、次が表示されます。

- 攻撃の開始場所。
- 使用された戦術。
- 攻撃がテナントにどの程度まで侵入したか。
- 攻撃の範囲 (影響を受けたデバイス、ユーザー、メールボックスの数など)。 
- 攻撃に関連付けられているすべてのデータ。

有効[にすると、](m365d-enable.md)自動化Microsoft 365 Defender[人工知能を使用して](m365d-autoir.md)アラートを自動的に調査および解決できます。 また、追加の修復手順を実行して攻撃を解決することもできます。 

## <a name="incidents-and-alerts-in-the-microsoft-365-defender-portal"></a>ポータル内のインシデントとMicrosoft 365 Defender

インシデント ポータルのクイック 起動時に&**アラート>** インシデントからインシデントを <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defenderします</a>。 次に例を示します。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="ポータルの [インシデント] ページMicrosoft 365 Defenderします。" lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

インシデント名を選択すると、インシデントの概要が表示され、追加情報を含むタブにアクセスできます。 例を次に示します。

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="ポータル内のインシデントの概要ページMicrosoft 365 Defender例" lightbox="../../media/incidents-overview/incidents-ss-incident-summary.png":::

インシデントの追加タブは次のとおりです。

- アラート 

  インシデントとその情報に関連するすべてのアラート。

- デバイス

  インシデントの一部または関連付けとして識別されたすべてのデバイス。

- ユーザー

  インシデントの一部または関連付けとして識別されたすべてのユーザー。

- メールボックス

  インシデントの一部または関連付けとして識別されたすべてのメールボックス。

- 調査

  インシデント内 [のアラートによって](m365d-autoir.md) トリガーされる、すべての自動調査。

- 証拠と対応

  インシデントの通知でサポートされているイベントと疑わしいエンティティすべて。

- Graph (プレビュー)

  攻撃の一部であるさまざまな不審なエンティティと、ユーザー、デバイス、メールボックスなどの関連する資産を接続する攻撃の視覚的な表現。

インシデントとデータの関係と、インシデントポータルのインシデントのタブMicrosoft 365 Defenderします。

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="インシデントとそのデータと、ポータル内のインシデントのタブとのMicrosoft 365 Defenderします。" lightbox="../../media/incidents-overview/incidents-security-center.png":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>インシデント対応ワークフローの例Microsoft 365 Defender

次に、ポータルでインシデントに対応するワークフロー Microsoft 365例Microsoft 365 Defender示します。

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="インシデント対応ワークフローの例Microsoft 365。" lightbox="../../media/incidents-overview/incidents-example-workflow.png":::

継続的に、インシデント キュー内で、分析と解決優先度が最も高いインシデントを特定し、対応の準備をします。 これは、次を組み合わせたものです：

- [インシデント キューの](incident-queue.md) フィルター処理と並べ替えを通じて、優先度の高いインシデントを特定するトリアージ。
- [タイトルを](manage-incidents.md) 変更し、アナリストに割り当て、タグとコメントを追加してインシデントを管理します。

独自のインシデント対応ワークフローでは、次の手順を検討してください。

1. インシデントごとに、攻撃とアラート [の調査と分析を開始します](investigate-incidents.md)。
 
   1. インシデントの概要を表示して、そのスコープと重大度、および [概要] タブと [プレビュー **] (プレビュー**) タブで影響を受けるエンティティGraphを確認します。

   1. [アラート] タブを使用して、アラートの分析を開始して、発生元、スコープ、重大度 **を理解** します。

   1. 必要に応じて、[デバイス]、[ユーザー]、および [メールボックス] タブを使用して、影響を受け取ったデバイス、ユーザー、およびメールボックスに関する情報 **を収集** します。

   1. [調査] Microsoft 365 Defenderで、一 [部](m365d-autoir.md)のアラートが自動的に解決された方法 **について説明** します。
   
   1. 必要に応じて、インシデントのデータ セットの情報を使用して、[証拠と応答] タブを使用して詳細 **を確認** します。

2. 分析後または分析中に、封じ込めを実行して、攻撃やセキュリティ上の追加の影響を軽減し、脅威を根絶する。

3. 可能な限り、テナント リソースをインシデントの前の状態に復元して攻撃から回復する。

4. [インシデント](manage-incidents.md#resolve-an-incident) を解決し、インシデント後の学習に時間を取って、次の処理を行います。

   - 攻撃の種類とその影響を理解する。
   - [Threat Analytics とセキュリティ](threat-analytics.md) コミュニティの攻撃を調査して、セキュリティ攻撃の傾向を調査します。
   - インシデントの解決に使用したワークフローを思い出し、必要に応じて標準のワークフロー、プロセス、ポリシー、プレイブックを更新する。
   - セキュリティ構成の変更が必要かどうかを判断し、実装する。

セキュリティ分析を初めて使用する場合は、[](incidents-overview.md)最初のインシデントへの対応の概要を参照し、詳細については、「インシデントの例」を参照してください。

Microsoft 製品全体のインシデント対応の詳細については、この記事を [参照してください](/security/compass/incident-response-overview)。

## <a name="example-security-operations-for-microsoft-365-defender"></a>ユーザーのセキュリティ操作のMicrosoft 365 Defender

次に、セキュリティ操作 (SecOps) の例を示Microsoft 365 Defender。

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="ユーザーのセキュリティ操作のMicrosoft 365 Defender。" lightbox="../../media/incidents-overview/incidents-example-operations.png":::

毎日のタスクには、次のものが含まれます。

- [インシデントの](manage-incidents.md) 管理
- アクション センター [での自動調査と応答 (AIR)](m365d-action-center.md) アクションの確認
- 最新の脅威分析 [の確認](threat-analytics.md)
- [インシデントへの](investigate-incidents.md) 対応

毎月のタスクには、次のものが含まれます。

- AIR 設定 [の確認](m365d-configure-auto-investigation-response.md)
- セキュリティで保護 [されたスコア](microsoft-secure-score-improvement-actions.md) と [脅威の&の管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- IT セキュリティ管理チェーンへのレポート

四半期ごとに、最高情報セキュリティ責任者 (CISO) へのセキュリティ結果の報告とブリーフィングが含まれます。

年次タスクには、スタッフ、システム、およびプロセスをテストする重大なインシデントや違反の演習を実行できます。 

毎日、月次、四半期、年次のタスクを使用して、プロセス、ポリシー、およびセキュリティ構成を更新または調整できます。

詳細[については、「Microsoft 365 Defenderをセキュリティ操作に統合する](integrate-microsoft-365-defender-secops.md)」を参照してください。

### <a name="secops-resources-across-microsoft-products"></a>Microsoft 製品全体の SecOps リソース

Microsoft 製品全体の SecOps の詳細については、次のリソースを参照してください。

- [Capabilities](/security/compass/security-operations-capabilities)
- [ベスト プラクティス](/security/compass/security-operations)
- [ビデオとスライド](/security/compass/security-operations-videos-and-decks)


## <a name="get-incident-notifications-by-email"></a>電子メールでインシデント通知を取得する

新しいインシデントやMicrosoft 365 Defenderに関するメールをスタッフに通知するメッセージを設定できます。 次に基づいて通知を受け取る方法を選択できます。

- インシデントの重大度。
- デバイス グループ。
- インシデントごとの最初の更新のみ。

電子メール通知には、インシデント名、重大度、カテゴリなど、インシデントに関する重要な詳細が含まれています。 インシデントに直接移動し、分析を直に開始することもできます。 詳細については、「インシデントの [調査」を参照してください](investigate-incidents.md)。

電子メール通知で受信者を追加または削除できます。 新しい受信者は、インシデントが追加された後に通知を受け取る。 

>[!NOTE]
>電子メール通知設定 **を構成するには、[セキュリティ設定の** 管理] 権限が必要です。 基本的なアクセス許可管理の使用を選択した場合、セキュリティ管理者またはグローバル管理者の役割を持つユーザーは、電子メール通知を構成できます。 <br> <br>
同様に、組織が役割ベースのアクセス制御 (RBAC) を使用している場合は、管理が許可されているデバイス グループに基づいて通知を作成、編集、削除、および受信できます。

### <a name="create-a-rule-for-email-notifications"></a>電子メール通知のルールを作成する

次の手順に従って新しいルールを作成し、メール通知設定をカスタマイズします。

1. ナビゲーション ウィンドウで、[インシデントメール通知設定 > Microsoft 365 Defender >**選択します**。
2. [アイテム **の追加] を選択します**。
3. [基本 **] ページで** 、ルール名と説明を入力し、[次へ] を選択 **します**。
4. [通知の **設定] ページで** 、次の構成を行います。
    - **アラートの重大度** - インシデント通知をトリガーするアラートの重大度を選択します。 たとえば、重大度の高いインシデントのみを通知する場合は、[高] を選択 **します**。
    - **デバイス グループ スコープ** - すべてのデバイス グループを指定するか、テナント内のデバイス グループの一覧から選択できます。
    - **インシデントごとに最初に発生した 場合にのみ通知する** - 他の選択内容に一致する最初のアラートについてのみ通知する場合に選択します。 インシデントに関連するその後の更新やアラートでは、追加の通知は送信されません。
    - [**メールに組織名を含める**] - 組織名をメール通知に表示する場合に選択します。
    - [**テナント固有のポータル リンクを含める**] - 特定の Microsoft 365 テナントにアクセスするため、メール通知にテナント ID を含むリンクを追加する場合、選択してください。

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="インシデントメール通知の通知設定。" lightbox="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png":::

5. **[次へ]** を選択します。 [受信者 **] ページ** で、インシデント通知を受信する電子メール アドレスを追加します。 新しい **メール アドレスを** 入力した後、[追加] を選択します。 通知をテストし、受信者が受信トレイで受信を確認するには、[テストメールの送信 **] を選択します**。 
6. **[次へ]** を選択します。 [ルール **の確認] ページ** で、ルールの設定を確認し、[ルールの作成] **を選択します**。 受信者は、設定に基づいて電子メールを介してインシデント通知の受信を開始します。

既存のルールを編集するには、ルールの一覧からルールを選択します。 ルール名を含むウィンドウで、[ルールの編集] **を** 選択し、[基本]、[通知の設定]、および [受信者] ページで変更を **行** います。

ルールを削除するには、ルールの一覧からルールを選択します。 ルール名を持つウィンドウで、[削除] を **選択します**。


## <a name="training-for-security-analysts"></a>セキュリティ アナリスト向けトレーニング

Microsoft Learn のこの学習モジュールを使用して、インシデントとアラートを管理するためにMicrosoft 365 Defender方法を理解します。

|トレーニング: |Microsoft 365 Defender を使用してインシデントを調査する|
|---|---|
|![トレーニング アイコンを使用してMicrosoft 365 Defenderを調査します。](../../media/incidents-overview/m365-defender-address-security-investigation.svg)| Microsoft 365 Defenderの脅威データを統合し、AI を使用してインシデントとアラートに組み合わせます。 インシデントからその管理までの時間を最小限に抑え、その後の対応と解決の方法について説明します。 <p> 27 分 ~ 6 単位 |

> [!div class="nextstepaction"]
> [スタート>](/learn/modules/defender-investigate-incidents/)

## <a name="next-steps"></a>次の手順

セキュリティ チームのエクスペリエンス レベルまたは役割に基づいて、一覧表示されている手順を使用します。

### <a name="experience-level"></a>エクスペリエンス レベル

セキュリティ分析とインシデント対応の経験レベルについては、次の表に従います。

| レベル | 手順 |
|:-------|:-----|
| **New** | <ol><li> 攻撃の[例を使用](first-incident-overview.md)して、Microsoft 365 Defender ポータルで分析、修復、およびインシデント後のレビューの一般的なプロセスのガイド付きツアーを取得するには、「最初のインシデントに対応する」のチュートリアルを参照してください。 </li><li> 重大度などの要因に基 [づいて優先順位](incident-queue.md) を付ける必要があるインシデントを確認します。 </li><li> [インシデント管理ワークフローに](manage-incidents.md)基づいて、名前の変更、割り当て、分類、タグとコメントの追加を含むインシデントを管理します。</li></ol> |
| **経験豊富** | <ol><li> ポータルの [インシデント] ページからインシデント  キューをMicrosoft 365 Defenderします。 グループ プロフィールでは次の操作ができます。 </li> <ul><li> 重大度などの要因に基 [づいて優先順位](incident-queue.md) を付ける必要があるインシデントを確認します。 </li><li> [インシデント管理ワークフローに](manage-incidents.md)基づいて、名前の変更、割り当て、分類、タグとコメントの追加を含むインシデントを管理します。 </li><li> インシデント [の調査](investigate-incidents.md) を実行します。 </li></ul> </li><li> 脅威分析を使用して、新たな脅威 [を追跡して対応します](threat-analytics.md)。 </li><li>  高度な脅威の検出を使用して脅威 [を積極的に探します](advanced-hunting-overview.md)。 </li><li> フィッシング攻撃 [、パスワード スプレー攻撃](/security/compass/incident-response-playbooks) 、アプリ同意許可攻撃の詳細なガイダンスについては、次のインシデント対応プレイブックを参照してください。 </li></ol> |


### <a name="security-team-role"></a>セキュリティ チームの役割

セキュリティ チームの役割に基づいて、次の表に従います。

| 役割 | 手順 |
|:-------|:-----|
| インシデントレスポンダー (Tier 1) | ポータルの [インシデント] ページからインシデント  キューをMicrosoft 365 Defenderします。 グループ プロフィールでは次の操作ができます。 <ul><li> 重大度などの要因に基 [づいて優先順位](incident-queue.md) を付ける必要があるインシデントを確認します。 </li><li> [インシデント管理ワークフローに](manage-incidents.md)基づいて、名前の変更、割り当て、分類、タグとコメントの追加を含むインシデントを管理します。 </li></ul> |
| セキュリティ調査担当者またはアナリスト (Tier 2) | <ol><li> ポータル[の [](investigate-incidents.md)インシデント] ページからインシデントの調査をMicrosoft 365 Defenderします。 </li><li> フィッシング攻撃 [、パスワード スプレー攻撃](/security/compass/incident-response-playbooks) 、アプリ同意許可攻撃の詳細なガイダンスについては、次のインシデント対応プレイブックを参照してください。 </li></ol> |
| 高度なセキュリティ アナリストまたは脅威の検出者 (Tier 3) | <ol><li>ポータル[の [](investigate-incidents.md)インシデント] ページからインシデントの調査をMicrosoft 365 Defenderします。 </li><li> 脅威分析を使用して、新たな脅威 [を追跡して対応します](threat-analytics.md)。 </li><li> 高度な脅威の検出を使用して脅威 [を積極的に探します](advanced-hunting-overview.md)。 </li><li> フィッシング攻撃 [、パスワード スプレー攻撃](/security/compass/incident-response-playbooks) 、アプリ同意許可攻撃の詳細なガイダンスについては、次のインシデント対応プレイブックを参照してください。 |
| SOC マネージャー | セキュリティ 運用センター ([SOC) にMicrosoft 365 Defenderを統合する方法を参照してください](integrate-microsoft-365-defender-secops.md)。 |

