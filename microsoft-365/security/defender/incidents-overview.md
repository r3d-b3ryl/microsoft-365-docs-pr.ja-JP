---
title: Microsoft 365 Defender のインシデント
description: セキュリティ センター内のデバイス、ユーザー、メールボックス間で発生したインシデントMicrosoft 365調査します。
keywords: インシデント、アラート、調査、分析、応答、相関関係、攻撃、コンピューター、デバイス、ユーザー、ID、ID、メールボックス、電子メール、365、microsoft、m365、インシデント対応、サイバー攻撃
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
ms.openlocfilehash: cc2fcd7410c2f3122fb3ce49a40e93bfa0767331
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539025"
---
# <a name="incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender のインシデント

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

> Microsoft 365 Defender を体験してみませんか? [ラボ環境で評価する](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)ことも、[実稼働環境でパイロット プロジェクトを実行する](m365d-pilot.md?ocid=cx-evalpilot)こともできます。
>

Defender のインシデントMicrosoft 365、関連付けられたアラートと、攻撃のストーリーを構成する関連データのコレクションです。 

Microsoft 365やアプリは、疑わしいイベントや悪意のあるイベントやアクティビティを検出すると、アラートを作成します。 個々のアラートは、完了または継続的な攻撃に関する貴重な手がかりを提供します。 ただし、攻撃は通常、デバイス、ユーザー、メールボックスなど、さまざまな種類のエンティティに対してさまざまな手法を採用します。 結果は、テナント内の複数のエンティティに対する複数の通知になります。 

個々のアラートを組み合わせて攻撃に関する洞察を得る場合は、困難で時間がかかる場合があります。Microsoft 365 Defender は自動的にアラートと関連情報をインシデントに集約します。

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Defender Microsoft 365エンティティからのイベントをインシデントに関連付ける方法":::

Defender でのインシデントのこの短い概要 (4 Microsoft 365) をご覧ください。

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

関連するアラートをインシデントにグループ化すると、攻撃の包括的なビューが得されます。 たとえば、次の情報を表示できます。

- 攻撃が開始された場所。
- どのような戦術が使用されたのか。
- 攻撃がテナントにどれくらいまで入ったか。
- 攻撃の範囲 (影響を受けたデバイス、ユーザー、メールボックスの数など)。 
- 攻撃に関連付けられているすべてのデータ。

有効[にした場合](m365d-enable.md)、Microsoft 365 Defender は自動化[と](m365d-autoir.md)人工知能を通じてアラートを自動的に調査および解決できます。 また、追加の修復手順を実行して攻撃を解決することもできます。 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a>セキュリティ センターでのインシデントMicrosoft 365アラート

インシデント &**アラート>** インシデントを管理するには、Microsoft 365 セキュリティ センター (security.microsoft.com) を [security.microsoft.com。](https://security.microsoft.com) 次に例を示します。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="セキュリティ センターの [インシデントMicrosoft 365ページ":::

インシデント名を選択すると、インシデントの概要が表示され、追加情報を含むタブにアクセスできます。

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="セキュリティ センターのインシデントの概要ページMicrosoft 365例":::

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

  インシデント内のアラートでサポートされているイベントと疑わしいエンティティすべて。

- Graph (プレビューで)

  組織内の影響を受け取った資産へのアラートの接続を示す図。

インシデントとそのデータと、セキュリティ センター内のインシデントのタブとのMicrosoft 365します。

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="インシデントとそのデータとセキュリティ センター内のインシデントのタブMicrosoft 365関係":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>Defender のインシデント対応ワークフロー Microsoft 365例

次に、セキュリティ センターでインシデントに対応Microsoft 365ワークフロー Microsoft 365示します。

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="インシデント対応ワークフローの例Microsoft 365":::

継続的に、インシデント キューの分析と解決に最も優先度の高いインシデントを特定し、対応の準備を整えます。 これは、次の組み合わせです。

- [インシデント キューの](incident-queue.md) フィルター処理と並べ替えを通じて、優先度の高いインシデントを特定するトリアージ。
- [タイトルを](manage-incidents.md) 変更し、アナリストに割り当て、タグとコメントを追加してインシデントを管理します。

1. インシデントごとに、攻撃とアラート [の調査と分析を開始します](investigate-incidents.md)。
 
   a. インシデントの概要を表示して、インシデントの範囲と重大度、および影響を受けるエンティティ ([概要] タブ) **を理解** します。

   b. アラートの分析を開始して、発生元、スコープ、重大度 ([アラート] タブ) **を理解** します。

   c. 必要に応じて、影響を受け取ったデバイス、ユーザー、およびメールボックス([デバイス]、[ユーザー]、および [メールボックス] タブ) に関する **情報を収集** します。

   d. Defender が一部Microsoft 365自動的に解決した方法 [([](m365d-autoir.md)調査] タブ)**を参照** してください。
   
   e. 必要に応じて、インシデントのデータ セットの情報を使用して詳細を確認します ([証拠と応答] **タブ** )。

2. 分析の後または分析中に、攻撃による追加の影響を軽減し、セキュリティ上の脅威を根絶するために、格納を実行します。

3. 可能な限り、テナント リソースをインシデントの前の状態に復元して攻撃から回復します。

4. [インシデント](manage-incidents.md#resolve-an-incident) を解決し、インシデント後の学習に時間を取って、次の処理を行います。

   - 攻撃の種類とその影響を理解します。
   - [Threat Analytics](threat-analytics.md)とセキュリティ コミュニティの攻撃を調査して、セキュリティ攻撃の傾向を調査します。
   - インシデントの解決に使用したワークフローを思い出し、必要に応じて標準のワークフロー、プロセス、ポリシー、プレイブックを更新します。
   - セキュリティ構成の変更が必要かどうかを判断し、実装します。

セキュリティ分析を初めて使用する場合は、[](incidents-overview.md)最初のインシデントへの対応の概要を参照し、詳細については、「インシデントの例」を参照してください。

## <a name="example-security-operations-for-microsoft-365-defender"></a>Defender のセキュリティ操作Microsoft 365例

Defender のセキュリティ操作の例をMicrosoft 365します。

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Defender のセキュリティ操作のMicrosoft 365例":::

毎日のタスクには、次のものが含まれます。

- [インシデントの](manage-incidents.md) 管理
- アクション センター [での自動調査と応答 (AIR)](m365d-action-center.md) アクションの確認
- 最新の脅威分析 [の確認](threat-analytics.md)
- [インシデントへの](investigate-incidents.md) 対応

毎月のタスクには、次のものが含まれます。

- AIR 設定 [の確認](m365d-configure-auto-investigation-response.md)
- セキュリティで保護[されたスコアと](microsoft-secure-score-improvement-actions.md)[脅威の&の管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- IT セキュリティ管理チェーンへのレポート

四半期ごとに、最高情報セキュリティ責任者 (CISO) へのセキュリティ結果の報告とブリーフィングが含まれます。

年次タスクには、スタッフ、システム、およびプロセスをテストする重大なインシデントや違反の演習を実行できます。 

毎日、月次、四半期、年次のタスクを使用して、プロセス、ポリシー、およびセキュリティ構成を更新または調整できます。

## <a name="next-steps"></a>次の手順

**セキュリティ分析とインシデント** 対応に関する情報が必要な場合は、次の情報を参照してください。

- Microsoft 365[](first-incident-overview.md)セキュリティ センターの分析、修復、インシデント後の一般的なプロセスのガイド付きツアーについては、「最初のインシデントに対応する」のチュートリアルを参照してください。攻撃の例を示します。

**セキュリティ分析とインシデント** 対応に関する経験がある場合:

- セキュリティ センターの [インシデント]ページからインシデント キュー Microsoft 365開始します。 ここから、以下の操作を行うことができます。

  - 重大度などの要因に基 [づいて優先順位](incident-queue.md) を付ける必要があるインシデントを確認します。 

  - [インシデント管理ワークフローに](manage-incidents.md)基づいて、名前の変更、割り当て、分類、タグとコメントの追加を含むインシデントを管理します。

  - インシデント [の調査](investigate-incidents.md) を実行します。

- フィッシング攻撃 [、パスワード スプレー攻撃](https://docs.microsoft.com/security/compass/incident-response-playbooks) 、アプリ同意許可攻撃の詳細なガイダンスについては、次のインシデント対応プレイブックを参照してください。

