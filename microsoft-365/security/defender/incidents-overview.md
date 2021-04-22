---
title: Microsoft 365 Defender でのインシデント
description: Microsoft 365 セキュリティ センターのデバイス、ユーザー、メールボックスで発生したインシデントを調査します。
keywords: インシデント、アラート、調査、調査、分析、応答、相関関係、攻撃、コンピューター、デバイス、ユーザー、ID、ID、メールボックス、電子メール、365、microsoft、m365
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
ms.openlocfilehash: 890e64367c49c24c8c70e2cbda9869a5d0797219
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939590"
---
# <a name="incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender でのインシデント

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

> Microsoft 365 Defender を体験してみませんか? [ラボ環境で評価する](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)ことも、[実稼働環境でパイロット プロジェクトを実行する](m365d-pilot.md?ocid=cx-evalpilot)こともできます。
>

Microsoft 365 Defender のインシデントは、関連付けられたアラートと、攻撃のストーリーを構成する関連データのコレクションです。 

Microsoft 365 サービスとアプリは、疑わしいイベントや悪意のあるイベントやアクティビティを検出すると、アラートを作成します。 個々のアラートは、完了または継続的な攻撃に関する貴重な手がかりを提供します。 ただし、攻撃は通常、デバイス、ユーザー、メールボックスなど、さまざまな種類のエンティティに対してさまざまな手法を採用します。 結果は、テナント内の複数のエンティティに対する複数の通知になります。 

個々のアラートを組み合わせて攻撃に関する洞察を得る場合は、困難で時間がかかる場合があります。Microsoft 365 Defender は自動的にアラートと関連情報をインシデントに集約します。

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Microsoft 365 Defender がエンティティからのイベントをインシデントに関連付ける方法":::

Microsoft 365 Defender でのインシデントのこの短い概要 (4 分) をご覧ください。

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

関連するアラートをインシデントにグループ化すると、攻撃の包括的なビューが得されます。 たとえば、次の情報を表示できます。

- 攻撃が開始された場所。
- どのような戦術が使用されたのか。
- 攻撃がテナントにどれくらいまで入ったか。
- 攻撃の範囲 (影響を受けたデバイス、ユーザー、メールボックスの数など)。 
- 攻撃に関連付けられているすべてのデータ。

有効 [にすると、Microsoft](m365d-enable.md)365 Defender は自動化と人工知能を通じて自動的にアラートを調査および解決できます。 また、追加の修復手順を実行して攻撃を解決することもできます。 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a>Microsoft 365 セキュリティ センターのインシデントとアラート

Microsoft 365 セキュリティ センター (& >) のクイック 起動時に、インシデント とアラートのインシデントを[管理 security.microsoft.com。](https://security.microsoft.com)  次に例を示します。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Microsoft 365 セキュリティ センターの [インシデント] ページ":::

インシデント名を選択すると、インシデントの概要が表示され、追加情報を含むタブにアクセスできます。

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 セキュリティ センターのインシデントの概要ページの例":::

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

  インシデント内のアラートによってトリガーされる、すべての自動調査。

- 証拠と対応

  インシデント内のアラートでサポートされているイベントと疑わしいエンティティすべて。

Microsoft 365 セキュリティ センターのインシデントとそのデータとインシデントのタブの関係を次に示します。

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="インシデントとそのデータと Microsoft 365 セキュリティ センターのインシデントのタブとの関係":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>Microsoft 365 Defender のインシデント対応ワークフローの例

Microsoft 365 セキュリティ センターを使用して Microsoft 365 のインシデントに対応するワークフローの例を次に示します。

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Microsoft 365 のインシデント対応ワークフローの例":::

継続的に、インシデント キューの分析と解決に最も優先度の高いインシデントを特定し、対応の準備を整えます。 これは、次の組み合わせです。

- [インシデント キューの](incident-queue.md) フィルター処理と並べ替えを通じて、優先度の高いインシデントを特定するトリアージ。
- [タイトルを](manage-incidents.md) 変更し、アナリストに割り当て、タグとコメントを追加してインシデントを管理します。

1. インシデントごとに、攻撃とアラート [の分析を開始します](investigate-incidents.md)。

   a. インシデントの概要を表示して、インシデントの範囲と重大度、および影響を受けるエンティティ ([概要] タブ) **を理解** します。

   b. アラートの分析を開始して、発生元、スコープ、重大度 ([アラート] タブ) **を理解** します。

   c. 必要に応じて、影響を受け取ったデバイス、ユーザー、およびメールボックス([デバイス]、[ユーザー]、および [メールボックス] タブ) に関する **情報を収集** します。

   d. Microsoft 365 Defender が一部のアラートを自動的に解決した方法 ([調査] タブ) **を参照** してください。
   
   e. 必要に応じて、インシデントのデータ セットの情報を使用して詳細を確認します ([証拠と応答] **タブ** )。

2. 分析の後または分析中に、攻撃による追加の影響を軽減し、セキュリティ上の脅威を根絶するためのアドレス格納。

3. 可能な限り、テナント リソースをインシデントの前の状態に復元して攻撃から回復します。

4. [インシデント](manage-incidents.md#resolve-incident) を解決し、インシデント後の学習に時間を取って、次の処理を行います。

   - 攻撃の種類とその影響を理解します。
   - [Threat Analytics](threat-analytics.md)とセキュリティ コミュニティの攻撃を調査して、セキュリティ攻撃の傾向を調査します。
   - インシデントの解決に使用したワークフローを思い出し、必要に応じて標準のワークフロー、プロセス、ポリシー、プレイブックを更新します。
   - セキュリティ構成の変更が必要かどうかを判断し、実装します。

## <a name="example-security-operations-for-microsoft-365-defender"></a>Microsoft 365 Defender のセキュリティ操作の例

Microsoft 365 Defender のセキュリティ操作の例を次に示します。

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Micosoft 365 Defender のセキュリティ操作の例":::

毎日のタスクには、次のものが含まれます。

- [インシデントの](manage-incidents.md) 管理
- 自動調査 [と応答 (AIR)](m365d-action-center.md) アクションの確認
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

[インシデント] ページの **インシデント キュー** には、最新のインシデントが一覧表示されます。 ここから、以下の操作を行うことができます。

- 重大度などの要因に基 [づいて優先順位](incident-queue.md) を付ける必要があるインシデントを確認します。 
- [インシデント管理ワークフローの](manage-incidents.md)名前の変更、割り当て、分類、タグとコメントの追加を含むインシデントを管理します。
- インシデントの [分析](investigate-incidents.md) を実行します。
